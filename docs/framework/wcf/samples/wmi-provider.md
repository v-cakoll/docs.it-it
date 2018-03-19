---
title: Provider WMI
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 462f0db3-f4a4-4a4b-ac26-41fc25c670a4
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: c1b1f923b6673ead42c7c702bd50d253ea06c765
ms.sourcegitcommit: 15316053918995cc1380163a7d7e7edd5c44e6d7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2018
---
# <a name="wmi-provider"></a>Provider WMI
In questo esempio viene illustrato come raccogliere dati dai servizi [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] in fase di esecuzione usando il provider di Strumentazione gestione Windows (WMI) incorporato in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. Viene inoltre illustrato come aggiungere un oggetto WMI definito dall'utente a un servizio. L'esempio attiva il provider WMI per il [Introduzione](../../../../docs/framework/wcf/samples/getting-started-sample.md) e viene illustrato come raccogliere dati di `ICalculator` servizio in fase di esecuzione.  
  
 WMI è l'implementazione Microsoft dello standard WBEM (Web-Based Enterprise Management). Per ulteriori informazioni sul SDK di WMI, vedere [Strumentazione gestione Windows](https://msdn.microsoft.com/library/aa394582.aspx). WBEM è uno standard industriale che definisce la modalità in cui le applicazioni espongono la strumentazione della gestione a strumenti di gestione esterni.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]implementa un provider WMI, un componente che espone la strumentazione in fase di esecuzione attraverso un'interfaccia compatibile con WBEM. Gli strumenti di gestione sono in grado di connettersi ai servizi attraverso l'interfaccia in fase di esecuzione. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] espone attributi di servizi quali indirizzi, associazioni, comportamenti e listener.  
  
 Il provider WMI incorporato viene attivato nel file di configurazione dell'applicazione. Questa operazione viene eseguita tramite il `wmiProviderEnabled` attributo del [ \<diagnostica >](../../../../docs/framework/configure-apps/file-schema/wcf/diagnostics.md) nel [ \<System. ServiceModel >](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) sezione, come illustrato nell'esempio seguente configurazione:  
  
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
 L'accesso ai dati WMI può essere eseguito in molti modi diversi. Microsoft fornisce le API di WMI per gli script, [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] le applicazioni, applicazioni C++ e la [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] (http://msdn.microsoft.com/library/default.asp?url=/library/wmisdk/wmi/using_wmi.asp).  
  
 In questo esempio vengono usati due script Java: uno per enumerare i servizi in esecuzione nel computer con alcune delle relative proprietà e il secondo per visualizzare i dati WMI definiti dall'utente. Lo script apre una connessione al provider WMI, analizza i dati e visualizza i dati raccolti.  
  
 Avviare l'esempio per creare un'istanza in esecuzione di un servizio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. Mentre il servizio è in esecuzione, eseguire ogni script Java usando il comando seguente nel prompt dei comandi:  
  
```  
cscript EnumerateServices.js  
```  
  
 Lo script accede alla strumentazione contenuta nel servizio e produce l'output seguente:  
  
```  
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
  
```  
cscript EnumerateCustomObjects.js  
```  
  
 Lo script accede alla strumentazione definita dall'utente contenuta nei servizi e produce l'output seguente:  
  
```  
1 WMIObject(s) found.  
|-PID:           30285bfd-9d66-4c4e-9be2-310499c5cef5  
|-InstanceId:    3839  
|-WMIInfo:       User Defined WMI Information.  
```  
  
 L'output mostra che nel computer è in esecuzione un solo servizio. Il servizio espone un endpoint che implementa il contratto `ICalculator`. Le impostazioni del comportamento e l'associazione implementate dall'endpoint sono elencate come la somma dei singoli elementi dello stack di messaggistica.  
  
 WMI non si limita a esporre la strumentazione di gestione dell'infrastruttura [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. Mediante lo stesso meccanismo l'applicazione può esporre dati specifici del dominio. WMI è un meccanismo unificato per l'ispezione e il controllo di un servizio Web.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio  
  
1.  Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Pubblicare lo schema dei servizi in WMI eseguendo InstallUtil.exe (il percorso predefinito per InstallUtil.exe è "%WINDIR%\Microsoft.NET\Framework\v4.0.30319") sul file service.dll nella directory di hosting. È necessario eseguire questo passaggio solo quando sono state apportate modifiche al file service.dll. Per altre informazioni, vedere fornendo le informazioni di gestione per la strumentazione di applicazioni: http://msdn2.microsoft.com/library/ms186147.aspx nella sezione "Come a: pubblicare il schema per WMI per un'applicazione instrumentata".  
  
4.  Per eseguire l'esempio in una configurazione a una o più computer, seguire le istruzioni in [esegue gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
    > [!NOTE]
    >  Se si installa [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] dopo avere installato ASP.NET, potrebbe essere necessario eseguire "%WINDIR%\ Microsoft.Net\Framework\v3.0\Windows Communication Foundation\servicemodelreg.exe " -r -x per fornire all'account ASP.NET l'autorizzazione per pubblicare oggetti WMI.  
  
5.  Visualizzare i dati dall'esempio riportato tramite WMI usando i comandi: `cscript EnumerateServices.js` o `cscript EnumerateCustomObjects.js`.  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\WMIProvider`  
  
## <a name="see-also"></a>Vedere anche  
 [Esempi di monitoraggio di AppFabric](http://go.microsoft.com/fwlink/?LinkId=193959)
