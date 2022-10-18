<h1>Implementing a distributed Search with Independent Indexers</h1>


<h2>Description</h2>
This project implements a simple distributed search environment on a single search head connected to independent indexers in a non clustered archtecture.Search peers are manually added to the search head in a distributed non clustered environment.When the search head participates in an indexer cluster,search heads are automatically added.Search heads can also be quarantined to isolate peer nodes from participating in a search as demostrated in this project.Quarantining a peer node  also helps to perform maintenance on the peer node without affecting searches.This project comprises of 3 independent indexers, 1 forwarder and 1 Search Head ruuning in AWS Cloud.


<br />


<h2>Lab Environment Setup</h2>

- <b>5 t2micro EC2 Intances running in AWS</b> 
- <b>Windows 10 work station (21H2)</b>
- <b>MobaXterm SSH Client</b>
<h2>Intances Set-up </h2>

- <b>Indexer1 - idx1</b> 
- <b>Indexer2 - idx2</b>
- <b>Indexer3 - idx3</b>
- <b>Forwarder - fw1</b>
- <b>Search Head - sh1</b>
<h2>Program walk-through:</h2>



<br />
Install Splunk in 5 instances running in AWS with appropriate labels:  <br/>
<img src="https://user-images.githubusercontent.com/112047285/196322087-524b160c-4140-4919-a673-15035c326833.png" height="80%" width="80%"/>
<br />
<br />
Add the indexers to the Search Head: <br/>
<img src="https://user-images.githubusercontent.com/112047285/196322929-c7e07180-99e4-4648-8623-e083046d49f6.png" height="80%" width="80%"/>
<br />
<br />
Enable receiving in all indexers:  <br/>
<img src="https://user-images.githubusercontent.com/112047285/196323838-a1417293-f4ec-4811-850e-be175ce7c8ea.png" height="80%" width="80%"/>
<br />
<br />
Create an index with the same name in all the indexers:  <br/>
<img src="https://user-images.githubusercontent.com/112047285/196324321-190b3032-5d04-467a-bbb0-04c8b35067ab.png" height="80%" width="80%"/>
                                                             
<br />
<br />
Enable distributed search on the search head:  <br/>
<img src="https://user-images.githubusercontent.com/112047285/195971158-d01a4c98-8f84-49d6-a1e0-82c0cd5f2546.png" height="80%" width="80%"/>
<br />
<br />
Configure monitoring and forwarding on the forwarder:  <br/>
<img src="https://user-images.githubusercontent.com/112047285/196326183-1e7d2feb-0c08-48f7-8b3f-ea260a2e8f6e.png" height="80%" width="80%"/>
</p>
Verify forwarder connections to the indexers:  <br/>
<img src="https://user-images.githubusercontent.com/112047285/196326649-d5bb0914-e0b5-4371-bb5c-17e52143fc8a.png" height="80%" width="80%"/>
</p>
Verify all Indexers are participating in a search:  <br/>
<img src="https://user-images.githubusercontent.com/112047285/196326940-6211c8e7-0869-417c-a240-56f534242d3a.png" height="80%" width="80%"/>
</p>
Quarantine an indexer:  <br/>
<img src="https://user-images.githubusercontent.com/112047285/196327284-1e673423-938b-4eef-8c1d-2314936c8f72.png" height="80%" width="80%"/>
</p>
Verify the quarantined indexer is not partiicipating in a search:  <br/>
<img src="https://user-images.githubusercontent.com/112047285/196328122-0476d35f-c583-4e41-ba22-addecb990541.png" height="80%" width="80%"/>
</p>
<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
