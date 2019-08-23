---
title: <webHttp>
ms.date: 03/30/2017
ms.assetid: 1f9d0754-d41e-44ce-a298-e51cb3096c64
ms.openlocfilehash: 366def5d0f4cc82b0ff0a5127701b0b5a6adb6a0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69940495"
---
# <a name="webhttp"></a>\<webHttp>
Questo elemento specifica il comportamento <xref:System.ServiceModel.Description.WebHttpBehavior> in un endpoint tramite la configurazione. Questo comportamento, se usato insieme [ \<a WebHttpBinding >](webhttpbinding.md) associazione standard, Abilita il modello di programmazione Web per un servizio di Windows Communication Foundation (WCF).  
  
 \<system.ServiceModel>  
\<comportamenti >  
\<endpointBehaviors>  
\<comportamento >  
\<webHttp>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<webHttp />
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|automaticFormatSelectionEnabled|Quando questa proprietà è impostata su `true`, l'infrastruttura di WCF determina il formato migliore da usare. La selezione automatica del formato è disabilitata per impostazione predefinita per la compatibilità con le versioni precedenti. La selezione automatica del formato automatica può essere abilitata a livello di codice o tramite la configurazione.|  
|defaultBodyStyle|Specifica lo stile predefinito del corpo dei messaggi restituiti. Per ulteriori informazioni, vedere <xref:System.ServiceModel.Web.WebMessageBodyStyle> e [formattazione http Web WCF](../../../wcf/feature-details/wcf-web-http-formatting.md).|  
|defaultOutgoingResponseFormat|Specifica il formato del messaggio di risposta in uscita predefinito per i messaggi. Per ulteriori informazioni, vedere la pagina relativa alla [formattazione http Web WCF](../../../wcf/feature-details/wcf-web-http-formatting.md).|  
|faultExceptionEnabled|Ottiene o imposta il flag che specifica se viene generata un'eccezione FaultException quando si verifica un errore interno del server (Codice di stato HTTP: 500).|  
|helpEnabled|Ottiene o imposta un valore che determina se la pagina della Guida è abilitata.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|Specifica l'insieme di comportamenti dell'endpoint.|  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Configuration.WebHttpElement>
- <xref:System.ServiceModel.Description.WebHttpBehavior>
- [Integrazione AJAX e supporto JSON](../../../wcf/feature-details/ajax-integration-and-json-support.md)
- [\<webHttpBinding>](webhttpbinding.md)
