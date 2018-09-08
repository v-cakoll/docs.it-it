---
title: Trasporto dell'associazione personalizzata e codifica
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 6c0b353d-79ee-4e61-b348-be49ad0e9a16
ms.openlocfilehash: ee15fd37390f8bf4ca3bc287f9a3dbd5f8ebd935
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2018
ms.locfileid: "44139748"
---
# <a name="custom-binding-transport-and-encoding"></a>Trasporto dell'associazione personalizzata e codifica
Un'associazione personalizzata viene definita da un elenco ordinato di elementi di associazione discreti. Questo esempio illustra come configurare un'associazione personalizzata con vari elementi di codifica di trasporto e messaggio.  
  
> [!NOTE]
>  La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.  
  
 In questo esempio si basa sul [self-hosting](../../../../docs/framework/wcf/samples/self-host.md)ed è stata modificata per configurare tre endpoint in modo da supportare trasporti HTTP, TCP e NamedPipe con associazioni personalizzate. La configurazione del client viene modificata in modo simile e il codice del client modificato per comunicare con ognuno dei tre endpoint.  
  
 L'esempio illustra come configurare un'associazione personalizzata che supporta una particolare codifica di trasporto e messaggio. Ciò viene effettuato configurando un trasporto e un messaggio che codificano per l'elemento `binding`. L'ordinamento degli elementi di associazione è importante nel definire un'associazione personalizzata, perché ognuna rappresenta un livello nello stack dei canali (vedere [associazioni personalizzate](../../../../docs/framework/wcf/extending/custom-bindings.md)). Questo esempio configura tre associazioni personalizzate: un trasporto HTTP con codifica di testo, un trasporto TCP con codifica di testo e un trasporto di NamedPipe con codifica binaria.  
  
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
  
 L'associazione `namedPipeTransport`  non supporta operazioni da computer a computer. Viene utilizzata solo per la comunicazione sullo stesso computer. Pertanto, quando si esegue l'esempio in un scenario a più computer, impostare come commento le righe seguenti nel file contenente il codice client:  
  
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
>  Se si usa Svcutil.exe per rigenerare la configurazione di questo esempio, assicurarsi di modificare il nome dell'endpoint nella configurazione client in modo che corrisponda al codice client.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio  
  
1.  Assicurarsi di avere eseguito il [monouso procedura di installazione per gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Per compilare l'edizione c#, C++ o Visual Basic .NET della soluzione, seguire le istruzioni in [Building Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Per eseguire l'esempio in una configurazione singola o tra computer, seguire le istruzioni in [esegue gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Custom\Transport`  
  
## <a name="see-also"></a>Vedere anche
