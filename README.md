# d8deploy.sh
Drupal 8 Deployment CI

## d8deploy.sh

git pull

composer install --no-dev

drush cache:rebuild

drush -y state:set system.maintenance_mode 1

drush -y updatedb

drush -y config:import

drush -y core:cron

drush -y state:set system.maintenance_mode 0

drush cache:rebuild
