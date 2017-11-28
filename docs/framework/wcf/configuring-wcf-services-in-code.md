---
title: Configurazione dei servizi WCF nel codice
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 193c725d-134f-4d31-a8f8-4e575233bff6
caps.latest.revision: "4"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 134de9fce41ccdcd9c26277c6a52d67823199da3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="configuring-wcf-services-in-code"></a>Configurazione dei servizi WCF nel codice
[!INCLUDE[indigo1](../../../includes/indigo1-md.md)] consente agli sviluppatori di configurare i servizi utilizzando file di configurazione o codice.  I file di configurazione sono utili quando è necessario configurare un servizio dopo la relativa distribuzione. Quando si utilizzano i file di configurazione, un professionista IT deve solo aggiornare il file di configurazione. Non è necessario eseguire la ricompilazione. I file di configurazione, tuttavia, possono risultare complessi e difficili da gestire. Non è disponibile alcun supporto per il debug dei file di configurazione e, poiché il riferimento agli elementi di configurazione viene fatto in base ai nomi, i file di configurazione della creazione possono risultare difficili e soggetti a errori. [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] consente inoltre di configurare i servizi nel codice. Nelle versioni precedenti di [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] (4.0 e versioni precedenti), la configurazione dei servizi nel codice era semplice negli scenari indipendenti. La classe <xref:System.ServiceModel.ServiceHost> consentiva di configurare endpoint e comportamenti prima di chiamare ServiceHost.Open. Negli scenari ospitati dal Web, tuttavia, non è possibile accedere direttamente alla classe <xref:System.ServiceModel.ServiceHost>. Per configurare un servizio ospitato dal Web era necessario creare un oggetto `System.ServiceModel.ServiceHostFactory` che creava l'oggetto <xref:System.ServiceModel.Activation.ServiceHostFactory> ed effettuava qualsiasi configurazione richiesta. A partire da .NET 4.5, [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] fornisce un modo più semplice per configurare sia i servizi indipendenti sia quelli ospitati dal Web nel codice.  
  
## <a name="the-configure-method"></a>Metodo Configure  
 Definire semplicemente un metodo statico pubblico denominato `Configure` con la firma seguente nella classe di implementazione del servizio:  
  
```csharp  
public static void Configure(ServiceConfiguration config)  
```  
  
 Il metodo Configure accetta un'istanza dell'oggetto <xref:System.ServiceModel.ServiceConfiguration> che consente allo sviluppatore di aggiungere endpoint e comportamenti. Questo metodo viene chiamato da [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] prima che venga aperto l'host del servizio. Una volta definito, tutte le impostazioni di configurazione del servizio specificate in un file app.config o web.config verranno ignorate.  
  
 Nel frammento di codice riportato di seguito viene illustrato come definire il metodo `Configure` e aggiungere un endpoint del servizio, un comportamento dell'endpoint e comportamenti del servizio:  
  
```csharp  
public class Service1 : IService1  
    {  
        public static void Configure(ServiceConfiguration config)  
        {  
            ServiceEndpoint se = new ServiceEndpoint(new ContractDescription("IService1"), new BasicHttpBinding(), new EndpointAddress("basic"));  
            se.Behaviors.Add(new MyEndpointBehavior());  
            config.AddServiceEndpoint(se);  
  
            config.Description.Behaviors.Add(new ServiceMetadataBehavior { HttpGetEnabled = true });  
            config.Description.Behaviors.Add(new ServiceDebugBehavior { IncludeExceptionDetailInFaults = true });  
        }  
  
        public string GetData(int value)  
        {  
            return string.Format("You entered: {0}", value);  
        }  
  
        public CompositeType GetDataUsingDataContract(CompositeType composite)  
        {  
            if (composite == null)  
            {  
                throw new ArgumentNullException("composite");  
            }  
            if (composite.BoolValue)  
            {  
                composite.StringValue += "Suffix";  
            }  
            return composite;  
        }  
    }  
```  
  
 Per abilitare un protocollo come HTTPS per un servizio, è possibile aggiungere in modo esplicito un endpoint che utilizza il protocollo oppure aggiungere automaticamente gli endpoint chiamando ServiceConfiguration.EnableProtocol(Binding) che aggiunge un endpoint per ogni indirizzo di base compatibile con il protocollo e ogni contratto di servizio definito. Nel codice seguente viene illustrato come utilizzare il metodo ServiceConfiguration.EnableProtocol:  
  
```csharp  
public class Service1 : IService1   
{   
    public string GetData(int value);   
    public static void Configure(ServiceConfiguration config)   
    {   
        // Enable "Add Service Reference" support   
       config.Description.Behaviors.Add( new ServiceMetadataBehavior { HttpGetEnabled = true });   
       // set up support for http, https, net.tcp, net.pipe   
       config.EnableProtocol(new BasicHttpBinding());   
       config.EnableProtocol(new BasicHttpBinding());   
       config.EnableProtocol(new NetTcpBinding());   
       config.EnableProtocol(new NetNamedPipeBinding());   
       // add an extra BasicHttpBinding endpoint at http:///basic   
       config.AddServiceEndpoint(typeof(IService1), new BasicHttpBinding(),"basic");   
    }   
}   
```  
  
 Le impostazioni di <`protocolMappings`> sezione vengono utilizzati solo se nessun endpoint applicazione aggiunti al <xref:System.ServiceModel.ServiceConfiguration> a livello di codice. Facoltativamente, è possibile caricare la configurazione del servizio dal file di configurazione dell'applicazione predefinito chiamando <xref:System.ServiceModel.ServiceConfiguration.LoadFromConfiguration%2A> e quindi modificare le impostazioni. La classe <xref:System.ServiceModel.ServiceConfiguration.LoadFromConfiguration> consente inoltre di caricare la configurazione da una configurazione centralizzata. Nell'esempio di codice seguente viene illustrato come implementare questa azione:  
  
```  
public class Service1 : IService1   
{   
    public void DoWork();   
    public static void Configure(ServiceConfiguration config)   
    {   
          config.LoadFromConfiguration(ConfigurationManager.OpenMappedExeConfiguration(new ExeConfigurationFileMap { ExeConfigFilename = @"c:\sharedConfig\MyConfig.config" }, ConfigurationUserLevel.None));   
    }   
}  
```  
  
> [!IMPORTANT]
>  Si noti che <xref:System.ServiceModel.ServiceConfiguration.LoadFromConfiguration%2A> Ignora <`host`> impostazioni all'interno di <`service`> tag di <`system.serviceModel`>. Concettualmente, <`host`> di configurazione dell'host, non la configurazione del servizio e si ottiene caricato prima di configurare il metodo viene eseguito.  
  
## <a name="see-also"></a>Vedere anche  
 [Configurazione dei servizi tramite file di configurazione](../../../docs/framework/wcf/configuring-services-using-configuration-files.md)  
 [Configurazione dei comportamenti client](../../../docs/framework/wcf/configuring-client-behaviors.md)  
 [Configurazione semplificata](../../../docs/framework/wcf/simplified-configuration.md)  
 [Attivazione basata sulla configurazione](../../../docs/framework/wcf/samples/configuration-based-activation.md)  
 [Configurazione](../../../docs/framework/wcf/samples/configuration-sample.md)  
 [Attivazione basata sulla configurazione in IIS e WAS](../../../docs/framework/wcf/feature-details/configuration-based-activation-in-iis-and-was.md)  
 [Configurazione e supporto dei metadati](../../../docs/framework/wcf/extending/configuration-and-metadata-support.md)  
 [Configurazione](../../../docs/framework/wcf/diagnostics/exceptions-reference/configuration.md)  
 [Procedura: Specificare un'associazione al servizio nella configurazione](../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md)  
 [Procedura: creare un Endpoint del servizio nella configurazione](../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md)  
 [Procedura: pubblicare metadati per un servizio utilizzando un File di configurazione](../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)  
 [Procedura: Specificare un'associazione al client nella configurazione](../../../docs/framework/wcf/how-to-specify-a-client-binding-in-configuration.md)
