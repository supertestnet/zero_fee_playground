# Zero fee playground
A site for trying out zero fee bitcoin transactions

# How to try it
Just click here: https://supertestnet.github.io/zero_fee_playground

# What is it?
This project showcases a recent upgrade to bitcoin in version 28. Before v28, all nodes refused, by default, to relay transactions that paid zero fees, and miners refused to mine them. Also, nodes and miners rejected transactions that *did* pay a fee if it was below a "minimum fee" threshold. The "minimum fee" threshold varied on a node-by-node basis, but it was related to the average fee paid by the transactions in each node's copy of the mempool.

V28 changed the rules. A transaction can now pay zero fees (or a fee below the "minimum fee" threshold) if it is paired with a second transaction that pays *extra* fees. To follow the new rule, the second transaction has to pay enough fees that, when the two transactions are considered together, their "combined feerate" is above the old "minimum fee" threshold. There are also several other conditions they have to follow; for example, the two transactions have to have version number 3, and the "first" one can't spend an unconfirmed utxo. The full rules are outlined in [Bip 431](https://bips.xyz/431) and [Bip 331](https://bips.xyz/331).

If you [visit this link](https://supertestnet.github.io/zero_fee_playground) and follow the steps, you will *create* a pair of transactions that follows the new rules. The first of your two transactions will pay zero fees, but nodes will still relay it (and miners will still mine it) as long as it is paired with the second transaction.
