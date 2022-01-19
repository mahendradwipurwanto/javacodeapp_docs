# ORDER

- [Home Page](https://github.com/mahendradwipurwanto/javacodeapp_docs/blob/main/README.md)

# #POST / order

**endpoint**
```
https://javacode.ngodingin.com/api/order/add
```

### Request body

<details><summary>Example Request</summary>
<p>

```
{
    "order": {
        "id_user": 1,
        "id_voucher": 1,
        "voucher": 10000,
        "id_diskon": [
            1,
            2
        ],
        "diskon": 20,
        "total_bayar": 100000
    },
    "menu": [
        {
            "id_menu": 2,
            "harga": 18000,
            "level": 1,
            "topping": [
                1,
                2
            ],
            "jumlah": 2
        },
        {
            "id_menu": 3,
            "harga": 10000,
            "level": 2,
            "topping": [
                2,
                3
            ],
            "jumlah": 1
        }
    ]
}
```

</p>
</details>
<details><summary>Schema</summary>
<p>

```
{
    "order": {
        "id_user": integer,
        "id_voucher": integer, #not required, choose between voucher or diskon
        "voucher": integer, #not required, choose between voucher or diskon (nominal of used voucher)
        "id_diskon": array(id_diskon: integer), #not required, choose between voucher or diskon
        "diskon": integer, #not required, choose between voucher or diskon
        "total_bayar": integer
    },
    "menu": [
        {
            "id_menu": integer,
            "harga": integer,
            "level": integer, #not required
            "topping": array(topping: integer), #not required
            "jumlah": integer
        },
        {
            "id_menu": integer,
            "harga": integer,
            "level": integer, #not required
            "topping": array(topping: integer), #not required
            "jumlah": integer
        }
    ]
}
```

</p>
</details>

### Responses

<details><summary>200</summary>
<p>

```
{
    "status_code": 200,
    "data": {
        "message": "Order has been successfuly added",
        "no_struk": "002/KWT/01/2022"
    }
}
```

</p>
</details>
<details><summary>422</summary>
<p>

```
{
    "status_code": 422,
    "errors": [
        "<span class=\"gump-field\">voucher</span> harus diisi"
    ]
}
```

</p>
</details>
<details><summary>403</summary>
<p>

```
{
    "status_code": 403,
    "errors": [
        "Mohon maaf, anda tidak mempunyai akses"
    ]
}
```

</p>
</details>



# #GET / order list of one user

**endpoint**
```
https://javacode.ngodingin.com/api/order/user/{id_user}
```

### Request body
none.

### Request Parameters

<details><summary>1 Path Parameter</summary>
<p>

> id_user: integer

</p>
</details>

### Responses

<details><summary>200</summary>
<p>

```
{
    "status_code": 200,
    "data": [
        {
            "id_order": 5,
            "no_struk": "001/KWT/01/2022",
            "nama": "Super Admin",
            "tanggal": "2022-01-19",
            "diskon": 20,
            "voucher": null,
            "total_bayar": 100000
        },
        {
            "id_order": 6,
            "no_struk": "002/KWT/01/2022",
            "nama": "Super Admin",
            "tanggal": "2022-01-19",
            "diskon": 20,
            "voucher": null,
            "total_bayar": 100000
        },
        {
            "id_order": 7,
            "no_struk": "003/KWT/01/2022",
            "nama": "dev noersy",
            "tanggal": "2022-01-19",
            "diskon": 10,
            "voucher": null,
            "total_bayar": 9000
        }
    ]
}
```

</p>
</details>
<details><summary>403</summary>
<p>

```
{
    "status_code": 403,
    "errors": [
        "Mohon maaf, anda tidak mempunyai akses"
    ]
}
```

</p>
</details>



# #GET / order list of one user by status order

**endpoint**
```
https://javacode.ngodingin.com/api/order/status/{id_user}/{status}
```

**status:**
0. diproses
1. selesai
2. dibatalkan

### Request body
none.

### Request Parameters

<details><summary>2 Path Parameter</summary>
<p>

> id_user: integer

> status: integer

</p>
</details>

### Responses

<details><summary>200</summary>
<p>

```
{
    "status_code": 200,
    "data": [
        {
            "id_order": 12,
            "no_struk": "001/KWT/01/2022",
            "nama": "Super Admin",
            "tanggal": "2022-01-19",
            "diskon": null,
            "voucher": 10000,
            "total_bayar": 100000
        }
    ]
}
```

</p>
</details>
<details><summary>403</summary>
<p>

```
{
    "status_code": 403,
    "errors": [
        "Mohon maaf, anda tidak mempunyai akses"
    ]
}
```

</p>
</details>



# #GET / order detail

**endpoint**
```
https://javacode.ngodingin.com/api/order/detail/{id_order}
```

### Request body
none.

### Request Parameters

<details><summary>1 Path Parameter</summary>
<p>

> id_order: integer

</p>
</details>

### Responses

<details><summary>200</summary>
<p>

```
{
    "status_code": 200,
    "data": {
        "order": {
            "id_order": 12,
            "no_struk": "001/KWT/01/2022",
            "nama": "Super Admin",
            "tanggal": "2022-01-19",
            "diskon": null,
            "voucher": 10000,
            "total_bayar": 100000
        },
        "detail": [
            {
                "id_menu": 2,
                "nama": "coto makassar",
                "jumlah": 2,
                "harga": "18000",
                "total": 36000
            },
            {
                "id_menu": 3,
                "nama": "thai tea",
                "jumlah": 1,
                "harga": "10000",
                "total": 10000
            }
        ]
    }
}
```

</p>
</details>
<details><summary>403</summary>
<p>

```
{
    "status_code": 403,
    "errors": [
        "Mohon maaf, anda tidak mempunyai akses"
    ]
}
```

</p>
</details>