---  
layout: post
title: Live on PostgreSQL
category: posts
---  
  
## In 10 Steps
  
1. Add    
    * gem 'pg' outside of any group in the Gemfile.    
2. Remove all group references to    
    * gem 'pg'    
      ...and    
    * gem 'sqlite'    
    * from the group :development, :test  
    * & from group :production, respectively  
3. Navigate to config/database.yml  
    * replace 'sqlite3' as adapter: postgresql  
4. Delete all references to database: db/development.sqlite3 from test: and development:  
5. Delete the config/development.sqlite3  
6. run `rake db:drop`  
7. Install the [POSTGRESAPP][POSTGRESAPP]  
    * Ensure it runs by opening the app which is now viewable from your navigation bar (elephant)   
8. run `rake db:create`  
    * this command must now be run prior to the beginning of all new pg apps    
9. run `rake db:migrate` as usual  
10. That was only 9!

---  
[POSTGRESAPP]: http://postgresapp.com/