---
title: Configurazione semplificata
ms.date: 03/30/2017
ms.assetid: dcbe1f84-437c-495f-9324-2bc09fd79ea9
ms.openlocfilehash: 13cf8bd46ef3aabb011cb2ddd207963235468662
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59184054"
---
# <a name="simplified-configuration"></a>Configurazione semplificata
Configurazione dei servizi Windows Communication Foundation (WCF) può essere un'attività complessa. Esistono diverse opzioni e non è sempre semplice determinare quali impostazioni sono necessarie. Mentre i file di configurazione aumentano la flessibilità dei servizi WCF, sono anche l'origine di molti problemi difficili da individuare. In [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] questi problemi vengono risolti e viene offerto un modo per ridurre la dimensione e la complessità della configurazione dei servizi.  
  
## <a name="simplified-configuration"></a>Configurazione semplificata  
 Nei file di configurazione del servizio WCF, la <`system.serviceModel`> della sezione sono un <`service`> (elemento) per ogni servizio ospitato. Il <`service`> elemento contiene una raccolta di <`endpoint`> gli elementi che specificano gli endpoint esposti per ogni servizio e facoltativamente un set di comportamenti del servizio. Il <`endpoint`> elementi specificano l'indirizzo, associazione e contratto esposti dall'endpoint e facoltativamente la configurazione di associazione e i comportamenti dell'endpoint. Il <`system.serviceModel`> sezione contiene inoltre un <`behaviors`> elemento che consente di specificare i comportamenti del servizio o dell'endpoint. L'esempio seguente mostra il <`system.serviceModel`> sezione di un file di configurazione.  
  
```  
<system.serviceModel>  
  <behaviors>  
    <serviceBehaviors>  
      <behavior name="MyServiceBehavior">  
        <serviceMetadata httpGetEnabled="true">  
        <serviceDebug includeExceptionDetailInFaults="false">  
      </behavior>  
    </serviceBehaviors>  
  </behaviors>  
  <bindings>  
   <basicHttpBinding>  
      <binding name=MyBindingConfig"  
               maxBufferSize="100"  
               maxReceiveBufferSize="100" />  
   </basicHttpBinding>  
   </bindings>   <services>  
    <service behaviorConfiguration="MyServiceBehavior"  
             name="MyService">  
      <endpoint address=""  
                binding="basicHttpBinding"  
                contract="ICalculator"  
                bindingConfiguration="MyBindingConfig" />  
      <endpoint address="mex"  
                binding="mexHttpBinding"  
                contract="IMetadataExchange"/>  
    </service>  
  </services>  
</system.serviceModel>  
```  
  
 [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] facilita la configurazione di un servizio WCF semplice rimuovendo il requisito per la <`service`> elemento. Se non si aggiunge un <`service`> sezione o nessun endpoint in un <`service`> sezione e il servizio non definisce a livello di codice tutti gli endpoint e quindi un set di endpoint predefiniti vengono aggiunti automaticamente al servizio, uno per ogni indirizzo di base del servizio e per ogni contratto implementato dal servizio. In ognuno di questi endpoint l'indirizzo endpoint corrisponde all'indirizzo di base, l'associazione viene determinata dallo schema dell'indirizzo di base e il contratto corrisponde a quell'implementato dal servizio. Se non è necessario specificare endpoint o comportamenti del servizio oppure apportare modifiche alle impostazioni dell'associazione, non è necessario specificare un file di configurazione dei servizi. Se un servizio implementa due contratti e l'host abilita sia il trasporto HTTP sia quello TCP, l'host del servizio crea quattro endpoint predefiniti, uno per ogni contratto che usa ogni trasporto. Per creare endpoint predefiniti, l'host del servizio deve sapere quali associazioni usare. Queste impostazioni vengono specificate un <`protocolMappings`> sezione all'interno di <`system.serviceModel`> sezione. Il <`protocolMappings`> sezione contiene un elenco degli schemi di protocollo di trasporto mappati ai tipi di associazione. L'host del servizio usa gli indirizzi di base passati per determinare quale associazione usare. L'esempio seguente usa il <`protocolMappings`> elemento.  
  
> [!WARNING]
>  La modifica di elementi predefiniti della configurazione, quali associazioni o comportamenti, potrebbe influire sugli eventuali servizi definiti nei livelli inferiori della gerarchia di configurazione che usino tali elementi. Pertanto, quando ci si accinge a modificare le associazioni e i comportamenti predefiniti, tenere sempre presente che tali modifiche potrebbero avere effetto su altri servizi nella gerarchia.  
  
> [!NOTE]
>  I servizi ospitati in Internet Information Services (IIS) o nel servizio Attivazione processo Windows (WAS, Windows Process Activation Service) usano la directory virtuale come indirizzo di base.  
  
```xml  
<protocolMapping>  
  <add scheme="http"     binding="basicHttpBinding" bindingConfiguration="MyBindingConfiguration"/>  
  <add scheme="net.tcp"  binding="netTcpBinding"/>  
  <add scheme="net.pipe" binding="netNamedPipeBinding"/>  
  <add scheme="net.msmq" binding="netMSMQBinding"/>  
</protocolMapping>  
```  
  
 Nell'esempio precedente un endpoint con un indirizzo di base che inizia con lo schema "http" usa <xref:System.ServiceModel.BasicHttpBinding>. Un endpoint con un indirizzo di base che inizia con lo schema "net.tcp" usa <xref:System.ServiceModel.NetTcpBinding>. È possibile eseguire l'override delle impostazioni in un file App.config locale o un file Web.config.  
  
 Ogni elemento all'interno di <`protocolMappings`> sezione deve specificare uno schema e un'associazione. Facoltativamente, è possibile specificare una `bindingConfiguration` attributo che specifica una configurazione dell'associazione all'interno di <`bindings`> sezione del file di configurazione. Se non viene specificato alcun elemento `bindingConfiguration`, viene usata la configurazione di associazione anonima del tipo di associazione appropriata.  
  
 I comportamenti del servizio vengono configurati per gli endpoint predefiniti tramite anonimo <`behavior`> all'interno delle sezioni <`serviceBehaviors`> sezioni. Qualsiasi senza nome <`behavior`> elementi all'interno di <`serviceBehaviors`> vengono usati per configurare i comportamenti del servizio. Il file di configurazione seguente abilita ad esempio la pubblicazione dei metadati del servizio per tutti i servizi all'interno del host.  
  
```xml  
<system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior>  
          <serviceMetadata httpGetEnabled="True"/>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>    <!-- No <service> tag is necessary. Default endpoints are added to the service -->  
    <!-- The service behavior with name="" is picked up by the service -->  
 </system.serviceModel>  
```  
  
 I comportamenti dell'endpoint vengono configurati tramite anonimo <`behavior`> all'interno delle sezioni <`serviceBehaviors`> sezioni.  
  
 L'esempio seguente è costituito da un file di configurazione equivalente a quello indicato all'inizio di questo argomento che usa il modello di configurazione semplificato.  
  
```xml  
<system.serviceModel>
    <behaviors>
      <serviceBehaviors>
        <behavior>
          <serviceMetadata httpGetEnabled="true" />
          <serviceDebug includeExceptionDetailInFaults="false" />
        </behavior>
      </serviceBehaviors>
    </behaviors>
    <bindings>
       <basicHttpBinding>
          <binding maxBufferSize="100"
                   maxReceiveBufferSize="100" />
       </basicHttpBinding>
    </bindings>
    <!-- No <service> tag is necessary. Default endpoints will be added to the service -->
    <!-- The service behavior with name="" will be picked up by the service -->
    <protocolMapping>
      <add scheme="http" binding="basicHttpBinding" />
  </protocolMapping>
  </system.serviceModel>
```  
  
> [!IMPORTANT]
>  Questa funzionalità si riferisce solo alla configurazione del servizio WCF, non alla configurazione client. Nella maggior parte dei casi, la configurazione client WCF viene generata da uno strumento come svcutil.exe o aggiungendo un riferimento al servizio da Visual Studio. Se si configura manualmente un client WCF, è necessario aggiungere un \<client > elemento alla configurazione e specificare tutti gli endpoint da chiamare.  
  
## <a name="see-also"></a>Vedere anche

- [Configurazione dei servizi tramite file di configurazione](../../../docs/framework/wcf/configuring-services-using-configuration-files.md)
- [Configurazione delle associazioni per i servizi](../../../docs/framework/wcf/configuring-bindings-for-wcf-services.md)
- [Configurazione di associazioni fornite dal sistema](../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [Configurazione dei servizi](../../../docs/framework/wcf/configuring-services.md)
- [Configurazione dei servizi WCF](configuring-services.md)
- [Configurazione dei servizi WCF nel codice](../../../docs/framework/wcf/configuring-wcf-services-in-code.md)
