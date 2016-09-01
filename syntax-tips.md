**1. find_each**

instead of *Model.all.each do |x| ..*, use directly *Model.find_each*
better because run in batches and not all at the same time

**2. casecmp('xxx')**
Case insensitive version of String
*Ex*
"abcdef".casecmp("abcde")     #=> 1
"aBcDeF".casecmp("abcdef")    #=> 0
"abcdef".casecmp("abcdefg")   #=> -1
"abcdef".casecmp("ABCDEF")    #=> 0


**3. **
