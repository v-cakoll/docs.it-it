---
title: Hosting IIS mediante il codice inline
ms.date: 03/30/2017
helpviewer_keywords:
- Web hosted service
- IIS Hosting Using Inline Code Sample [Windows Communication Foundation]
ms.assetid: 56fe3687-a34b-4661-8e30-b33770f413fa
ms.openlocfilehash: 304da4fa7d2bb48899cdec864fb2dc1f9fdfb9ef
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746430"
---
# <a name="iis-hosting-using-inline-code"></a>Hosting IIS mediante il codice inline

In questo esempio viene illustrato come implementare un servizio ospitato da Internet Information Services (IIS), in cui il codice del servizio è contenuto inline in un file con estensione svc e viene compilato su richiesta. Il codice del servizio può anche essere implementato direttamente nei file del codice sorgente presenti nella directory \App_Code dell'applicazione, oppure essere compilato in assembly distribuiti in \bin. In questo esempio non vengono illustrate tali tecniche.

> [!NOTE]
> La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.

> [!IMPORTANT]
> È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\WebHost\InlineCode`

Nell'esempio viene illustrato un servizio tipico che implementa un contratto in cui viene definito un modello di comunicazione richiesta/risposta. Il servizio è ospitato in IIS e il codice del servizio è interamente contenuto nel file Service.svc. Il servizio viene attivato dall'host e compilato su richiesta dal primo messaggio inviato al servizio. Non è necessaria la precompilazione. Il servizio implementa un contratto `ICalculator`, come definito nel codice seguente:

```csharp
// Define a service contract.
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]
    public interface ICalculator
{
    [OperationContract]
    double Add(double n1, double n2);
    [OperationContract]
    double Subtract(double n1, double n2);
    [OperationContract]
    double Multiply(double n1, double n2);
    [OperationContract]
    double Divide(double n1, double n2);
}
```

L'implementazione del servizio calcola e restituisce il risultato appropriato.

`<%@ServiceHost language=c# Debug="true" Service="Microsoft.ServiceModel.Samples.CalculatorService" %>`

```csharp
// Service class that implements the service contract.
public class CalculatorService : ICalculator
{
    public double Add(double n1, double n2)
    {
        return n1 + n2;
    }
    public double Subtract(double n1, double n2)
    {
        return n1 - n2;
    }
    public double Multiply(double n1, double n2)
    {
        return n1 * n2;
    }
    public double Divide(double n1, double n2)
    {
        return n1 / n2;
    }
}
```

Quando si esegue l'esempio, le richieste e le risposte dell'operazione vengono visualizzate nella finestra della console client. Premere INVIO nella finestra del client per arrestare il client.

```console
Add(100,15.99) = 115.99
Subtract(145,76.54) = 68.46
Multiply(9,81.25) = 731.25
Divide(22,7) = 3.14285714285714

Press <ENTER> to terminate client.
```

### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio

1. Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).

2. Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).

3. Una volta compilata la soluzione, eseguire Setup. bat per configurare l'applicazione ServiceModelSamples in IIS 7,0. La directory ServiceModelSamples dovrebbe ora essere visualizzata come applicazione IIS 7,0.

4. Per eseguire l'esempio in una configurazione con un solo computer o tra computer diversi, seguire le istruzioni in [esecuzione degli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md). Per un esempio su come creare un'applicazione client in grado di chiamare questo servizio, vedere [procedura: creare un client](../../../../docs/framework/wcf/how-to-create-a-wcf-client.md).

## <a name="see-also"></a>Vedere anche

- [Esempi di persistenza e hosting di AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ff383418(v=azure.10))
