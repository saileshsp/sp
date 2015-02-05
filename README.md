



movies = Hash.new
movies = { "arya" => 5 , "AD" => 5 ,"gopala gopala" => 5 }


puts "-- Type 'add' to add a movie."
puts "-- Type 'update' to update a movie."
puts "-- Type 'display' to display all movies."
puts "-- Type 'delete' to delete a movie."

cond = gets.chomp
case cond
 when 'add'
puts "enter the movie name that you want to add"
movie_name=gets.chomp
 if(movies.has_key?(movie_name))
    puts "movie already exists"
    rating=movies.values_at(movie_name)
           
       
        puts("movie name is #{movie_name} and rating is #{rating}  ")
    
else
    
     puts("enter the rating of movie")
    

 rat=gets.chomp
     movies.store(movie_name , rat)
    puts("movie name is #{movie_name} and rating is #{rat} ")
end
 when 'display'
      puts "total movies in list are "
    movies.each do |movie, rating|
  
    puts "movie name is #{movie} and rating is #{rating} "
   
       end 
 when 'delete'
    puts "enter movie name that  you want to delete?"
    movie_name = gets.chomp
   if(movies.has_key?(movie_name))
    movies.delete(movie_name)
      puts "#{movie_name} has been removed."
      puts "movies left in list are"
      movies.each do|movie , rating|
      puts "movie #{movie} and rating #{rating} "
  else
    puts "movie not found"
      end
  
 end
when 'update'
  puts "enter the movie name that you want to update"
  movie_name = gets.chomp
  if(movies.has_key?(movie_name))
   puts "enter the new rating of movie"
    rating = gets.chomp
    movies[movie_name] = rating
    puts "#{movie_name} has been updated with new rating of #{rating}."
  else
   puts "movie not found"
  end
  
  end
  
  
  
