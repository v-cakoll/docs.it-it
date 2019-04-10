---
title: Compatibilità con ASP.NET
ms.date: 03/30/2017
ms.assetid: c8b51f1e-c096-4c42-ad99-0519887bbbc5
ms.openlocfilehash: 01381dc579f5ae3eadd2f913a0e09d7d259794a1
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59304221"
---
# <a name="aspnet-compatibility"></a>Compatibilità con ASP.NET
In questo esempio viene illustrato come abilitare la modalità di compatibilità ASP.NET in Windows Communication Foundation (WCF). Servizi in esecuzione nella compatibilità ASP.NET partecipano completamente la pipeline dell'applicazione ASP.NET di modalità e può rendere usano le funzionalità ASP.NET, ad esempio l'autorizzazione file/URL, lo stato della sessione e <xref:System.Web.HttpContext> classe. Il <xref:System.Web.HttpContext> classe consente l'accesso ai cookie, le sessioni e altre funzionalità ASP.NET. Questa modalità richiede che le associazioni usino il trasporto HTTP e che il servizio stesso debba essere ospitato in IIS.  
  
 In questo esempio, il client è un'applicazione console (un file eseguibile) e il servizio è ospitato da Internet Information Services (IIS).  
  
> [!NOTE]
>  La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.  
  
Per eseguire questo esempio è necessario un pool di applicazioni di [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)]. Per creare un nuovo pool di applicazioni o modificare il pool di applicazioni predefinito, attenersi alla procedura seguente.  

1. Aprire il **Pannello di controllo**.  Aprire il **strumenti di amministrazione** applet sotto il **sistema e sicurezza** intestazione. Aprire il **Internet Information Services (IIS) Manager** applet.  

2. Espandere il treeview nel **connessioni** riquadro. Selezionare il **pool di applicazioni** nodo.  

3. Per impostare il pool di applicazioni predefinito da utilizzare [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] (che potrebbe causare problemi di incompatibilità con i siti esistenti), fare doppio clic il **DefaultAppPool** voce di elenco e selezionare **le impostazioni di base...** . Impostare il **.Net Framework versione** pull-down **.Net Framework v4.0.30128** (o versioni successive).  

4. Per creare un nuovo pool di applicazioni che utilizza [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] (per mantenere la compatibilità per le altre applicazioni), fare doppio clic il **pool di applicazioni** nodo e selezionare **Aggiungi Pool di applicazioni...** . Denominare il nuovo pool di applicazioni e impostare il **.Net Framework versione** pull-down **.Net Framework v4.0.30128** (o versione successiva). Dopo che esegue l'installazione i passaggi di seguito, fare doppio clic il **ServiceModelSamples** dell'applicazione e selezionare **Gestisci applicazione**, **impostazioni avanzate...** . Impostare il **Pool di applicazioni** al nuovo pool di applicazioni.  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\WebHost\ASPNetCompatibility`  
  
 In questo esempio si basa sul [introduttiva](../../../../docs/framework/wcf/samples/getting-started-sample.md), che implementa un servizio di calcolatrice. Il contratto `ICalculator` è stato modificato al contratto `ICalculatorSession` per consentire l'esecuzione di un set di operazioni mantenendo il risultato della sessione.  
  
```csharp  
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public interface ICalculatorSession  
{  
    [OperationContract]  
    void Clear();  
    [OperationContract]  
    void AddTo(double n);  
    [OperationContract]  
    void SubtractFrom(double n);  
    [OperationContract]  
    void MultiplyBy(double n);  
    [OperationContract]  
    void DivideBy(double n);  
    [OperationContract]  
    double Result();  
}  
```  
  
 Usando questa funzionalità il servizio mantiene lo stato di ogni client, mentre vengono chiamate più operazioni del servizio per eseguire un calcolo. Il client può recuperare il risultato corrente chiamando `Result` e può azzerare il risultato chiamando `Clear`.  
  
 Il servizio Usa la sessione ASP.NET per memorizzare il risultato per ogni sessione client. Questo consente al servizio di mantenere il risultato della sessione per ogni client, su più chiamate al servizio.  
  
> [!NOTE]
> Stato della sessione ASP.NET e WCF sessioni sono molto diversi. Visualizzare [sessione](../../../../docs/framework/wcf/samples/session.md) per informazioni dettagliate sulle sessioni WCF.
  
 Il servizio ha una dipendenza stretta sullo stato della sessione ASP.NET e richiede la modalità di compatibilità ASP.NET per funzionare correttamente. Questi requisiti vengono espressi in modo dichiarativo applicando l'attributo `AspNetCompatibilityRequirements`.  
  
```csharp  
[AspNetCompatibilityRequirements(RequirementsMode =  
                       AspNetCompatibilityRequirementsMode.Required)]  
public class CalculatorService : ICalculatorSession  
{  
    double Result  
    {  // store result in AspNet Session  
       get {  
          if (HttpContext.Current.Session["Result"] != null)  
             return (double)HttpContext.Current.Session["Result"];  
          return 0.0D;  
       }  
       set  
       {  
          HttpContext.Current.Session["Result"] = value;  
       }  
    }  
    public void Clear()  
    {  
        Result = 0.0D;  
    }  
    public void AddTo(double n)  
    {  
        Result += n;  
    }  
    public void SubtractFrom(double n)  
    {  
        Result -= n;  
    }  
    public void MultiplyBy(double n)  
    {  
        Result *= n;  
    }  
    public void DivideBy(double n)  
    {  
        Result /= n;  
    }  
    public double Result()  
    {  
        return Result;  
    }  
}  
```
  
 Quando si esegue l'esempio, le richieste e le risposte dell'operazione vengono visualizzate nella finestra della console client. Premere INVIO nella finestra del client per arrestare il client.  
  
```console
0, + 100, - 50, * 17.65, / 2 = 441.25  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio  
  
1. Assicurarsi di avere eseguito il [monouso procedura di installazione per gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3. Dopo aver compilato la soluzione, eseguire Setup.bat per configurare l'applicazione ServiceModelSamples in [!INCLUDE[iisver](../../../../includes/iisver-md.md)]. La directory ServiceModelSamples verrà ora visualizzata come applicazione [!INCLUDE[iisver](../../../../includes/iisver-md.md)].  
  
4. Per eseguire l'esempio in una configurazione singola o tra computer, seguire le istruzioni in [esegue gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
## <a name="see-also"></a>Vedere anche

- [Hosting e salvataggio permanente](https://go.microsoft.com/fwlink/?LinkId=193961)
