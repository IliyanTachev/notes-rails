# notes-rails
rails new app

rails generate scaffold Teacher last_name:string middle_name:string first_name:string title:string subject:string
rake db:migrate

rails generate scaffold Subject subject_name:string teacher_id:integer
rake db:migrate

NBB!! add @teachers = Teacher.all TO Subjects Controller

  #VALIDATION
  1. go to subjects controller
    -> after Subject.new -> if Teacher.exists?(:id => (subject_params[:teacher_id]))
    !!!! Don't forget aboud 'end' keyword
  2. go to teachers controller
    -> after Teacher.new -> if !Teacher.exists?(:title => (teacher_params[:title]))
    !!!! Don't forget aboud 'end' keyword
    
    #TABLE
    1. go to config/routes.rb
    2. get '/11b_11_IliyanTachevsubjects', to: 'subjects#index'
    3. go to /views/subjects/index.html.erb
    4. add <th>'s for your need
    5. add <td>'s  --> @teachers.find(subject.teacher_id).last_name
    
    
    FINAL:   PRAY TO WORKs!
