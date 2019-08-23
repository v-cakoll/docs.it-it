---
title: <add> di <backupList>
ms.date: 03/30/2017
ms.assetid: bc5939fc-314a-4ea4-a533-c96958da7173
ms.openlocfilehash: c590dbd671807b32e08ad5d871d376a0dc51e611
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926880"
---
# <a name="add-of-backuplist"></a>\<Aggiungi > di \<> di backup
Rappresenta un elemento di configurazione che definisce un elemento dell'endpoint di backup.  
  
 \<system.serviceModel>  
\<routing>  
\<> backupLists  
\<> di backup  
\<add>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<routing>
  <backupLists>
    <backupList name="String">
      <add endpointName="String" />
    </backupList>
  </backupLists>
</routing>
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
  
|Elemento|DESCRIZIONE|  
|-------------|-----------------|  
|[\<routing>](routing.md)|Contiene un elenco di endpoint che si desidera vengano utilizzati dal servizio di routing nel caso in cui non sia possibile raggiungere l'endpoint primario.|  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Routing.Configuration.BackupEndpointElement?displayProperty=nameWithType>
