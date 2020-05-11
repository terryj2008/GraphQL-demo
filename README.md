#please use below command and paremeters to run the demo on your loal machine

query Query{
  movies{
  id
  name
  company
  movieRating
  releaseDate
  actorId
  customString
    actor{
      id
      name
    }
  }
}

mutation Delete($id:ID!){
  deleteMovie(id:$id)
}

mutation Update($input:MovieInput!){
  updateMovie(movie: $input){
    id
    name
    company
    movieRating
    releaseDate
    actorId
    actor{
      id
      name
    }
  }
}

mutation Create($input:MovieInput!){
  createMovie(movie: $input){
    
    name
    company
    movieRating
    releaseDate
    actorId
    actor{
      id
      name
    }
  }
}


--add
{
  "input":{
     "id":5,
     "name": "亚索",
     "company": "天下",
     "movieRating": "UNRATED",
     "releaseDate": "1821-12-1",
     "actorId":1 
  }
}

--update
{
  "input":{
     "id":1,
     "name": "The Shawshank Redemption",
     "company": "美国",
     "movieRating": "G",
     "releaseDate": "0001-01-01",
     "actorId":1 
  }
}


--delete
{
	"movieId": 5
}
