---
title: Configurazione del client
ms.date: 03/30/2017
ms.assetid: 5da5bd3b-65d9-43b7-91b9-cc9e989b1350
ms.openlocfilehash: ff82f56639ec451c04624d22fff0bcb03f46d946
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185367"
---
# <a name="client-configuration"></a>Configurazione del client
È possibile utilizzare la configurazione client di Windows Communication Foundation (WCF) per specificare l'indirizzo, l'associazione, il comportamento e il contratto, le proprietà "ABC" dell'endpoint client, usate dai client per connettersi agli endpoint del servizio. L'elemento [ \<>client](../../configure-apps/file-schema/wcf/client.md) dispone di un [ \<](../../configure-apps/file-schema/wcf/endpoint-of-client.md) elemento>endpoint i cui attributi vengono utilizzati per configurare gli ABC dell'endpoint. Questi attributi sono descritti nella sezione [Configurazione degli endpoint.](#configuring-endpoints)  
  
 [ \<L'elemento>endpoint](../../configure-apps/file-schema/wcf/endpoint-of-client.md) contiene anche un [ \<](../../configure-apps/file-schema/wcf/headers.md) [ \<](../../configure-apps/file-schema/wcf/metadata.md) elemento>metadati utilizzato per specificare le impostazioni per l'importazione [ \<](../../configure-apps/file-schema/wcf/identity.md) e l'esportazione di metadati, un elemento>intestazioni che contiene una raccolta di intestazioni di indirizzi personalizzate e un elemento>di identità che consente l'autenticazione di un endpoint da parte di altri endpoint che scambiano messaggi con esso. Le [ \<intestazioni>](../../configure-apps/file-schema/wcf/headers.md) e <xref:System.ServiceModel.EndpointAddress> [ \<gli](../../configure-apps/file-schema/wcf/identity.md) elementi>identità fanno parte di e sono illustrati nell'articolo [Indirizzi.](../../wcf/feature-details/endpoint-addresses.md) I collegamenti agli argomenti che illustrano l'utilizzo delle estensioni di metadati sono disponibili nella sezione [Configurazione dei metadati.](#configuring-metadata)  
  
## <a name="configuring-endpoints"></a>Configurazione degli endpoint  
 La configurazione client è progettata per consentire al client di specificare uno o più endpoint, ognuno con il proprio nome, indirizzo e contratto, ognuno dei quali fa riferimento alle [ \<associazioni>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) e [ \<ai comportamenti>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) elementi nella configurazione client vengano utilizzati per configurare tale endpoint. Il file di configurazione client deve essere denominato "App.config" perché questo è il nome previsto dal runtime WCF. Nell'esempio seguente viene illustrato un file di configurazione client.  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
        <client>  
          <endpoint  
            name="endpoint1"  
            address="http://localhost/ServiceModelSamples/service.svc"  
            binding="wsHttpBinding"  
            bindingConfiguration="WSHttpBinding_IHello"  
            behaviorConfiguration="IHello_Behavior"  
            contract="IHello" >  
  
            <metadata>  
              <wsdlImporters>  
                <extension  
                  type="Microsoft.ServiceModel.Samples.WsdlDocumentationImporter, WsdlDocumentation"/>  
              </wsdlImporters>  
            </metadata>  
  
            <identity>  
              <servicePrincipalName value="host/localhost" />  
            </identity>  
          </endpoint>  
// Add another endpoint by adding another <endpoint> element.  
          <endpoint  
            name="endpoint2">  
           //Configure another endpoint here.  
          </endpoint>  
        </client>  
  
//The bindings section references by the bindingConfiguration endpoint attribute.  
    <bindings>  
      <wsHttpBinding>  
        <binding name="WSHttpBinding_IHello"
                 bypassProxyOnLocal="false"
                 hostNameComparisonMode="StrongWildcard">  
          <readerQuotas maxDepth="32"/>  
          <reliableSession ordered="true"
                           enabled="false" />  
          <security mode="Message">  
           //Security settings go here.  
          </security>  
        </binding>  
        <binding name="Another Binding"  
        //Configure this binding here.  
        </binding>  
          </wsHttpBinding>  
        </bindings>  
  
//The behavior section references by the behaviorConfiguration endpoint attribute.  
        <behaviors>  
            <endpointBehaviors>  
                <behavior name=" IHello_Behavior ">  
                    <clientVia />  
                </behavior>  
            </endpointBehaviors>  
        </behaviors>  
  
    </system.serviceModel>  
</configuration>  
```  
  
 L'attributo `name` facoltativo identifica in modo univoco un endpoint per un dato contratto. In particolare, tale attributo viene utilizzato dal costruttore <xref:System.ServiceModel.ChannelFactory%601.%23ctor%2A> o dal costruttore <xref:System.ServiceModel.ClientBase%601.%23ctor%2A> per specificare l'endpoint della configurazione client da configurare e da caricare quando viene creato un canale per il servizio. Un nome di\*configurazione dell'endpoint con <xref:System.ServiceModel.ChannelFactory.ApplyConfiguration%2A> caratteri jolly " " è disponibile e indica al metodo che deve caricare qualsiasi configurazione dell'endpoint nel file, a condizione che ne sia esattamente uno disponibile, e in caso contrario genera un'eccezione. Se questo attributo viene omesso, l'endpoint corrispondente viene utilizzato come endpoint predefinito associato al tipo di contratto specificato. Il valore predefinito dell'attributo `name` è una stringa vuota a cui si fa riferimento con le stesse modalità utilizzate per qualsiasi altro nome.  
  
 Affinché possa essere individuato e identificato, ogni endpoint deve presentare un indirizzo. L'attributo `address` può essere utilizzato per specificare l'URL che indica la posizione dell'endpoint. Tuttavia, l'indirizzo di un endpoint di servizio può anche essere specificato in codice creando un Uniform Resource Identifier (URI) e aggiungendo tale identificatore all'elemento <xref:System.ServiceModel.ServiceHost> tramite uno dei metodi <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A>. Per ulteriori informazioni, vedere [Indirizzi](../../../../docs/framework/wcf/feature-details/endpoint-addresses.md). Come <xref:System.ServiceModel.EndpointAddress> indicato nell'introduzione, le [ \<intestazioni>](../../../../docs/framework/configure-apps/file-schema/wcf/headers.md) e [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/identity.md) gli elementi>di identità fanno parte di e sono descritti anche nell'argomento [Addresses.](../../../../docs/framework/wcf/feature-details/endpoint-addresses.md)  
  
 L'attributo `binding` indica il tipo di associazione che l'endpoint prevede di utilizzare per la connessione a un servizio. Se si prevede di fare riferimento al tipo occorre registrare per quest'ultimo una sezione di configurazione. Nell'esempio precedente, si tratta della <xref:System.ServiceModel.WSHttpBinding> [ \<sezione>wsHttpBinding,](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) che indica che l'endpoint utilizza un file . È tuttavia possibile che l'endpoint utilizzi più di un'associazione di un determinato tipo. Ognuno di questi [ \<](../../configure-apps/file-schema/wcf/bindings.md) ha il proprio elemento di associazione>all'interno dell'elemento di tipo (associazione). L'attributo `bindingconfiguration` viene utilizzato per distinguere le associazioni dello stesso tipo. Il valore viene confrontato con l'attributo `name` dell'elemento [ \<>di associazione.](../../configure-apps/file-schema/wcf/bindings.md) Per ulteriori informazioni su come configurare un'associazione client utilizzando la configurazione, vedere [Procedura: specificare un'associazione client nella configurazione](../../../../docs/framework/wcf/how-to-specify-a-client-binding-in-configuration.md).  
  
 L'attributo `behaviorConfiguration` viene utilizzato per specificare il [ \<comportamento](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) che>degli [ \<endpointBehaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/endpointbehaviors.md) l'endpoint deve utilizzare. Il valore viene confrontato con l'attributo `name` [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) del comportamento>elemento. Per un esempio di utilizzo della configurazione per specificare i comportamenti client, vedere [Configurazione dei comportamenti client](../../../../docs/framework/wcf/configuring-client-behaviors.md).  
  
 L'attributo `contract` specifica il contratto esposto dall'endpoint. Questo valore fa riferimento alla proprietà <xref:System.ServiceModel.ServiceContractAttribute.ConfigurationName%2A> dell'attributo <xref:System.ServiceModel.ServiceContractAttribute>. Il valore predefinito è il nome di tipo completo della classe che implementa il servizio.  
  
### <a name="configuring-metadata"></a>Configurazione di metadati  
 L'elemento [ \<>metadati](../../../../docs/framework/configure-apps/file-schema/wcf/metadata.md) viene utilizzato per specificare le impostazioni utilizzate per registrare le estensioni di importazione dei metadati. Per ulteriori informazioni sull'estensione del sistema di metadati, consultate [Estensione del sistema di metadati.](../../../../docs/framework/wcf/extending/extending-the-metadata-system.md)  
  
## <a name="see-also"></a>Vedere anche

- [Endpoint: indirizzi, associazioni e contratti](../../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)
- [Configurazione dei comportamenti client](../../../../docs/framework/wcf/configuring-client-behaviors.md)
