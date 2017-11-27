---
title: '&lt;add&gt; di &lt;backupList&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bc5939fc-314a-4ea4-a533-c96958da7173
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 1475983f7dc54a597198d48a2a404e431ce9c0a0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="ltaddgt-of-ltbackuplistgt"></a>&lt;add&gt; di &lt;backupList&gt;
Rappresenta un elemento di configurazione che definisce un elemento dell'endpoint di backup.  
  
 \<System. ServiceModel >  
\<routing >  
\<backupLists >  
\<backupList >  
\<add>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
   <routing>  <backupLists>    <backupList name="String">      <add endpointName="String" />    </backupList>    </backupLists></routing>  
```  
  
```csharp  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|name|Stringa che specifica il nome dell'endpoint di backup.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<routing >](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|Contiene un elenco di endpoint che si desidera che il servizio di Routing da utilizzare nel caso in cui l'endpoint primario non è raggiungibile.|  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceModel.Routing.Configuration.BackupEndpointElement?displayProperty=nameWithType> 
