#
# Dockerfile
#
# 
#
FROM ruby:3.2.2

# Install Rails
RUN gem install rails

# Set up a working directory
WORKDIR /app

# Create a new Rails application
RUN rails new . --minimal

COPY routes.rb                   config/routes.rb
COPY application_controller.rb   app/controllers/application_controller.rb

# Expose port 3000
EXPOSE 3000

# Start the Rails server
CMD ["rails", "server", "-b", "0.0.0.0"]
