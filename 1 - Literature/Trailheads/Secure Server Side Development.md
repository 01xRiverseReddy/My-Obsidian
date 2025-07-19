#SFDCDev  #unmerged 
- The first unit is pretty important from an interview perspective as the author describes why it is important to consider the sharing factors . He also introduces CRUD checking operations like isCreatable(),isUpdatable, isDeleteable etc . 
- Second unit is about SOQL injection and this is pretty obvious on how to mitigate , we either use string.escapeSingleQuotes or a regex expression to filter out nonsense content . 
- Next unit talks about client side request forgery which is basically attacker making requests on behalf of the user . This can be prevented through a one-line that is mentioned in the trailhead . 
- Server side request forgery is when we the attacker takes advantage invalidated user input and manages to gain access to the company’s internal server . The best way to mitigate this is through allowlisting . 
