---
title: Sessioni affidabili WS
ms.date: 03/30/2017
helpviewer_keywords:
- Reliable session
ms.assetid: 86e914f2-060b-432b-bd17-333695317745
ms.openlocfilehash: 68123ba9a273bf2c1eaa7b3747930ebca386064b
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84589695"
---
# <a name="ws-reliable-session"></a>Sessioni affidabili WS
Nell'esempio viene illustrato l'utilizzo delle sessioni affidabili. Le sessioni affidabili forniscono supporto per la messaggistica affidabile e le sessioni. La messaggistica affidabile ritenta la comunicazione in caso di errore e consente di specificare assicurazioni del recapito quali l'arrivo nell'ordine di invio dei messaggi. Le sessioni gestiscono lo stato per i client tra le chiamate. L'esempio implementa le sessioni per mantenere lo stato del client e specifica assicurazioni di recapito nell'ordine.  
  
> [!IMPORTANT]
> È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) ed [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\WS\wsReliableSession`  
  
 Questo esempio si basa sul [Introduzione](getting-started-sample.md) che implementa un servizio di calcolatrice. Le funzionalità di sessioni affidabili vengono abilitate e configurate nei file di configurazione dell'applicazione per il client e il servizio.  
  
 In questo esempio, il servizio è ospitato da Internet Information Services (IIS) e il client è un'applicazione console (.exe).  
  
> [!NOTE]
> La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.  
  
 Nell'esempio viene utilizzato il file `wsHttpBinding`. L'associazione è specificata nei file di configurazione per il client e il servizio. Il tipo di associazione è specificato nell'attributo `binding` dell'elemento endpoint, come illustrato nell'esempio di configurazione seguente.  
  
```xml  
<endpoint address=""  
          binding="wsHttpBinding"  
          bindingConfiguration="Binding1"
          contract="Microsoft.ServiceModel.Samples.ICalculator" />  
```  
  
 L'endpoint contiene l'attributo `bindingConfiguration` che fa riferimento a una configurazione di associazione denominata "Binding1". La configurazione dell'associazione consente sessioni affidabili impostando l' `enabled` attributo di [\<reliableSession>](../../configure-apps/file-schema/wcf/reliablesession.md) su `true` . Le garanzie di recapito per le sessioni ordinate possono essere controllate impostando l'attributo ordinato su `true` o `false`. Il valore predefinito è `true`.  
  
```xml  
<bindings>  
    <wsHttpBinding>  
        <binding name="Binding1">  
            <reliableSession enabled="true" />  
        </binding>  
    </wsHttpBinding>  
</bindings>  
```  
  
 La classe dell'implementazione del servizio implementa l'istanza <xref:System.ServiceModel.InstanceContextMode.PerSession> per gestire un'istanza della classe separata per ciascun client, come mostra il codice di esempio seguente.  

```csharp
[ServiceBehavior(InstanceContextMode=InstanceContextMode.PerSession)] public class CalculatorService : ICalculator  
{  
    ...  
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
  
1. Installare ASP.NET 4,0 usando il comando seguente.  
  
    ```console  
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable  
    ```  
  
2. Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).  
  
3. Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](building-the-samples.md).  
  
4. Per eseguire l'esempio in una configurazione con un solo computer o tra computer diversi, seguire le istruzioni in [esecuzione degli esempi di Windows Communication Foundation](running-the-samples.md).  
