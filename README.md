# Securing-Azure-Storage-Account-Lab
In the lab, you will learn how to secure your Azure storage against malicious or un-authorized access by configuring firewall rules to limit access to your storage account requests that originate from specified IP addresses or ranges, or from a list of subnets in an Azure Virtual Network (VNet) as the case may be. For more information about configuring firewall rules, see: https://learn.microsoft.com/en-us/azure/storage/common/storage-network-security?toc=/azure/storage/blobs/toc.json

<h2>Platform Used</h2>

- <b>Azure Portal: https://portal.azure.com/</b> 

<h3>OVERVIEW</h3>
<p>An Azure storage account contains all of your Azure Storage data objects: blobs, files, queues, and tables. </p>
<p>The storage account provides a unique namespace for your Azure Storage data that's accessible from anywhere in the world over HTTP or HTTPS. 
<li>https://store-account-name.blob.core.windows.net/ #For blob sub service
<li>https://store-account-name.file.core.windows.net/ #For file sub service
<li>https://store-account-name.table.core.windows.net/ #For Table sub service
<li>https://store-account-name.queue.core.windows.net/ #For Queue sub service
</p>
<p align="center">
<br />
<h2>Project-lab walk-through:</h2>
<h3>Let’s get started…</h3>
  <br>
<li>Go to Azure portal: https://portal.azure.com/
<li>Locate your storage account
<li>On the left blade, locate ‘Networking’
<p>Notice the default setting is set to 'Allow from all networks'?
 <br>
 <br>
  
![image](https://github.com/user-attachments/assets/c3b3059b-6aef-4553-83ed-a874c266510f)
<br />
<br />
Next, we select the option 'Enabled from selected virtual networks and IP addresses'
<br />
<br />
![image](https://github.com/user-attachments/assets/faa0afbb-7bdc-4cfd-9021-332ed72bfc97)

![image](https://github.com/user-attachments/assets/032126ff-c11d-47b6-8f98-82686dd340d2)
<br />
<br />
Select the Virtual network, followed by subnet to grant access to the storage account and click on 'Add'
<br />
<br />
![image](https://github.com/user-attachments/assets/1f542372-48a8-4ccc-a3d0-7ca787741ba8)
<br />
<br />
At this point, you can duplicate your tab as we need to add service endpoint for 'Microsoft.Storage' for the subnet
<br />
<br />
![image](https://github.com/user-attachments/assets/1387570a-15a6-462c-bb40-9a0773ab1722)
<br />
<br />
Hint: For the whitelisting of IP address/range, you can only whitelist a public IP. 
<p>Hence, if your organization make use of  both Azure VMs and on-premises machine as well, you can the proceed to whitelist the public IP address of the user you wish you grant access to the storage in the space dedicated:
<br />
<br />
  
 ![image](https://github.com/user-attachments/assets/150001ff-8ea3-44a5-a1f8-7301ad6fe628) 

![image](https://github.com/user-attachments/assets/344e8a9d-720e-4d81-aeed-76102908f84f)

<br />
At this stage, you can save your changes.
<br />
<br />
The process you have just configured would ensure only virtual machines connected to the "Default" subnet & a physical machine with the IP address specified would be able to access the storage account. Every other requests originating from other sources are blocked!
<br />
<br />
THANK YOU FOR FOLLOWING THROUGH!!!!
