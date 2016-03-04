# Chapter 3 常用库

- Java
    1. `org.json`
        
        ```
        // build.gradle
        compile 'org.json:json:20151123'
        ```
        
        ```java
        // object to json
        JSONObject jsonObject = new JSONObject(model);
        String json = jsonObject.toString(4);
        
        // json to object
        
        ```
        
    2. `Jackson JSON Processor`
    
        > gradlew dependencies
        
        ```
        // build.gradle
        compile 'com.fasterxml.jackson.core:jackson-databind:2.5.3'
        ```
        
        ```java
        
        ObjectMapper objectMapper = new ObjectMapper();
        objectMapper.configure(SerializationFeature.INDENT_OUTPUT, true);
        
        // object to json
        String json = objectMapper.writeValueAsString(model);
        
        // json to object
        Model model = objectMapper.readValue(json, Model.class);
        ```
        
    3. `Google-gson`
    
        ```
        // build.gradle
        compile 'com.google.code.gson:gson:2.5'
        ```
        
        ```java
        Gson gson = new GsonBuilder().setPrettyPrinting().create();
        
        //  object to json
        String json = gson.toJson(model); 
        
        // json to object
        Model model = gson.fromJson(json, Model.class);
        ```
        
    4. `fastjson`
    
        ```
        // build.gradle
        compile 'com.alibaba:fastjson:1.2.7'
        ```
        
        ```java
        // object to json
        String json = JSON.toJSONString(model);
        
        // json to object
        Model model = JSON.parseObject(json, Model.class);
        ```
    
- JavaScript