---
title: Configurazione semplificata per servizi WCF
ms.date: 03/30/2017
ms.assetid: 1e39ec25-18a3-4fdc-b6a3-9dfafbd60112
ms.openlocfilehash: 333469cecdf2acae72e6d1add8f96829a127dcf8
ms.sourcegitcommit: 586dbdcaef9767642436b1e4efbe88fb15473d6f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/06/2018
ms.locfileid: "48836722"
---
# <a name="simplified-configuration-for-wcf-services"></a>Configurazione semplificata per servizi WCF
In questo esempio viene illustrato come implementare e configurare un servizio tipico e un client tramite Windows Communication Foundation (WCF). Questo esempio è la base per tutti gli altri esempi di tecnologia di base.  
  
 Questo servizio, che espone un endpoint per comunicare con il servizio, utilizza la configurazione semplificata in [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)]. Prima di [!INCLUDE[netfx40_short](../../../../includes/netfx40-short-md.md)], l'endpoint viene in genere definito in un file di configurazione (Web.config), come mostrato nel codice di configurazione di esempio seguente.  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<!-- Copyright ©) Microsoft Corporation.  All Rights Reserved. -->  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="CalculatorServiceBehavior">  
          <serviceMetadata httpGetEnabled="True"/>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    <services>  
      <service name="Microsoft.Samples.GettingStarted.CalculatorService"  
               behaviorConfiguration="CalculatorServiceBehavior">  
        <endpoint address="" binding="basicHttpBinding" contract="ICalculator"/>  
        <endpoint address="mex" binding="mexHttpBinding" contract="IMetadataExchange"/>  
      </service>  
    </services>  
  </system.serviceModel>  
</configuration>  
```  
  
 In [!INCLUDE[netfx40_short](../../../../includes/netfx40-short-md.md)], l'elemento `<service>` è facoltativo. Quando un servizio non definisce alcun endpoint, al servizio viene aggiunto un endpoint per ogni indirizzo di base e contratto implementato. L'indirizzo di base viene aggiunto al nome del contratto per determinare l'endpoint e l'associazione è determinata dallo schema dell'indirizzo. Nell'esempio di codice seguente viene illustrato un file di configurazione semplificato. In base alla configurazione, è possibile accedere al servizio `http://localhost/servicemodelsamples/service.svc` da un client sullo stesso computer. Affinché i client presenti nei computer remoti accedano al servizio, è necessario specificare un nome di dominio completo anziché localhost. Per impostazione predefinita, il servizio non espone metadati. In quanto tale, il servizio attiva il comportamento <xref:System.ServiceModel.Description.ServiceMetadataBehavior>.  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<!-- Copyright © Microsoft Corporation.  All Rights Reserved. -->  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="">  
          <serviceMetadata httpGetEnabled="True"/>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
### <a name="to-use-this-sample"></a>Per usare questo esempio  
  
1.  Assicurarsi di avere eseguito il [monouso procedura di installazione per gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Per compilare la soluzione, seguire le istruzioni riportate in [Building Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Eseguire l'esempio attenendosi ai passaggi seguenti:  
  
    1.  Fare clic il **Service** del progetto e selezionare **imposta come progetto di avvio**, quindi premere **Ctrl + F5**.  
  
    2.  Attendere l'output della console che conferma che il servizio è in esecuzione.  
  
    3.  Fare clic il **Client** del progetto e selezionare **imposta come progetto di avvio**, quindi premere **Ctrl + F5**.  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\ConfigSimplificationIn40`  
  
## <a name="see-also"></a>Vedere anche  
 [Esempi di gestione di AppFabric](https://go.microsoft.com/fwlink/?LinkId=193960)  
 [Configurazione semplificata](../../../../docs/framework/wcf/simplified-configuration.md)
