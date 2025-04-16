## Steps to create a Drupal Project with ddev

# 1 => Initialize ddev on directory
  ddev config --project-type=drupal11 --docroot=web --create-docroot
# 2 => Initialize ddev containers
  ddev start
# 3 => Create Drupal Project
  ddev composer create "drupal/project-name" -y
# 4 => Install Drush in the container 
  ddev composer require drush/drush
# 5 => Install Drupal in the container
   ddev drush site:install --site-name="Drupal 11 Frontend" -y
#  6 => Launch app
   ddev launch   

## Create a custom theme
  # How to install a new theme
   ddev php web/core/scripts/drupal generate-theme thmeName --path themes/custom

## Install and configurate Tailwindcss in our Drupal project   
  # 1 => How to install Tailwind cssin our theme (make sure you are in the root of the theme folder)
   ddev npm install tailwindcss @tailwindcss/cli
  # 2 => Configure tailwindcss in our theme (create a tailwind.css file in the css folder and paste this content)
   @import "tailwindcss";
  # 3 => Configure tailwindcss in your .libraries.yml. Add the following option on the top of css options 
      base:
      css/tailwind.output.css: {}
  # 4 => Create a scripts in package.json 
    "build": "npx @tailwindcss/cli -i ./css/tailwind.css -o ./css/tailwind.output.css --watch"
  # 5 => Run the script 
    ddev npm run build

This is an initial project to learn Drupal v11
