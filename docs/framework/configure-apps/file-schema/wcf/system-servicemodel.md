---
title: <system.serviceModel>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#system.ServiceModel
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.ServiceModel
helpviewer_keywords:
- <system.serviceModel> element
- system.serviceModel element
ms.assetid: 78519531-ad7a-40d3-b3e7-42f1103d8854
ms.openlocfilehash: c176f7f470cc65bb135e5f92935102e09c7e8485
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61758444"
---
# <a name="systemservicemodel"></a>\<system.serviceModel>
Questa sezione di configurazione contiene tutti gli elementi di configurazione di ServiceModel di Windows Communication Foundation (WCF).  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<system.serviceModel>
  <behaviors>
  </behaviors>
  <bindings>
  </bindings>
  <client>
  </client>
  <comContracts>
  </comContracts>
  <commonBehaviors>
  </commonBehaviors>
  <diagnostics>
  </diagnostics>
  <extensions>
  </extensions>
  <protocolMapping>
  </protocolMapping>
  <routing>
  </routing>
  <serviceHostingEnvironment>
  </serviceHostingEnvironment>
  <services>
  </services>
  <standardEndpoints>
  </standardEndpoints>
  <tracking>
  </tracking>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
 nessuno  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<behaviors>](../../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md)|Questa sezione definisce due raccolte figlio denominate `endpointBehaviors` e `serviceBehaviors`.  Ogni raccolta definisce elementi di comportamento usati rispettivamente da endpoint e servizi. Ogni elemento di comportamento è identificato dal relativo attributo `name` univoco.|  
|[\<bindings>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|Questa sezione contiene una raccolta di associazioni standard e personalizzate. Ogni voce è identificata dal relativo attributo `name` univoco. I servizi usano le associazioni collegandole mediante l'oggetto `name`.|  
|[\<client>](../../../../../docs/framework/configure-apps/file-schema/wcf/client.md)|Questa sezione include un elenco degli endpoint usati da un client per connettersi a un servizio.|  
|[\<comContracts>](../../../../../docs/framework/configure-apps/file-schema/wcf/comcontracts.md)|Questa sezione definisce i contratti COM che consentono l'interoperabilità tra WCF e COM.|  
|[\<commonBehaviors>](../../../../../docs/framework/configure-apps/file-schema/wcf/commonbehaviors.md)|Il contenuto di questa sezione può essere definito solo nel file machine.config. e definisce due raccolte figlio denominate `endpointBehaviors` e `serviceBehaviors`.  Ogni raccolta definisce elementi di comportamento usati rispettivamente da tutti gli endpoint WCF e servizi nel computer.  Se un comportamento viene definito in entrambe `<commonBehaviors>` e `<behaviors>` sezioni, il comportamento nel \<comportamenti > sezione è data la preferenza.|  
|[\<diagnostics>](../../../../../docs/framework/configure-apps/file-schema/wcf/diagnostics.md)|Questa sezione include le impostazioni per le funzionalità di diagnostica di WCF. L'utente può abilitare o disabilitare tracce, contatori di prestazioni e il provider WMI e può aggiungere filtri dei messaggi personalizzati.|  
|[\<extensions>](../../../../../docs/framework/configure-apps/file-schema/wcf/extensions-section.md)|Questa sezione include una raccolta di estensioni che consentono di creare associazioni definite dall'utente, comportamenti e altri aspetti relativi alle estensioni.|  
|[\<protocolMapping>](../../../../../docs/framework/configure-apps/file-schema/wcf/protocolmapping.md)|In questa sezione definisce un set di mapping del protocollo predefinito tra gli schemi di protocollo di trasporto (ad esempio, http, NET. TCP, NET. pipe, e così via) e le associazioni di WCF.|  
|[\<routing>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|In questa sezione definisce un set di filtri di routing, che determinano il tipo di Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> da utilizzare durante la valutazione di messaggi in arrivo, nonché di routing di tabelle che definiscono gli endpoint di destinazione per l'invio di messaggi a quello in cui un corrisponde al filtro.|  
|[\<serviceHostingEnvironment>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md)|Questa sezione definisce il tipo del quale l'ambiente host del servizio crea un'istanza per un determinato trasporto. Se questa sezione è vuota, viene usato il tipo predefinito.|  
|[\<services>](../../../../../docs/framework/configure-apps/file-schema/wcf/services.md)|Questa sezione include una raccolta di servizi. Per ogni servizio definito nell'assembly, questo elemento contiene un elemento `service` nel quale vengono specificate le impostazioni per il servizio.|  
|[\<standardEndpoints>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|Questa sezione definisce una raccolta di endpoint standard rappresentati da endpoint preconfigurati riusabili. Un endpoint standard disporrà di uno o più indirizzi, attributi di associazione e del contratto impostati su un valore fisso. Ad esempio, nell'endpoint di individuazione il contratto è fisso. È inoltre possibile usare endpoint standard per estendere endpoint servizio con nuove proprietà in modo analogo alla definizione di associazioni personalizzate.|
|[\<tracking>](../../../../../docs/framework/configure-apps/file-schema/wcf/tracking-of-wcf.md)|Questa sezione definisce le impostazioni di rilevamento per un servizio del flusso di lavoro.|

### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|\<configuration>|Elemento radice di tutti gli elementi di configurazione contenuti in un file di configurazione .NET.|  
  
## <a name="remarks"></a>Note  
 WCF non aggiunge elementi alle sezioni di configurazione di altri prodotti.  
  
 Servizi WCF sono definiti nel `services` sezione del file di configurazione. Un assembly può contenere un numero qualsiasi di servizi. Ogni servizio dispone di una propria sezione di configurazione `service`. La sezione e il relativo contenuto definiscono in modo specifico il contratto, il comportamento e gli endpoint del servizio.  
  
 Fra gli attributi di un servizio, solo `name` è obbligatorio.  Per impostazione predefinita, il nome di un servizio descrive il tipo CLR sottostante usato per implementare un servizio. È tuttavia possibile modificare la proprietà ConfigurationName di un attributo <xref:System.ServiceModel.ServiceContractAttribute> per eseguire l'override del requisito del tipo CLR.  
  
 L'attributo `behaviorConfiguration` è facoltativo. identifica il comportamento usato dal servizio. Il comportamento specificato da questo attributo deve essere collegato a un comportamento di servizio definito nell'ambito dello stesso file di configurazione, ad esempio lo stesso file o un file padre.  
  
 Ogni servizio espone uno o più endpoint definiti in un elemento `endpoint`. Ogni endpoint presenta indirizzo e associazione propri. Tutte le associazioni usate all'interno del file di configurazione devono essere definite nell'ambito del file.  
  
 Le associazioni sono collegate agli endpoint tramite la combinazione di attributi `name` e `bindingConfiguration`. L'attributo `binding` definisce la sezione in cui è definita l'associazione. L'attributo `bindingConfiguration` definisce quale associazione configurata viene usata fra quelle contenute nella sezione di associazione. Una sezione di associazione può infatti definire varie associazioni configurate.  
  
## <a name="example"></a>Esempio  
 Segue un esempio di file di configurazione di WCF.  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>
<configuration>
  <system.serviceModel>
    <behaviors>
      <!-- List of Behaviors -->
    </behaviors>
    <client>
      <!-- List of Endpoints -->
    </client>
    <diagnostics wmiProviderEnabled="false"
                 performanceCountersEnabled="false"
                 tracingEnabled="false">
    </diagnostics>
    <serviceHostingEnvironment>
      <!-- List of entries -->
    </serviceHostingEnvironment>
    <comContracts>
      <!-- List of COM+ Contracts -->
    </comContracts>
    <services>
      <!-- List of Services -->
    </services>
    <bindings>
      <!-- List of Bindings -->
    </bindings>
  </system.serviceModel>
</configuration>
```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Configuration.ServiceModelSectionGroup>
