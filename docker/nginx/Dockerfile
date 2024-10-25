FROM nginx:stable

# Install required libs
RUN apt-get update && apt-get install -y vim

# Copy custom nginx config
COPY ./templates/laravel.local.conf /etc/nginx/conf.d/laravel.local.conf
COPY ./templates/nginx.conf /etc/nginx/nginx.conf

# Remove default config
RUN rm /etc/nginx/conf.d/default.conf

# Disable vim visual
RUN echo "set mouse-=a" >> ~/.vimrc