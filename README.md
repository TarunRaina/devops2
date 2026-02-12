🚀 DevOps Hands-On Journey — Linux, Docker & Jenkins

Author: Tarun Raina

📌 Overview

This repository documents a multi-day practical DevOps journey covering:

Linux fundamentals

Git workflows

Docker containerization

Nginx deployment

Jenkins CI/CD automation

Each day is maintained as a separate Git branch with its own detailed markdown documentation and command logs.

The main branch acts purely as a navigation layer and executive summary.

For full implementation details, switch to the respective day branch.

🗂 Branch Breakdown
🔹 Day 1 — Linux + Git Foundations + Ubuntu Server Setup

👉 Branch:
https://github.com/TarunRaina/devops2/tree/day1

Focus areas:

Directory navigation (ls, cd)

Git basics (clone, branch, checkout, commit, push)

Ubuntu VM setup

Initial repository creation

Terminal history logging

Multi-branch workflow introduction

Jenkins installation (Java + Jenkins service setup)

Core themes:

✔ Linux command line fluency
✔ Git branching fundamentals
✔ Ubuntu server preparation
✔ Jenkins installation & unlock

Artifacts:

day-1.txt

Day-1.md

🔹 Day 2 — Docker Installation + Node App Containerization

👉 Branch:
https://github.com/TarunRaina/devops2/tree/day2

Focus areas:

Installing Docker from official repository

Docker validation (hello-world)

User permission setup (docker group)

Node.js application execution

Building Docker images

Running containers

Image and container cleanup

Core themes:

✔ Docker engine installation
✔ Image creation
✔ Container lifecycle management
✔ Node app inside Docker

Artifacts:

day-2.txt

Day-2.md

🔹 Day 3 — Nginx + Static Website Hosting via Docker

👉 Branch:
https://github.com/TarunRaina/devops2/tree/day3

Focus areas:

Pulling Nginx images

Running Nginx containers

Port exposure

Hosting static websites using Docker volumes

Mapping local folders into containers

Serving custom UI through Nginx

Core themes:

✔ Reverse proxy fundamentals
✔ Volume mounting
✔ Static site deployment
✔ Containerized web hosting

Artifacts:

day-3.txt

Day-3.md

🔹 Day 4 — Jenkins + Docker CI/CD Pipeline

👉 Branch:
https://github.com/TarunRaina/devops2/tree/day4

Focus areas:

Jenkins + Docker integration

Jenkins permission fixes

React + Node app testing

Dockerfile creation

GitHub integration

Three-stage Jenkins pipeline:

Pipeline Flow:

Clone Git repository

Build Docker image

Run Docker container

Manual trigger at stage 1 → automated downstream execution.

Core themes:

✔ CI/CD fundamentals
✔ Jenkins freestyle jobs
✔ Docker image automation
✔ Live container deployment

Artifacts:

day-4.txt

Day-4.md

🎯 Outcome

By Day 4, the workflow achieves:

GitHub → Jenkins → Docker → Live Application

A complete Continuous Integration + Continuous Deployment pipeline.

📍 How to Navigate Locally
git checkout day1
git checkout day2
git checkout day3
git checkout day4


Each branch is fully self-contained.