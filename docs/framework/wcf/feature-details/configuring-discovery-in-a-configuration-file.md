---
title: Configurazione dell'individuazione in un file di configurazione
ms.date: 03/30/2017
ms.assetid: b9884c11-8011-4763-bc2c-c526b80175d0
ms.openlocfilehash: 59eaecb7e34b9105bc694f444d98c13c036d552f
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84597553"
---
# <a name="configuring-discovery-in-a-configuration-file"></a>Configurazione dell'individuazione in un file di configurazione
Nell'individuazione vengono usati quattro gruppi principali di impostazioni di configurazione. In questo argomento viene illustrato brevemente ciascuno di questi gruppi e vengono mostrati esempi per poterli configurare. Al termine di ogni sezione sarà disponibile un collegamento a documenti più dettagliati su ogni area.  
  
## <a name="behavior-configuration"></a>Comportamento di configurazione  
 L'individuazione usa comportamenti del servizio e dell'endpoint. Il comportamento <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> abilita l'individuazione per tutti gli endpoint di un servizio e consente di specificare endpoint annunci.  Nell'esempio seguente viene illustrato come aggiungere l'elemento <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> e specificare un endpoint annunci.  
  
```xml  
<behaviors>  
      <serviceBehaviors>  
        <behavior name="helloWorldServiceBehavior">  
          <serviceDiscovery>  
            <announcementEndpoints>  
              <endpoint kind="udpAnnouncementEndpoint"/>  
            </announcementEndpoints>  
          </serviceDiscovery>  
        </behavior>  
      </serviceBehaviors>  
</behaviors>  
```  
  
 Una volta specificato il comportamento, farvi riferimento da un `service` elemento <>, come illustrato nell'esempio seguente.  
  
```xml  
<system.serviceModel>  
   <services>  
      <service name="HelloWorldService" behaviorConfiguration="helloWorldServiceBehavior">  
         <!-- Application Endpoint -->  
         <endpoint address="endpoint0"  
                   binding="basicHttpBinding"  
                   contract="IHelloWorldService" />  
         <!-- Discovery Endpoints -->  
         <endpoint kind="udpDiscoveryEndpoint" />  
        </service>  
    </services>  
</system.serviceModel>  
```  
  
 Affinché un servizio sia individuabile, è necessario aggiungere anche un endpoint di individuazione. Nell'esempio precedente viene aggiunto un endpoint <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> standard.  
  
 Quando si aggiungono endpoint degli annunci, è necessario aggiungere anche un servizio listener di annunci all' `services` elemento <>, come illustrato nell'esempio seguente.  
  
```xml  
<services>  
   <service name="HelloWorldService" behaviorConfiguration="helloWorldServiceBehavior">  
      <!-- Application Endpoint -->  
      <endpoint address="endpoint0"  
                binding="basicHttpBinding"  
                contract="IHelloWorldService" />  
      <!-- Discovery Endpoints -->  
      <endpoint kind="udpDiscoveryEndpoint" />  
   </service>  
   <!-- Announcement Listener Configuration -->  
   <service name="AnnouncementListener">  
      <endpoint kind="udpAnnouncementEndpoint" />  
   </service>  
</services>
```  
  
 Il comportamento <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior> viene usato per abilitare o disabilitare l'individuazione di un endpoint specifico.  Nell'esempio seguente viene configurato un servizio con due endpoint dell'applicazione, uno con l'individuazione abilitata e uno con l'individuazione disabilitata. Per ogni endpoint viene aggiunto un comportamento <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>.  
  
```xml  
<system.serviceModel>  
   <services>  
      <service name="HelloWorldService"  
               behaviorConfiguration="helloWorldServiceBehavior">  
  
        <!-- Application Endpoints -->  
        <endpoint address="endpoint0"  
                 binding="basicHttpBinding"  
                 contract="IHelloWorldService"
                 behaviorConfiguration="ep0Behavior" />  
  
        <endpoint address="endpoint1"  
                  binding="basicHttpBinding"  
                  contract="IHelloWorldService"  
                  behaviorConfiguration="ep1Behavior" />  
  
        <!-- Discovery Endpoints -->  
        <endpoint kind="udpDiscoveryEndpoint" />  
      </service>  
   </services>  
   <behaviors>  
      <serviceBehaviors>  
        <behavior name="helloWorldServiceBehavior">  
          <serviceDiscovery />  
        </behavior>  
      </serviceBehaviors>  
      <endpointBehaviors>  
        <behavior name="ep0Behavior">  
          <endpointDiscovery enabled="true"/>  
        </behavior>  
        <behavior name="ep1Behavior">  
          <endpointDiscovery enabled="false"/>  
        </behavior>  
     </endpointBehaviors>  
   </behaviors>  
</system.serviceModel>  
```  
  
 Il comportamento <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior> può essere inoltre usato per aggiungere metadati personalizzati ai metadati dell'endpoint restituiti dal servizio. L'esempio seguente illustra come farlo.  
  
```xml  
<behavior name="ep4Behavior">  
   <endpointDiscovery enabled="true">  
      <extensions>  
         <CustomMetadata>This is custom metadata.</CustomMetadata>  
         <d:Types xmlns:d="http://schemas.xmlsoap.org/ws/2005/04/discovery" xmlns:i="http://printer.example.org/2003/imaging">i:PrintBasic</d:Types>  
         <CustomMetadata netsted="true">  
            <NestedMetadata>This is a nested custom metadata.</NestedMetadata>  
         </CustomMetadata>  
      </extensions>  
   </endpointDiscovery>  
</behavior>  
```  
  
 Il comportamento <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior> può essere inoltre usato per aggiungere ambiti e tipi usati dai client per cercare servizi. Nell'esempio seguente viene descritto come effettuare questa operazione in un file di configurazione lato client.  
  
```xml  
<behavior name="ep2Behavior">  
   <endpointDiscovery enabled="true">  
      <scopes>  
         <add scope="http://www.microsoft.com/building42/floor1"/>  
         <add scope="ldap:///ou=engineeringo=examplecomc=us"/>  
      </scopes>  
      <types>  
         <add name="test" namespace="http://example.microsoft.com/" />  
         <add name="additionalContract" namespace="http://example.microsoft.com/" />  
      </types>  
   </endpointDiscovery>  
</behavior>  
```  
  
 Per ulteriori informazioni su <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> e <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior> vedere [Cenni preliminari sull'individuazione WCF](wcf-discovery-overview.md).  
  
## <a name="binding-element-configuration"></a>Configurazione di elementi di associazione  
 La configurazione degli elementi di associazione è particolarmente interessante nel lato client. È possibile usare la configurazione per specificare i criteri di ricerca usata per individuare servizi da un'applicazione client WCF.  Nell'esempio seguente viene creata un'associazione personalizzata con il canale <xref:System.ServiceModel.Discovery.DiscoveryClient> e vengono specificati criteri di ricerca che includono un tipo e un ambito. Vengono inoltre specificati valori per le proprietà <xref:System.ServiceModel.Discovery.FindCriteria.Duration%2A> e <xref:System.ServiceModel.Discovery.FindCriteria.MaxResults%2A>.  
  
```xml  
<bindings>  
   <customBinding>  
      <!-- Binding Configuration for the Application Endpoint -->  
      <binding name="discoBindingConfiguration">  
         <discoveryClient>  
            <endpoint kind="discoveryEndpoint"  
                      address="http://localhost:8000/ConfigTest/Discovery"  
                      binding="customBinding"  
                      bindingConfiguration="httpSoap12WSAddressing10"/>  
            <findCriteria duration="00:00:10" maxResults="2">  
              <types>  
                <add name="IHelloWorldService"/>  
              </types>  
              <scopes>  
                <add scope="http://www.microsoft.com/building42/floor1"/>  
              </scopes>
            </findCriteria>  
          </discoveryClient>  
          <textMessageEncoding messageVersion="Soap11"/>  
          <httpTransport />  
      </binding>
   </customBinding>
</bindings>  
```  
  
 È necessario che un endpoint client faccia riferimento a questa configurazione di associazione personalizzata.  
  
```xml  
<client>  
      <endpoint address="http://schemas.microsoft.com/discovery/dynamic"  
                binding="customBinding"  
                bindingConfiguration="discoBindingConfiguration"  
                contract="IHelloWorldService" />  
</client>  
```  
  
 Per ulteriori informazioni sui criteri di ricerca [, vedere Discovery Find e FindCriteria](discovery-find-and-findcriteria.md). Per ulteriori informazioni sull'individuazione e sugli elementi di associazione, vedere [Cenni preliminari sull'individuazione WCF](wcf-discovery-overview.md)  
  
## <a name="standard-endpoint-configuration"></a>Configurazione di endpoint standard  
 Gli endpoint standard sono endpoint con valori predefiniti per una o più proprietà (indirizzo, associazione o contratto) o uno o più valori di proprietà non modificabili. .NET 4 viene fornito con 3 endpoint standard relativi all'individuazione: <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>, <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint> e <xref:System.ServiceModel.Discovery.DynamicEndpoint>.  <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> è un endpoint standard preconfigurato per le operazioni di individuazione su un'associazione multicast UDP. <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint> è un endpoint standard preconfigurato per l'invio di messaggi di annuncio su un'associazione multicast UDP. <xref:System.ServiceModel.Discovery.DynamicEndpoint> è un endpoint standard che usa l'individuazione per cercare l'indirizzo endpoint di un servizio individuato in modo dinamico al runtime.  Le associazioni standard vengono specificate con un `endpoint` elemento <> contenente l'attributo kind che specifica il tipo di endpoint standard da aggiungere. Nell'esempio seguente viene illustrato come aggiungere un elemento <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> e un elemento <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint>.  
  
```xml  
<services>  
   <service name="HelloWorldService">  
      <!-- ...  -->
      <endpoint kind="udpDiscoveryEndpoint" />  
   </service>  
   <service name="AnnouncementListener">  
      <endpoint kind="udpAnnouncementEndpoint" />  
   </service>  
</services>  
```  
  
 Gli endpoint standard vengono configurati in un `standardEndpoints` elemento <>. Nell'esempio seguente viene illustrato come configurare l'elemento <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> e l'elemento <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint>.  
  
```xml  
<standardEndpoints>  
      <udpAnnouncementEndpoint>  
        <standardEndpoint
            name="udpAnnouncementEndpointSettings"
            multicastAddress="soap.udp://239.255.255.250:3703"
            maxAnnouncementDelay="00:00:00.800">  
          <transportSettings  
            duplicateMessageHistoryLength="1028"  
            maxPendingMessageCount="10"  
            maxMulticastRetransmitCount="3"  
            maxUnicastRetransmitCount="2"  
            socketReceiveBufferSize="131072"  
            timeToLive="2" />  
        </standardEndpoint>  
      </udpAnnouncementEndpoint>  
      <udpDiscoveryEndpoint>  
        <standardEndpoint  
            name="udpDiscoveryEndpointSettings"  
            multicastAddress="soap.udp://239.255.255.252:3704"  
            maxResponseDelay="00:00:00.800">  
          <transportSettings  
            duplicateMessageHistoryLength="2048"  
            maxPendingMessageCount="5"  
            maxReceivedMessageSize="8192"  
            maxBufferPoolSize="262144"/>  
        </standardEndpoint>  
      </udpDiscoveryEndpoint>
</standardEndpoints>
```  
  
 Dopo aver aggiunto la configurazione dell'endpoint standard, fare riferimento alla configurazione nel <`endpoint` elemento> per ogni endpoint, come illustrato nell'esempio seguente.  
  
```xml  
<services>  
   <service name="HelloWorldService">  
      <!-- ...  -->
      <endpoint kind="udpDiscoveryEndpoint" endpointConfiguration="udpDiscoveryEndpointSettings"/>  
   </service>  
   <service name="AnnouncementListener">  
      <endpoint kind="udpAnnouncementEndpoint" endpointConfiguration="udpAnnouncementEndpointSettings" >  
   </service>  
</services>  
```  
  
 A differenza degli altri endpoint standard usati nell'individuazione, vengono specificati un'associazione e un contratto per <xref:System.ServiceModel.Discovery.DynamicEndpoint>. Nell'esempio seguente viene illustrato come aggiungere e configurare un elemento <xref:System.ServiceModel.Discovery.DynamicEndpoint>.  
  
```xml  
<system.serviceModel>  
    <client>  
      <endpoint kind="dynamicEndpoint" binding="basicHttpBinding" contract="IHelloWorldService" endpointConfiguration="dynamicEndpointConfiguration" />  
    </client>
   <standardEndpoints>  
      <dynamicEndpoint>  
         <standardEndpoint name="dynamicEndpointConfiguration">  
             <discoveryClientSettings>  
              <findCriteria scopeMatchBy="http://schemas.microsoft.com/ws/2008/06/discovery/rfc" duration="00:00:10" maxResults="2">  
                 <types>  
                   <add name="IHelloWorldService"/>  
                 </types>  
                 <scopes>  
                   <add scope="http://www.microsoft.com/building42/floor1"/>  
                 </scopes>  
                 <extensions>  
                   <CustomMetadata>This is custom metadata.</CustomMetadata>
                 </extensions>  
               </findCriteria>  
             </discoveryClientSettings>  
           </standardEndpoint>  
         </dynamicEndpoint>  
   </standardEndpoints>  
</system.ServiceModel>  
```  
  
 Per altre informazioni sugli endpoint standard, vedere [endpoint standard](standard-endpoints.md).
