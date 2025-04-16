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

## Create a custom theme in terminal
   ddev php web/core/scripts/drupal generate-theme thmeName --path themes/custom


This is an initial project to learn Drupal v11
