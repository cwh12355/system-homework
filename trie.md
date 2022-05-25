###trie is auto-update system,the trie has three option(create,update,delete)
##### update
* when we update a trie node,its ancestors all the way up to the root must be updated,
##### delete
* we can set a filter in front of the trie cache,trie cache->filter layer->API servers;
* unwanted suggestions are removed physically from the database asynchronically
##### scale the storage
* we can split queries up to 26 alphabetic charactre,but we realiza that there are a lot more words that start with the letter 'c' than 'x',so this creates uneven distribution.to mitigate the data imbalance problem,we analyse histories,data disbution pattern and apply smarter sharding logic ,the shard map manager maintains a lookup database for identifying where rows should be stored