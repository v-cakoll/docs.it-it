---
title: Configurazione del client
ms.date: 03/30/2017
ms.assetid: 5da5bd3b-65d9-43b7-91b9-cc9e989b1350
ms.openlocfilehash: 2d17438095e65ccf922061c03e406bab35b07c5d
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84593659"
---
# <a name="client-configuration"></a>Configurazione del client
È possibile utilizzare la configurazione client di Windows Communication Foundation (WCF) per specificare l'indirizzo, l'associazione, il comportamento e il contratto, ovvero le proprietà "ABC" dell'endpoint client, che i client utilizzano per connettersi agli endpoint del servizio. L' [\<client>](../../configure-apps/file-schema/wcf/client.md) elemento include un [\<endpoint>](../../configure-apps/file-schema/wcf/endpoint-of-client.md) elemento i cui attributi vengono utilizzati per configurare l'endpoint ABC. Questi attributi sono descritti nella sezione [configurazione degli endpoint](#configuring-endpoints) .  
  
 L' [\<endpoint>](../../configure-apps/file-schema/wcf/endpoint-of-client.md) elemento contiene anche un [\<metadata>](../../configure-apps/file-schema/wcf/metadata.md) elemento utilizzato per specificare le impostazioni per l'importazione e l'esportazione di metadati, un [\<headers>](../../configure-apps/file-schema/wcf/headers.md) elemento che contiene una raccolta di intestazioni di indirizzo personalizzate e un [\<identity>](../../configure-apps/file-schema/wcf/identity.md) elemento che consente di eseguire l'autenticazione di un endpoint da altri endpoint con i quali vengono scambiati messaggi. Gli [\<headers>](../../configure-apps/file-schema/wcf/headers.md) [\<identity>](../../configure-apps/file-schema/wcf/identity.md) elementi e fanno parte di <xref:System.ServiceModel.EndpointAddress> e vengono descritti nell'articolo relativo agli [indirizzi](endpoint-addresses.md) . I collegamenti ad argomenti che illustrano l'utilizzo delle estensioni dei metadati sono disponibili nella sezione [configurazione dei metadati](#configuring-metadata) .  
  
## <a name="configuring-endpoints"></a>Configurazione degli endpoint  
 La configurazione client è progettata per consentire al client di specificare uno o più endpoint, ognuno con nome, indirizzo e contratto, ciascuno dei quali fa riferimento agli [\<bindings>](../../configure-apps/file-schema/wcf/bindings.md) [\<behaviors>](../../configure-apps/file-schema/wcf/behaviors.md) elementi e nella configurazione client da utilizzare per configurare tale endpoint. Il nome del file di configurazione client deve essere "app. config" perché è il nome previsto dal runtime di WCF. Nell'esempio seguente viene illustrato un file di configurazione client.  
  
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
            <!-- Add another endpoint by adding another <endpoint> element. -->
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
          <!-- Configure this binding here. -->  
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
  
 L'attributo `name` facoltativo identifica in modo univoco un endpoint per un dato contratto. In particolare, tale attributo viene utilizzato dal costruttore <xref:System.ServiceModel.ChannelFactory%601.%23ctor%2A> o dal costruttore <xref:System.ServiceModel.ClientBase%601.%23ctor%2A> per specificare l'endpoint della configurazione client da configurare e da caricare quando viene creato un canale per il servizio. È disponibile un nome di configurazione dell'endpoint con caratteri jolly " \* " <xref:System.ServiceModel.ChannelFactory.ApplyConfiguration%2A> , che indica al metodo che deve caricare qualsiasi configurazione dell'endpoint nel file, purché sia disponibile una sola eccezione e in caso contrario genera un'eccezione. Se questo attributo viene omesso, l'endpoint corrispondente viene utilizzato come endpoint predefinito associato al tipo di contratto specificato. Il valore predefinito dell'attributo `name` è una stringa vuota a cui si fa riferimento con le stesse modalità utilizzate per qualsiasi altro nome.  
  
 Affinché possa essere individuato e identificato, ogni endpoint deve presentare un indirizzo. L'attributo `address` può essere utilizzato per specificare l'URL che indica la posizione dell'endpoint. Tuttavia, l'indirizzo di un endpoint di servizio può anche essere specificato in codice creando un Uniform Resource Identifier (URI) e aggiungendo tale identificatore all'elemento <xref:System.ServiceModel.ServiceHost> tramite uno dei metodi <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A>. Per ulteriori informazioni, vedere [indirizzi](endpoint-addresses.md). Come indicato nell'introduzione, gli [\<headers>](../../configure-apps/file-schema/wcf/headers.md) [\<identity>](../../configure-apps/file-schema/wcf/identity.md) elementi e fanno parte di <xref:System.ServiceModel.EndpointAddress> e vengono descritti anche nell'argomento degli [indirizzi](endpoint-addresses.md) .  
  
 L'attributo `binding` indica il tipo di associazione che l'endpoint prevede di utilizzare per la connessione a un servizio. Se si prevede di fare riferimento al tipo occorre registrare per quest'ultimo una sezione di configurazione. Nell'esempio precedente, si tratta della [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) sezione, che indica che l'endpoint usa un oggetto <xref:System.ServiceModel.WSHttpBinding> . È tuttavia possibile che l'endpoint utilizzi più di un'associazione di un determinato tipo. Ognuno di questi dispone di un proprio [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) elemento all'interno dell'elemento di tipo (Binding). L'attributo `bindingconfiguration` viene utilizzato per distinguere le associazioni dello stesso tipo. Il relativo valore corrisponde all' `name` attributo dell' [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) elemento. Per altre informazioni su come configurare un'associazione client usando la configurazione, vedere [procedura: specificare un'associazione client nella configurazione](../how-to-specify-a-client-binding-in-configuration.md).  
  
 L' `behaviorConfiguration` attributo viene utilizzato per specificare quale dell' [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) [\<endpointBehaviors>](../../configure-apps/file-schema/wcf/endpointbehaviors.md) endpoint deve utilizzare. Il relativo valore corrisponde all' `name` attributo dell' [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) elemento. Per un esempio di utilizzo della configurazione per specificare i comportamenti dei client, vedere [Configuring Client Behaviors](../configuring-client-behaviors.md).  
  
 L'attributo `contract` specifica il contratto esposto dall'endpoint. Questo valore fa riferimento alla proprietà <xref:System.ServiceModel.ServiceContractAttribute.ConfigurationName%2A> dell'attributo <xref:System.ServiceModel.ServiceContractAttribute>. Il valore predefinito è il nome di tipo completo della classe che implementa il servizio.  
  
### <a name="configuring-metadata"></a>Configurazione di metadati  
 L' [\<metadata>](../../configure-apps/file-schema/wcf/metadata.md) elemento viene utilizzato per specificare le impostazioni utilizzate per registrare le estensioni di importazione dei metadati. Per ulteriori informazioni sull'estensione del sistema di metadati, vedere [estensione del sistema di metadati](../extending/extending-the-metadata-system.md).  
  
## <a name="see-also"></a>Vedere anche

- [Endpoint: indirizzi, associazioni e contratti](endpoints-addresses-bindings-and-contracts.md)
- [Configurazione dei comportamenti client](../configuring-client-behaviors.md)
