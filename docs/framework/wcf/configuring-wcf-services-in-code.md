---
title: Configurazione dei servizi WCF nel codice
description: Informazioni su come configurare i servizi WCF utilizzando codice anziché file di configurazione per i servizi indipendenti e ospitati sul Web.
ms.date: 03/30/2017
ms.assetid: 193c725d-134f-4d31-a8f8-4e575233bff6
ms.openlocfilehash: d28115236a4582fe251adf1537b9e8b3e996d611
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85245414"
---
# <a name="configuring-wcf-services-in-code"></a>Configurazione dei servizi WCF nel codice
Windows Communication Foundation (WCF) consente agli sviluppatori di configurare i servizi usando i file di configurazione o il codice.  I file di configurazione sono utili quando è necessario configurare un servizio dopo la relativa distribuzione. Quando si utilizzano i file di configurazione, un professionista IT deve solo aggiornare il file di configurazione. Non è necessario eseguire la ricompilazione. I file di configurazione, tuttavia, possono risultare complessi e difficili da gestire. Non è disponibile alcun supporto per il debug dei file di configurazione e, poiché il riferimento agli elementi di configurazione viene fatto in base ai nomi, i file di configurazione della creazione possono risultare difficili e soggetti a errori. WCF consente inoltre di configurare i servizi nel codice. Nelle versioni precedenti di WCF (4,0 e versioni precedenti) la configurazione dei servizi nel codice era molto semplice negli scenari indipendenti, la <xref:System.ServiceModel.ServiceHost> classe consentiva di configurare gli endpoint e i comportamenti prima di chiamare ServiceHost. Open. Negli scenari ospitati dal Web, tuttavia, non è possibile accedere direttamente alla classe <xref:System.ServiceModel.ServiceHost>. Per configurare un servizio ospitato dal Web era necessario creare un oggetto `System.ServiceModel.ServiceHostFactory` che creava l'oggetto <xref:System.ServiceModel.Activation.ServiceHostFactory> ed effettuava qualsiasi configurazione richiesta. A partire da .NET 4,5, WCF fornisce un modo più semplice per configurare i servizi ospitati in modalità self-hosted e Web nel codice.  
  
## <a name="the-configure-method"></a>Metodo Configure  
 Definire semplicemente un metodo statico pubblico denominato `Configure` con la firma seguente nella classe di implementazione del servizio:  
  
```csharp  
public static void Configure(ServiceConfiguration config)  
```  
  
 Il metodo Configure accetta un'istanza dell'oggetto <xref:System.ServiceModel.ServiceConfiguration> che consente allo sviluppatore di aggiungere endpoint e comportamenti. Questo metodo viene chiamato da WCF prima dell'apertura dell'host del servizio. Una volta definito, tutte le impostazioni di configurazione del servizio specificate in un file app.config o web.config verranno ignorate.  
  
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
            return $"You entered: {value}";
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
       config.EnableProtocol(new BasicHttpsBinding());
       config.EnableProtocol(new NetTcpBinding());
       config.EnableProtocol(new NetNamedPipeBinding());
       // add an extra BasicHttpBinding endpoint at http:///basic
       config.AddServiceEndpoint(typeof(IService1), new BasicHttpBinding(),"basic");
    }
}
```  
  
 Le impostazioni nella sezione <`protocolMappings`> vengono utilizzate solo se non viene aggiunto alcun endpoint dell'applicazione a a <xref:System.ServiceModel.ServiceConfiguration> livello di codice. Facoltativamente, è possibile caricare la configurazione del servizio dal file di configurazione dell'applicazione predefinito chiamando <xref:System.ServiceModel.ServiceConfiguration.LoadFromConfiguration%2A> , quindi modificare le impostazioni. La classe <xref:System.ServiceModel.ServiceConfiguration.LoadFromConfiguration> consente inoltre di caricare la configurazione da una configurazione centralizzata. Nell'esempio di codice seguente viene illustrato come implementare questa azione:  
  
```csharp
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
> Si noti che <xref:System.ServiceModel.ServiceConfiguration.LoadFromConfiguration%2A> ignora <`host` Impostazioni> all'interno del `service` tag di> <di <`system.serviceModel`>. Concettualmente, <`host`> riguarda la configurazione host e non la configurazione del servizio e viene caricata prima dell'esecuzione del metodo Configure.  
  
## <a name="see-also"></a>Vedere anche

- [Configurazione dei servizi tramite file di configurazione](configuring-services-using-configuration-files.md)
- [Configurazione dei comportamenti client](configuring-client-behaviors.md)
- [Configurazione semplificata](simplified-configuration.md)
- [Configuration](./samples/configuration-sample.md)
- [Attivazione basata sulla configurazione in IIS e WAS](./feature-details/configuration-based-activation-in-iis-and-was.md)
- [Supporto di configurazione e metadati](./extending/configuration-and-metadata-support.md)
- [Configuration](./diagnostics/exceptions-reference/configuration.md)
- [Procedura: Specificare un'associazione al servizio nella configurazione](how-to-specify-a-service-binding-in-configuration.md)
- [Procedura: creare un endpoint di servizio nella configurazione](./feature-details/how-to-create-a-service-endpoint-in-configuration.md)
- [Procedura: pubblicare metadati per un servizio usando un file di configurazione](./feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [Procedura: Specificare un'associazione al client nella configurazione](how-to-specify-a-client-binding-in-configuration.md)
