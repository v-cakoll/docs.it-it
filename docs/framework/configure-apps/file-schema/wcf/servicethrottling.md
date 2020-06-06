---
title: <serviceThrottling>
ms.date: 03/30/2017
ms.assetid: a337d064-1e64-4209-b4a9-db7fdb7e3eaf
ms.openlocfilehash: ad87a5876381a7224341babdb076c85edcd1dd87
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70399571"
---
# \<serviceThrottling>
Specifica il meccanismo della limitazione di un servizio Windows Communication Foundation (WCF).  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceThrottling>**  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<serviceThrottling maxConcurrentCalls="Integer"
                   maxConcurrentInstances="Integer"
                   maxConcurrentSessions="Integer" />
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|maxConcurrentCalls|Numero intero positivo che limita il numero di messaggi attualmente elaborati in un oggetto <xref:System.ServiceModel.ServiceHost>. Le chiamate oltre il limite vengono accodate. L'impostazione di questo valore su 0 è equivalente alla relativa impostazione su Int32.MaxValue. L'impostazione predefinita è 16 * il numero dei processori.|  
|maxConcurrentInstances|Numero intero positivo che limita il numero di oggetti <xref:System.ServiceModel.InstanceContext> eseguiti contemporaneamente in un oggetto <xref:System.ServiceModel.ServiceHost>. Le richieste di creare istanze aggiuntive vengono messe in coda e completate quando diventa disponibile uno slot sotto il limite. L'impostazione predefinita è la somma di maxConcurrentSessions più MaxConcurrentCalls|  
|maxConcurrentSessions|Numero intero positivo che limita il numero di sessioni che possono essere accettate da un oggetto <xref:System.ServiceModel.ServiceHost>.<br /><br /> Il servizio accetterà le connessioni oltre il limite, ma sono attivi solo i canali sotto il limite (i messaggi vengono letti dal canale). L'impostazione di questo valore su 0 è equivalente alla relativa impostazione su Int32.MaxValue. L'impostazione predefinita è 100 * il numero dei processori.|  
  
### <a name="child-elements"></a>Elementi figlio  
 No.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|Specifica un elemento di comportamento.|  
  
## <a name="remarks"></a>Commenti  
 I controlli di limitazione pongono dei limiti sul numero di chiamate, istanze o sessioni simultanee per impedire l'uso eccessivo di risorse.  
  
 Viene scritta una traccia ogni volta che viene raggiunto il valore di attributi. La prima traccia viene scritta come un avviso.  
  
## <a name="example"></a>Esempio  
 Nell'esempio di configurazione seguente viene specificato che il servizio limita il numero massimo di chiamate simultanee a 2 e il numero massimo di istanze simultanee a 10. Per un esempio dettagliato dell'esecuzione di questo esempio, vedere [limitazione delle richieste](../../../wcf/samples/throttling.md).  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="CalculatorServiceBehavior">
      <serviceDebug includeExceptionDetailInFaults="False" />
      <serviceMetadata httpGetEnabled="True" />
      <!-- Specify throttling behavior -->
      <serviceThrottling maxConcurrentCalls="2"
                         maxConcurrentInstances="10" />
    </behavior>
  </serviceBehaviors>
</behaviors>
```  
  
## <a name="see-also"></a>Vedi anche

- <xref:System.ServiceModel.Description.ServiceThrottlingBehavior>
- <xref:System.ServiceModel.Configuration.ServiceThrottlingElement>
- [Uso di ServiceThrottlingBehavior per controllare le prestazioni dei servizi WCF](../../../wcf/feature-details/using-servicethrottlingbehavior-to-control-wcf-service-performance.md)
