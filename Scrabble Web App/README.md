## Starting Up

```bash
npm install
```

```json
  "scripts": {
    "start": "node server/index.js"
  },
```

```bash
npm start
```

This will run the server.

## Task 1 (Client): Adding scrabble rules


Add the following ExpressJS middleware to the Express application:

  1. **static**: This middleware will serve static files from the `client` directory. See examples we covered in class for how to do this.

  2. **morgan**: This middleware will log the requests to the console. Make sure you import this library into your application. See examples we covered in class for how to do this.

Add the following API endpoints to the Express application:

  1. **POST /wordScore**

    This endpoint will be used to save a word score on the server. The response should only consist of a 200 status code, with a success JSON object (see below).

    **Example Request**:

    [http://localhost:3000/wordScore](http://localhost:3000/wordScore)

    **Example Request Body**:

    ```json
    {
      "name": "Artemis",
      "word": "test",
      "score": 8
    }
    ```

    **Example Response** (200 OK status code):

    ```json
    {
      "status": "success"
    }
    ```

  2. **GET /highestWordScores**

    This endpoint will be used to get the top 10 word scores saved on the server (or top X scores if only X < 10 scores are saved). It should return a JSON response, which will be an array of objects consisting of a word and a score.

    **Example Request**:

    [http://localhost:3000/highestWordScores](http://localhost:3000/highestWordScores)

    **Example Response** (200 OK status code):

    ```json
    [{ "name": "Artemis", "word": "test", "score": 8 }, ..., { "name": "Parzival", "word": "school", "score": 11 }]
    ```

  3. **POST /gameScore**

    This endpoint will be used to save a game score for a single player on the server. The response should only consist of a 200 status code, with no body.

    **Example Request**:

    [http://localhost:3000/gameScore](http://localhost:3000/gameScore)

    **Example Request Body**:

    ```json
    {
      "name": "Artemis",
      "score": 361
    }
    ```

    **Example Response** (200 OK status code):

    ```json
    {
      "status": "success"
    }
    ```

  4. **GET /highestGameScores**

    This endpoint will be used to get the top 10 game scores saved on the server (or top X scores if only X < 10 scores are saved). It should return a JSON response, which will be an array of objects consisting of a name and a score.

    **Example Request**:

    [http://localhost:3000/highestGameScores](http://localhost:3000/highestGameScores)

    **Example Response** (200 OK status code):

    ```json
    [{ "name": "Artemis", "score": 650 }, ..., { "name": "Parzival", "score": 513 }]
    ```

  Like the last server, the saved scores should be persistent: if the server is restarted, it should still have the previous scores saved. For now, you can just use a JSON file that you read and write to. You should be able to copy your solution from the previous homework into this file to continue to support this functionality.

It is recommended that you test each endpoint before proceeding to the next to ensure that it is working correctly. You should use [Postman](https://www.postman.com/downloads/) to manually test each endpoint.



