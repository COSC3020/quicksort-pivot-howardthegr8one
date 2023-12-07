[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-718a45dd9cf7e7f842a935f5ebbe5719a5e09af4491e668f4dbf3b35d5cca122.svg)](https://classroom.github.com/online_ide?assignment_repo_id=13173292&assignment_repo_type=AssignmentRepo)
# Quicksort Pivots

in the lectures I only briefly mentioned strategies for determining a good pivot
for quicksort. The implementation on the slides simply picks the leftmost
element in the part of the array that we consider as a pivot. I also mentioned a
few other ways of picking a good pivot, e.g. randomly.

Median-of-three is also a good way of picking a pivot -- inspect the first,
middle, and last elements of the part of the array under consideration and
choose the median value. Using the probabilities for picking a pivot in a
particular part of the array (in the same way as we did on slide 34), argue
whether this method is more or less (or equally) likely to pick a good pivot
compared to simply choosing the first element. Assume that all permutations are
equally likely, i.e. the input array is ordered randomly.

Your answer must derive probabilities for choosing a good pivot and
quantitatively reason with them.

Add your answer to this markdown file. [This
page](https://docs.github.com/en/get-started/writing-on-github/working-with-advanced-formatting/writing-mathematical-expressions)
might help with the notation for mathematical expressions.

# My Solution:

Knowing that we have good pivot choices in the middle half of a given array we can break our array into 4 sections like so:

$B_1, G_1, G_2, B_2$

Where each section contains 25% of the possible pivot choices, then the 4 sections give us bad pivots on either end, with 
two sections of good pivots in the middle. When taking the median of three any time we have more bad options than good options 
among the three our pivot will end up being bad. Thus any of the following combinations would produce a bad pivot:


$B_1 B_1 G_1$  $B_2 B_2 G_1$ \
$B_1 B_1 G_2$  $B_2 B_2 G_2$ \
$B_1 B_1 B_2$  $B_2 B_2 B_1$ 

All permutations of the above would result in bad pivots. Thus $6*3$ bad pivots, or $18$, but we're still missing two more bad permuations:

$B_1 B_1 B_1$ and $B_2 B_2 B_2$ giving us a total of 20 bad pivots, and we have a total of 64 pivot possibilities (4 * 4 * 4). Therefore to find
the probability of choosing a good pivot when using the median of three method we have $44/64$ chance because of our $64$ possibilities $20$ of them 
are bad. Therefore using this method gives us a probability of $11/16$ or $68.75$%. So using the median of three method gives us a good pivot significantly
more often than the random method or by simply choosing the left-most or right-most index. 



