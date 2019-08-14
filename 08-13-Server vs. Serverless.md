# Server vs. Serverless

![meme](https://tr4.cbsistatic.com/hub/i/r/2016/11/29/9ea5f375-d0dd-4941-891b-f35e7580ae27/resize/770x/982bcf36f7a68242dce422f54f8d445c/49nocloud.jpg)

Some terms:

- `fullstack`:  the entirety of a computer system or application, comprising both the front end and the back end.
- `serverless`: Serverless computing is a cloud-computing execution model in which the cloud provider runs the server, and dynamically manages the allocation of machine resources.
- `Ubuntu`: A popular Linux distro
- `Stack`: A **web stack** is a type of solution **stack**, which is a collection of software for performing specific tasks, WP runs on a `LAMP` stack etc



We can either run all the services ourselves or let a Cloud provider (AWS, Google, Microsoft etc.) take care of it. Both have advantages it just depends on your needs/situation.

## Mern:

![mern](https://blog.hyperiondev.com/wp-content/uploads/2018/09/Blog-Article-MERN-Stack.jpg)

### Technologies:

#### MongoDB:

A `nonsql` database

#### Express:

the most popular `nodejs` server solution

#### React:

the most popular front-end library

#### NodeJS:

JavaScript that runs on the server

#### Also:

`Redux`, `mapbox`, `docker`, `webpack`,`nginx`

`MERN` is a modern popular solution to build `fullstack` apps. They are easy to host on for example a DigitalOcean Ubuntu server.  Usually you would put it all behind an `nginx` server.

`Docker` or another container solution is also very useful to include in this stack.

![stack1](https://res.cloudinary.com/dyb5d1jmz/image/upload/v1565585331/mern-stack_o2u0ki.jpg)





### Pros:

- vendor independent
- full control
- all open source, non-commercial
- very flexible
- predictable cost
- already know `git`,`vim` etc so you can use known technologies

### Cons:

- you have to do everything, `SSL`, firewall, DB security, maintanance, upgrades
- takes a while to set-up 
- might not be up to spikes in traffic
- additional services for metrics etc needed

## Serverless:

![stack2](https://i0.wp.com/markoinsights.com/wp-content/uploads/2016/11/logo_lockup_cloud_platform_icon_vertical.png)

Popular solutions are `AWS`, `GCP`, `Azure` etc

All have `cli` to manage services. You can use single parts or join different services, `AWS` exceeds at that.

### Technologies:

#### React:

front-end, but can be anything

#### GCP (Google Cloud Platform):

Gives us a lot of services, we are going to use `firebase`, which is a limited subset of services perfect for `fullstack` apps. So with firebase with have

- hosting

- file storage
- database (`firestore`)
- authentication
- Google Cloud functions

out of the box, it reduces complexity that the full GCP would have. There is a generous free quota for us to experiment with. We can write/read directly from the web client or through cloud functions. We can directly call cloud functions from the web client or have cloud functions invoked on 'events' like file storage events or certain database operations. I.e. we can generate a thumbnail on an image upload where the image get's uploaded, invokes a cloud function that then generates a thumbnail and saves that. We can also have periodic invocations of cloud functions like a `cron` job on a traditional server.

Deployment of the frontend and the cloud functions can be done with the `firebase` cli, same with `AWS` etc

###### ![serverless-stack](https://res.cloudinary.com/dyb5d1jmz/image/upload/v1565643521/Serverless_stack_congresscards.jpg)

### Pros:

- fully managed
- some security out of the box, including SSL 
- scales under load
- has a free tier, so initial costs will be 0
- Amazing tooling and services, create a db and `API` with a single command etc
- often easy to get started 
- metrics from the start

### Cons:

- vendor lock-in, will be difficult to change later on
- can be expensive, make sure what services will cost (AWS cost explosion)
- can be a lot to learn (AWS) 
- can be dangerous if you don't fully understand what you're doing (Capital One hack etc)
- startup delay on 'cold start', though  **80% of instances survive 5 hours of inactivity**. Cold starts are about 2 seconds on average.

