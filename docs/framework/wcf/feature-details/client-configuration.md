---
title: Configurazione del client
ms.date: 03/30/2017
ms.assetid: 5da5bd3b-65d9-43b7-91b9-cc9e989b1350
ms.openlocfilehash: b9975c6caeedc94bf4a7773e71a95eb0d8c7aed2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59144690"
---
# <a name="client-configuration"></a>Configurazione del client
È possibile usare la configurazione del client Windows Communication Foundation (WCF) per specificare l'indirizzo, associazione, comportamento e contratto, le proprietà di "ABC" dell'endpoint client, quali i client usano per connettersi agli endpoint del servizio. Il [ \<client >](../../configure-apps/file-schema/wcf/client.md) elemento dispone di un [ \<endpoint >](../../configure-apps/file-schema/wcf/endpoint-of-client.md) cui attributi consentono di configurare l'endpoint di base sull'elemento. Questi attributi vengono discussi nel [configurazione degli endpoint](#configuring-endpoints) sezione.  
  
 Il [ \<endpoint >](../../configure-apps/file-schema/wcf/endpoint-of-client.md) elemento contiene anche una [ \<metadati >](../../configure-apps/file-schema/wcf/metadata.md) elemento usato per specificare le impostazioni di importazione ed esportazione dei metadati, un [ \<intestazioni >](../../configure-apps/file-schema/wcf/headers.md) elemento che contiene una raccolta di intestazioni di indirizzo personalizzate, e un [ \<identità >](../../configure-apps/file-schema/wcf/identity.md) elemento che consente l'autenticazione di un endpoint da altri endpoint con cui scambia messaggi. Il [ \<intestazioni >](../../configure-apps/file-schema/wcf/headers.md) e [ \<identità >](../../configure-apps/file-schema/wcf/identity.md) elementi fanno parte del <xref:System.ServiceModel.EndpointAddress> e sono descritti nella [indirizzi](../../wcf/feature-details/endpoint-addresses.md) articolo. Vengono forniti collegamenti ad argomenti che illustrano l'uso delle estensioni di metadati nel [configurazione di metadati](#configuring-metadata) sezione.  
  
## <a name="configuring-endpoints"></a>Configurazione degli endpoint  
 La configurazione del client è progettata per consentire al client di specificare uno o più endpoint, ognuno con il proprio nome, indirizzo e contratto, con ogni tipo di riferimento il [ \<associazioni >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) e [ \< i comportamenti >](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) elementi della configurazione del client da utilizzare per configurare tale endpoint. Il file di configurazione client deve essere denominato "App" poiché si tratta del nome che si aspetta che il runtime di WCF. Nell'esempio seguente viene illustrato un file di configurazione client.  
  
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
  
 L'attributo `name` facoltativo identifica in modo univoco un endpoint per un dato contratto. In particolare, tale attributo viene utilizzato dal costruttore <xref:System.ServiceModel.ChannelFactory%601.%23ctor%2A> o dal costruttore <xref:System.ServiceModel.ClientBase%601.%23ctor%2A> per specificare l'endpoint della configurazione client da configurare e da caricare quando viene creato un canale per il servizio. Un nome di configurazione di endpoint con caratteri jolly "\*" è disponibile e indica al <xref:System.ServiceModel.ChannelFactory.ApplyConfiguration%2A> metodo carica qualsiasi configurazione di endpoint nel file specificato è presente esattamente uno disponibile e in caso contrario, genera un'eccezione. Se questo attributo viene omesso, l'endpoint corrispondente viene utilizzato come endpoint predefinito associato al tipo di contratto specificato. Il valore predefinito dell'attributo `name` è una stringa vuota a cui si fa riferimento con le stesse modalità utilizzate per qualsiasi altro nome.  
  
 Affinché possa essere individuato e identificato, ogni endpoint deve presentare un indirizzo. L'attributo `address` può essere utilizzato per specificare l'URL che indica la posizione dell'endpoint. Tuttavia, l'indirizzo di un endpoint di servizio può anche essere specificato in codice creando un Uniform Resource Identifier (URI) e aggiungendo tale identificatore all'elemento <xref:System.ServiceModel.ServiceHost> tramite uno dei metodi <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A>. Per altre informazioni, vedere [indirizzi](../../../../docs/framework/wcf/feature-details/endpoint-addresses.md). Come indica l'introduzione, il [ \<intestazioni >](../../../../docs/framework/configure-apps/file-schema/wcf/headers.md) e [ \<identità >](../../../../docs/framework/configure-apps/file-schema/wcf/identity.md) elementi fanno parte del <xref:System.ServiceModel.EndpointAddress> e vengono illustrati anche nel [ Gli indirizzi](../../../../docs/framework/wcf/feature-details/endpoint-addresses.md) argomento.  
  
 L'attributo `binding` indica il tipo di associazione che l'endpoint prevede di utilizzare per la connessione a un servizio. Se si prevede di fare riferimento al tipo occorre registrare per quest'ultimo una sezione di configurazione. Nell'esempio precedente, questo è il [ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) sezione, che indica che l'endpoint utilizza un <xref:System.ServiceModel.WSHttpBinding>. È tuttavia possibile che l'endpoint utilizzi più di un'associazione di un determinato tipo. Ognuno di questi dispone di propri [ \<associazione >](../../../../docs/framework/misc/binding.md) elemento nell'elemento type (binding). L'attributo `bindingconfiguration` viene utilizzato per distinguere le associazioni dello stesso tipo. Il relativo valore viene confrontato con il `name` attributo del [ \<associazione >](../../../../docs/framework/misc/binding.md) elemento. Per altre informazioni su come configurare un client di associazione utilizzando la configurazione, vedere [come: Specificare un'associazione Client nella configurazione](../../../../docs/framework/wcf/how-to-specify-a-client-binding-in-configuration.md).  
  
 Il `behaviorConfiguration` attributo è usato per specificare quali [ \<comportamento >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) del [ \<endpointBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/endpointbehaviors.md) l'endpoint deve utilizzare. Il relativo valore viene confrontato con il `name` attributo del [ \<comportamento >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) elemento. Per un esempio di utilizzo della configurazione per specificare i comportamenti dei client, vedere [configurazione dei comportamenti Client](../../../../docs/framework/wcf/configuring-client-behaviors.md).  
  
 L'attributo `contract` specifica il contratto esposto dall'endpoint. Questo valore fa riferimento alla proprietà <xref:System.ServiceModel.ServiceContractAttribute.ConfigurationName%2A> dell'attributo <xref:System.ServiceModel.ServiceContractAttribute>. Il valore predefinito è il nome di tipo completo della classe che implementa il servizio.  
  
### <a name="configuring-metadata"></a>Configurazione di metadati  
 Il [ \<metadati >](../../../../docs/framework/configure-apps/file-schema/wcf/metadata.md) elemento viene usato per specificare le impostazioni utilizzate per registrare i metadati di importazione delle estensioni. Per altre informazioni sull'estensione del sistema di metadati, vedere [estensione del sistema di metadati](../../../../docs/framework/wcf/extending/extending-the-metadata-system.md).  
  
## <a name="see-also"></a>Vedere anche

- [Endpoint: indirizzi, associazioni e contratti](../../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)
- [Configurazione dei comportamenti client](../../../../docs/framework/wcf/configuring-client-behaviors.md)
