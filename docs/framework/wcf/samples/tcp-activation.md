---
title: Attivazione TCP
ms.date: 03/30/2017
ms.assetid: bf8c215c-0228-4f4f-85c2-e33794ec09a7
ms.openlocfilehash: 5e7f441873ec4d3ad087d1ff28510d92d87db9b1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54677829"
---
# <a name="tcp-activation"></a>Attivazione TCP
In questo esempio viene illustrato come ospitare un servizio che usa i servizi di attivazione dei processi Windows (WAS) per attivare un servizio che comunica mediante il protocollo net.tcp. In questo esempio si basa sul [introduttiva](../../../../docs/framework/wcf/samples/getting-started-sample.md).  
  
> [!NOTE]
>  La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\WASHost\TCPActivation`  
  
 L'esempio è costituito da un programma console del client (.exe) e una libreria di servizi (.dll) ospitati in un processo di lavoro attivato dal servizio di attivazione dei processi di Windows (WAS). L'attività del client è visibile nella finestra della console.  
  
 Il servizio implementa un contratto che definisce un modello di comunicazione richiesta/risposta. Il contratto è definito dall'interfaccia `ICalculator`, che espone operazioni matematiche (somma, sottrazione, moltiplicazione e divisione), come illustrato nell'esempio di codice seguente.  
  
```csharp
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
  
 L'implementazione del servizio calcola e restituisce il risultato appropriato:  
  
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
  
 L'esempio usa una variante dell'associazione net.tcp con la condivisione delle porte TCP attivata e la sicurezza disattivata. Se si desidera usare un'associazione TCP protetta, impostare la modalità di sicurezza del server sul tipo desiderato ed eseguire di nuovo Svcutil.exe sul client per generare un file di configurazione client aggiornato.  
  
 Nell'esempio seguente viene illustrata la configurazione del servizio:  
  
```xml  
<system.serviceModel>  
  
    <services>  
      <service name="Microsoft.ServiceModel.Samples.CalculatorService"  
               behaviorConfiguration="CalculatorServiceBehavior">  
        <!-- This endpoint is exposed at the base address provided by host: net.tcp://localhost/servicemodelsamples/service.svc  -->  
        <endpoint binding="netTcpBinding" bindingConfiguration="PortSharingBinding"  
          contract="Microsoft.ServiceModel.Samples.ICalculator" />  
        <!-- the mex endpoint is explosed at net.tcp://localhost/servicemodelsamples/service.svc/mex -->  
        <endpoint address="mex"  
                  binding="mexTcpBinding"  
                  contract="IMetadataExchange" />  
      </service>  
    </services>  
    <bindings>  
      <netTcpBinding>  
        <binding name="PortSharingBinding" portSharingEnabled="true">  
          <security mode="None" />  
        </binding>  
      </netTcpBinding>  
    </bindings>  
  
    <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="CalculatorServiceBehavior">  
          <serviceMetadata />  
          <serviceDebug includeExceptionDetailInFaults="False" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  
  </system.serviceModel>  
```  
  
 L'endpoint del client è configurato come illustrato nell'esempio di codice seguente:  
  
```xml  
<system.serviceModel>  
    <bindings>  
        <netTcpBinding>  
          <binding name="NetTcpBinding_ICalculator">  
            <security mode="None"/>  
          </binding>  
        </netTcpBinding>  
    </bindings>  
    <client>  
        <endpoint address="net.tcp://localhost/servicemodelsamples/service.svc"  
            binding="netTcpBinding" bindingConfiguration="NetTcpBinding_ICalculator"  
            contract="Microsoft.ServiceModel.Samples.ICalculator" name="NetTcpBinding_ICalculator" />  
    </client>  
</system.serviceModel>  
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
  
1.  Assicurarsi che [!INCLUDE[iisver](../../../../includes/iisver-md.md)] sia installato. Per l'attivazione WAS è necessario l'uso di [!INCLUDE[iisver](../../../../includes/iisver-md.md)].  
  
2.  Assicurarsi di avere eseguito il [monouso procedura di installazione per gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
     Inoltre, è necessario installare i componenti di attivazione non HTTP di WCF:  
  
    1.  Fare clic sul pulsante **Start** e scegliere **Pannello di controllo**.  
  
    2.  Selezionare **programmi e funzionalità**.  
  
    3.  Fare clic su **attivare i componenti di Windows o disattivare**.  
  
    4.  Espandere la **Microsoft .NET Framework 3.0** nodo e selezionare il **attivazione Non HTTP di Windows Communication Foundation** funzionalità.  
  
3.  Configurare WAS per supportare l'attivazione TCP.  
  
     Per maggiore praticità, i due passaggi seguenti vengono implementati in un file batch di nome AddNetTcpSiteBinding.cmd situato nella directory degli esempi.  
  
    1.  Per supportare l'attivazione net.tcp, è prima necessario associare il sito Web predefinito a una porta net.tcp. A tale fine, usare Appcmd.exe, installato con il set di strumenti di gestione di Internet Information Services 7.0 (IIS). Da un prompt dei comandi con privilegi di amministratore, eseguire il comando seguente:  
  
        ```console  
        %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site" -+bindings.[protocol='net.tcp',bindingInformation='808:*']  
        ```  
  
        > [!TIP]
        >  Questo comando è una singola riga di testo. Il comando aggiunge un'associazione del sito net.tcp al sito Web predefinito in ascolto sulla porta TCP 808 con un nome host qualsiasi.  
  
    2.  Anche se tutte le applicazioni all'interno di un sito condividono un'associazione net.tcp comune, ognuna di esse può attivare il supporto net.tcp individualmente. Per attivare net.tcp per l'applicazione /servicemodelsamples, eseguire il comando seguente da un prompt dei comandi a livello di amministratore:  
  
        ```console  
        %windir%\system32\inetsrv\appcmd.exe set app   
        "Default Web Site/servicemodelsamples" /enabledProtocols:http,net.tcp  
        ```  
  
        > [!NOTE]
        > Questo comando è una singola riga di testo. Questo comando consente di accedervi usando sia l'applicazione /servicemodelsamples `http://localhost/servicemodelsamples` e `net.tcp://localhost/servicemodelsamples`.  
  
4.  Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
5.  Per eseguire l'esempio in una configurazione singola o tra computer, seguire le istruzioni in [esegue gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
     Rimuovere l'associazione del sito net.tcp aggiunta per questo esempio.  
  
     Per comodità, i due passaggi seguenti vengono implementati in un file batch chiamato RemoveNetTcpSiteBinding.cmd situato nella directory di esempio.  
  
    1.  Rimuovere net.tcp dall'elenco dei protocolli attivati tramite il comando seguente da una finestra del prompt dei comandi a livello di amministratore:  
  
        ```console  
        %windir%\system32\inetsrv\appcmd.exe set app   
        "Default Web Site/servicemodelsamples" /enabledProtocols:http  
        ```  
  
        > [!NOTE]
        >  Questo comando deve essere immesso come una sola riga del testo.  
  
    2.  Rimuovere l'associazione del sito net.tcp eseguendo il comando seguente da una finestra del prompt dei comandi a livello di amministratore:  
  
        ```console  
        %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site"   
        --bindings.[protocol='net.tcp',bindingInformation='808:*']  
        ```  
  
        > [!NOTE]
        >  Questo comando deve essere digitato come una singola riga di testo.  
  
## <a name="see-also"></a>Vedere anche
- [Hosting di AppFabric e salvataggio permanente](https://go.microsoft.com/fwlink/?LinkId=193961)
