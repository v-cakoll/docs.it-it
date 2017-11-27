---
title: '&lt;clientVia&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c27ee94e-babd-459b-9574-2a6d67d11314
caps.latest.revision: "12"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 7cdc85c23202154728610ab4721bf830004928c8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ltclientviagt"></a>&lt;clientVia&gt;
Specifica l'URI per il quale creare il canale del trasporto. Per altre informazioni, vedere <xref:System.ServiceModel.Description.ClientViaBehavior>.  
  
 \<System. ServiceModel >  
\<i comportamenti >  
\<endpointBehaviors >  
\<comportamento >  
\<clientVia >  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<clientVia viaUri="String"/>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`viaUri`|Stringa che specifica un Uri che indica la route che deve essere presa da un messaggio.|  
  
### <a name="child-elements"></a>Elementi figlio  
 None  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<comportamento >](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|Specifica un comportamento dell'endpoint.|  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceModel.Configuration.ClientViaElement>  
 <xref:System.ServiceModel.Description.ClientViaBehavior>
