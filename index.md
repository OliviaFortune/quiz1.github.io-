<!DOCTYPE html>
<html>
<body>

<select id="Movie" onchange="ChangeMovieList()">
  <option value="">-- Movie --</option>
  <option value="CO">Comedy</option>
  <option value="AD">Adventure</option>
  <option value="DR">Drama</option>
</select>

<select id="MovieGenre"></select>


<p id="demo"></p>

<script>
function myFunction() {
    document.getElementById("demo").innerHTML = result;
}
</script>



<script>
var MoviesAndGenres = {};
MoviesAndGenres['CO'] = ['Comedy1', 'Comedy2', 'Comedy3'];
MoviesAndGenres['AD'] = ['Adventure1', 'Adventure2', 'Adventure3', 'Adventure4'];
MoviesAndGenres['DR'] = ['Drama1', 'Drama2', 'Drama3'];

function ChangeMovieList() {
  var MovieList = document.getElementById("Movie");
  var GenreList = document.getElementById("MovieGenre");
  var selMovie = MovieList.options[MovieList.selectedIndex].value;

  while (GenreList.options.length) {
    GenreList.remove(0);
  }


  var Movies = MoviesAndGenres[selMovie];
  if (Movies) {
    var i;
    for (i = 0; i < Movies.length; i++) {
      var Movie = new Option(Movies[i], i);
      GenreList.options.add(Movie);
    }

  }


}




</script>

</body>
</html>

