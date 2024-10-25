FROM mariadb:10.11

# Make sure we have the correct timezone in the database
COPY ./templates/conf.cnf /etc/mysql/conf.d/99-custom.cnf

# Disable vim visual mode
RUN echo "set mouse-=a" >> ~/.vimrc
