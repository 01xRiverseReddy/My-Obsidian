
### Background 

The Gale-Shapely Algorithm is a Nobel winning algorithm that aims to provide a stable match for any pair in pool . This is used in Hinge’s dating algorithm to provide the best possible partner of a person , also used in find the best possible college a student can go to . The alternate name for this algorithm is stable matching problem .

The stable matching problem gives a stable pair to each data points which means that it provides a one to one mapping . 


### Intuition 

Given a set of pair imagined as a group of males and females , we have to find a pair such that each pair is satisfied with their counter-part matching . We can have a one group be the proposers while the other as the receivers . Based on the series of preference we can get maintain a certain set of pairs such that everyone is satisfied . 


### Approach 

- We let the proposers , one group make a set of choices , aka their proposal preference of the females in the order to their liking . We repeat this process to the receivers as well based on who they would prefer . 
- At this point of the algorithm we have two parties who have rated their opposite sex based on their preference . 
- ![[Pasted image 20250213184344.png]]
- Now we initially check for the easiest pairs to match , a pair such that both proposer and receiver would want . If such a pair exists then we can create the first stable match .
- As we keep checking we might not find a perfect match which is perfectly alright , this algorithm aims to find the best possible match rather than the best match .
- We don’t have to find a match perfectly just yet . We can just initially match them for the time-being . 
- Let’s say A prefers B , but B already matched C because we started matching with C earlier . But we soon discover that B’s matching preference has A at a higher rank than C . We then unmatch B with C , match her with A and repeat the matching process for C . 
- This process repeats until we have created a best possible match for both all people in the breeding pool .
- ![[Pasted image 20250213184414.png]]

### Mysogonistic Approach 

This is a variation of the original approach where the pairing is biased . I do not have much idea on this yet but the idea behind this is that it is more favourable to the proposers than to the receiver.  It is termed as proposer optimistic and receiver pessimistic . Here what happens is that based on the preference given and regardless of the perfect choice at hand , the worst possible proposer would receive the best possible receiver . The ugly dude gets the hot chick 


Time Complexity - `O(n^2) `  where n are the participants in the breeding pool . 


Literature : 

