**Restaurant API**
----
  此 Restaurant API 為利用假資料來練習之範例API文件，若需使用本範例之API，需使用 token 獲取權限，格視為json。
  (目前還尚未提供可用API，因此本文件為模擬正式專案先做呈現)

* **Base URL:**

  base_url: http://localhost:3000

* **Method / Router:**
  
  **Restaurant(前台):**
  
  `GET`：/api/restaurants/top 顯示最新建立的餐廳排名資料
  
  `GET`: /api/restaurants 顯示全部餐廳
  
  
  **Restaurant(後台):**
  
  `GET`：/api/admin/categories  顯示全部餐廳類別
  
  `GET`：/api/admin/restaurants 顯示全部餐廳
  
  
*  **URL Parameters:**
    
    n/a

*  **Request Body:**
    
    n/a

* **Success Response:**

  * **Code:** 200 <br />
    **Content:**
    ```json
    {
      "status": "success",
      "data": {
          "restaurant": 
            {
              "id": 6,
              "name": "Laurence Gulgowski",
              "tel": "(518) 623-3827 x33396",
              "address": "24785 Stiedemann Expressway",
              "openingHours": "08:00",
              "description": "Est est maiores ad totam et.\nUllam sint aut quis id cum.",
              "image": "https://loremflickr.com/320/240/restaurant,food/?random=11.976448119367667",
              "viewCounts": 0,
              "createdAt": "2022-09-26T07:53:27.000Z",
              "updatedAt": "2022-09-26T07:53:27.000Z",
              "categoryId": 3,
              "Category": {
                  "id": 3,
                  "name": "義大利料理",
                  "createdAt": "2022-09-26T07:53:26.000Z",
                  "updatedAt": "2022-09-26T07:53:26.000Z"
              }
            },
            {
              "id": 7, // 略...
            }
        }
    }
    
    OR
    
    {
      "status": "success",
      "data": {
         "restaurant": null
      }
    }
    ```
 
* **Error Response:**
    
  * **Code:** 401 <br />
    **Content:** 
    ```json
    {
      "status": "error",
      "message": "unauthorized"
    }
    ```

  OR
  
  * **Code:** 403 <br />
    **Content:** 
    ```json
    {
      "status": "error",
      "message": "permission denied"
    }
    
  OR
  
  * **Code:** 500 <br />
    **Content:** 
    ```json
    {
      "status": "error",
      "message": "Internal Server Error"
    }
    ```
 <hr />
 
   **Restaurant(前台):**
  
  `GET`: /api/restaurants/:id 顯示一筆選定餐廳資料以及詳細資訊
  
   **Restaurant(後台):**

  `GET`： /api/admin/restaurants/:id 顯示一筆選定餐廳資訊以及詳細資訊
    
  
*  **URL Parameters:**
    
    `id=[integer]`

*  **Request Body:**
    
    n/a

* **Success Response:**

  * **Code:** 200 <br />
    **Content:**
    ```json
    {
      "restaurant": {
        "id": 4,
        "name": "Antonia Cassin II",
        "tel": "(670) 348-5426 x084",
        "address": "26948 Ankunding Inlet",
        "openingHours": "08:00",
        "description": "Libero quo labore corporis a omnis quaerat esse dolore adipisci.\nError corrupti nihil sit.",
        "image": "https://loremflickr.com/320/240/restaurant,food/?random=1.7251746513071042",
        "viewCounts": 1,
        "createdAt": "2022-09-26T07:53:27.000Z",
        "updatedAt": "2022-09-29T04:25:39.000Z",
        "categoryId": 7,
        "Category": {
            "id": 7,
            "name": "複合式料理",
            "createdAt": "2022-09-26T07:53:26.000Z",
            "updatedAt": "2022-09-26T07:53:26.000Z"
        },
        "Comments": [],
        "FavoritedUsers": [],
        "LikedUsers": []
      },
      "isFavorited": false,
      "isLiked": false
    }
    
    OR
    {
      "status": "success",
      "data": {
          "restaurant": null
      }
    }
    ```
 
* **Error Response:**
    
  * **Code:** 401 <br />
    **Content:** 
    ```json
    {
        "status": "error",
        "message": "unauthorized"
    }
    ```

  OR
  
  * **Code:** 403 <br />
    **Content:** 
    ```json
    {
        "status": "error",
        "message": "permission denied"
    }
    
  OR
  
  * **Code:** 404 <br />
    **Content:** 
    ```json
    {
        "status": "error",
        "message": "Restaurant didn't exist!"
    }
    
  OR
  
  * **Code:** 500 <br />
    **Content:** 
    ```json
    {
        "status": "error",
        "message": "Internal Server Error"
    }
    ```
<hr /> 
  
  **`PUT` Restaurant(後台):**
  
  `PUT`：/api/admin/restaurants/:id 更新一筆選定餐廳資訊
  
  
*  **URL Parameters:**
    
    `id=[integer]`

*  **Request Body:**
    ```json
      {
        "name": "Della Mosciski IIII",
        "tel": "1-879-612-8880 x7981",
        "address": "45884 Charlie Views",
        "openingHours": "08:00",
        "description": "bla bla bla",
        "image": "https://loremflickr.com/320/240/restaur...",
        "categoryId": "7"
      }
    ```


* **Success Response:**

  * **Code:** 200 <br />
    **Content:**
    ```json
    {
      "status": "success",
      "data": {
          "restaurant": {
              "id": 6,
              "name": "Laurence Gulgowski",
              "tel": "(518) 623-3827 x33396",
              "address": "24785 Stiedemann Expressway",
              "openingHours": "08:00",
              "description": "Est est maiores ad totam et.\nUllam sint aut quis id cum.",
              "image": "https://loremflickr.com/320/240/restaurant,food/?random=11.976448119367667",
              "viewCounts": 0,
              "createdAt": "2022-09-26T07:53:27.000Z",
              "updatedAt": "2022-09-26T07:53:27.000Z",
              "categoryId": 3,
              "Category": {
                  "id": 3,
                  "name": "義大利料理",
                  "createdAt": "2022-09-26T07:53:26.000Z",
                  "updatedAt": "2022-09-26T07:53:26.000Z"
              }
           }
        }
    }
    ```
 
* **Error Response:**
    
  * **Code:** 401 <br />
    **Content:** 
    ```json
    {
        "status": "error",
        "message": "unauthorized"
    }
    ```

  OR
  
  * **Code:** 403 <br />
    **Content:** 
    ```json
    {
        "status": "error",
        "message": "permission denied"
    }
    
  OR
  
  * **Code:** 404 <br />
    **Content:** 
    ```json
    {
        "status": "error",
        "message": "Restaurant didn't exist!"
    }
    
  OR
  
  * **Code:** 500 <br />
    **Content:** 
    ```json
    {
        "status": "error",
        "message": "Internal Server Error"
    }
    ```
 <hr />
  
  **`delete` Restaurant(後台):**
  
  `delete`：/api/admin/categories/:id 刪除一筆選定類別
  
  
*  **URL Parameters:**
    
    `id=[integer]`

*  **Request Body:**

    n/a


* **Success Response:**

  * **Code:** 200 <br />
    **Content:**
    ```json
    {
      "status": "success",
      "data": {
          "restaurant": {
              "id": 5,
              "name": "Danielle Gusikowski",
              "tel": "(616) 789-0384 x6560",
              "address": "9043 Jacobi Camp",
              "openingHours": "08:00",
              "description": "Placeat ad eos sed aut aut doloremque et.\nEius sed harum molestiae.\nAssumenda tempora explicabo et.",
              "image": "https://loremflickr.com/320/240/restaurant,food/?random=90.06427653705529",
              "viewCounts": 0,
              "createdAt": "2022-09-26T07:53:27.000Z",
              "updatedAt": "2022-09-26T07:53:27.000Z",
              "categoryId": 5
          }
      }
    }
    ```
 
* **Error Response:**
    
  * **Code:** 401 <br />
    **Content:** 
    ```json
    {
        "status": "error",
        "message": "unauthorized"
    }
    ```

  OR
  
  * **Code:** 403 <br />
    **Content:** 
    ```json
    {
        "status": "error",
        "message": "permission denied"
    }
    
  OR
  
  * **Code:** 404 <br />
    **Content:** 
    ```json
    {
        "status": "error",
        "message": "Restaurant didn't exist!"
    }
    
  OR
  
  * **Code:** 500 <br />
    **Content:** 
    ```json
    {
        "status": "error",
        "message": "Internal Server Error"
    }
    ```

