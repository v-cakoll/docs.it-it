---
title: Concorrenza
ms.date: 03/30/2017
helpviewer_keywords:
- service behaviors, concurency sample
- Concurrency Sample [Windows Communication Foundation]
ms.assetid: f8dbdfb3-6858-4f95-abe3-3a1db7878926
ms.openlocfilehash: 393c8a79cb60a33203b41a0778176a4d78a9b6ee
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84585311"
---
# <a name="concurrency"></a>Concorrenza
L'esempio Concorrenza dimostra l'uso di <xref:System.ServiceModel.ServiceBehaviorAttribute> con l'enumerazione <xref:System.ServiceModel.ConcurrencyMode> che controlla se un'istanza di un servizio elabora i messaggi in sequenza o contemporaneamente. L'esempio è basato sulla [Introduzione](getting-started-sample.md), che implementa il `ICalculator` contratto di servizio. In questo esempio viene definito un nuovo contratto, `ICalculatorConcurrency`, che eredita da `ICalculator`, fornendo due operazioni aggiuntive per ispezionare lo stato della concorrenza del servizio. Modificando l'impostazione della concorrenza, è possibile osservare come viene modificato il comportamento quando si esegue il client.  
  
 In questo esempio, il client è un'applicazione console (.exe) e il servizio è ospitato da Internet Information Services (IIS).  
  
> [!NOTE]
> La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.  
  
 Sono disponibili tre modalità di concorrenza:  
  
- `Single`: Ogni istanza del servizio elabora uno messaggio alla volta. Si tratta della modalità di concorrenza predefinita.  
  
- `Multiple`: ogni istanza del servizio elabora più messaggi contemporaneamente. Per essere in grado di usare questa modalità di concorrenza, l'implementazione del servizio deve essere thread-safe.  
  
- `Reentrant`: ogni istanza del servizio elabora un messaggio alla volta ma accetta chiamate di operazioni rientranti. Il servizio accetta queste chiamate solo quando viene chiamato. Il rientrante è illustrato nell'esempio [ConcurrencyMode. Reentrant](concurrencymode-reentrant.md) .  
  
 L'uso della concorrenza è correlato alla modalità di istanza. Nelle istanze di <xref:System.ServiceModel.InstanceContextMode.PerCall>, la concorrenza non è rilevante perché ogni messaggio viene elaborato da una nuova istanza del servizio. Nelle istanze di <xref:System.ServiceModel.InstanceContextMode.Single>, la concorrenza <xref:System.ServiceModel.ConcurrencyMode.Single> o <xref:System.ServiceModel.ConcurrencyMode.Multiple> è rilevante a seconda che la singola istanza elabori i messaggi in modo sequenziale o concorrente. Nelle istanze di <xref:System.ServiceModel.InstanceContextMode.PerSession>, può essere rilevante qualsiasi modalità di concorrenza.  
  
 La classe del servizio specifica il comportamento della concorrenza con l'attributo `[ServiceBehavior(ConcurrencyMode=<setting>)]`, come illustrato nell'esempio di codice seguente. Tramite la modifica delle righe impostate come commento, è possibile provare le modalità di concorrenza `Single` e `Multiple`. Ricordare di ricompilare il servizio dopo avere modificato la modalità di concorrenza.  
  
```csharp
// Single allows a single message to be processed sequentially by each service instance.  
//[ServiceBehavior(ConcurrencyMode = ConcurrencyMode.Single, InstanceContextMode = InstanceContextMode.Single)]  
  
// Multiple allows concurrent processing of multiple messages by a service instance.  
// The service implementation should be thread-safe. This can be used to increase throughput.  
[ServiceBehavior(ConcurrencyMode=ConcurrencyMode.Multiple, InstanceContextMode = InstanceContextMode.Single)]  
  
// Uses Thread.Sleep to vary the execution time of each operation.  
public class CalculatorService : ICalculatorConcurrency  
{  
    int operationCount;  
  
    public double Add(double n1, double n2)  
    {  
        operationCount++;  
        System.Threading.Thread.Sleep(180);  
        return n1 + n2;  
    }  
  
    public double Subtract(double n1, double n2)  
    {  
        operationCount++;  
        System.Threading.Thread.Sleep(100);  
        return n1 - n2;  
    }  
  
    public double Multiply(double n1, double n2)  
    {  
        operationCount++;  
        System.Threading.Thread.Sleep(150);  
        return n1 * n2;  
    }  
  
    public double Divide(double n1, double n2)  
    {  
        operationCount++;  
        System.Threading.Thread.Sleep(120);  
        return n1 / n2;  
    }  
  
    public string GetConcurrencyMode()  
    {
        // Return the ConcurrencyMode of the service.  
        ServiceHost host = (ServiceHost)OperationContext.Current.Host;  
        ServiceBehaviorAttribute behavior = host.Description.Behaviors.Find<ServiceBehaviorAttribute>();  
        return behavior.ConcurrencyMode.ToString();  
    }  
  
    public int GetOperationCount()  
    {
        // Return the number of operations.  
        return operationCount;  
    }  
}  
```  
  
 Per impostazione predefinita l'esempio usa la concorrenza <xref:System.ServiceModel.ConcurrencyMode.Multiple> con istanze <xref:System.ServiceModel.InstanceContextMode.Single>. Il codice client è stato modificato per usare un proxy asincrono. Consente al client di eseguire più chiamate al servizio senza attendere una risposta tra ogni chiamata. È possibile osservare la differenza nel comportamento della modalità di concorrenza del servizio.  
  
 Quando si esegue l'esempio, le richieste e le risposte dell'operazione vengono visualizzate nella finestra della console client. Viene visualizzata la modalità di concorrenza usata dal servizio, viene chiamata ciascuna operazione e quindi viene visualizzato il conteggio dell'operazione. Notare che quando la modalità di concorrenza è `Multiple`, i risultati vengono restituiti in un ordine diverso da quello con cui sono stati chiamati, perché il servizio elabora più messaggi contemporaneamente. Tramite la modifica della modalità di concorrenza su `Single`, i risultati vengono restituiti nell'ordine con cui sono stati chiamati, perché il servizio elabora ogni messaggio in sequenza. Premere INVIO nella finestra del client per arrestare il client.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio  
  
1. Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Se si utilizza Svcutil. exe per generare il client proxy, assicurarsi di includere l' `/async` opzione.  
  
3. Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](building-the-samples.md).  
  
4. Per eseguire l'esempio in una configurazione con un solo computer o tra computer diversi, seguire le istruzioni in [esecuzione degli esempi di Windows Communication Foundation](running-the-samples.md).  
  
> [!IMPORTANT]
> È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) ed [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Behaviors\Concurrency`  
