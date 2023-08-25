Multistage docker file
--------------------

```
# Stage 1 - Build
FROM alpine AS build

# Write the variable value to a file
RUN echo "hello" > /tmp/myvar

# Stage 2 - Run
FROM alpine AS run

# Copy the variable value from the previous stage using a file
COPY --from=build /tmp/myvar /tmp/myvar
# Read the variable value from the file
RUN MY_VAR=$(cat /tmp/myvar) && echo "Running the app with MY_VAR=$MY_VAR"

docker build --no-cache -t my_image .

$ docker run --rm my_image /bin/sh -c "cat /tmp/myvar"
hello

```
```
example-2

FROM alpine:latest as base
ENV MY_ENV="my_env"

FROM base
RUN echo ${MY_ENV}
```
