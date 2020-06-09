---
title: Unidirezionale
ms.date: 03/30/2017
ms.assetid: 74e3e03d-cd15-4191-a6a5-1efa2dcb9e73
ms.openlocfilehash: 07fc4ecf981acbad577758c943aa22405f528a52
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84575252"
---
# <a name="one-way"></a>Unidirezionale
Questo esempio illustra un contatto di servizio con operazioni di servizio unidirezionali. Il client non aspetta il completamento delle operazioni del servizio per terminare le operazioni, come accade invece con le operazioni di servizio bidirezionali. Questo esempio è basato sul [Introduzione](getting-started-sample.md) e usa l' `wsHttpBinding` associazione. Il servizio, in questo esempio, è un'applicazione console indipendente che consente di osservare il servizio che riceve ed elabora messaggi in coda. Il client è anche un'applicazione console.  
  
> [!NOTE]
> La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.  
  
 Per creare un contratto di servizio unidirezionale, definire il contratto del servizio, applicare la classe <xref:System.ServiceModel.OperationContractAttribute> a ogni operazione e impostare la proprietà <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A> su `true`, come illustrato nel codice di esempio seguente:  
  
```csharp
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public interface IOneWayCalculator  
{  
    [OperationContract(IsOneWay=true)]  
    void Add(double n1, double n2);  
    [OperationContract(IsOneWay = true)]  
    void Subtract(double n1, double n2);  
    [OperationContract(IsOneWay = true)]  
    void Multiply(double n1, double n2);  
    [OperationContract(IsOneWay = true)]  
    void Divide(double n1, double n2);  
}  
```  
  
 Per dimostrare che il client non aspetta il completamento delle operazioni del servizio, il codice del servizio, in questo esempio, implementa un ritardo di cinque secondi, come mostra il codice di esempio seguente:  
  
```csharp
// This service class implements the service contract.  
// This code writes output to the console window.  
 [ServiceBehavior(ConcurrencyMode = ConcurrencyMode.Multiple,  
    InstanceContextMode = InstanceContextMode.PerCall)]  
public class CalculatorService : IOneWayCalculator  
{  
    public void Add(double n1, double n2)  
    {  
        Console.WriteLine("Received Add({0},{1}) - sleeping", n1, n2);  
        System.Threading.Thread.Sleep(1000 * 5);  
        double result = n1 + n2;  
        Console.WriteLine("Processing Add({0},{1}) - result: {2}", n1, n2, result);  
    }  
    ...  
}  
```  
  
 Quando il client chiama il servizio, la chiamata viene restituita senza aspettare il completamento dell'operazione del servizio.  
  
 Quando si esegue l'esempio, le attività del client e del servizio vengono visualizzate nelle finestre della console del servizio e del client. È possibile osservare il servizio che riceve i messaggi dal client. Premere INVIO in tutte le finestre della console per arrestare il servizio e il client.  
  
 Il client termina prima del servizio, dimostrando che un client non aspetta il completamento delle operazioni unidirezionali del servizio. L'output del client è il seguente:  
  
```console  
Add(100,15.99)  
Subtract(145,76.54)  
Multiply(9,81.25)  
Divide(22,7)  
  
Press <ENTER> to terminate client.  
```  
  
 Viene mostrato l'output del servizio seguente:  
  
```console  
The service is ready.  
Press <ENTER> to terminate service.  
  
Received Add(100,15.99) - sleeping  
Received Subtract(145,76.54) - sleeping  
Received Multiply(9,81.25) - sleeping  
Received Divide(22,7) - sleeping  
Processing Add(100,15.99) - result: 115.99  
Processing Subtract(145,76.54) - result: 68.46  
Processing Multiply(9,81.25) - result: 731.25  
Processing Divide(22,7) - result: 3.14285714285714  
```  
  
> [!NOTE]
> HTTP è, per definizione, un protocollo di richiesta/risposta; quando viene effettuata una richiesta, viene restituita una risposta. Ciò è vero anche per un'operazione del servizio unidirezionale esposta su HTTP. Quando l'operazione viene chiamata, il servizio restituisce un codice di stato HTTP 202 prima che l'operazione del servizio abbia completato l'esecuzione. Questo codice di stato significa che la richiesta è stata accettata, ma l'elaborazione non è stata ancora completata. Il client che ha chiamato l'operazione si blocca fino a che non riceve la risposta 202 dal servizio. Questo può provocare alcuni comportamenti imprevisti quando più messaggi unidirezionali vengono inviati utilizzando un'associazione configurata per utilizzare sessioni. L'associazione `wsHttpBinding` utilizzata in questo esempio è configurata per utilizzare sessioni per impostazione predefinita e stabilire un contesto di sicurezza. Per impostazione predefinita, in una sessione, è garantito l'arrivo dei messaggi nell'ordine in cui sono stati inviati. Perciò, quando viene inviato il secondo messaggio di una sessione, non viene elaborato fino a che non è stato elaborato il primo messaggio. Ne risulta che il client non riceve la risposta 202 per un messaggio sino al completamento dell'elaborazione del messaggio precedente. Il client sembra pertanto bloccarsi su ogni chiamata successiva dell'operazione. Per evitare questo comportamento questo esempio configura il runtime in modo da inviare contemporaneamente i messaggi alle varie istanze per l'elaborazione. Nell'esempio la proprietà <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> viene impostata su `PerCall` in modo che ogni messaggio possa essere elaborato da un'istanza diversa. La proprietà <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A> viene impostata su `Multiple` per consentire l'invio contemporaneo di messaggi da parte di più thread.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio  
  
1. Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](building-the-samples.md).  
  
3. Per eseguire l'esempio in una configurazione con un solo computer o tra computer diversi, seguire le istruzioni in [esecuzione degli esempi di Windows Communication Foundation](running-the-samples.md).  
  
> [!NOTE]
> Eseguire il servizio prima di eseguire il client e spegnere il client prima di spegnere il servizio. Ciò impedisce che il client restituisca un'eccezione quando non può chiudere la sessione di sicurezza in modo pulito perché il servizio non c'è più.  
  
> [!IMPORTANT]
> È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) ed [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Service\Oneway`  
