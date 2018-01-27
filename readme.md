# Carmudi DevOps Engineer Exam

## About us

Carmudi is a vehicle classifieds platform that operates in many countries. As a DevOps engineer you will be working with apps being used by millions of users monthly.

## Goals

1. Develop your own microservices
2. Create a mechanism for automatic deployments

## Problem

"Today's Featured Image"

This app has 2 components: `image-service` and `viewer-service`. `image-service` is a web microservice that has a single endpoint/function: to serve random 4x4 PNG images. `viewer-service` is a simple static site that shows a big "Today's Featured Image" text and then shows the image served by `image-service`.

Your task is to develop this app and implement CI/CD.

## Tasks

* Make sure that all your solutions are hosted on a public GitHub repository and that you are able to use git to record all your activity
* Update `image-service` to accept this query parameter `?date=yyyy-mm-dd` to view the featured image of any date specified (a certain date's image should stay the same across requests)
* Create a docker image for running both `image-service` and `viewer-service` (reusing existing Docker Hub images is highly encouraged)
* Create a docker-compose config to run both `image-service` and `viewer-service` on any local machine
* Implement CI/CD with Travis (travis-ci.com)
    * Travis should deploy the `image-service` docker container to Heroku (travis-support ootb) or sloppy.io or somewhere else - whatever you prefer
    * It should be deployed NOT as a PHP app but as a Dockerized app. Failure to do so results to failing the whole exam.
    * Travis should deploy the `viewer-service` static file to GitHub Pages (of the same repo) or Firebase Hosting or somewhere else - whatever you prefer
    * Note: Make sure to create simple tests for both services before deploying (integral for doing CI/CD)
* PRs submitted should be built first by Travis
* Create 2 PRs: 1 designed to have a passing build (your tests pass) and another having a failing build (your tests fail)
* Create a brief documentation of what you've done

## Bonus

Implement some form of security on `image-service` to prevent hotlinking

> (c) Carmudi 2018+
