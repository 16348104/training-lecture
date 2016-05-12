# Chapter 3 常用库

- Java
    1. `org.json`
        
        ```
        // build.gradle
        compile 'org.json:json:20151123'
        ```
        
        ```java
        // Java object to JSON object 
        JSONObject jsonObject = new JSONObject(model);
        String json = jsonObject.toString(4);
        
        // Java collection to JSON array
        JSONArray jsonArray = new JSONArray(collection);
        String json = jsonArray.toString(4);
        
        // JSON object to Java object
        
        ```
        
    2. `Jackson JSON Processor`
    
        ```
        // build.gradle
        compile 'com.fasterxml.jackson.core:jackson-databind:2.5.3'
        ```
        
        ```java
        
        ObjectMapper objectMapper = new ObjectMapper();
        objectMapper.configure(SerializationFeature.INDENT_OUTPUT, true);
        
        // Java object to JSON Object
        String json = objectMapper.writeValueAsString(model);
        
        // Java collection to JSON Array
        String json = objectMapper.writeValueAsString(collection);
        
        // JSON Object to Java object
        Model model = objectMapper.readValue(json, Model.class);
        
        ```
        
    3. `Google-gson`
    
        ```
        // build.gradle
        compile 'com.google.code.gson:gson:2.5'
        ```
        
        ```java
        Gson gson = new GsonBuilder().setPrettyPrinting().create();
        
        //  Java object to JSON object
        String json = gson.toJson(model); 
        
        // JSON object to JAVA object
        Model model = gson.fromJson(json, Model.class);
        ```
        
    4. `fastjson`
    
        ```
        // build.gradle
        compile 'com.alibaba:fastjson:1.2.7'
        ```
        
        ```java
        // Java Object to JSON object
        String json = JSON.toJSONString(model, true);
        
        // JSON object to Java object
        Model model = JSON.parseObject(json, Model.class);
        ```
    
- JavaScript
  1. Parse JSON in jQuery AJAX

    ```javascript
    $(function () {
        $.ajax({
            url: 'request_url',
            type: 'POST',
            data: {'key': value},
            dataType: 'json',
            success: function (result) {
                // parse JSON object
                alert(result.property);
                // iterate JSON array
                $.each(result, function (index, item) {
                    alert(item.property);
                });
            }
        });
    });
    ```

  