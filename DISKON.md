# DISKON

# #GET / diskon

**endpoint**
```
https://javacode.ngodingin.com/api/diskon/all
```

### Request body
none.

### Responses

<details><summary>200</summary>
<p>

```
{
    "status_code": 200,
    "data": [
        {
            "id_diskon": 1,
            "id_user": 1,
            "nama_user": "Super Admin",
            "nama": "Mengisi survey",
            "diskon": 10
        }
    ]
}
```

</p>
</details>


# #GET / diskon list of one user

**endpoint**
```
https://javacode.ngodingin.com/api/diskon/user/{id_user}
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
            "id_diskon": 1,
            "id_user": 1,
            "nama_user": "Super Admin",
            "nama": "Mengisi survey",
            "diskon": 10
        }
    ]
}
```

</p>
</details>


# #GET / detail diskon

**endpoint**
```
https://javacode.ngodingin.com/api/diskon/detail/{id_diskon}
```

### Request body
none.

### Request Parameters

<details><summary>1 Path Parameter</summary>
<p>

> id_diskon: integer

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
            "id_diskon": 1,
            "id_user": 1,
            "nama_user": "Super Admin",
            "nama": "Mengisi survey",
            "diskon": 10
        }
    ]
}
```

</p>
</details>