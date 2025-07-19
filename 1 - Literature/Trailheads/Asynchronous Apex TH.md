
- Asynchronous Process has various forms in apex . Future methods , Batch Apex , Queueable Apex , Scheduled apex . The advantage of using async apex increasing governor limits , increased Heap and CPU time , offloading computational time . 
- Future method are blocks of asynchronous code that can be called from Apex . It can be used to make web call-outs or offload DML operations 
- Batchable apex is a functionality that is used when large number of records need to be processed . When we talk about millions etc. In such scenarios the governor limit is bypassed . 
- Queueable is better option(sometimes ) than future where you can pass non-primitive data types , and you can chain Queueable . 
- Apex scheduler is scheduling batches through code . 
- 