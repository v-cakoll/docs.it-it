---
title: '&lt;developmentMode&gt; elemento'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/developmentMode
- http://schemas.microsoft.com/.NetConfiguration/v2.0#developmentMode
helpviewer_keywords:
- developmentMode element
- container tags, <developmentMode> element
- <developmentMode> element
ms.assetid: 60e79a8c-415a-497d-be29-b9d0fd9bdee3
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 982bc04e362f82760226b1cd2b8b3febe9cc7107
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/19/2018
ms.locfileid: "53612049"
---
# <a name="ltdevelopmentmodegt-element"></a>&lt;developmentMode&gt; elemento
Specifica se il runtime cerca gli assembly nelle directory specificate dalla variabile di ambiente DEVPATH.  
  
 \<configuration>  
\<runtime>  
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
  
|Value|Descrizione|  
|-----------|-----------------|  
|**true**|Cerca gli assembly nelle directory specificate dalla variabile di ambiente DEVPATH.|  
|**false**|Non esegue la ricerca per gli assembly nelle directory specificate dalla variabile di ambiente DEVPATH. Questo è il valore predefinito|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`runtime`|Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.|  
  
## <a name="remarks"></a>Note  
 Usare questa impostazione solo in fase di sviluppo. Il runtime non verifica se le versioni di assembly con nome sicuro trovato nel DEVPATH. Utilizza semplicemente il primo assembly individuato.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come parte del runtime cercare gli assembly nelle directory specificate dalla variabile di ambiente DEVPATH.  
  
```xml  
<configuration>  
   <runtime>  
      <developmentMode developerInstallation="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche  
- [Schema delle impostazioni di runtime](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
- [Schema dei file di configurazione](../../../../../docs/framework/configure-apps/file-schema/index.md)  
- [Procedura: Individuare assembly mediante DEVPATH](../../../../../docs/framework/configure-apps/how-to-locate-assemblies-by-using-devpath.md)
