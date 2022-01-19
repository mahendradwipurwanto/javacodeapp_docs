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
        "id_diskon": [1, 2],
        "diskon": 20,
        "total_bayar": 100000
    },
    "menu": [
        {
            "id_menu": 2,
            "harga": 18000,
            "jumlah": 2
        },
        {
            "id_menu": 3,
            "harga": 10000,
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
        "id_diskon": array(id_diskon: integer), #not required, choose between voucher or diskon
        "diskon": integer,
        "total_bayar": integer
    },
    "menu": [
        {
            "id_menu": integer,
            "harga": integer,
            "jumlah": integer
        },
        {
            "id_menu": integer,
            "harga": integer,
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
        "<span class=\"gump-field\">Id User</span> harus diisi"
    ]
}
```

</p>
</details>
