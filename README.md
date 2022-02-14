# مستندات پروژه دیجی فنی
### مستندات انگلیسی پروژه
[English Documents](https://documenter.getpostman.com/view/16734909/U16gPSvj)

لیست ای پی آی های موجود پروژه

## ثبت نام
 ارسال میشود  post این متد به صورت 

```bash
http://localhost/api/users/add/user
```
مقادیر ورودی آن به شرح زیر است
```js
{
    fistName : "Taha",
    lastName : "Shokri",
    gender : {"man" || "woman"},
    birthday : "1995-11-12",
    phone : "09197956244",
    email : "tahashokri77@gmail.com"
}
```

### خروجی موفق

```json
{
    "success" : true,
    "code" : 200,
    "data" : {
        "message" : "ثبت نام با موفقیت انجام شد",
        "token" : "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
        "data" : null
    }
}
```
## ورود با ارسال پیامک
ارسال میشود Get این متد به صورت 

```bash
http://localhost/api/users/send/code
```
مقادیر ورودی به صورت زیر میباشد
```js
{
    phone : "09197956244"
}
```
### خروجی موفق
```json
{
    "success" : true,
    "code" : 200,
    "data" : {
        "message" : "پیامک حاوی کد تأیید ارسال گردید",
        "token" : "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
        "data" : null
         
    }
}
```
## تأیید شماره ی همراه
ارسال میشود Post این متد به صورت 
```bash
http://localhost/api/users/check/code
```
### مقادیر ورودی
```js
{
    token : "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
    code : "1234"
}
```
### خروجی موفق
```json
{
    "success" : true,
    "code" : 200,
    "data" : {
        "message" : "حساب شما با موفقیت فعال گردید",
        "token" : "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
        "data" : null
    }
}
```
## بروزرسانی اطلاعات کاربری
ارسال میشود Put این متد به صورت 
```bash
http://localhost/api/users/edit/user
```
### مقادیر ورودی
```js
{
    token : "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",  // required
    email : "Tahashokri77@gmail.com",  // Optional
    firstName : "Taha",  // Optional
    lastName : "Shokri", // Optional
    gender : "man",  // Optional
    birthday : "1995-11-12" // Optional
}
```
### خروجی موفق
```json
{
    "success" : true,
    "code" : 200,
    "data" : {
        "message" : "اطلاعات کاربری شما با موفقیت به روزرسانی گردید",
        "token" : "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
        "data" : null
    }
}
```

## گرفتن اطلاعات کاربری
فراخوانی میشود Get این متد با 
```bash
http://localhost/api/users/get/my/data
```
### مقادیر ورودی
```js
{
    token : "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx"
}
```
### خروجی موفق
```json
{
    "success": true,
    "code": 200,
    "data": {
        "message": "اطلاعات کاربری با موفقیت دریافت گردید",
        "token": "nR3tIGdem2tkcFWyozUKMLQ7MmrJU1x2xeGPdVyGMHB3eZEAThUqHe8Zr9CGYa87",
        "data": {
            "id": 2,
            "firstName": "Taha",
            "lastName": "shokri",
            "birthday": "1995-11-12",
            "gender": "man",
            "email": "tahashokri77@gmail.com",
            "phone": "09197956244",
            "token": "nR3tIGdem2tkcFWyozUKMLQ7MmrJU1x2xeGPdVyGMHB3eZEAThUqHe8Zr9CGYa87",
            "status": "active",
            "created_at": "2021-09-05T09:12:48.000000Z"
        }
    }
}
```
## گرفتن لیست تمام کاربران ![Generic badge](https://img.shields.io/badge/Role-Admin-success.svg)
فراخوانی میشود Get این متد با 
```bash
http://localhost/api/users/get/all
```
### مقادیر ورودی
```js
{
    token : "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx"
}
```
### خروجی موفق
```json
{
    "success": true,
    "code": 200,
    "token": "AH91mY4GwTH2DJfVvixYWWK8t8EcvYlAeYw7dYmc3fTr9kWyaT6Pb5049vSbV8Lp",
    "data": {
        "message": "اطلاعات تمامی کاربران دریافت شد",
        "data": [
            {
                "id": 1,
                "firstName": "Taha",
                "lastName": "Shokri",
                "birthday": "1995-11-12",
                "gender": "man",
                "email": "tahashokri77@gmail.com",
                "phone": "09197956244",
                "role": "developer",
                "token": "AH91mY4GwTH2DJfVvixYWWK8t8EcvYlAeYw7dYmc3fTr9kWyaT6Pb5049vSbV8Lp",
                "code": 7211,
                "status": "notActive",
                "wallet": 20000,
                "created_at": "2021-09-13T11:20:23.000000Z",
                "updated_at": "2021-09-18T12:03:37.000000Z"
            },
            {
                "id": 2,
                "firstName": "شعله توفیق",
                "lastName": "زرشناس",
                "birthday": "2014-10-19",
                "gender": "woman",
                "email": "cmahmoudi@example.net",
                "phone": "09774294346",
                "role": "user",
                "token": null,
                "code": null,
                "status": "notActive",
                "wallet": 0,
                "created_at": "2021-09-13T11:20:23.000000Z",
                "updated_at": "2021-09-13T11:20:23.000000Z"
            },
            {
                "id": 3,
                "firstName": "آذرجهر خسروپناه",
                "lastName": "جهانی",
                "birthday": "1989-12-22",
                "gender": "man",
                "email": "donya46@example.org",
                "phone": "09785391338",
                "role": "user",
                "token": null,
                "code": null,
                "status": "notActive",
                "wallet": 0,
                "created_at": "2021-09-13T11:20:23.000000Z",
                "updated_at": "2021-09-13T11:20:23.000000Z"
            },
            {
                "id": 4,
                "firstName": "دکتر کاظم شاملو",
                "lastName": "پورنگ",
                "birthday": "1976-03-08",
                "gender": "man",
                "email": "turan62@example.net",
                "phone": "09111619134",
                "role": "user",
                "token": null,
                "code": null,
                "status": "notActive",
                "wallet": 0,
                "created_at": "2021-09-13T11:20:23.000000Z",
                "updated_at": "2021-09-13T11:20:23.000000Z"
            },
            {
                "id": 5,
                "firstName": "تاجور سادات",
                "lastName": "غضنفری",
                "birthday": "2001-09-17",
                "gender": "woman",
                "email": "eshahidi@example.net",
                "phone": "09816403280",
                "role": "user",
                "token": null,
                "code": null,
                "status": "notActive",
                "wallet": 0,
                "created_at": "2021-09-13T11:20:23.000000Z",
                "updated_at": "2021-09-13T11:20:23.000000Z"
            },
            {
                "id": 6,
                "firstName": "ژیلا نهاوندی",
                "lastName": "یلدا",
                "birthday": "1977-06-29",
                "gender": "man",
                "email": "nmohammady@example.org",
                "phone": "09704004580",
                "role": "user",
                "token": null,
                "code": null,
                "status": "notActive",
                "wallet": 0,
                "created_at": "2021-09-13T11:20:23.000000Z",
                "updated_at": "2021-09-13T11:20:23.000000Z"
            },
            {
                "id": 7,
                "firstName": "استاد شکرانه کاملی",
                "lastName": "ذاکری",
                "birthday": "1984-06-05",
                "gender": "woman",
                "email": "niloufar08@example.com",
                "phone": "09920595694",
                "role": "user",
                "token": null,
                "code": null,
                "status": "notActive",
                "wallet": 0,
                "created_at": "2021-09-13T11:20:23.000000Z",
                "updated_at": "2021-09-13T11:20:23.000000Z"
            },
            {
                "id": 8,
                "firstName": "تیبا مقدم",
                "lastName": "پایور",
                "birthday": "2001-12-14",
                "gender": "man",
                "email": "behnaz.jamshidi@example.com",
                "phone": "09204491204",
                "role": "user",
                "token": null,
                "code": null,
                "status": "notActive",
                "wallet": 0,
                "created_at": "2021-09-13T11:20:23.000000Z",
                "updated_at": "2021-09-13T11:20:23.000000Z"
            },
            {
                "id": 9,
                "firstName": "شاهین مصباح‌زاده",
                "lastName": "مفتح",
                "birthday": "2018-01-20",
                "gender": "woman",
                "email": "uabedini@example.org",
                "phone": "09316018801",
                "role": "user",
                "token": null,
                "code": null,
                "status": "notActive",
                "wallet": 0,
                "created_at": "2021-09-13T11:20:23.000000Z",
                "updated_at": "2021-09-13T11:20:23.000000Z"
            },
            {
                "id": 10,
                "firstName": "کیمیا جهانی",
                "lastName": "خراسانی",
                "birthday": "1972-07-08",
                "gender": "man",
                "email": "gfarsi@example.net",
                "phone": "09812256202",
                "role": "user",
                "token": null,
                "code": null,
                "status": "notActive",
                "wallet": 0,
                "created_at": "2021-09-13T11:20:23.000000Z",
                "updated_at": "2021-09-13T11:20:23.000000Z"
            },
            {
                "id": 11,
                "firstName": "حسین داودی",
                "lastName": "شاه‌حسینی",
                "birthday": "2002-08-04",
                "gender": "man",
                "email": "kzare@example.net",
                "phone": "09582568124",
                "role": "user",
                "token": null,
                "code": null,
                "status": "notActive",
                "wallet": 0,
                "created_at": "2021-09-13T11:20:23.000000Z",
                "updated_at": "2021-09-13T11:20:23.000000Z"
            },
            {
                "id": 12,
                "firstName": "گوجه ندارم",
                "lastName": "خیارشور بزارم",
                "birthday": "1965-03-23",
                "gender": "woman",
                "email": "we@gmail.com",
                "phone": "09194139940",
                "role": "user",
                "token": "rw8IGDE0fXRnWE6rYQnb44MibNkwMD8qkYZAsfojzrN2RQafQBWMm6OUosCbETBD",
                "code": 5232,
                "status": "active",
                "wallet": 0,
                "created_at": "2021-09-13T11:29:42.000000Z",
                "updated_at": "2021-09-14T06:06:58.000000Z"
            },
            {
                "id": 13,
                "firstName": "fateme",
                "lastName": "afshar",
                "birthday": "1997-11-12",
                "gender": "woman",
                "email": "ut4760@gmail.com",
                "phone": "09304213780",
                "role": "admin",
                "token": "AUIc2riyzeRs6vi35Vjc2wMYOTfYbU3ErAc9Z2LJl7RQsXVKS9VrPyc6BbKpak6D",
                "code": 3633,
                "status": "notActive",
                "wallet": 0,
                "created_at": "2021-09-13T11:39:50.000000Z",
                "updated_at": "2021-09-14T11:16:38.000000Z"
            }
        ]
    }
}
```
## حذف اکانت کاربری
فراخوانی میشود Delete این متد به صورت 
```bash
http://localhost/api/users/remove
```
### مقادیر ورودی
```js
{
   token : "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx"
}
```
### خروجی موفق
```json
{
    "success": true,
    "code": 200,
    "data": {
        "message": "کاربر با موفقیت از سیستم حذف گردید",
        "token": null,
        "data": null
    }
}
```
## گرفتن لیست تمام دسته بندی ها
فراخوانی میشود Get این متد به صورت 
```bash
http://localhost/api/categories/get/all
```
### مقادیر ورودی
```bash
مقدار ورودی ندارد
```
### خروجی موفق
```json
{
    "success": true,
    "code": 200,
    "data": {
        "message": "دسته بندی ها با موفقیت دریافت شد",
        "data": [
            {
                "id": 1,
                "title": "quibusdam",
                "description": "Et necessitatibus dolores molestiae vel. Reiciendis est nemo consequatur exercitationem optio rem ullam. Aspernatur nulla reprehenderit non qui rem est. Aut quibusdam enim dolorem dolore vitae sit sequi. Et ipsa ipsum dolores nulla aliquam minima earum. Nesciunt qui magnam enim eos deleniti quod quo. Adipisci consectetur hic in aliquid adipisci.",
                "image": "https://via.placeholder.com/640x480.png/0088ff?text=inventore",
                "created_at": "2021-09-05T11:16:39.000000Z",
                "updated_at": "2021-09-05T11:16:39.000000Z"
            },
            {
                "id": 2,
                "title": "tempora",
                "description": "Nisi quasi qui enim. Perspiciatis facere consequatur eius quia officia illum. Eum tempora autem architecto quidem repellat recusandae. Aut repudiandae molestiae perferendis hic deleniti eaque. Distinctio incidunt est at et atque temporibus. Dolorem iste accusamus quasi. Est et dolorum aperiam enim nam quis voluptatum nulla. Laborum illum inventore qui expedita. Fugit in fugit consectetur ut autem aliquid sunt. Voluptatibus aut voluptate sed cumque aliquid optio.",
                "image": "https://via.placeholder.com/640x480.png/00ff66?text=pariatur",
                "created_at": "2021-09-05T11:16:39.000000Z",
                "updated_at": "2021-09-05T11:16:39.000000Z"
            },
            {
                "id": 3,
                "title": "ex",
                "description": "Totam quisquam illum maiores quo dolore sapiente. Non distinctio voluptatem qui qui dolores. Quo voluptatem quaerat voluptatem facere consequatur quae. Id et rem autem nisi. Expedita corporis quaerat ullam qui. Ipsa aut rerum consequatur sit deserunt. Iure incidunt tenetur dolorem. Numquam et possimus provident pariatur. Sit sint porro molestias dolor quas odit tenetur doloremque. Deleniti reprehenderit perferendis libero nam. Dolore quibusdam possimus eaque molestias.",
                "image": "https://via.placeholder.com/640x480.png/00ee00?text=molestiae",
                "created_at": "2021-09-05T11:16:39.000000Z",
                "updated_at": "2021-09-05T11:16:39.000000Z"
            },
            {
                "id": 4,
                "title": "rerum",
                "description": "Et quia non officiis odit aliquam voluptatibus atque. Earum animi quidem quam. Ipsam voluptatem et animi dolores ea soluta. Odit ab eveniet neque alias eum et. Qui voluptas vel ut et. Aut nam et est eos velit est. Ea molestiae tenetur atque nihil. Facilis aut doloribus molestiae molestiae. Eos dicta distinctio consequuntur inventore dolores.",
                "image": "https://via.placeholder.com/640x480.png/0022dd?text=est",
                "created_at": "2021-09-05T11:16:40.000000Z",
                "updated_at": "2021-09-05T11:16:40.000000Z"
            },
            {
                "id": 5,
                "title": "et",
                "description": "Minima et sed et officiis. Voluptas consequatur illum nobis hic maiores culpa. Dolorum voluptas enim rerum cumque repellat accusantium tempora ducimus. Adipisci aut minus est quis. Quia nihil eaque doloremque facilis similique sed tenetur. Unde dolore quisquam quia quis aliquam. Quos suscipit quasi laboriosam laboriosam dolorum explicabo. Aut animi quia aliquam sed. Dolore quis consequuntur est aut sunt quia. Rerum et eaque atque labore.",
                "image": "https://via.placeholder.com/640x480.png/008822?text=facilis",
                "created_at": "2021-09-05T11:16:40.000000Z",
                "updated_at": "2021-09-05T11:16:40.000000Z"
            },
            {
                "id": 7,
                "title": "دسته بندی 1",
                "description": "توضیحات دسته بندی اول",
                "image": "categories/fbFxZaMgFzKRyne9mNnNOJ1MDlTrOSF9ko5oQm2b.jpg",
                "created_at": "2021-09-05T11:32:17.000000Z",
                "updated_at": "2021-09-05T11:32:17.000000Z"
            },
            {
                "id": 8,
                "title": "دسته بندی 1",
                "description": "توضیحات دسته بندی اول",
                "image": "categories/aKRgC1gcQA1kJqUYkh1g33AdLiiikHMwwJum1zyb.jpg",
                "created_at": "2021-09-05T11:37:34.000000Z",
                "updated_at": "2021-09-05T11:37:34.000000Z"
            }
        ]
    }
}
```
## افزودن دسته بندی جدید ![Generic badge](https://img.shields.io/badge/Role-Admin-success.svg)
فراخوانی میشود Post این متد با 
```bash
http://localhost/api/categories/add/category
```
### مقادیر ورودی
```js
{
    token : "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
    title : "دسته بندی 1",
    description : "توضیحات دسته بندی اول",
    image : imageFile
}
```
### خروجی موفق
```json
{
    "success": true,
    "code": 200,
    "data": {
        "message": "دسته بندی جدید با موفقیت ثبت گردید",
        "data": {
            "title": "دسته بندی 1",
            "description": "توضیحات دسته بندی اول",
            "image": "categories/aKRgC1gcQA1kJqUYkh1g33AdLiiikHMwwJum1zyb.jpg",
            "updated_at": "2021-09-05T11:37:34.000000Z",
            "created_at": "2021-09-05T11:37:34.000000Z",
            "id": 8
        }
    }
}
```
## به روزرسانی دسته بندی ![Generic badge](https://img.shields.io/badge/Role-Admin-success.svg)
فراخوانی میشود Put این متد به صورت 
```bash
http://localhost/api/categories/update/category
```
### مقادیر ورودی
```js
{
    token : "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx" // required,
    title : "دسته بندی اول", // optional
    description : "توضیحات دسته بندی اول", // optional
    image : imageFile // optional
}
```
### خروجی موفق
```json
{
    "success": true,
    "code": 200,
    "data": {
        "message": "دسته بندی دسته بندی اول با موفقیت به روزرسانی گردید",
        "data": {
            "id": 1,
            "title": "دسته بندی اول",
            "description": "توضیحات دسته بندی اول",
            "image": "categories/9QwbTxaPHv2dZfVZbrvm7J6wppdhn2Yf39lHrOFI.jpg",
            "created_at": "2021-09-05T11:16:39.000000Z",
            "updated_at": "2021-09-05T11:16:39.000000Z"
        }
    }
}
```
## حذف دسته بندی ![Generic badge](https://img.shields.io/badge/Role-Admin-success.svg)
فراخوانی میشود Delete این متد به صورت 
```bash
http://localhost/api/categories/delete/category
```
### مقادیر ورودی
```js
{
    token : "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
    category_id : 1
}
```
### خروجی موفق
```json
{
    "success": true,
    "code": 200,
    "data": {
        "message": "دسته بندی مورد نظر با موفقیت حذف گردید",
        "data": null
    }
}
```
## گرفتن لیست زیر دسته های یک دسته بندی
فراخوانی میشود Get این متد به صورت 
```bash
http://localhost/api/sub/categories/get/sub/categories
```
### مقادیر ورودی
```js
{
    category_id : 1
}
```
### خروجی موفق
```json
{
    "success": true,
    "code": 200,
    "data": {
        "message": "زیر دسته بندی ها با موفقیت دریافت شد",
        "data": {
            "category_id": "1",
            "title": "زیر دسته ی اول",
            "description": "توضیحات زیر دسته ی اول",
            "image": "subCategories/OnK3QZtRKv5aO0RQ57WcCyWqwoO51CExVF14RZ4w.jpg",
            "updated_at": "2021-09-06T10:17:34.000000Z",
            "created_at": "2021-09-06T10:17:34.000000Z",
            "id": 16
        }
    }
}
```
## افزودن یک زیر دسته جدید به یک دسته بندی ![Generic badge](https://img.shields.io/badge/Role-Admin-success.svg)
فراخوانی میشود Post این متد به صورت 
```bash
http://localhost/api/sub/categories/add/sub/category
```
### مقادیر ورودی
```js
{
    token : "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx", 
    category_id : 1,
    title : "زیر دسته ی اول",
    description : "توضیحات زیر دسته ی اول",
    image : imageFile
}
```
### خروجی موفق
```json
{
    "success": true,
    "code": 200,
    "data": {
        "message": "زیر دسته بندی جدید با موفقیت ثبت گردید",
        "data": {
            "category_id": "1",
            "title": "زیر دسته ی اول",
            "description": "توضیحات زیر دسته ی اول",
            "image": "subCategories/OnK3QZtRKv5aO0RQ57WcCyWqwoO51CExVF14RZ4w.jpg",
            "updated_at": "2021-09-06T10:17:34.000000Z",
            "created_at": "2021-09-06T10:17:34.000000Z",
            "id": 16
        }
    }
}
```
## به روزرسانی زیردسته بندی  ![Generic badge](https://img.shields.io/badge/Role-Admin-success.svg)
فراخوانی میشود Put این متد به صورت 
```bash
http://localhost/api/sub/categories/update/sub/category
```
### مقادیر ورودی
```js
{
    token : "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx", // Required
    subCategory_id : 1,  // Required
    title : "زیر دسته ی اول",  // Optional
    description : "توضیحات زیر دسته ی اول",  // Optional
    image : imageFile  // Optional
}
```
### خروجی موفق
```json
{
    "success": true,
    "code": 200,
    "data": {
        "message": "زیر دسته بندی با موفقیت بروزرسانی شد",
        "data": {
            "id": 1,
            "category_id": 1,
            "title": "زیر دسته ی اول",
            "description": "توضیحات زیر دسته ی اول",
            "image": "subCategories/sndbLjp3SieiWfcxeGqce2ghRSAeSRcdqivWHqwx.jpg",
            "created_at": "2021-09-06T09:13:25.000000Z",
            "updated_at": "2021-09-06T11:47:37.000000Z"
        }
    }
}
```
## حذف زیردسته بندی  ![Generic badge](https://img.shields.io/badge/Role-Admin-success.svg)
فراخوانی میشود Delete این متد به صورت 
```bash
http://localhost/api/sub/categories/delete/sub/category
```
### مقادیر ورودی
```js
{
    token : "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
    subCategory_id : 1,
}
```
### خروجی موفق
```json
{
    "success": true,
    "code": 200,
    "data": {
        "message": "زیر دسته بندی با موفقیت حذف گردید",
        "data": null
    }
}
```
## گرفتن لیست تمام آدرس های قبلی کاربر
فراخوانی میشود Get این متد به صورت
```bash
http://localhost/api/addresses/get/address
```
### مقادیر ورودی
```js
{
    token : "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx"
}
```
### خروجی موفق
```json
{
    "success": true,
    "code": 200,
    "data": {
        "message": "آدرس های کاربر با موفقیت دریافت شد",
        "data": [
            {
                "id": 5,
                "user_id": 1,
                "town": "اردبیل",
                "address": "استان چهارمحال و بختیاری خیابان مجتبوی ساختمان ستّار پلاک 81",
                "latitude": "31.425812",
                "longitude": "51.755624",
                "created_at": "2021-09-07T06:28:10.000000Z",
                "updated_at": "2021-09-07T06:28:10.000000Z"
            },
            {
                "id": 7,
                "user_id": 1,
                "town": "استان کردستان",
                "address": "سیستان و بلوچستان خیابان موسویان ساختمان طاهر قطعه 18",
                "latitude": "31.367466",
                "longitude": "51.177042",
                "created_at": "2021-09-07T06:28:10.000000Z",
                "updated_at": "2021-09-07T06:28:10.000000Z"
            }
        ]
    }
}
```
## افزودن آدرس جدید به کاربر
فراخوانی میشود Post این متد به صورت
```bash
http://localhost/api/addresses/add/address
```
### مقادیر ورودی
```js
{
    token : "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
    town : "تهران",
    address : "اندیشه فاز ۱",
    latitude : "51.01955348",
    longitude : "35.68852885"
}
```
### خروجی موفق
```json
{
    "success": true,
    "code": 200,
    "data": {
        "message": "آدرس جدید کاربر با موفقیت ثبت گردید",
        "data": {
            "user_id": 11,
            "town": "تهران",
            "address": "اندیشه فاز ۱",
            "latitude": "51.01955348",
            "longitude": "35.68852885",
            "updated_at": "2021-09-10T06:22:13.000000Z",
            "created_at": "2021-09-10T06:22:13.000000Z",
            "id": 11
        }
    }
}
```
## به روزرسانی آدرس کاربر
فراخوانی میشود Put این متد به صورت
```bash
http://localhost/api/addresses/update/address
```
### مقادیر ورودی
```js
{
    token : "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx", // Required
    address_id : 11, // Required
    town : "تهران",
    address : "اندیشه فاز ۱",
    latitude : "51.01955348",
    longitude : "35.68852885"
}
```
### خروجی موفق
```json
{
    "success": true,
    "code": 200,
    "data": {
        "message": "آدرس با موفقیت ویرایش شد",
        "data": {
            "user_id": 11,
            "town": "تهران",
            "address": "اندیشه فاز ۱",
            "latitude": "51.01955348",
            "longitude": "35.68852885",
            "updated_at": "2021-09-10T06:22:13.000000Z",
            "created_at": "2021-09-10T06:22:13.000000Z",
            "id": 11
        }
    }
}
```
## حذف آدرس کاربر 
فراخوانی میشود Delete این متد به صورت
```bash
http://localhost/api/addresses/delete/address
```
### مقادیر ورودی
```js
{
    token : "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
    address_id : 11,
}
```
### خروجی موفق
```json
{
    "success": true,
    "code": 200,
    "data": {
        "message": "آدرس مورد نظر با موفقیت حذف گردید",
        "data": null
    }
}
```
## افزودن سفارش جدید 
فراخوانی میشود Post این متد به صورت
```bash
http://localhost/api/orders/add/order
```
### مقادیر ورودی
```js
{
    token : "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
    subCategory_id : 1,
}
```
### خروجی موفق
```json
{
    "success": true,
    "code": 200,
    "token": "P59Q3bBv6dlR8MNbAvGiahpi1vgmElIqxMMPotCGBwL5FdWQLdQPfsanSVOrE4jR",
    "data": {
        "message": "سفارش جدید با موفقیت ثبت شد",
        "data": {
            "order_id": 18
        }
    }
}
```
## بروزرسانی سفارش برای ثبت نوع فنی کار 
فراخوانی میشود Put این متد به صورت
```bash
http://localhost/api/orders/update/order/type
```
### مقادیر ورودی
```js
{
    token : "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
    order_id : 18,
    type : "firstExpert"
}
```
### خروجی موفق
```json
{
    "success": true,
    "code": 200,
    "token": "P59Q3bBv6dlR8MNbAvGiahpi1vgmElIqxMMPotCGBwL5FdWQLdQPfsanSVOrE4jR",
    "data": {
        "message": "نوع فنی کار درخواستی با موفقیت ثبت گردید",
        "data": {
            "order_id": 18
        }
    }
}
```
## بروزرسانی سفارش برای ثبت تاریخ سفارش 
فراخوانی میشود Put این متد به صورت
```bash
http://localhost/api/orders/update/order/date
```
### مقادیر ورودی
```js
{
    token : "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
    order_id : 18,
    date : "2021-11-12 13:42:26"
}
```
### خروجی موفق
```json
{
    "success": true,
    "code": 200,
    "token": "P59Q3bBv6dlR8MNbAvGiahpi1vgmElIqxMMPotCGBwL5FdWQLdQPfsanSVOrE4jR",
    "data": {
        "message": "تاریخ و زمان سفارش ثبت گردید",
        "data": {
            "order_id": 18
        }
    }
}
```
## بروزرسانی سفارش برای ثبت آدرس سفارش 
فراخوانی میشود Put این متد به صورت
```bash
http://localhost/api/orders/update/order/address
```
### مقادیر ورودی
```js
{
    token : "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
    order_id : 18,
    town : "تهران",
    address : "اندیشه فاز ۱",
    latitude : "51.14598752",
    longitude : "32.54658126"
}
```
دریافت میکند یا مقادیر کامل آدرس به شکل بالا address_id این متد یا مقدار 
### مقادیر ورودی
```js
{
    token : "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
    order_id : 18,
    address_id : 11
}
```
### خروجی موفق
```json
{
    "success": true,
    "code": 200,
    "token": "P59Q3bBv6dlR8MNbAvGiahpi1vgmElIqxMMPotCGBwL5FdWQLdQPfsanSVOrE4jR",
    "data": {
        "message": "آدرس با موفقیت ثبت شد",
        "data": {
            "order_id": 18
        }
    }
}
```
## بروزرسانی سفارش برای ثبت توضیحات سفارش 
فراخوانی میشود Put این متد به صورت
```bash
http://localhost/api/orders/update/order/description
```
### مقادیر ورودی
```js
{
    token : "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
    order_id : 18,
    description : "توضیحات مربوط به سفارش 18"
}
```
### خروجی موفق
```json
{
    "success": true,
    "code": 200,
    "token": "KrOunNmCgkNjsrEVQ8IqXS7L1NCABlFOK3v5ly7ryXQWiZNjcsvjXaUOjZ1pVYox",
    "data": {
        "message": "توضیحات سفارش با موفقیت ثبت شد`",
        "data": {
            "order_id": 18
        }
    }
}
```
## بروزرسانی سفارش برای ثبت عکس سفارش 
فراخوانی میشود Put این متد به صورت
```bash
http://localhost/api/orders/update/order/image
```
### مقادیر ورودی
```js
{
    token : "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
    order_id : 18,
    image : imageFile
}
```
### خروجی موفق
```json
{
    "success": true,
    "code": 200,
    "token": "KrOunNmCgkNjsrEVQ8IqXS7L1NCABlFOK3v5ly7ryXQWiZNjcsvjXaUOjZ1pVYox",
    "data": {
        "message": "عکس سفارش با موفقیت ثبت شد",
        "data": {
            "id": 18,
            "user_id": 1,
            "category_id": 1,
            "subCategory_id": 1,
            "type": "firstExpert",
            "time": "2021-12-12 13:52:25",
            "address_id": null,
            "town": "تهران",
            "address": "اندیشه فاز ۱",
            "latitude": "51.15487523",
            "longitude": "31.14697538",
            "description": "توضیحات مربوط به سفارش",
            "image": null,
            "price": 0,
            "status": "pending",
            "created_at": "2021-09-11T07:59:40.000000Z",
            "updated_at": "2021-09-12T07:19:57.000000Z"
        }
    }
}
```
## گرفتن یک سفارش  
فراخوانی میشود Get این متد به صورت
```bash
http://localhost/api/orders/get/order
```
### مقادیر ورودی
```js
{
    token : "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
    order_id : 18,
}
```
### خروجی موفق
```json
{
    "success": true,
    "code": 200,
    "token": "KrOunNmCgkNjsrEVQ8IqXS7L1NCABlFOK3v5ly7ryXQWiZNjcsvjXaUOjZ1pVYox",
    "data": {
        "message": "سفارش مورد نظر با موفقیت دریافت شد",
        "data": {
            "id": 18,
            "user_id": 1,
            "category_id": 1,
            "subCategory_id": 1,
            "type": "firstExpert",
            "time": "2021-12-12 13:52:25",
            "address_id": null,
            "town": "تهران",
            "address": "اندیشه فاز ۱",
            "latitude": "51.15487523",
            "longitude": "31.14697538",
            "description": "توضیحات مربوط به سفارش",
            "image": null,
            "price": 0,
            "status": "pending",
            "created_at": "2021-09-11T07:59:40.000000Z",
            "updated_at": "2021-09-12T07:19:57.000000Z"
        }
    }
}
```

## گرفتن همه سفارش  ![Generic badge](https://img.shields.io/badge/Role-Admin-success.svg)
فراخوانی میشود Get این متد به صورت
```bash
http://localhost/api/orders/get/all/orders
```
### مقادیر ورودی
```js
{
    token : "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx"
}
```
### خروجی موفق
```json
{
    "success": true,
    "code": 200,
    "token": "AH91mY4GwTH2DJfVvixYWWK8t8EcvYlAeYw7dYmc3fTr9kWyaT6Pb5049vSbV8Lp",
    "data": {
        "message": "اطلاعات تمامی سفارشات دریافت شد",
        "data": [
            {
                "id": 2,
                "user_id": 9,
                "category_id": 3,
                "subCategory_id": 12,
                "type": "favoriteExpert",
                "time": "2007-05-06 06:40:48",
                "address_id": 8,
                "town": "کرمانشاه",
                "address": "استان مازندران خیابان صغیری ساختمان اوزن پلاک 20 کد پستی 4204864416",
                "latitude": "32.266585",
                "longitude": "52.645131",
                "description": "Enim dolorum iusto saepe qui impedit. Atque quae sit qui quia. Fugiat rerum ex expedita.",
                "image": "https://via.placeholder.com/640x480.png/00aa11?text=voluptas",
                "price": 0,
                "status": "pending",
                "created_at": "2021-09-13T11:20:24.000000Z",
                "updated_at": "2021-09-13T11:20:24.000000Z"
            },
            {
                "id": 3,
                "user_id": 1,
                "category_id": 2,
                "subCategory_id": 4,
                "type": "firstExpert",
                "time": "2005-08-16 06:51:23",
                "address_id": 9,
                "town": "استان مازندران",
                "address": "استان تهران خیابان عصار ساختمان اقبال قطعه 26 کد پستی 2790525175",
                "latitude": "31.3043",
                "longitude": "52.254088",
                "description": "Aliquid aut rerum voluptas et atque. Non aspernatur fugiat harum dolorum.",
                "image": "https://via.placeholder.com/640x480.png/0099dd?text=qui",
                "price": 15500,
                "status": "complete",
                "created_at": "2021-09-13T11:20:24.000000Z",
                "updated_at": "2021-09-15T12:08:40.000000Z"
            },
            {
                "id": 4,
                "user_id": 8,
                "category_id": 3,
                "subCategory_id": 13,
                "type": "favoriteExpert",
                "time": "1996-09-21 08:05:09",
                "address_id": 10,
                "town": "سمنان",
                "address": "استان البرز خیابان نواب ساختمان سامیه",
                "latitude": "32.039161",
                "longitude": "51.28934",
                "description": "Ut aut quas voluptates. Mollitia aut in voluptatem et molestiae.",
                "image": "https://via.placeholder.com/640x480.png/00ff55?text=ut",
                "price": 0,
                "status": "pending",
                "created_at": "2021-09-13T11:20:24.000000Z",
                "updated_at": "2021-09-13T11:20:24.000000Z"
            },
            {
                "id": 5,
                "user_id": 6,
                "category_id": 4,
                "subCategory_id": 6,
                "type": "firstExpert",
                "time": "1981-08-07 22:32:50",
                "address_id": 8,
                "town": "هرمزگان",
                "address": "استان اردبیل خیابان شریف ساختمان بهنوش پلاک 68",
                "latitude": "31.281713",
                "longitude": "52.762981",
                "description": "Quo optio et et dolores. Odio laborum impedit doloribus eum ratione earum accusamus.",
                "image": "https://via.placeholder.com/640x480.png/009900?text=saepe",
                "price": 0,
                "status": "pending",
                "created_at": "2021-09-13T11:20:24.000000Z",
                "updated_at": "2021-09-13T11:20:24.000000Z"
            },
            {
                "id": 6,
                "user_id": 9,
                "category_id": 3,
                "subCategory_id": 7,
                "type": "firstExpert",
                "time": "1984-06-01 20:07:38",
                "address_id": 8,
                "town": "زنجان",
                "address": "استان هرمزگان خیابان خوئینی‌ها ساختمان نیکی ناز قطعه 72 کد پستی 6152504985",
                "latitude": "31.573832",
                "longitude": "51.115752",
                "description": "Quis qui et veritatis enim ut. Temporibus sed natus hic commodi iste iusto voluptas.",
                "image": "https://via.placeholder.com/640x480.png/00ddcc?text=maiores",
                "price": 0,
                "status": "pending",
                "created_at": "2021-09-13T11:20:24.000000Z",
                "updated_at": "2021-09-13T11:20:24.000000Z"
            },
            {
                "id": 7,
                "user_id": 4,
                "category_id": 1,
                "subCategory_id": 5,
                "type": "favoriteExpert",
                "time": "1976-01-13 02:14:35",
                "address_id": 4,
                "town": "لرستان",
                "address": "استان گلستان خیابان شادمهر ساختمان ثابت کد پستی 1723258617",
                "latitude": "31.74451",
                "longitude": "51.038425",
                "description": "Laborum et quo temporibus rem animi omnis. Consequuntur placeat dolorum magnam odit.",
                "image": "https://via.placeholder.com/640x480.png/0099ee?text=possimus",
                "price": 0,
                "status": "pending",
                "created_at": "2021-09-13T11:20:24.000000Z",
                "updated_at": "2021-09-13T11:20:24.000000Z"
            },
            {
                "id": 8,
                "user_id": 3,
                "category_id": 4,
                "subCategory_id": 8,
                "type": "firstExpert",
                "time": "1980-05-12 03:57:31",
                "address_id": 7,
                "town": "استان همدان",
                "address": "خوزستان خیابان مصباح ساختمان سپند کد پستی 9903330255",
                "latitude": "31.899555",
                "longitude": "51.334404",
                "description": "Temporibus corrupti ea sit quae. Vel incidunt facilis quis. Est dolores aut est sint voluptas.",
                "image": "https://via.placeholder.com/640x480.png/006688?text=dolorem",
                "price": 0,
                "status": "pending",
                "created_at": "2021-09-13T11:20:24.000000Z",
                "updated_at": "2021-09-13T11:20:24.000000Z"
            },
            {
                "id": 9,
                "user_id": 5,
                "category_id": 3,
                "subCategory_id": 6,
                "type": "allExperts",
                "time": "2020-07-27 22:10:12",
                "address_id": 5,
                "town": "استان سیستان و بلوچستان",
                "address": "استان قزوین خیابان نوبخت ساختمان کاموس کد پستی 2540733503",
                "latitude": "31.65567",
                "longitude": "53.227729",
                "description": "Modi facere explicabo eligendi aut. Dolor molestias et rerum.",
                "image": "https://via.placeholder.com/640x480.png/00ff33?text=fugiat",
                "price": 0,
                "status": "pending",
                "created_at": "2021-09-13T11:20:24.000000Z",
                "updated_at": "2021-09-13T11:20:24.000000Z"
            },
            {
                "id": 10,
                "user_id": 3,
                "category_id": 1,
                "subCategory_id": 14,
                "type": "favoriteExpert",
                "time": "1974-02-03 11:04:05",
                "address_id": 3,
                "town": "ایلام",
                "address": "تهران خیابان پایدار ساختمان ملیسا پلاک 16",
                "latitude": "31.929056",
                "longitude": "52.224811",
                "description": "Aut iure sed praesentium natus velit excepturi molestiae. Eius optio fuga ullam.",
                "image": "https://via.placeholder.com/640x480.png/007711?text=veniam",
                "price": 0,
                "status": "pending",
                "created_at": "2021-09-13T11:20:24.000000Z",
                "updated_at": "2021-09-13T11:20:24.000000Z"
            },
            {
                "id": 11,
                "user_id": 2,
                "category_id": 2,
                "subCategory_id": 5,
                "type": "favoriteExpert",
                "time": "1995-02-13 21:04:02",
                "address_id": 4,
                "town": "استان فارس",
                "address": "خراسان رضوی خیابان نقدی ساختمان سروشه قطعه 51",
                "latitude": "32.403491",
                "longitude": "53.149709",
                "description": "Inventore est quia enim aperiam. Non excepturi ullam quis aut. In dicta est deserunt distinctio.",
                "image": "https://via.placeholder.com/640x480.png/00aadd?text=soluta",
                "price": 0,
                "status": "pending",
                "created_at": "2021-09-13T11:20:24.000000Z",
                "updated_at": "2021-09-13T11:20:24.000000Z"
            },
            {
                "id": 12,
                "user_id": 2,
                "category_id": 1,
                "subCategory_id": 15,
                "type": "firstExpert",
                "time": "1992-04-21 22:46:12",
                "address_id": 9,
                "town": "هرمزگان",
                "address": "خراسان شمالی خیابان مصاحب ساختمان اپرنگ کد پستی 7408781049",
                "latitude": "32.043076",
                "longitude": "53.06145",
                "description": "Expedita incidunt quo dolores non fugiat qui. Incidunt doloribus ipsa aut inventore.",
                "image": "https://via.placeholder.com/640x480.png/00ff66?text=nulla",
                "price": 0,
                "status": "pending",
                "created_at": "2021-09-13T11:20:24.000000Z",
                "updated_at": "2021-09-13T11:20:24.000000Z"
            },
            {
                "id": 13,
                "user_id": 4,
                "category_id": 3,
                "subCategory_id": 6,
                "type": "firstExpert",
                "time": "2007-08-03 10:47:11",
                "address_id": 10,
                "town": "استان همدان",
                "address": "آذربایجان غربی خیابان سرمد ساختمان کوشا",
                "latitude": "32.379123",
                "longitude": "52.418719",
                "description": "Est ratione aut aut. Et et soluta nihil aut.",
                "image": "https://via.placeholder.com/640x480.png/006688?text=nisi",
                "price": 0,
                "status": "pending",
                "created_at": "2021-09-13T11:20:25.000000Z",
                "updated_at": "2021-09-13T11:20:25.000000Z"
            },
            {
                "id": 14,
                "user_id": 10,
                "category_id": 3,
                "subCategory_id": 13,
                "type": "allExperts",
                "time": "2006-12-25 20:54:19",
                "address_id": 8,
                "town": "استان چهارمحال و بختیاری",
                "address": "استان هرمزگان خیابان کمالی ساختمان شیفته",
                "latitude": "31.439071",
                "longitude": "52.352896",
                "description": "Dolores ullam ut laudantium sapiente. Aliquid delectus ducimus ab. Sit ea odio ut praesentium.",
                "image": "https://via.placeholder.com/640x480.png/0000bb?text=ab",
                "price": 0,
                "status": "pending",
                "created_at": "2021-09-13T11:20:25.000000Z",
                "updated_at": "2021-09-13T11:20:25.000000Z"
            },
            {
                "id": 15,
                "user_id": 8,
                "category_id": 1,
                "subCategory_id": 3,
                "type": "allExperts",
                "time": "2016-08-20 03:48:29",
                "address_id": 4,
                "town": "استان گیلان",
                "address": "استان کرمانشاه خیابان واعظ ساختمان همراز کد پستی 9257818017",
                "latitude": "32.011324",
                "longitude": "50.879191",
                "description": "Ut numquam amet est. Eum quas hic qui. Ut harum eos quas porro eveniet aut provident.",
                "image": "https://via.placeholder.com/640x480.png/00cc55?text=optio",
                "price": 0,
                "status": "pending",
                "created_at": "2021-09-13T11:20:25.000000Z",
                "updated_at": "2021-09-13T11:20:25.000000Z"
            },
            {
                "id": 16,
                "user_id": 12,
                "category_id": 1,
                "subCategory_id": 2,
                "type": "allExperts",
                "time": "2021-09-18 01:00:00",
                "address_id": null,
                "town": "فرديس",
                "address": "باغستان غربیشسی باغسیشسیتانسپلاک 10 - درب ابی رنشسیشسیگ - پلاک اخلاقی - واشسیحد 6",
                "latitude": "35.816180185873826",
                "longitude": "51.01027572207387",
                "description": "asdasdasdasdasd",
                "image": "orders/DpLqnve9GyrBDhSapJAti61DlTqXjWTPAYsaK2h5.jpg",
                "price": 0,
                "status": "active",
                "created_at": "2021-09-13T11:32:37.000000Z",
                "updated_at": "2021-09-13T11:34:13.000000Z"
            },
            {
                "id": 28,
                "user_id": 12,
                "category_id": 1,
                "subCategory_id": 3,
                "type": "allExperts",
                "time": "2021-09-19 01:00:00",
                "address_id": 22,
                "town": null,
                "address": null,
                "latitude": null,
                "longitude": null,
                "description": "hdkas;kd;las;ldkas;ld;lasd;las;lk;lasdk;las;ldsk;lasdk;asdkas;ldx",
                "image": "orders/85kUHaoSUETCsXPTFrlvVSGWKoDyMwCBmgMwxwCr.jpg",
                "price": 0,
                "status": "active",
                "created_at": "2021-09-14T07:06:15.000000Z",
                "updated_at": "2021-09-14T09:52:04.000000Z"
            },
            {
                "id": 29,
                "user_id": 12,
                "category_id": 1,
                "subCategory_id": 1,
                "type": "allExperts",
                "time": "2021-09-19 01:00:00",
                "address_id": 11,
                "town": null,
                "address": null,
                "latitude": null,
                "longitude": null,
                "description": "مکنیشکسنمنیکسشخینسکمشنیکمنشسنیکم",
                "image": "orders/9scm1eGdvPck86NOkQcSUsJ9ljYW80a8Ldsy0w9E.jpg",
                "price": 0,
                "status": "active",
                "created_at": "2021-09-14T12:09:49.000000Z",
                "updated_at": "2021-09-14T12:11:10.000000Z"
            }
        ]
    }
}
```

## گرفتن لیست تمامی سفارشات کاربر 
فراخوانی میشود Get این متد به صورت
```bash
http://localhost/api/orders/get/all/orders
```
### مقادیر ورودی
```js
{
    token : "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
}
```
### خروجی موفق
```json
{
    "success": true,
    "code": 200,
    "token": "KrOunNmCgkNjsrEVQ8IqXS7L1NCABlFOK3v5ly7ryXQWiZNjcsvjXaUOjZ1pVYox",
    "data": [{
        "message": "تمامی سفارشات شما با موفقیت دریافت شد",
        "data": {
            "id": 18,
            "user_id": 1,
            "category_id": 1,
            "subCategory_id": 1,
            "type": "firstExpert",
            "time": "2021-12-12 13:52:25",
            "address_id": null,
            "town": "تهران",
            "address": "اندیشه فاز ۱",
            "latitude": "51.15487523",
            "longitude": "31.14697538",
            "description": "توضیحات مربوط به سفارش",
            "image": null,
            "price": 0,
            "status": "pending",
            "created_at": "2021-09-11T07:59:40.000000Z",
            "updated_at": "2021-09-12T07:19:57.000000Z"
        }
    }]
}
```

## فعال کردن سفارش  
فراخوانی میشود Put این متد به صورت
```bash
http://localhost/api/orders/update/order/status
```
### مقادیر ورودی
```js
{
    token : "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
    order_id : 18,
}
```
### خروجی موفق
```json
{
    "success": true,
    "code": 200,
    "token": "KrOunNmCgkNjsrEVQ8IqXS7L1NCABlFOK3v5ly7ryXQWiZNjcsvjXaUOjZ1pVYox",
    "data": {
        "message": "سفارش مورد نظر با موفقیت دریافت شد",
        "data": {
            "id": 18,
            "user_id": 1,
            "category_id": 1,
            "subCategory_id": 1,
            "type": "firstExpert",
            "time": "2021-12-12 13:52:25",
            "address_id": null,
            "town": "تهران",
            "address": "اندیشه فاز ۱",
            "latitude": "51.15487523",
            "longitude": "31.14697538",
            "description": "توضیحات مربوط به سفارش",
            "image": null,
            "price": 0,
            "status": "pending",
            "created_at": "2021-09-11T07:59:40.000000Z",
            "updated_at": "2021-09-12T07:19:57.000000Z"
        }
    }
}
```

## حذف یک سفارش  
فراخوانی میشود Delete این متد به صورت
```bash
http://localhost/api/orders/delete/order
```
### مقادیر ورودی
```js
{
    token : "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
    order_id : 18,
}
```
### خروجی موفق
```json
{
    "success": true,
    "code": 200,
    "token": "KrOunNmCgkNjsrEVQ8IqXS7L1NCABlFOK3v5ly7ryXQWiZNjcsvjXaUOjZ1pVYox",
    "data": {
        "message": "سفارش مورد نظر با موفقیت حذف گردید",
        "data": null
    }
}
```
## افزودن یک کد تخفیف جدید  ![Generic badge](https://img.shields.io/badge/Role-Admin-success.svg)
فراخوانی میشود Post این متد به صورت
```bash
http://localhost/api/tickets/add/ticket
```
### مقادیر ورودی
```js
{
    token : "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
    code : "testCode",  // کد تخفیف مورد نظر
    percent : 50  // درصد تخفیف این کد
}
```
### خروجی موفق
```json
{
    "success": true,
    "code": 200,
    "token": "KrOunNmCgkNjsrEVQ8IqXS7L1NCABlFOK3v5ly7ryXQWiZNjcsvjXaUOjZ1pVYox",
    "data": {
        "message": "کد تخفیف جدید افزوده شد",
        "data": {
            "code": "testCode",
            "percent": "50",
            "updated_at": "2021-09-12T11:29:24.000000Z",
            "created_at": "2021-09-12T11:29:24.000000Z",
            "id": 11
        }
    }
}
```
## استفاده کردن از کد تخفیف
فراخوانی میشود Post این متد به صورت
```bash
http://localhost/api/tickets/use/ticket
```
### مقادیر ورودی
```js
{
    token : "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
    code : "testCode",
    order_id : 15  
}
```
### خروجی موفق
```json
{
    "success": true,
    "code": 200,
    "token": "KrOunNmCgkNjsrEVQ8IqXS7L1NCABlFOK3v5ly7ryXQWiZNjcsvjXaUOjZ1pVYox",
    "data": {
        "message": "کد تخفیف با موفقیت اعمال شد",
        "data": null
    }
}
```
## بروزرسانی کد تخفیف ![Generic badge](https://img.shields.io/badge/Role-Admin-success.svg)
فراخوانی میشود Put این متد به صورت
```bash
http://localhost/api/tickets/update/ticket
```
### مقادیر ورودی
```js
{
    token : "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx", // Required
    ticket_id : 15,  // Required
    code : "testCode", // Optional
    percent : 50 // Optional
}
```
### خروجی موفق
```json
{
    "success": true,
    "code": 200,
    "token": "AH91mY4GwTH2DJfVvixYWWK8t8EcvYlAeYw7dYmc3fTr9kWyaT6Pb5049vSbV8Lp",
    "data": {
        "message": "کد تخفیف مورد نظر با موفقیت به روزرسانی شد",
        "data": {
            "id": 1,
            "code": "UpdateCode",
            "percent": "30",
            "created_at": "2021-09-13T11:20:25.000000Z",
            "updated_at": "2021-09-14T06:26:29.000000Z"
        }
    }
}
```
## حذف کد تخفیف ![Generic badge](https://img.shields.io/badge/Role-Admin-success.svg)
فراخوانی میشود Delete این متد به صورت
```bash
http://localhost/api/tickets/delete/ticket
```
### مقادیر ورودی
```js
{
    token : "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx", 
    ticket_id : 1
}
```
### خروجی موفق
```json
{
    "success": true,
    "code": 200,
    "token": "AH91mY4GwTH2DJfVvixYWWK8t8EcvYlAeYw7dYmc3fTr9kWyaT6Pb5049vSbV8Lp",
    "data": {
        "message": "کد تخفیف مورد نظر با موفقیت حذف گردید",
        "data": null
    }
}
```
## گرفتن لیست فنی کاران منتخب کاربر
فراخوانی میشود Get این متد به صورت
```bash
http://localhost/api/experts/get/favorite/experts
```
### مقادیر ورودی
```js
{
    token : "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx"
}
```
### خروجی موفق
```json
{
    "success": true,
    "code": 200,
    "token": "AH91mY4GwTH2DJfVvixYWWK8t8EcvYlAeYw7dYmc3fTr9kWyaT6Pb5049vSbV8Lp",
    "data": {
        "message": "فنی کارهای منتخب با موفقیت دریافت گردید",
        "data": [
            {
                "id": 1,
                "firstName": "برین",
                "lastName": "شفا",
                "nationalCode": "4712090960",
                "gender": "man",
                "email": "uhamidi@example.com",
                "phone": "09940624363",
                "birthday": "1988-02-01",
                "point": 151,
                "projects": 179,
                "bio": "Qui ad natus at a est exercitationem. Possimus nisi nobis aut qui autem a. Illum fugit aut rem consectetur fugiat.",
                "city": "چهارمحال و بختیاری",
                "address": "استان هرمزگان خیابان قانونی ساختمان توتک پلاک 80 کد پستی 4031642312",
                "ability": "optio",
                "status": "active",
                "created_at": "2021-09-14T10:40:49.000000Z",
                "updated_at": "2021-09-14T10:40:49.000000Z"
            },
            {
                "id": 2,
                "firstName": "عقیق",
                "lastName": "محدثی",
                "nationalCode": "1860321586",
                "gender": "woman",
                "email": "payam85@example.org",
                "phone": "09341365255",
                "birthday": "1995-06-21",
                "point": 355,
                "projects": 200,
                "bio": "Neque eos natus vel. Sit et expedita sed voluptas mollitia necessitatibus. Et nostrum voluptatem accusantium fugiat consequatur consectetur.",
                "city": "استان بوشهر",
                "address": "سیستان و بلوچستان خیابان حبیبی ساختمان جاودانه پلاک 25",
                "ability": "velit",
                "status": "pending",
                "created_at": "2021-09-14T10:40:50.000000Z",
                "updated_at": "2021-09-14T10:40:50.000000Z"
            },
            {
                "id": 3,
                "firstName": "برسام",
                "lastName": "قهرمان",
                "nationalCode": "9141816531",
                "gender": "woman",
                "email": "shapour44@example.org",
                "phone": "09189664520",
                "birthday": "2003-02-03",
                "point": 814,
                "projects": 177,
                "bio": "Recusandae quia sit tempora reiciendis. Debitis tempore voluptatibus dolores quis mollitia et similique. Suscipit commodi distinctio officia consequuntur. Porro cumque et recusandae recusandae.",
                "city": "گیلان",
                "address": "استان کرمان خیابان هومن ساختمان ماهر قطعه 16",
                "ability": "veniam",
                "status": "active",
                "created_at": "2021-09-14T10:40:50.000000Z",
                "updated_at": "2021-09-14T10:40:50.000000Z"
            }
        ]
    }
}
```
## افزودن فنی کار به لیست علاقه مندی های کاربر
فراخوانی میشود Post این متد به صورت
```bash
http://localhost/api/experts/add/favorite/expert
```
### مقادیر ورودی
```js
{
    token : "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
    expert_id : 1
}
```
### خروجی موفق
```json
{
    "success": true,
    "code": 200,
    "token": "AH91mY4GwTH2DJfVvixYWWK8t8EcvYlAeYw7dYmc3fTr9kWyaT6Pb5049vSbV8Lp",
    "data": {
        "message": "فنی کار با موفقیت به لیست فنی کاران مورد علاقه افزوده شد",
        "data": {
            "id": 1,
            "firstName": "برین",
            "lastName": "شفا",
            "nationalCode": "4712090960",
            "gender": "man",
            "email": "uhamidi@example.com",
            "phone": "09940624363",
            "birthday": "1988-02-01",
            "point": 151,
            "projects": 179,
            "bio": "Qui ad natus at a est exercitationem. Possimus nisi nobis aut qui autem a. Illum fugit aut rem consectetur fugiat.",
            "city": "چهارمحال و بختیاری",
            "address": "استان هرمزگان خیابان قانونی ساختمان توتک پلاک 80 کد پستی 4031642312",
            "ability": "optio",
            "status": "active",
            "created_at": "2021-09-14T10:40:49.000000Z",
            "updated_at": "2021-09-14T10:40:49.000000Z"
        }
    }
}
```
## حذف فنی کار از لیست علاقه مندی های کاربر
فراخوانی میشود Delete این متد به صورت
```bash
http://localhost/api/experts/delete/favorite/expert
```
### مقادیر ورودی
```js
{
    token : "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
    expert_id : 1
}
```
### خروجی موفق
```json
{
    "success": true,
    "code": 200,
    "token": "AH91mY4GwTH2DJfVvixYWWK8t8EcvYlAeYw7dYmc3fTr9kWyaT6Pb5049vSbV8Lp",
    "data": {
        "message": "فنی کار مورد نظر با موفقیت از لیست علاقه مندی ها حذف گردید",
        "data": {
            "id": 1,
            "firstName": "برین",
            "lastName": "شفا",
            "nationalCode": "4712090960",
            "gender": "man",
            "email": "uhamidi@example.com",
            "phone": "09940624363",
            "birthday": "1988-02-01",
            "point": 151,
            "projects": 179,
            "bio": "Qui ad natus at a est exercitationem. Possimus nisi nobis aut qui autem a. Illum fugit aut rem consectetur fugiat.",
            "city": "چهارمحال و بختیاری",
            "address": "استان هرمزگان خیابان قانونی ساختمان توتک پلاک 80 کد پستی 4031642312",
            "ability": "optio",
            "status": "active",
            "created_at": "2021-09-14T10:40:49.000000Z",
            "updated_at": "2021-09-14T10:40:49.000000Z"
        }
    }
}
```
## گرفتن لیست تمامی تراکنش های کاربر
فراخوانی میشود Get این متد به صورت
```bash
http://localhost/api/transactions/get/all/transactions
```
### مقادیر ورودی
```js
{
    token : "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx"
}
```
### خروجی موفق
```json
{
    "success": true,
    "code": 200,
    "token": "AH91mY4GwTH2DJfVvixYWWK8t8EcvYlAeYw7dYmc3fTr9kWyaT6Pb5049vSbV8Lp",
    "data": {
        "message": "لیست تراکنش های کاربر با موفقیت دریافت شد",
        "data": [
            {
                "id": 2,
                "user_id": 1,
                "refId": "19279498",
                "price": "808923",
                "created_at": "2021-09-15T06:52:24.000000Z",
                "updated_at": "2021-09-15T06:52:24.000000Z"
            },
            {
                "id": 8,
                "user_id": 1,
                "refId": "99296107",
                "price": "577664",
                "created_at": "2021-09-15T06:52:25.000000Z",
                "updated_at": "2021-09-15T06:52:25.000000Z"
            }
        ]
    }
}
```

## پرداخت
فراخوانی میشود Get این متد به صورت
```bash
http://localhost/api/transactions/pay
```
### مقادیر ورودی
```js
{
    token : "XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX",
    type : "charge", // two possible values 1 - charge 2 - order  --> charge for balance charge and order if  pay is for order and must send order_id
    order_id : 1, // only if the pay is for order
    price : 10000 // Rials
}
```
### خروجی موفق
```js
    در صورت درست بودن به صفحه پرداخت هدایت میشود
```
## گرفتن محتوی درباره ی ما
فراخوانی میشود Get این متد به صورت
```bash
http://localhost/api/about/get/about
```
### مقادیر ورودی
```js
{
    ورودی ندارد
}
```
### خروجی موفق
```json
{
    "success": true,
    "code": 200,
    "token": "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
    "data": {
        "message": "محتوی درباره ی ما با موفقیت دریافت شد",
        "data": {
            "about": "test about us page contents",
            "image": "about/TlLyqzvAOtVqvNGKg0p6ldgKBPpEWbuQJPJUpDBr.jpg",
            "updated_at": "2021-09-25T12:40:25.000000Z",
            "created_at": "2021-09-25T12:40:25.000000Z",
            "id": 2
        }
    }
}
```
## افزودن محتوی درباره ی ما ![Generic badge](https://img.shields.io/badge/Role-Admin-success.svg)
فراخوانی میشود Post این متد به صورت
```bash
http://localhost/api/about/add/about
```
### مقادیر ورودی
```js
{
    token : "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx", 
    about : "test about us page contents",
    image : ImageFile
}
```
### خروجی موفق
```json
{
    "success": true,
    "code": 200,
    "token": "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
    "data": {
        "message": "محتوی درباره ی ما با موفقیت افزوده شد",
        "data": {
            "about": "test about us page contents",
            "image": "about/TlLyqzvAOtVqvNGKg0p6ldgKBPpEWbuQJPJUpDBr.jpg",
            "updated_at": "2021-09-25T12:40:25.000000Z",
            "created_at": "2021-09-25T12:40:25.000000Z",
            "id": 2
        }
    }
}
```
## حذف محتوی درباره ی ما ![Generic badge](https://img.shields.io/badge/Role-Admin-success.svg)
فراخوانی میشود Delete این متد به صورت
```bash
http://localhost/api/about/delete/about
```
### مقادیر ورودی
```js
{
    token : "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx", 
    about_id : 1
}
```
### خروجی موفق
```json
{
    "success": true,
    "code": 200,
    "token": "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
    "data": {
        "message": "محتوی درباره ی ما با موفقیت حذف گردید",
        "data": null
    }
}
```
## افزودن محتوی درباره ی ما ![Generic badge](https://img.shields.io/badge/Role-Admin-success.svg)
فراخوانی میشود Post این متد به صورت
```bash
http://localhost/api/contact/add/contact
```
### مقادیر ورودی
```js
{
    token : "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx", 
    primary_number : "09197956244",
    secondary_number : "09037089787",
    address : "اندیشه فاز 1 خیابان لاله 4",
    telegram : "llaravell",
    instagram : "taha.sh_74",
    whatsapp : "09197956244",
    email : "tahashokri77@gmail.com"
}
```
### خروجی موفق
```json
{
    "success": true,
    "code": 200,
    "token": "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
    "data": {
        "message": "محتوی تماس با ما با موفقیت افزوده شد",
        "data": {
            primary_number : "09197956244",
            secondary_number : "09037089787",
            address : "اندیشه فاز 1 خیابان لاله 4",
            telegram : "llaravell",
            instagram : "taha.sh_74",
            whatsapp : "09197956244",
            email : "tahashokri77@gmail.com",
            id : 2
        }
    }
}
```
## حذف محتوی ارتباط با ما ![Generic badge](https://img.shields.io/badge/Role-Admin-success.svg)
فراخوانی میشود Delete این متد به صورت
```bash
http://localhost/api/contact/delete/contact
```
### مقادیر ورودی
```js
{
    token : "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx", 
    contact_id : 1
}
```
### خروجی موفق
```json
{
    "success": true,
    "code": 200,
    "token": "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
    "data": {
        "message": "محتوی تماس با ما با موفقیت حذف گردید",
        "data": null
    }
}
```
## گرفتن محتوی تماس با ما
فراخوانی میشود Get این متد به صورت
```bash
http://localhost/api/contact/get/contact
```
### مقادیر ورودی
```js
{
    ورودی ندارد
}
```
### خروجی موفق
```json
{
    "success": true,
    "code": 200,
    "token": "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
    "data": {
        "message": "محتوی درباره ی ما با موفقیت دریافت شد",
        "data": {
            primary_number : "09197956244",
            secondary_number : "09037089787",
            address : "اندیشه فاز 1 خیابان لاله 4",
            telegram : "llaravell",
            instagram : "taha.sh_74",
            whatsapp : "09197956244",
            email : "tahashokri77@gmail.com",
            id : 2
        }
    }
}
```
## گرفتن محتوی پروژه های صفر تا صد ![Generic badge](https://img.shields.io/badge/Role-Admin-success.svg)
فراخوانی میشود Get این متد به صورت
```bash
http://localhost/api/projects/get/projects
```
### مقادیر ورودی
```js
{
    token : "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
    page : 1 // optional for pagination
}
```
### خروجی موفق
```json
{
  "success": true,
  "code": 200,
  "token": "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
  "data": {
    "message": "لیست پروژه ها با موفقیت دریافت شد",
    "data": [
      
    ]
  }
}
```
## افزودن محتوی پروژه های صفر تا صد
فراخوانی میشود Post این متد به صورت
```bash
http://localhost/api/projects/add/projects
```
### مقادیر ورودی
```js
{
    firstName : "Taha",
    lastName : "Shokri",
    phone : "09197956244",
    number : "02165522122",
    state : "Tehran",
    city : "Karaj",
    description : "some descriptions"
}
```
### خروجی موفق
```json
{
  "success": true,
  "code": 200,
  "data": {
    "message": "پروژه جدید با موفقیت افزوده شد",
    "data": {
        firstName : "Taha",
        lastName : "Shokri",
        phone : "09197956244",
        number : "02165522122",
        state : "Tehran",
        city : "Karaj",
        description : "some descriptions"
    }
  }
}
```
## حذف محتوی پروژه های صفر تا صد ![Generic badge](https://img.shields.io/badge/Role-Admin-success.svg)
فراخوانی میشود Delete این متد به صورت
```bash
http://localhost/api/projects/remove/projects
```
### مقادیر ورودی
```js
{
    token : "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
    project_id : 1
}
```
### خروجی موفق
```json
{
  "success": true,
  "code": 200,
  "data": {
    "message": "پروژه با موفقیت حذف شد",
    "data": null
  }
}
```
