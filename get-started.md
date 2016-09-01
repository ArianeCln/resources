**to run migrations**
In routes.rb --> comment *ActiveAdmin.routes(self)*

**to drop db and re-run all migrations**
...
1. rake db:drop
2. do smthg in:
  psql --u postgres \c conichi_development
