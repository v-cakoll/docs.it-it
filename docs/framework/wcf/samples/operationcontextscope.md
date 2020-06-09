---
title: OperationContextScope
ms.date: 03/30/2017
ms.assetid: 11c11108-8eb4-4d49-95a0-83285a812262
ms.openlocfilehash: 0b2b4d9b22f654fa433c7473160444b41a5adfa4
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84575153"
---
# <a name="operationcontextscope"></a>OperationContextScope
Nell'esempio OperationContextScope viene illustrato come inviare informazioni aggiuntive su una chiamata Windows Communication Foundation (WCF) utilizzando le intestazioni. In questo esempio sia il server che il client sono applicazioni console.  
  
> [!NOTE]
> La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.  
  
 Nell'esempio viene illustrato in che modo un client può inviare informazioni aggiuntive come un <xref:System.ServiceModel.Channels.MessageHeader> utilizzando <xref:System.ServiceModel.OperationContextScope>. Un oggetto <xref:System.ServiceModel.OperationContextScope> viene creato definendone l'ambito su un canale. Le intestazioni che devono essere tradotte nel servizio remoto possono essere aggiunte alla raccolta <xref:System.ServiceModel.OperationContext.OutgoingMessageHeaders%2A>. Le intestazioni aggiunte alla raccolta possono essere recuperate nel servizio accedendo alla proprietà <xref:System.ServiceModel.OperationContext.IncomingMessageHeaders%2A>. Le chiamate a questa proprietà vengono effettuate sui più canali e quindi le intestazioni aggiunte al client possono essere applicate solo al canale utilizzato per creare <xref:System.ServiceModel.OperationContextScope>.  
  
## <a name="messageheaderreader"></a>MessageHeaderReader  
 Si tratta del servizio di esempio che riceve un messaggio dal client e tenta di cercare l'intestazione nella raccolta <xref:System.ServiceModel.OperationContext.IncomingMessageHeaders%2A>. Il client passa il GUID inviato nell'intestazione, quindi il servizio recupera l'intestazione personalizzata e, se presente, lo confronta con il GUID passato come argomento dal client.  
  
```csharp
public bool RetrieveHeader(string guid)  
{  
     MessageHeaders messageHeaderCollection =
             OperationContext.Current.IncomingMessageHeaders;  
     String guidHeader = null;  
  
     Console.WriteLine("Trying to check if IncomingMessageHeader " +  
               " collection contains header with value {0}", guid);  
     if (messageHeaderCollection.FindHeader(  
                       CustomHeader.HeaderName,
                       CustomHeader.HeaderNamespace) != -1)  
     {  
          guidHeader = messageHeaderCollection.GetHeader<String>(  
           CustomHeader.HeaderName, CustomHeader.HeaderNamespace);  
     }  
     else  
     {  
          Console.WriteLine("No header was found");  
     }  
     if (guidHeader != null)  
     {  
          Console.WriteLine("Found header with value {0}. "+
         "Does it match with GUID sent as parameter: {1}",
          guidHeader, guidHeader.Equals(guid));  
      }  
  
      Console.WriteLine();  
      //Return true if header is present and equals the guid sent by  
      // client as argument  
      return (guidHeader != null && guidHeader.Equals(guid));  
}  
```  
  
## <a name="messageheaderclient"></a>MessageHeaderClient  
 Si tratta dell'implementazione client che utilizza il proxy generato dallo [strumento ServiceModel Metadata Utility Tool (Svcutil. exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) per comunicare con il servizio remoto. Crea innanzitutto due oggetti proxy di `MessageHeaderReaderClient`.  
  
```csharp
//Create two clients to the remote service.  
MessageHeaderReaderClient client1 = new MessageHeaderReaderClient();  
MessageHeaderReaderClient client2 = new MessageHeaderReaderClient();  
```  
  
 Il client crea quindi un OperationContextScope e ne definisce l'ambito su `client1`. Aggiunge un <xref:System.ServiceModel.Channels.MessageHeader> a <xref:System.ServiceModel.OperationContext.OutgoingMessageHeaders%2A> ed esegue una chiamata su entrambi i client. Garantisce che l'intestazione venga inviata solo in `client1` e non in `client2` controllando il valore restituito dalla `RetrieveHeader` chiamata.  
  
```csharp
using (new OperationContextScope(client1.InnerChannel))  
{  
    //Create a new GUID that is sent as the header.  
    String guid = Guid.NewGuid().ToString();  
  
    //Create a MessageHeader for the GUID we just created.  
    MessageHeader customHeader = MessageHeader.CreateHeader(CustomHeader.HeaderName, CustomHeader.HeaderNamespace, guid);  
  
    //Add the header to the OutgoingMessageHeader collection.  
    OperationContext.Current.OutgoingMessageHeaders.Add(customHeader);  
  
    //Now call RetrieveHeader on both the proxies. Since the OperationContextScope is tied to
    //client1's InnerChannel, the header should only be added to calls made on that client.  
    //Calls made on client2 should not be sending the header across even though the call  
    //is made in the same OperationContextScope.  
    Console.WriteLine("Using client1 to send message");  
    Console.WriteLine("Did server retrieve the header? : Actual: {0}, Expected: True", client1.RetrieveHeader(guid));  
  
    Console.WriteLine();  
    Console.WriteLine("Using client2 to send message");  
    Console.WriteLine("Did server retrieve the header? : Actual: {0}, Expected: False", client2.RetrieveHeader(guid));  
}  
```  
  
 Questo esempio è indipendente. L'esecuzione dell'esempio fornisce l'output di esempio seguente:  
  
```console  
Prompt> Service.exe  
The service is ready.  
Press <ENTER> to terminate service.  
  
Trying to check if IncomingMessageHeader collection contains header with value 2239da67-546f-42d4-89dc-8eb3c06215d8  
Found header with value 2239da67-546f-42d4-89dc-8eb3c06215d8. Does it match with GUID sent as parameter: True  
  
Trying to check if IncomingMessageHeader collection contains header with value 2239da67-546f-42d4-89dc-8eb3c06215d8  
No header was found  
  
Prompt>Client.exe  
Using client1 to send message  
Did server retrieve the header? : Actual: True, Expected: True  
  
Using client2 to send message  
Did server retrieve the header? : Actual: False, Expected: False  
  
Press <ENTER> to terminate client.  
```  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio  
  
1. Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](building-the-samples.md).  
  
3. Per eseguire l'esempio in una configurazione con un solo computer o tra computer diversi, seguire le istruzioni in [esecuzione degli esempi di Windows Communication Foundation](running-the-samples.md).  
  
> [!IMPORTANT]
> È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) ed [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\OperationContextScope`  
