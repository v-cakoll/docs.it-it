---
title: <endpointDiscovery>
ms.date: 03/30/2017
ms.assetid: 70812717-888a-4748-9640-0df6715ff029
ms.openlocfilehash: 98b1655f42b7b43604ed4ab9d66870ec204a9590
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398012"
---
# \<endpointDiscovery>
Specifica le varie impostazioni di individuazione per un endpoint, quali l'individuazione, gli ambiti e le eventuali estensioni personalizzate ai relativi metadati.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<endpointDiscovery>**  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<behaviors>
  <endpointBehaviors>
    <behavior name="String">
      <endpointDiscovery enabled="Boolean">
        <scopes>
          <add scope="URI"/>
        </scopes>
        <extensions />
      </endpointDiscovery>
    </behavior>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|Enabled|Valore booleano che specifica se è abilitata l'individuabilità sull'endpoint. Il valore predefinito è `false`.|  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<scopes>](scopes.md)|Raccolta di URI di ambito per l'endpoint. A un singolo endpoint è possibile associare più URI di ambito.|  
|[\<extensions>](extensions.md)[di \<endpointDiscovery> ]|Raccolta di elementi XML che consente di specificare metadati personalizzati da pubblicare per un endpoint.|  
|\<types>|Raccolta di interfacce da cercare.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|Specifica un elemento di comportamento.|  
|||  
  
## <a name="remarks"></a>Commenti  
 L'aggiunta di questo elemento di configurazione alla configurazione di comportamento dell'endpoint con l'attributo `enabled` impostato su `true` ne determina l'abilitazione dell'individuazione. Inoltre, è possibile utilizzare l' [\<scopes>](scopes.md) elemento figlio per specificare gli URI di ambito personalizzati che possono essere utilizzati per filtrare gli endpoint di servizio durante la query, nonché l' [\<extensions>](extensions.md) elemento figlio per specificare metadati personalizzati da pubblicare insieme ai metadati individuabili standard (EPR, ContractTypeName, BindingName, scope e ListenUri).  
  
 Questo elemento di configurazione dipende dall' [\<serviceDiscovery>](servicediscovery.md) elemento che fornisce il controllo del livello di servizio dell'individuabilità. Ciò significa che le impostazioni di questo elemento vengono ignorate se [\<serviceDiscovery>](servicediscovery.md) non è presente nella configurazione.  
  
## <a name="example"></a>Esempio  
 Nell'esempio di configurazione seguente vengono specificati ambiti di filtro e metadati di estensione da pubblicare per un endpoint.  
  
```xml  
<services>
  <service name="CalculatorService"
           behaviorConfiguration="CalculatorServiceBehavior">
    <endpoint binding="basicHttpBinding"
              address="calculator"
              contract="ICalculatorService"
              behaviorConfiguration="calculatorEndpointBehavior" />
  </service>
</services>
<behaviors>
  <serviceBehaviors>
    <behavior name="CalculatorServiceBehavior">
      <serviceDiscovery />
    </behavior>
  </serviceBehaviors>
  <endpointBehaviors>
    <behavior name="calculatorEndpointBehavior">
      <endpointDiscovery enabled="true">
        <scopes>
          <add scope="http://contoso/test1" />
          <add scope="http://contoso/test2" />
        </scopes>
        <extensions>
          <e:Publisher xmlns:e="http://example.org">
            <e:Name>The Example Organization</e:Name>
            <e:Address>One Example Way, ExampleTown, EX 12345</e:Address>
            <e:Contact>support@example.org</e:Contact>
          </e:Publisher>
          <AnotherCustomMetadata>Custom Metadata</AnotherCustomMetadata>
        </extensions>
      </endpointDiscovery>
    </behavior>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
