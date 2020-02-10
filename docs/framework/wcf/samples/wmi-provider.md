---
title: Provider WMI
ms.date: 03/30/2017
ms.assetid: 462f0db3-f4a4-4a4b-ac26-41fc25c670a4
ms.openlocfilehash: a170a20212791d789af589c1ff99dcd1abad1c9e
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/09/2020
ms.locfileid: "77094774"
---
# <a name="wmi-provider"></a>Provider WMI
In questo esempio viene illustrato come raccogliere dati dai servizi Windows Communication Foundation (WCF) in fase di esecuzione utilizzando il provider di Strumentazione gestione Windows (WMI) incorporato in WCF. Viene inoltre illustrato come aggiungere un oggetto WMI definito dall'utente a un servizio. L'esempio attiva il provider WMI per la [Introduzione](../../../../docs/framework/wcf/samples/getting-started-sample.md) e illustra come raccogliere dati dal servizio `ICalculator` in fase di esecuzione.  
  
 WMI è l'implementazione Microsoft dello standard WBEM (Web-Based Enterprise Management). Per ulteriori informazioni su WMI SDK, vedere [Strumentazione gestione Windows](/windows/desktop/WmiSdk/wmi-start-page). WBEM è uno standard industriale che definisce la modalità in cui le applicazioni espongono la strumentazione della gestione a strumenti di gestione esterni.  
  
 WCF implementa un provider WMI, un componente che espone la strumentazione in fase di esecuzione tramite un'interfaccia compatibile con WBEM. Gli strumenti di gestione sono in grado di connettersi ai servizi attraverso l'interfaccia in fase di esecuzione. WCF espone attributi di servizi quali indirizzi, associazioni, comportamenti e listener.  
  
 Il provider WMI incorporato viene attivato nel file di configurazione dell'applicazione. Questa operazione viene eseguita tramite l'attributo `wmiProviderEnabled` del [> di diagnostica\<](../../../../docs/framework/configure-apps/file-schema/wcf/diagnostics.md) nella sezione [\<system. ServiceModel >](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) , come illustrato nella configurazione di esempio seguente:  
  
```xml  
<system.serviceModel>  
    ...  
    <diagnostics wmiProviderEnabled="true" />  
    ...  
</system.serviceModel>  
```  
  
 Questa voce di configurazione espone un'interfaccia WMI. Le applicazioni di gestione possono ora connettersi usando questa interfaccia e accedere la strumentazione di gestione dell'applicazione.  
  
## <a name="custom-wmi-object"></a>Oggetto WMI personalizzato  
 L'aggiunta di oggetti WMI a un servizio rende possibile la rivelazione di informazioni definite dall'utente insieme alle informazioni del provider WMI incorporato. Questa operazione viene eseguita pubblicando lo schema del servizio in WMI usando l'applicazione Installutil.exe. Le istruzioni per svolgere questa operazione, insieme ad altri dettagli, sono disponibili tra le istruzioni di installazione alla fine dell'argomento.  
  
## <a name="accessing-wmi-information"></a>Accesso alle informazioni WMI  

L'accesso ai dati WMI può essere eseguito in molti modi diversi. Microsoft fornisce le API WMI per gli script, Visual Basic C++ applicazioni, le applicazioni e i .NET Framework. Per ulteriori informazioni, vedere [utilizzo di WMI](/windows/desktop/wmisdk/using-wmi).
  
 In questo esempio vengono utilizzati due script Java: uno per enumerare i servizi in esecuzione nel computer con alcune delle relative proprietà e il secondo per visualizzare i dati WMI definiti dall'utente. Lo script apre una connessione al provider WMI, analizza i dati e visualizza i dati raccolti.  
  
 Avviare l'esempio per creare un'istanza in esecuzione di un servizio WCF. Mentre il servizio è in esecuzione, eseguire ogni script Java utilizzando il comando seguente nel prompt dei comandi:  
  
```console  
cscript EnumerateServices.js  
```  
  
 Lo script accede alla strumentazione contenuta nel servizio e produce l'output seguente:  
  
```console  
Microsoft (R) Windows Script Host Version 5.6  
Copyright © Microsoft Corporation 1996-2001. All rights reserved.  
  
1 service(s) found.  
|-PID:           5776  
|-DistinguishedName:  CalculatorService@http://localhost/ServiceModelSamples/service.svc  
|-Endpoints:     1 endpoints  
  |-CalculatorService.ICalculator@http://localhost/ServiceModelSamples/service.svc  
    |-Address:                        http://localhost/ServiceModelSamples/service.svc  
    |-CounterInstanceName:  
    |-AddressHeaders:                 0  
    |-ContractType:                   Contract.Name='ICalculator'  
    |-BindingElements:                4 bindings  
      |-BindingElements[0]  
        |-Type:                       TransactionFlowBindingElement  
      |-BindingElements[1]  
        |-Type:                       SymmetricSecurityBindingElement  
      |-BindingElements[2]  
        |-Type:                       TextMessageEncodingBindingElement  
        |-MaxReadPoolSize:            64  
        |-MaxWritePoolSize:           16  
      |-BindingElements[3]  
        |-Type:                       HttpTransportBindingElement  
        |-ManualAddressing:           false  
        |-MaxBufferSize:              65536  
        |-AllowCookies:               false  
        |-AuthenticationScheme:       Anonymous  
        |-BypassProxyOnLocal:         false  
        |-HostNameComparisonMode:     StrongWildcard  
        |-ProxyAddress:               null  
        |-ProxyAuthenticationScheme:  Anonymous  
        |-Realm:  
        |-TransferMode:               Buffered  
        |-UseDefaultWebProxy:         true  
|-Behaviors:     5 behaviors  
      |-Behavior[0]  
      |-Type:                       ServiceBehaviorAttribute  
        |-AddressFilterMode:               Exact  
        |-AutomaticSessionShutdown:        true  
        |-ConcurrencyMode:                 Single  
        |-IncludeExceptionDetailInFaults:  false  
        |-InstanceContextMode:             PerSession  
        |-TransactionIsolationLevel:       Unspecified  
        |-TransactionTimeout:              null  
        |-ValidateMustUnderstand:          true  
      |-Behavior[1]  
      |-Type:                       AspNetCompatibilityRequirementsAttribute  
      |-Behavior[2]  
      |-Type:                       ServiceDebugBehavior  
      |-Behavior[3]  
      |-Type:                       ServiceAuthorizationBehavior  
      |-Behavior[4]  
      |-Type:                       Behavior  
```  
  
 Eseguire quindi il secondo script Java per visualizzare i dati WMI definiti dall'utente:  
  
```console  
cscript EnumerateCustomObjects.js  
```  
  
 Lo script accede alla strumentazione definita dall'utente contenuta nei servizi e produce l'output seguente:  
  
```console 
1 WMIObject(s) found.  
|-PID:           30285bfd-9d66-4c4e-9be2-310499c5cef5  
|-InstanceId:    3839  
|-WMIInfo:       User Defined WMI Information.  
```  
  
 L'output mostra che nel computer è in esecuzione un solo servizio. Il servizio espone un endpoint che implementa il contratto `ICalculator`. Le impostazioni del comportamento e l'associazione implementate dall'endpoint sono elencate come la somma dei singoli elementi dello stack di messaggistica.  
  
 WMI non è limitato all'esposizione della strumentazione di gestione dell'infrastruttura WCF. Mediante lo stesso meccanismo l'applicazione può esporre dati specifici del dominio. WMI è un meccanismo unificato per l'ispezione e il controllo di un servizio Web.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio  
  
1. Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3. Pubblicare lo schema dei servizi in WMI eseguendo InstallUtil.exe (il percorso predefinito per InstallUtil.exe è "%WINDIR%\Microsoft.NET\Framework\v4.0.303197") sul file service.dll nella directory di hosting. È necessario eseguire questo passaggio solo quando sono state apportate modifiche al file service.dll.
  
4. Per eseguire l'esempio in una configurazione con un solo computer o tra computer diversi, seguire le istruzioni in [esecuzione degli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
    > [!NOTE]
    > Se WCF è stato installato dopo l'installazione di ASP.NET, potrebbe essere necessario eseguire "% WINDIR% \ Microsoft. Net\Framework\v3.0\Windows Communication Foundation\servicemodelreg.exe "-r-x per concedere all'account ASPNET l'autorizzazione per la pubblicazione di oggetti WMI.  
  
5. Visualizzare i dati dall'esempio riportato tramite WMI utilizzando i comandi: `cscript EnumerateServices.js` o `cscript EnumerateCustomObjects.js`.  
  
> [!IMPORTANT]
> È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\WMIProvider`  
  
## <a name="see-also"></a>Vedere anche

- [Esempi di monitoraggio di AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))
