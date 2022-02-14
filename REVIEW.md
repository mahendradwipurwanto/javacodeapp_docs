
# REVIEW

- [Home Page](https://github.com/mahendradwipurwanto/javacodeapp_docs/blob/main/README.md)

# #GET / all review

**endpoint**
```
https://javacode.ngodingin.com/api/review
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
            "id_review": 1,
            "id_user": 47,
            "nama": "dev noersy",
            "score": 5,
            "type": "Penyajian Makanan",
            "review": "Keren bangetsss",
            "image": "http://localhost/jacode/img/60/review/review_60_6203811375f05.png",
            "created_at": 2147483647
        },
        {
            "id_review": 2,
            "id_user": 57,
            "nama": "Zildjian",
            "score": 4,
            "type": "Fasilitas",
            "review": "Lumayan",
            "image": "[]",
            "created_at": 2147483647
        },
        {
            "id_review": 20,
            "id_user": 58,
            "nama": "Nur Syahfei",
            "score": 3.5,
            "type": "Fasilitas",
            "review": "Fasilitas kurang, kamar mandi tidak begitu bersih",
            "image": "[]",
            "created_at": 1644396889
        }
    ]
}
```

</p>
</details>
<details><summary>204</summary>
<p>

> This mean that, there is no data can be found on database

</p>
</details>
<details><summary>422</summary>
<p>

```
{
    "status_code": 422,
    "errors": [
        "Terjadi kesalahan saat mengambil data"
    ]
}
```

</p>
</details>



# #POST / add review

**endpoint**
```
https://javacode.ngodingin.com/api/review/add
```

### Request body
```
{
	"id_user":  58,
	"score"  :  3.5,
	"type":  "Fasilitas",
	"review":  "Fasilitas kurang, kamar mandi tidak begitu bersih"
	"image": "iVBORw0KGgoAAAANSUhEUgAAAQ4AAAC7CAMAAACjH4DlAAAAXVBMVEUpMTRnjLEiJiNcfJxrkbgkKSgoLzEmLS5EWWxXdpM0QkxAVGUuOT9kiKslKytSbohPaYJggqM+UF8wO0I6SldIX3Q2RE9LY3oyP0crNDk+UWFWdJA7S1lPaH9jhacMRR/OAAADlElEQVR4nO3c7XKqMBSFYSi4CSCB8CGkKvd/mUfAVoNgHUiPdbuef51aprwDAQLiOAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA........."
}
```


</p>
</details>

### Schema

<details><summary>Image</summary>
<p>
<br> // * image is base64 string
<br> // * image optional. set image to null if there'is no image.
<br> // * image can start with "data:image/png;base64,blablabal...." or without it (see above).

</p>
</details>

### Responses

<details><summary>200</summary>
<p>

```
    "status_code": 200,
    "data": [
		         "id_review": 1,
		         "id_user": 47,
		         "nama": "dev noersy",
		         "score": 5,
		         "type": "Penyajian Makanan",
		         "review": "Keren bangetsss",
		         "image": "http://localhost/jacode/img/60/review/review_60_6203811375f05.png",
		         "created_at": 2147483647
			]
```

</p>
</details>
<details><summary>204</summary>
<p>

> This mean that, there is no data can be found on database

</p>
</details>
<details><summary>422</summary>
<p>

```
{
    "status_code": 422,
    "errors": {
        "message": "Anda hanya dapat melakukan penilaian sebanyak 1 kali dalam sebulan.",
        "waiting_time": "30 days, 10 hours, 29 minutes and 2 seconds"
    }
}
```

</p>
</details>



# #GET / review by id_user

**endpoint**
```
https://javacode.ngodingin.com/api/review/{id_user}
```

### Request body
none.

### Request Parameters

<details><summary>1 Path Parameter</summary>
<p>

> id_user: integer #required

</p>
</details>

### Responses

<details><summary>200</summary>
<p>

```
{
    "status_code": 200,
    "data": {
        "id_review": 1,
        "id_user": 47,
        "nama": "dev noersy",
        "score": 5,
        "type": "Penyajian Makanan",
        "review": "Keren bangetsss",
        "image": "http://localhost/jacode/img/60/review/review_60_6203811375f05.png",
        "created_at": 2147483647
    }
}
```

</p>
</details>
<details><summary>204</summary>
<p>

> This mean that, there is no data can be found on database

</p>
</details>
<details><summary>422</summary>
<p>

```
{
    "status_code": 403,
    "errors": [
        "Terjadi kesalahan"
    ]
}
```

</p>
</details>



# #POST / add answer

**endpoint**
```
https://javacode.ngodingin.com/api/review/answer/add
```

### Request body
```
{
	"answer":  "Mantab banget fasilitasnya kerennn",
	"id_user"  :  47,
	"id_review":  "Fasilitas"
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
        "id_answer": 7,
        "answer": "Wokey siap!",
        "id_user": 47,
        "id_review": 1,
    }
}
```

</p>
</details>
<details><summary>204</summary>
<p>

> This mean that, there is no data can be found on database

</p>
</details>
<details><summary>422</summary>
<p>

```
{
    "status_code": 403,
    "errors": [
        "Terjadi kesalahan saat menyimpan data"
    ]
}
```

</p>
</details>



# #GET / detail review by id_review

**endpoint**
```
https://javacode.ngodingin.com/api/review/detail{id_review}
```

### Request body
none.

### Request Parameters

<details><summary>1 Path Parameter</summary>
<p>

> id_review: integer #required

</p>
</details>

### Responses

<details><summary>200</summary>
<p>

```
{
    "status_code": 200,
    "data": {
        "review": {
            "id_review": 1,
            "id_user": 47,
            "nama": "dev noersy",
            "score": 5,
            "type": "Penyajian Makanan",
            "review": "Keren bangetsss",
            "image": "http://localhost/jacode/img/60/review/review_60_6203811375f05.png",
            "created_at": 2147483647
        },
        "answer": [
            {
                "id_answer": 4,
                "id_user": 71,
                "nama": "Kitchen",
                "answer": "Terimakasih",
                "created_at": 1644393534,
                "is_customer": false,
                "is_kitchen": true
            },
            {
                "id_answer": 5,
                "id_user": 47,
                "nama": "dev noersy",
                "answer": "Sama sama",
                "created_at": 1644393627,
                "is_customer": true,
                "is_kitchen": false
            },
            {
                "id_answer": 6,
                "id_user": 71,
                "nama": "Kitchen",
                "answer": "Jangan lupa datang lagi mas. Mantab!",
                "created_at": 1644415138,
                "is_customer": false,
                "is_kitchen": true
            },
            {
                "id_answer": 7,
                "id_user": 47,
                "nama": "dev noersy",
                "answer": "Wokey siap!",
                "created_at": 1644416757,
                "is_customer": true,
                "is_kitchen": false
            }
        ]
    }
}
```

</p>
</details>
<details><summary>204</summary>
<p>

> This mean that, there is no data can be found on database

</p>
</details>
<details><summary>422</summary>
<p>

```
{
    "status_code": 403,
    "errors": [
        "Terjadi kesalahan"
    ]
}
```

</p>
</details>
