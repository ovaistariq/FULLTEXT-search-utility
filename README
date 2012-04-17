=== Description
This is a search utility that i developed that parses a search query submitted by user and converts it into Boolean Full Text Search query that can be used in SQL with all the words stemmed to their base word.

=== Installation
No installation is needed, just copy the two files search.php and wordstemmer.php to your project and include them:

include "wordstemmer.php";
include "search.php";

=== Requirements
PHP version 5+

=== wordstemmer.php
External package with implementation of Porter Stemming algorithm.

=== search.php
The class that generates the Boolean Full Text search query from user submitted search terms.

=== Usage
Usage is pretty simple. First you need to create an object of the search library, by passing it the search query that user has submitted:

$lib_search = new Libs_Search('some user search string here');

Next you would need to call the method GetSearchQueryString and it would return the query string that you can use in your searches:

$query_string = $lib_search->GetSearchQueryString();

Now you can use the generated query string as follows:

$sql = "SELECT * FROM tbl where MATCH(txt_col) AGAINST('$query_string' IN BOOLEAN MODE)";
mysql_query( $sql );

=== Examples
-- Example 1
$lib_search = new Libs_Search("Life's");
echo $lib_search->GetSearchQueryString(); // This will echo life*

-- Example 2
$lib_search = new Libs_Search("Life's making");
echo $lib_search->GetSearchQueryString(); // This will echo life* make*

-- Example 3
$lib_search = new Libs_Search("Annie's and Song");
echo $lib_search->GetSearchQueryString(); // This will echo +ann* +song*
