---
title: Richiesta-risposta non tipizzata
ms.date: 03/30/2017
ms.assetid: 0bf0f9d9-7caf-4d3d-8c9e-2d468cca16a5
ms.openlocfilehash: 46047d1671fadb18052991451910b9056015edd2
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84591100"
---
# <a name="untyped-requestreply"></a>Richiesta/risposta non tipizzata
In questo esempio viene illustrato come definire i contratti dell'operazione che utilizzano la classe Message.  
  
> [!NOTE]
> La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.  
  
 Questo esempio è basato sul [Introduzione](getting-started-sample.md). Il contratto di servizio definisce un'operazione che accetta un tipo di messaggio come argomento e restituisce un messaggio. L'operazione raccoglie tutti i dati necessari per calcolare la somma dal corpo del messaggio e quindi invia la somma come corpo nel messaggio restituito.  
  
```csharp
[OperationContract(Action = CalculatorService.RequestAction, ReplyAction = CalculatorService.ReplyAction)]  
Message ComputeSum(Message request);  
```  
  
 Nel servizio, l'operazione recupera la matrice di numeri Integer passata nel messaggio di input e quindi calcola la somma. Per inviare un messaggio di risposta, nell'esempio viene creato un nuovo messaggio con la versione del messaggio e l'azione appropriata e viene aggiunta la somma calcolata come corpo. Nel codice di esempio seguente viene illustrata questa operazione.  
  
```csharp
public Message ComputeSum(Message request)  
{  
    //The body of the message contains a list of numbers which will be
    //read as a int[] using GetBody<T>  
    int result = 0;  
  
    int[] inputs = request.GetBody<int[]>();  
    foreach (int i in inputs)  
    {  
        result += i;  
    }  
  
    Message response = Message.CreateMessage(request.Version,
                                      ReplyAction, result);  
    return response;  
}  
```  
  
 Il client utilizza il codice generato dallo [strumento ServiceModel Metadata Utility Tool (Svcutil. exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) per creare un proxy per il servizio remoto. Per inviare un messaggio di richiesta, il client deve avere la versione del messaggio, che dipende dal canale sottostante. Di conseguenza, crea una nuova classe <xref:System.ServiceModel.OperationContextScope> con ambito impostato sul canale del proxy creato, che crea una classe <xref:System.ServiceModel.OperationContext> con la versione del messaggio corretta inserita nella relativa proprietà `OutgoingMessageHeaders.MessageVersion`. Il client passa una matrice di input come corpo al messaggio di richiesta e quindi richiama `ComputeSum` sul proxy. Il client recupera quindi la somma degli input passati accedendo al metodo `GetBody<T>` sul messaggio di risposta. Nel codice di esempio seguente viene illustrata questa operazione.  
  
```csharp
using (new OperationContextScope(client.InnerChannel))  
{  
    // Call the Sum service operation.  
    int[] values = { 1, 2, 3, 4, 5 };  
    Message request = Message.CreateMessage(  
        OperationContext.Current.OutgoingMessageHeaders.MessageVersion,
        RequestAction, values);  
    Message reply = client.ComputeSum(request);  
    int response = reply.GetBody<int>();  
  
    Console.WriteLine("Sum of numbers passed (1,2,3,4,5) = {0}",
                                                       response);  
}  
```  
  
 Questo è un esempio ospitato sul Web, pertanto deve essere eseguito solo il file eseguibile del client. Di seguito è riportato l'output di esempio sul client.  
  
```console  
Prompt>Client.exe  
Sum of numbers passed (1,2,3,4,5) = 15  
  
Press <ENTER> to terminate client.  
```  
  
 Questo è un esempio ospitato sul Web, pertanto è necessario esaminare il collegamento fornito nel passaggio 3 per comprendere come compilare ed eseguire l'esempio.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio  
  
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
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Message\Untyped`  
