### Setup tutorial
1. bundle install
2. change `database.yml` to your configuration
3. rake db:create_migration NAME=create_articles
4. change db/migrate/20162234234_create_articles.rb to :
```
class CreateArticles < ActiveRecord::Migration
  def change
    create_table :articles do |t|
      t.string :title
      t.string :content
      t.boolean :published, :default => false
      t.datetime :published_on, :required => false
      t.integer :likes, :default => 0
      t.timestamps null: false
    end
  end
end

```
5. rake db:migrate