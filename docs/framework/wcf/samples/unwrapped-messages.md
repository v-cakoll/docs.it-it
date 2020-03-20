---
title: Messaggi non incapsulati
ms.date: 03/30/2017
ms.assetid: 019657bd-1f9b-4315-ad74-eaa4e7551ff6
ms.openlocfilehash: 81592910d8530cea2df5ec1fd8a8b1145350ef78
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79143733"
---
# <a name="unwrapped-messages"></a>Messaggi non incapsulati
In questo esempio vengono illustrati i messaggi non incapsulati. Per impostazione predefinita, il corpo del messaggio è formattato in modo tale che i parametri di un'operazione del servizio sono incapsulati. Nell'esempio seguente viene illustrato un messaggio di richiesta `Add` al servizio `ICalculator` in modalità incapsulata.  
  
```xml  
<s:Envelope
    xmlns:s="http://www.w3.org/2003/05/soap-envelope"  
    xmlns:a="http://schemas.xmlsoap.org/ws/2005/08/addressing">  
    <s:Header>  
        …  
    </s:Header>  
    <s:Body>  
      <Add xmlns="http://Microsoft.ServiceModel.Samples">  
        <n1>100</n1>  
        <n2>15.99</n2>  
      </Add>  
    </s:Body>  
</s:Envelope>  
```  
  
 L'elemento `<Add>` nel corpo del messaggio incapsula i parametri `n1` e `n2`. Diversamente, nell'esempio seguente viene illustrato il messaggio equivalente nella modalità non incapsulata.  
  
```xml  
<s:Envelope
    xmlns:s="http://www.w3.org/2003/05/soap-envelope"
    xmlns:a="http://schemas.xmlsoap.org/ws/2005/08/addressing">  
    <s:Header>  
        ….  
    </s:Header>  
    <s:Body>  
      <n1 xmlns="http://Microsoft.ServiceModel.Samples">100</n1>  
      <n2 xmlns="http://Microsoft.ServiceModel.Samples">15.99</n2>  
    </s:Body>  
  </s:Envelope>  
</MessageLogTraceRecord>  
```  
  
 Nel messaggio non incapsulato i parametri `n1` e `n2` non sono incapsulati in un elemento contenitore, bensì sono elementi figlio diretti dell'elemento del corpo SOAP.  
  
> [!NOTE]
> La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.  
  
 In questo esempio viene creato un messaggio non incapsulato applicando la classe <xref:System.ServiceModel.MessageContractAttribute> al tipo di parametro dell'operazione del servizio e al tipo di valore restituito, come illustrato nel codice di esempio seguente.  
  
```csharp
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public interface ICalculator  
{  
    [OperationContract]  
    ResponseMessage Add(RequestMessage request);  
    [OperationContract]  
    ResponseMessage Subtract(RequestMessage request);  
    [OperationContract]  
    ResponseMessage Multiply(RequestMessage request);  
    [OperationContract]  
    ResponseMessage Divide(RequestMessage request);  
}  
  
//setting IsWrapped to false means the n1 and n2  
//members will be direct children of the soap body element  
[MessageContract(IsWrapped = false)]  
public class RequestMessage  
{  
    [MessageBodyMember]  
    private double n1;  
    [MessageBodyMember]  
    private double n2;  
    //…  
}  
  
//setting IsWrapped to false means the result  
//member will be a direct child of the soap body element  
[MessageContract(IsWrapped = false)]  
public class ResponseMessage  
{  
    [MessageBodyMember]  
    private double result;  
    //…  
}  
```  
  
 Per poter visualizzare i messaggi inviati e ricevuti, in questo esempio viene utilizzata la traccia. Inoltre, <xref:System.ServiceModel.WSHttpBinding> è stato configurato senza la sicurezza, per ridurre il numero di messaggi registrati.  
  
 È possibile visualizzare il registro di traccia risultante (c:,logs,Message.log) utilizzando lo strumento Visualizzatore di tracce dei servizi [(SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md). Per visualizzare il contenuto dei messaggi, selezionare **Messaggi** sia nel riquadro sinistro che in quello destro dello strumento Visualizzatore di traccia dei servizi. I registri di traccia in questo esempio sono configurati in modo da essere generati nella cartella C:\LOGS. Creare questa cartella prima di eseguire l'esempio e assegnare all'account Servizio di rete le autorizzazioni di scrittura per questa directory.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio  
  
1. Assicurarsi di aver eseguito la procedura di [installazione una tantera per Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Creare una directory C:\LOGS per la registrazione dei messaggi. Assegnare all'account Servizio di rete le autorizzazioni di scrittura per questa directory.  
  
3. Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
4. Per eseguire l'esempio in una configurazione su un singolo o più computer, seguire le istruzioni in Esecuzione di [Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
> È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) Esempi per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti gli esempi e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (WCF). Questo esempio si trova nella directory seguente.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Message\Unwrapped`  
