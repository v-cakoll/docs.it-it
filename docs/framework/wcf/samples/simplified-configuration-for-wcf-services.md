---
title: Configurazione semplificata per servizi WCF
ms.date: 03/30/2017
ms.assetid: 1e39ec25-18a3-4fdc-b6a3-9dfafbd60112
ms.openlocfilehash: c78f5ca281c784a8f554ad1f4e3a1f245eee4914
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/16/2019
ms.locfileid: "74141859"
---
# <a name="simplified-configuration-for-wcf-services"></a>Configurazione semplificata per servizi WCF
This sample demonstrates how to implement and configure a typical service and client using Windows Communication Foundation (WCF). Questo esempio è la base per tutti gli altri esempi di tecnologia di base.  
  
 This service, which exposes an endpoint for communicating with the service, uses the simplified configuration in .NET Framework 4. Prior to .NET Framework 4, the endpoint is typically defined in a configuration file (Web.config), as shown in the following example configuration code.  
  
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
  
 In .NET Framework 4, the `<service>` element is optional. Quando un servizio non definisce alcun endpoint, al servizio viene aggiunto un endpoint per ogni indirizzo di base e contratto implementato. L'indirizzo di base viene aggiunto al nome del contratto per determinare l'endpoint e l'associazione è determinata dallo schema dell'indirizzo. Nell'esempio di codice seguente viene illustrato un file di configurazione semplificato. As configured, the service can be accessed at `http://localhost/servicemodelsamples/service.svc` by a client on the same computer. Affinché i client presenti nei computer remoti accedano al servizio, è necessario specificare un nome di dominio completo anziché localhost. Per impostazione predefinita, il servizio non espone metadati. In quanto tale, il servizio attiva il comportamento <xref:System.ServiceModel.Description.ServiceMetadataBehavior>.  
  
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
  
1. Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3. Eseguire l'esempio attenendosi ai passaggi seguenti:  
  
    1. Right click the **Service** project and select **Set as StartUp project**, then press **Ctrl+F5**.  
  
    2. Attendere l'output della console che conferma che il servizio è in esecuzione.  
  
    3. Right click the **Client** project and select **Set as StartUp project**, then press **Ctrl+F5**.  
  
> [!IMPORTANT]
> È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples. Questo esempio si trova nella directory seguente.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\ConfigSimplificationIn40`  
  
## <a name="see-also"></a>Vedere anche

- [AppFabric Management Samples](https://go.microsoft.com/fwlink/?LinkId=193960)
- [Configurazione semplificata](../../../../docs/framework/wcf/simplified-configuration.md)
