---
title: <routing> di <serviceBehavior>
ms.date: 03/30/2017
ms.assetid: d8f9c844-4629-4a45-9599-856dc8f01794
ms.openlocfilehash: b7a9be18395ef8878900d754b5aa5afdeee0cff8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59202508"
---
# <a name="routing-of-servicebehavior"></a>\<routing > di \<serviceBehavior >
Fornisce l'accesso in fase di esecuzione al servizio di routing per consentire la modifica dinamica della configurazione di routing.  
  
 \<system.ServiceModel>  
\<behaviors>  
\<serviceBehaviors>  
\<behavior>  
\<routing>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <routing filterTable="String"
               routeOnHeadersOnly="Boolean"
               SoapProcessingEnabled="Boolean" />
    </behavior>
  </serviceBehaviors>
</behaviors>
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|filterTable|Stringa che specifica il nome della tabella di routing contenente i filtri per la valutazione da parte del servizio di routing. Questo valore deve corrispondere il `name` attributo di un [ \<filterTable >](../../../../../docs/framework/configure-apps/file-schema/wcf/filtertable.md) elemento il [ \<filterTables >](../../../../../docs/framework/configure-apps/file-schema/wcf/filtertables.md) sezione.|  
|routeOnHeaderOnly|Valore booleano che specifica se il filtro esaminerà il corpo del messaggio e l'intestazione oppure solo l'intestazione. Il valore predefinito è `true`.|  
|soapProcessingEnabled|Valore booleano che specifica se è necessario che si verifichi l'elaborazione SOAP.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<behavior>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|Specifica un elemento di comportamento.|  
  
## <a name="remarks"></a>Note  
 Quando viene aggiunto alla configurazione del comportamento del servizio, questo elemento di configurazione abilita il routing del servizio. È possibile specificare la tabella di routing effettiva per l'uso da parte del servizio in questo elemento.  
  
 L'uso di questa sezione di configurazione consente di modificare le impostazioni di routing non appena cambia il modello di distribuzione. In fase di esecuzione è possibile registrare l'estensione di routing personalizzata con le nuove impostazioni del routing e il servizio di routing inizierà a utilizzare le informazioni di configurazione aggiornate per i nuovi messaggi e sessioni, mentre per i messaggi e le sessioni in corso continueranno a essere utilizzate le regole implementate al momento dell'avvio.  In questo modo è possibile eseguire la riconfigurazione indipendente dalla sessione e senza riciclo del servizio di routing in fase di esecuzione.  
