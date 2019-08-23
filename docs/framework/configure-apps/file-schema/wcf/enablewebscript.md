---
title: <enableWebScript>
ms.date: 03/30/2017
ms.assetid: 9c7e96e1-af70-4e6e-ac5c-d67929dddbaa
ms.openlocfilehash: 123f58ee3d77bf605db21fa0d9537b3196d56468
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919119"
---
# <a name="enablewebscript"></a>\<enableWebScript>
Questo elemento attiva il comportamento dell'endpoint che rende possibile l'uso del servizio da pagine Web ASP.NET AJAX.  
  
 \<system.ServiceModel>  
\<comportamenti >  
\<endpointBehaviors>  
\<comportamento >  
\<enableWebScript>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<enableWebScript />
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
 Nessuno.  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|Specifica l'insieme di comportamenti dell'endpoint.|  
  
## <a name="remarks"></a>Note  
 Questo comportamento deve essere usato solo in combinazione con l' [ \<associazione WebHttpBinding >](webhttpbinding.md) standard o con l' [ \<](webmessageencoding.md) elemento di associazione > webMessageEncoding.  Per altre informazioni su questo comportamento, vedere <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Configuration.WebScriptEnablingElement>
- <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>
- [Integrazione AJAX e supporto JSON](../../../wcf/feature-details/ajax-integration-and-json-support.md)
- [\<webHttp>](webhttp.md)
