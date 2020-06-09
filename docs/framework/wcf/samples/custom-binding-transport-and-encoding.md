---
title: Trasporto dell'associazione personalizzata e codifica
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 6c0b353d-79ee-4e61-b348-be49ad0e9a16
ms.openlocfilehash: 3b3a0f1b52afce495ca41a426ebc9e57314d8254
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84592528"
---
# <a name="custom-binding-transport-and-encoding"></a>Trasporto dell'associazione personalizzata e codifica
Un'associazione personalizzata viene definita da un elenco ordinato di elementi di associazione discreti. Questo esempio illustra come configurare un'associazione personalizzata con vari elementi di codifica di trasporto e messaggio.  
  
> [!NOTE]
> La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.  
  
 Questo esempio è basato sull' [host indipendente](self-host.md)ed è stato modificato per configurare tre endpoint per supportare i trasporti HTTP, TCP e NamedPipe con binding personalizzati. La configurazione del client viene modificata in modo simile e il codice del client modificato per comunicare con ognuno dei tre endpoint.  
  
 L'esempio illustra come configurare un'associazione personalizzata che supporta una particolare codifica di trasporto e messaggio. Ciò viene effettuato configurando un trasporto e un messaggio che codificano per l'elemento `binding`. L'ordinamento degli elementi di associazione è importante per la definizione di un'associazione personalizzata, perché ogni rappresenta un livello nello stack dei canali (vedere [binding personalizzati](../extending/custom-bindings.md)). Questo esempio configura tre associazioni personalizzate: un trasporto HTTP con codifica di testo, un trasporto TCP con codifica di testo e un trasporto di NamedPipe con codifica binaria.  
  
 La configurazione del servizio definisce l'associazione personalizzata nel modo seguente:  
  
```xml  
<bindings>  
    <customBinding>  
        <binding name="HttpBinding" >  
            <textMessageEncoding
                messageVersion="Soap12Addressing10"/>  
            <httpTransport />  
        </binding>  
        <binding name="TcpBinding" >  
            <textMessageEncoding />  
            <tcpTransport />  
        </binding>  
        <binding name="NamedPipeBinding" >  
            <binaryMessageEncoding />  
            <namedPipeTransport />  
        </binding>  
    </customBinding>  
</bindings>  
```  
  
 Quando si esegue l'esempio, le richieste e le risposte dell'operazione vengono visualizzate nella finestra della console client e del servizio. Il client comunica con ognuno dei tre endpoint, accedendo prima a HTTP, quindi a TCP e finalmente a NamedPipe. Premere INVIO in tutte le finestre della console per arrestare il servizio e il client.  
  
 L'associazione `namedPipeTransport` non supporta operazioni da computer a computer. Viene utilizzata solo per la comunicazione sullo stesso computer. Pertanto, quando si esegue l'esempio in un scenario a più computer, impostare come commento le righe seguenti nel file contenente il codice client:  
  
```csharp  
CalculatorClient client = new CalculatorClient("default");  
Console.WriteLine("Communicate with named pipe endpoint.");  
// Call operations.  
DoCalculations(client);  
//Closing the client gracefully closes the connection and cleans up resources  
client.Close();  
```  
  
```vb  
Dim client As New CalculatorClient("default")  
Console.WriteLine("Communicate with named pipe endpoint.")  
' call operations  
DoCalculations(client)  
'Closing the client gracefully closes the connection and cleans up resources  
client.Close()  
```  
  
> [!NOTE]
> Se si usa Svcutil.exe per rigenerare la configurazione di questo esempio, assicurarsi di modificare il nome dell'endpoint nella configurazione client in modo che corrisponda al codice client.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio  
  
1. Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Per compilare l'edizione C#, C++ o Visual Basic .NET della soluzione, seguire le istruzioni in [compilazione degli esempi di Windows Communication Foundation](building-the-samples.md).  
  
3. Per eseguire l'esempio in una configurazione con un solo computer o tra computer diversi, seguire le istruzioni in [esecuzione degli esempi di Windows Communication Foundation](running-the-samples.md).  
  
> [!IMPORTANT]
> È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) ed [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Custom\Transport`  
