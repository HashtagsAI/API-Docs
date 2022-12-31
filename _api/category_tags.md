---
title: Category Tags
position_number: 1.6
type: get
description: Get a list of tags from a category
left_code_blocks:
  - code_block: |-
        curl --request GET \
        --url https://hashtag5.p.rapidapi.com/api/v1/categories/1/tags \
        --header 'X-RapidAPI-Host: hashtag5.p.rapidapi.com' \
        --header 'X-RapidAPI-Key: YOUR_API_KEY'
    title: Curl
    language: bash

  - code_block: |-
        const axios = require("axios");

        const options = {
        method: 'GET',
        url: 'https://hashtag5.p.rapidapi.com/api/v1/categories/1/tags',
        headers: {
            'X-RapidAPI-Key': 'YOUR_API_KEY',
            'X-RapidAPI-Host': 'hashtag5.p.rapidapi.com'
        }
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

        val request = Request.Builder()
            .url("https://hashtag5.p.rapidapi.com/api/v1/categories/1/tags")
            .get()
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
            "net/http"
            "io/ioutil"
        )

        func main() {

            url := "https://hashtag5.p.rapidapi.com/api/v1/categories/1/tags"

            req, _ := http.NewRequest("GET", url, nil)

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
                    "tag": "meme",
                    "postCount": 149560135
                },
                {
                    "tag": "beer",
                    "postCount": 75289321
                },
                ...
                {
                    "tag": "alcoholengel",
                    "postCount": 36968
                },
                {
                    "tag": "alcoholabuse",
                    "postCount": 35630
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
            "path": "/api/v1/categories/:id/tags"
        }
    title: Error
    language: json
---