---
title: '&lt;developmentMode&gt; elemento'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/developmentMode
- http://schemas.microsoft.com/.NetConfiguration/v2.0#developmentMode
helpviewer_keywords:
- developmentMode element
- container tags, <developmentMode> element
- <developmentMode> element
ms.assetid: 60e79a8c-415a-497d-be29-b9d0fd9bdee3
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4573c3a5e0cf64996f2a4e109736d966b754494a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ltdevelopmentmodegt-element"></a>&lt;developmentMode&gt; elemento
Specifica se il runtime cerca gli assembly nelle directory specificate dalla variabile di ambiente DEVPATH.  
  
 \<configuration>  
\<runtime >  
\<developmentMode >  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<developmentMode developerInstallation="true | false"/>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|**developerInstallation**|Specifica se il runtime cerca gli assembly nelle directory specificate dalla variabile di ambiente DEVPATH.|  
  
## <a name="developerinstallation-attribute"></a>Attributo developerInstallation  
  
|Valore|Descrizione|  
|-----------|-----------------|  
|**true**|Cerca gli assembly nelle directory specificate dalla variabile di ambiente DEVPATH.|  
|**false**|Non esegue la ricerca per gli assembly nelle directory specificate dalla variabile di ambiente DEVPATH. Questa è l'impostazione predefinita|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`runtime`|Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.|  
  
## <a name="remarks"></a>Note  
 Utilizzare questa impostazione solo in fase di sviluppo. Il runtime non controllate le versioni degli assembly con nome sicuro, vedere il DEVPATH. Usa semplicemente il primo assembly individuato.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come impostare il runtime cercare gli assembly nelle directory specificate dalla variabile di ambiente DEVPATH.  
  
```xml  
<configuration>  
   <runtime>  
      <developmentMode developerInstallation="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Schema delle impostazioni di runtime](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [Schema dei file di configurazione](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [Procedura: individuare assembly mediante DEVPATH](../../../../../docs/framework/configure-apps/how-to-locate-assemblies-by-using-devpath.md)
