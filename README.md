# Blockchain implementation in Phyton

Based on the "Blockchain A-Z" course (superdatascience.com and udemy.com)
Basic implementation of blockchain prinicples that serve nothing but educational purposes.

## Blockchain
*blockchain.py* creates a simple general-purpose blockchain that runs as a Flask app and allows simple interactions over HTTP requests. It is used as the basis for the other scripts.

## Cryptocurrency
*TIC_node_500x.py* Three scripts representing three nodes of a fictious cryptocurrency ("Terran Imperial Credit" taken from Star Trek shows). To run all nodes locally on one computer you can use e.g. Spyder which allows opening multiple ipython kernels:
![opnening multiple kernels](https://github.com/felixsc1/blockchain/blob/master/spyder_running_multiple_nodes.PNG "opening multiple kernels") The nodes can then be accessed at http://127.0.0.1:5001/ , http://127.0.0.1:5002/, and http://127.0.0.1:5003/.

To interact with the nodes, I recommend Postman, which has a simple GUI:
*/connect_node* is a POST request to a node that expects the addresses of the other nodes as  input in json format, see example.
![connecting nodes](https://github.com/felixsc1/blockchain/blob/master/postman_connecting_nodes.PNG "connecting nodes")

*/get_chain* get request that creates the genesis block if the blockchain does not exist yet and returns the current chain.

*/mine_block* is a get request that will mine a new block
![mining a block](https://github.com/felixsc1/blockchain/blob/master/postman_mining_a_block.PNG "mining a block")

*/replace_chain* get request that adresses the consensus problem. Queries connected nodes and replaces the current chain with the longest chain in the entire network. Must be executed on each node manually, whenever transactions are made and blocks are mined.

*/add_transaction* post request that will add transaction to the next block mined on this node. Transactions consist of Sender, Receiver, and Amount in json format (see transaction.json for example).
![adding a transaction](https://github.com/felixsc1/blockchain/blob/master/postman_add_transacton.PNG "adding a transaction")
