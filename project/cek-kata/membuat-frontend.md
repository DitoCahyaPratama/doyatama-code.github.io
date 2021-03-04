---
description: >-
  Halo semua, project yang akan dibuat pada kesempatan kali ini adalah cek kata.
  Project ini dibuat dengan menggunakan lumen dan react js.
---

# Membuat Frontend

### Install front end react js

* install        : npx create-react-app frontend
* docs          : [https://reactjs.org/](https://reactjs.org/)

### install this package:

* axios                        :   [https://www.npmjs.com/package/axios](https://www.npmjs.com/package/axios)
* react-router-dom    :  [https://www.npmjs.com/package/react-router-dom](https://www.npmjs.com/package/react-router-dom)
* reactstrap                :  [https://reactstrap.github.io/](https://reactstrap.github.io/)
* bootstrap                 

{% api-method method="post" host="http://localhost:8000/api/v1/" path="cekkata" %}
{% api-method-summary %}
Cek kata
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="Kalimat" type="string" required=false %}

{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=201 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
    "message": "success",
    "estimasi": 0.5756261348724365,
    "totalKata": 3,
    "totalKarakter": 14,
    "totalSalah": 1,
    "teksOri": "saya lagi makn",
    "pembenaran": "<span>Saya</span> <span> lagi</span> <select class='spell'><option>makn</option><option>maki</option><option>makna</option><option>man</option><option>maka</option><option>mak</option><option>makan</option><option>makin</option><option>main</option></select>"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

* Follow this video

