---
title: Configurazione semplificata
ms.date: 03/30/2017
ms.assetid: dcbe1f84-437c-495f-9324-2bc09fd79ea9
ms.openlocfilehash: 4e316290c045b75896c61e36c1646440c18678e2
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249630"
---
# <a name="simplified-configuration"></a>Configurazione semplificata
La configurazione dei servizi Windows Communication Foundation (WCF) può essere un'attività complessa. Esistono diverse opzioni e non è sempre semplice determinare quali impostazioni sono necessarie. Mentre i file di configurazione aumentano la flessibilità dei servizi WCF, sono anche l'origine per molti problemi difficili da trovare. In [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] questi problemi vengono risolti e viene offerto un modo per ridurre la dimensione e la complessità della configurazione dei servizi.  
  
## <a name="simplified-configuration"></a>Configurazione semplificata  
 Nei file di configurazione `system.serviceModel` del servizio WCF, la sezione> <contiene un elemento <`service`> per ogni servizio ospitato. L'elemento <`service`> contiene `endpoint` una raccolta di <> elementi che specificano gli endpoint esposti per ogni servizio e, facoltativamente, un set di comportamenti del servizio. Il `endpoint` <> elementi specificano l'indirizzo, l'associazione e il contratto esposti dall'endpoint e, facoltativamente, associano la configurazione e i comportamenti dell'endpoint. La `system.serviceModel` sezione <> `behaviors` contiene anche un elemento <> che consente di specificare i comportamenti del servizio o dell'endpoint. Nell'esempio seguente `system.serviceModel` viene illustrata la sezione> <di un file di configurazione.  
  
```xml  
<system.serviceModel>  
  <behaviors>  
    <serviceBehaviors>  
      <behavior name="MyServiceBehavior">  
        <serviceMetadata httpGetEnabled="true" />  
        <serviceDebug includeExceptionDetailInFaults="false" />  
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
  
 [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)]semplifica la configurazione di un servizio WCF rimuovendo `service` il requisito per l'elemento> <. Se non si aggiunge `service` una sezione> <o `service` si aggiungono endpoint in una sezione <> e il servizio non definisce a livello di codice alcun endpoint, al servizio viene aggiunto automaticamente un set di endpoint predefiniti, uno per ogni indirizzo di base del servizio e per ogni contratto implementato dal servizio. In ognuno di questi endpoint l'indirizzo endpoint corrisponde all'indirizzo di base, l'associazione viene determinata dallo schema dell'indirizzo di base e il contratto corrisponde a quell'implementato dal servizio. Se non è necessario specificare endpoint o comportamenti del servizio oppure apportare modifiche alle impostazioni dell'associazione, non è necessario specificare un file di configurazione dei servizi. Se un servizio implementa due contratti e l'host abilita sia il trasporto HTTP sia quello TCP, l'host del servizio crea quattro endpoint predefiniti, uno per ogni contratto che usa ogni trasporto. Per creare endpoint predefiniti, l'host del servizio deve sapere quali associazioni usare. Queste impostazioni sono specificate in una sezione> <`protocolMappings` all'interno della sezione> <. `system.serviceModel` La `protocolMappings` sezione <> contiene un elenco di schemi di protocollo di trasporto mappati ai tipi di associazione. L'host del servizio usa gli indirizzi di base passati per determinare quale associazione usare. Nell'esempio seguente `protocolMappings` viene utilizzato l'elemento> <.  
  
> [!WARNING]
> La modifica di elementi predefiniti della configurazione, quali associazioni o comportamenti, potrebbe influire sugli eventuali servizi definiti nei livelli inferiori della gerarchia di configurazione che usino tali elementi. Pertanto, quando ci si accinge a modificare le associazioni e i comportamenti predefiniti, tenere sempre presente che tali modifiche potrebbero avere effetto su altri servizi nella gerarchia.  
  
> [!NOTE]
> I servizi ospitati in Internet Information Services (IIS) o nel servizio Attivazione processo Windows (WAS, Windows Process Activation Service) usano la directory virtuale come indirizzo di base.  
  
```xml  
<protocolMapping>  
  <add scheme="http"     binding="basicHttpBinding" bindingConfiguration="MyBindingConfiguration"/>  
  <add scheme="net.tcp"  binding="netTcpBinding"/>  
  <add scheme="net.pipe" binding="netNamedPipeBinding"/>  
  <add scheme="net.msmq" binding="netMSMQBinding"/>  
</protocolMapping>  
```  
  
 Nell'esempio precedente un endpoint con un indirizzo di base che inizia con lo schema "http" usa <xref:System.ServiceModel.BasicHttpBinding>. Un endpoint con un indirizzo di base che inizia con lo schema "net.tcp" usa <xref:System.ServiceModel.NetTcpBinding>. È possibile eseguire l'override delle impostazioni in un file App.config locale o un file Web.config.  
  
 Ogni elemento all'interno della sezione <`protocolMappings`> deve specificare uno schema e un'associazione. Facoltativamente, è `bindingConfiguration` possibile specificare un attributo `bindings` che specifica una configurazione di associazione all'interno della sezione <> del file di configurazione. Se non viene specificato alcun elemento `bindingConfiguration`, viene usata la configurazione di associazione anonima del tipo di associazione appropriata.  
  
 I comportamenti del servizio vengono configurati per `behavior` gli endpoint `serviceBehaviors` predefiniti utilizzando le sezioni di <> anonime all'interno di <sezioni di>. Tutti gli `behavior` elementi di `serviceBehaviors`> <senza nome all'interno di <> vengono utilizzati per configurare i comportamenti del servizio. Il file di configurazione seguente abilita ad esempio la pubblicazione dei metadati del servizio per tutti i servizi all'interno del host.  
  
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
  
 I comportamenti degli endpoint vengono `behavior` configurati utilizzando `serviceBehaviors` le sezioni di> di <anonime all'interno di <sezioni>.  
  
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
> Questa funzionalità si riferisce solo alla configurazione del servizio WCF, non alla configurazione client. Nella maggior parte dei casi, la configurazione client WCF viene generata da uno strumento come svcutil.exe o aggiungendo un riferimento al servizio da Visual Studio. Se si configura manualmente un client WCF, \<sarà necessario aggiungere un elemento client> alla configurazione e specificare gli endpoint che si desidera chiamare.  
  
## <a name="see-also"></a>Vedere anche

- [Configurazione dei servizi tramite file di configurazione](configuring-services-using-configuration-files.md)
- [Configurazione di associazioni per servizi](configuring-bindings-for-wcf-services.md)
- [Configurazione di associazioni fornite dal sistema](./feature-details/configuring-system-provided-bindings.md)
- [Configurazione dei servizi](configuring-services.md)
- [Configurazione dei servizi WCFConfiguring WCF services](configuring-services.md)
- [Configurazione dei servizi WCF nel codice](configuring-wcf-services-in-code.md)
