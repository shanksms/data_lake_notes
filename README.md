# data_lake_notes
## references
TBD

## Datalake on AWS

### Right tools for the right job
If you have streaming data (coming from IOT device), then following architecture might be suitable
![](images/auto_gen_data.PNG)
You may also have operational data, such inventory and sales, expense reports, and other inputs. Those likely come in batches and are usually consumed by people who wants to visualize graphs and have access to statistics. This data may be suitable for being ingested with API Gateway, stored in S3, catalogs with Glue, transported to Amazon Elasticsearch Service and visualized with Kibana.
![](images/operational_data.PNG)
In addition to that, you may want to have human-generated data, such as social media feeds, contact forms, call center audio, e-mails, etc. For these, you may think about access patterns needed by Data Analysis Services
 You could ingest that data with S3, SFTP or Upflow, store it in S3, catalog with Glue and use a service like Amazon Comprehend, which is a natural language processing service that uses machine learning to find insights in texts, such as sentimental analysis
![](images/human_gen_data.PNG) 
### ETL versus ELT
Let's say you are working in a company that the interplanetary expeditions where you have devices on other planets sending their findings. This type of data is absolutely rare. And no matter what you were going to do with that data, you want to start the data in it's raw format to avoid losing anything. In this case, you would like to store immediately without any kind of pre processing. In this case, you would like to perform the classic ELT. Extract and Load and then, in the future, do some eventual transformation. Think that if you transform before loading, you may risk losing something
<br>
imagine you are working with the medical system that needs to meet compliance standards, where you cannot store PII. Or personally Identifiable Information. If you receive MRI or X ray images from medical hardware. You can remove the PII during the data ingestion before story into a storage service like Amazon S3. Once data lands in S3, you can run another processing layer that will convert the images into a friendly file format that is needed for the data, statistics, components or any other processing layer.
## Datalake on AWS - ends


