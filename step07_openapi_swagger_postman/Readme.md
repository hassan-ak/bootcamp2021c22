# Step07 - Open API Testing and Development with Swagger and Postman

## Class Notes

API's are used for communication between softwares on different platforms. For developing API first applications we develop the API first and rest of the application afterwards. There is design first as compare to code first where we define the design for our app (design the schema).

- [Designing APIs with Swagger and OpenAPI](https://www.manning.com/books/designing-apis-with-swagger-and-openapi)

  - OpenAPI is a description of HTTP-based APIs which are typically, RESTful APIs, It comes in e form of a YAML file which document input, output, hosting and authorization types etc.
  - Example of an OpenAPI defination

    ```yml
    openapi: 3.0.0
    info:
      title: Dog API
      version: 1.0.0
    servers:
      - url: https://dog.ceo/api
    paths:
      /breed/{breedName}/images:
        get:
          description: Get images of dog breeds
          parameters:
            - in: path
              name: breedName
              schema:
                type: string
                example: hound
              required: true
          responses:
            '200':
            description: A list of dog images
            content:
              application/json:
                schema:
                  type: object
                  properties:
                    status:
                      type: string
                      example: success
                    message:
                      type: array
                      items:
                        type: string
                        example: https://images.dog.ceo/breeds/hound-afghan/n02088094_1003.jp
    ```

  - This file will be consumed by SwaggerUI and given a human readable data.
