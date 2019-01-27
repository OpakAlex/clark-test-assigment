# Coding Challenge Reward System

Implementation a system for calculating rewards based on recommendations of customers.
Data structure for this task, looks like graph (https://en.wikipedia.org/wiki/Graph_(abstract_data_type)).
My implementation based on simple graph tree, which we keep into memory while calculation. I dont want to use any database, because i follow this requirements:
 - Implement the solution using Ruby.

I put all logic of this task into services: `app/services/rewards`.
I created simple tree, where each node knowns about parent node, then, when we have any updates(like accept invite) we just update parent node, and lookup into 3 levels (1 point, 0.5 points, 0.25 points). I added some more logic about validate input data, and parsing this data. Each of my classes independent, this means, we can refactor / replace each part safely.
I didn't use any gems for implement this task (just rails, etc for webservice), because i think you want to see my ruby level.
Web endpoint exists into: `app/controllers/rewards_controller.rb`
I used `rubocop` gem (https://github.com/rubocop-hq/rubocop) for this project code style, i don't known if you use it.
Follow my instructions for setup, tests, run, and feel free to contact me if you have any questions.

### Requirements:
 - `Ruby version >= 2.3.1`
 - `Bundler version 1.12.5`

### Install:
 - `bundle install`

### Tests:
 - `bundle exec rubocop`
 - `bundle exec rspec`

### Run:
 - `rails s`
 - `curl -X POST localhost:3000/rewards --data-binary @example.txt -H "Content-Type: text/plain"`
