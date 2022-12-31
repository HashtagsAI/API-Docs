---
title: Image Relevant
position_number: 1.7
type: post
description: Generates hashtags from an image provided.
left_code_blocks:
  - code_block: |-
        curl --request POST \
        --url https://hashtag5.p.rapidapi.com/api/v1/tag/generate \
        --header 'Content-Type: application/json' \
        --header 'X-RapidAPI-Host: hashtag5.p.rapidapi.com' \
        --header 'X-RapidAPI-Key: YOUR_API_KEY' \
        --header 'content-type: application/json' \
        --data '{
            "image": "base64encodedImage"
        }'
    title: Curl
    language: bash

  - code_block: |-
        const axios = require("axios");

        const options = {
        method: 'POST',
        url: 'https://hashtag5.p.rapidapi.com/api/v1/tag/generate',
        headers: {
            'content-type': 'application/json',
            'Content-Type': 'application/json',
            'X-RapidAPI-Key': 'YOUR_API_KEY',
            'X-RapidAPI-Host': 'hashtag5.p.rapidapi.com'
        },
        data: '{"image":"base64encodedImage"}'
        };

        axios.request(options).then(function (response) {
            console.log(response.data);
        }).catch(function (error) {
            console.error(error);
        });
    title: Node.js
    language: javascript
  - code_block: |-
        val client = OkHttpClient()

        val mediaType = MediaType.parse("application/json")
        val body = RequestBody.create(mediaType, "{\n    \"image\": \"base64encodedImage\"\n}")
        val request = Request.Builder()
            .url("https://hashtag5.p.rapidapi.com/api/v1/tag/generate")
            .post(body)
            .addHeader("content-type", "application/json")
            .addHeader("Content-Type", "application/json")
            .addHeader("X-RapidAPI-Key", "YOUR_API_KEY")
            .addHeader("X-RapidAPI-Host", "hashtag5.p.rapidapi.com")
            .build()

        val response = client.newCall(request).execute()
    title: Kotlin
    language: kotlin

  - code_block: |-
        package main

        import (
            "fmt"
            "strings"
            "net/http"
            "io/ioutil"
        )

        func main() {

            url := "https://hashtag5.p.rapidapi.com/api/v1/tag/generate"

            payload := strings.NewReader("{\n    \"image\": \"base64encodedImage\"\n}")

            req, _ := http.NewRequest("POST", url, payload)

            req.Header.Add("content-type", "application/json")
            req.Header.Add("Content-Type", "application/json")
            req.Header.Add("X-RapidAPI-Key", "YOUR_API_KEY")
            req.Header.Add("X-RapidAPI-Host", "hashtag5.p.rapidapi.com")

            res, _ := http.DefaultClient.Do(req)

            defer res.Body.Close()
            body, _ := ioutil.ReadAll(res.Body)

            fmt.Println(res)
            fmt.Println(string(body))

        }
    title: Go
    language: go
right_code_blocks:
  - code_block: |2-
        {
            "tags": [
                {
                    "tag": "fashionblogger",
                    "postCount": 147676162
                },
                {
                    "tag": "shopping",
                    "postCount": 143208337
                },
                ...
                {
                    "tag": "fashiondaily",
                    "postCount": 11310766
                },
                {
                    "tag": "fashionhijab",
                    "postCount": 10565760
                }
            ]
        }
    title: Response
    language: json
  - code_block: |2-
        {
            "timestamp": "2022-12-31T07:17:53.127+00:00",
            "status": 404,
            "error": "Failed to get tags",
            "path": "/api/v1/tag/generate"
        }
    title: Error
    language: json
---