---
title: <developmentMode> Elemento
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
ms.openlocfilehash: 0253c3ced52b575097fe5d18abb8ce188c0164fb
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252689"
---
# <a name="developmentmode-element"></a>\<Elemento > developmentMode
Specifica se il runtime cerca gli assembly nelle directory specificate dalla variabile di ambiente DEVPATH.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<> di runtime**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp; **\<developmentMode>**  
  
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
|**false**|Non cerca gli assembly nelle directory specificate dalla variabile di ambiente DEVPATH. Questa è l'impostazione predefinita|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`runtime`|Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.|  
  
## <a name="remarks"></a>Note  
 Usare questa impostazione solo in fase di sviluppo. Il runtime non controlla le versioni in assembly con nome sicuro presenti in DEVPATH. Usa semplicemente il primo assembly trovato.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come fare in modo che il runtime cerchi gli assembly nelle directory specificate dalla variabile di ambiente DEVPATH.  
  
```xml  
<configuration>  
   <runtime>  
      <developmentMode developerInstallation="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche

- [Schema delle impostazioni di runtime](index.md)
- [Schema dei file di configurazione](../index.md)
- [Procedura: Individuare gli assembly usando DEVPATH](../../how-to-locate-assemblies-by-using-devpath.md)
