# LaaS Image API Service

[![CI](https://github.com/llama-as-a-service/images-service/actions/workflows/ci.yml/badge.svg?branch=main)](https://github.com/llama-as-a-service/images-service/actions/workflows/ci.yml) [![Vercel Deploy](https://github.com/llama-as-a-service/images-service/actions/workflows/vercel-deploy.yml/badge.svg?branch=main)](https://github.com/llama-as-a-service/images-service/actions/workflows/vercel-deploy.yml) [![Heroku Deploy](https://github.com/llama-as-a-service/images-service/actions/workflows/heroku-deploy.yml/badge.svg?branch=main)](https://github.com/llama-as-a-service/images-service/actions/workflows/heroku-deploy.yml) [![Publish Docker](https://github.com/llama-as-a-service/images-service/actions/workflows/publish-to-ghcr.yml/badge.svg?branch=main)](https://github.com/llama-as-a-service/images-service/actions/workflows/publish-to-ghcr.yml) [![Stable Version](https://img.shields.io/github/v/tag/llama-as-a-service/images-service)](https://img.shields.io/github/v/tag/llama-as-a-service/images-service) [![Latest Release](https://img.shields.io/github/v/release/llama-as-a-service/images-service?color=%233D9970)](https://img.shields.io/github/v/tag/llama-as-a-service/images-service?color=%233D9970)

Image API Service. Built with NodeJS, Express, and Docker. Connects to the MongoDB Image Database.

> ⚠️ Heroku Deployment may be depreciated

#### ✅ Try It Out:
```sh
curl https://llama-as-a-service-images.herokuapp.com/random
```
##### JSON Response
```json
{
  "message": "https://images.theconversation.com/files/337593/original/file-20200526-106811-ql6d51.jpg?ixlib=rb-1.1.0&q=45&auto=format&w=1200&h=900.0&fit=crop"
}
```

## 🎥 Walkthrough Video

[![YouTube Video](https://user-images.githubusercontent.com/60903378/202875326-30bc7b91-3bf3-48be-a688-c74493fb4964.png)](https://www.youtube.com/watch?v=uDQUA_JTMJk)

## ⚙️ Setup
```sh
$ git clone https://github.com/llama-as-a-service/images-service.git
$ cd images-service
$ cp .env.sample .env
$ docker-compose up -d
# access on localhost:3000
```

## 🧪 Test
```sh
$ docker-compose exec images_service yarn run test
```

## 📦 Pull from GitHub Repository Container Registry
```sh
# docker pull ghcr.io/OWNER/IMAGE_NAME
$ docker pull ghcr.io/llama-as-a-service/images-service:0.1.0
```

## API Documentation

### Random Endpoint

| URL            | /random |
|----------------|---------|
| Method         | GET     |
| Status         | 200 OK  |
| Authentication | None    |

#### Optional Parameters
Defualt = 1
Max = 25
```
?count=9
```

#### Sample Response:
```json
{
    "message": [
      "https://cdn.britannica.com/41/1/Alpaca.jpg?w=400&h=300&c=crop",
      "https://images.pexels.com/photos/3396661/pexe61.jpg&fm=jpg",
      "https://www.openaccess.org/wp-content/scaled.jpg",
      ...
    ],
}
```

### Upload Endpoint

| URL            | /upload     |
|----------------|-------------|
| Method         | POST        |
| Status         | 201 CREATED |
| Authentication | Admin       |

#### Example body:
```json
{
    "url": "https://cdn.britannica.com/41/1/Alpaca.jpg?w=400&h=300&c=crop",
}
```

#### Sample Response:
```json
{
    "message": "Successfully upload image!",
}
```

## Alternative Setup
```sh
$ yarn install
$ yarn run start # yarn run dev
```