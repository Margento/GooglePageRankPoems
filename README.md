# GooglePageRankPoems
PageRank for a multiplex of poems obtained as Google search results

Google & Margento War in Ukraine

PageRank is THE Google algorithm. The higher up a website in the relevant google search results, the greater its PageRank score among the other search results. It is just that Google has tweaked their search algorithm in so many ways over time, not all of them really transparent it seems. We have been assured for instance that Hummingbird would only work better with its addition RankBrain, even if they are both rather opaque… whereas PageRank has remained the only algorithm(ic component) genuinely open-source-clear and available to everybody. But what is in the meantime (if any) the relevance of PageRank to the way Google works?
In this experiment I ran a google search for ukraine war poem [no quotes], collected the first 36 results (off the first four SERPs) and arranged them as poems [mostly of 2 lines, 3 tops], and then wrote a 37th distich myself which I also tossed in the mix. Then represented the 37 poems as 2-layer multiplex, with a tf-idf layer and a ‘vector prosody’ one. The latter involved using the FastText word vectors to compute vectors for all lines of verse in all poems, and then average them per poem to get each poem’s ‘meter.’ This [computational/vector] poetic meter was used in creating the second layer of the multiplex.

Then I computed PageRank scores for all nodes in the multiplex, and, as expected, my own poem ranked the lowest. Interestingly though, the highest in PageRank turned out to be a poem on the fourth page of google search results, followed suite by the 3rd and the very 1st result of the entire search. This output relevantly showed that while my way of ranking converged once in a while with Google’s, it also produced wildly disparate (when not fully opposite) positions for some of the poems. 

My #GraphPoem in this particular case is the GitLit repo in its entirety.

My data poem is the folder of poems in their google search result order combined with the same folder in the order outputted by my PageRank implementation. 

And, last but not least, my page poem has been obtained by (doubly) sampling the folder as follows. From all poems I have selected the line with the greatest cosine similarity to the meter of the (added) 37th poem, and arranged them in the descending order of the PageRank score of the poems they were selected from. Each of these lines was then continued with the second-most-similar-to-poem-37 line in each poem, only now in the order of their google search ranking (that is, their order in my data—-war_in_ukraine—-folder).
