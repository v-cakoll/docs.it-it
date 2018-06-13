---
title: Compatibilità con ASP.NET
ms.date: 03/30/2017
ms.assetid: c8b51f1e-c096-4c42-ad99-0519887bbbc5
ms.openlocfilehash: f621a3f13fafee67a015d463898a10aaf9104008
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2018
ms.locfileid: "33806221"
---
# <a name="aspnet-compatibility"></a>Compatibilità con ASP.NET
In questo esempio viene illustrato come abilitare [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] modalità di compatibilità in Windows Communication Foundation (WCF). I servizi in esecuzione nella modalità di compatibilità di [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] si integrano pienamente nella pipeline dell'applicazione [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] e possono avvalersi delle funzionalità di [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)], ad esempio l'autorizzazione file/URL, lo stato della sessione e la classe <xref:System.Web.HttpContext>. La classe <xref:System.Web.HttpContext> consente di accedere ai cookie, alle sessioni e ad altre funzionalità di [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]. Questa modalità richiede che le associazioni usino il trasporto HTTP e che il servizio stesso debba essere ospitato in IIS.  
  
 In questo esempio, il client è un'applicazione console (un file eseguibile) e il servizio è ospitato da Internet Information Services (IIS).  
  
> [!NOTE]
>  La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.  
  
> [!NOTE]
>  Per eseguire questo esempio è necessario un pool di applicazioni di [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)]. Per creare un nuovo pool di applicazioni o modificare il pool di applicazioni predefinito, attenersi alla procedura seguente.  
>   
>  1.  Aprire il **Pannello di controllo**.  Aprire il **strumenti di amministrazione** applet sotto il **sistema e sicurezza** intestazione. Aprire il **Gestione Internet Information Services (IIS)** applet.  
> 2.  Espandere il treeview nel **connessioni** riquadro. Selezionare il **pool di applicazioni** nodo.  
> 3.  Per impostare il pool di applicazioni predefinito da utilizzare [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] (che potrebbe causare problemi di incompatibilità con i siti esistenti), fare doppio clic su di **DefaultAppPool** voce di elenco e selezionare **impostazioni di base...** . Impostare il **.Net Framework versione** pull-down **.Net Framework v 4.0.30128** (o versione successiva).  
> 4.  Per creare un nuovo pool di applicazioni che utilizza [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] (per mantenere la compatibilità per le altre applicazioni), fare doppio clic su di **pool di applicazioni** nodo e selezionare **Aggiungi Pool di applicazioni...** . Denominare il nuovo pool di applicazioni e impostare il **.Net Framework versione** pull-down **.Net Framework v 4.0.30128** (o versione successiva). Dopo che è in esecuzione il programma di installazione di passaggi inferiore, destro la **ServiceModelSamples** dell'applicazione e selezionare **Gestione applicazione**, **impostazioni avanzate...** . Impostare il **Pool di applicazioni** per il nuovo pool di applicazioni.  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\WebHost\ASPNetCompatibility`  
  
 Questo esempio è basato sul [Introduzione](../../../../docs/framework/wcf/samples/getting-started-sample.md), che implementa un servizio di calcolatrice. Il contratto `ICalculator` è stato modificato al contratto `ICalculatorSession` per consentire l'esecuzione di un set di operazioni mantenendo il risultato della sessione.  
  
```  
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
  
 Il servizio usa la sessione di [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] per archiviare il risultato per ogni sessione client. Questo consente al servizio di mantenere il risultato della sessione per ogni client, su più chiamate al servizio.  
  
> [!NOTE]
>  [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] lo stato della sessione e le sessioni WCF sono molto diversi.  Vedere la [sessione](../../../../docs/framework/wcf/samples/session.md) per informazioni dettagliate sulle sessioni WCF.  
  
 Il servizio ha una dipendenza stretta con lo stato della sessione di [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] e richiede che la modalità di compatibilità di [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] funzioni correttamente. Questi requisiti vengono espressi in modo dichiarativo applicando l'attributo `AspNetCompatibilityRequirements`.  
  
```  
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
  
```  
0, + 100, - 50, * 17.65, / 2 = 441.25  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio  
  
1.  Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Dopo aver compilato la soluzione, eseguire Setup.bat per configurare l'applicazione ServiceModelSamples in [!INCLUDE[iisver](../../../../includes/iisver-md.md)]. La directory ServiceModelSamples verrà ora visualizzata come applicazione [!INCLUDE[iisver](../../../../includes/iisver-md.md)].  
  
4.  Per eseguire l'esempio in una configurazione a una o più computer, seguire le istruzioni in [esegue gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Hosting di AppFabric ed esempi di persistenza](http://go.microsoft.com/fwlink/?LinkId=193961)
