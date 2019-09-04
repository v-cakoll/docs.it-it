---
title: <probing> Elemento
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/probing
- http://schemas.microsoft.com/.NetConfiguration/v2.0#probing
helpviewer_keywords:
- <probing> element
- container tags, <probing> element
- probing element
ms.assetid: 09c80fc9-1ba5-4192-89f7-3a79b2e4b024
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 05634cb319ac69bd76e16e592ba59490b30c9c9d
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252394"
---
# <a name="probing-element"></a>\<Elemento > Probe
Specifica le sottodirectory di base dell'applicazione per la ricerca del Common Language Runtime durante il caricamento degli assembly.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<> di runtime**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> di associazione**](assemblybinding-element-for-runtime.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<probing>**  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<probing privatePath="paths"/>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`privatePath`|Attributo obbligatorio.<br /><br /> Specifica le sottodirectory della directory di base dell'applicazione che potrebbero contenere assembly. Delimita ogni sottodirectory con un punto e virgola.|  
  
### <a name="child-elements"></a>Elementi figlio  

Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|DESCRIZIONE|  
|-------------|-----------------|  
|`assemblyBinding`|Contiene le informazioni sul reindirizzamento della versione degli assembly e i relativi percorsi.|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`runtime`|Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.|  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come specificare le sottodirectory di base dell'applicazione in cui il runtime deve cercare gli assembly.  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <probing privatePath="bin;bin2\subbin;bin3"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche

- [Schema delle impostazioni di runtime](index.md)
- [Schema dei file di configurazione](../index.md)
- [Specifica della posizione di un assembly](../../specify-assembly-location.md)
- [Come il runtime individua gli assembly](../../../deployment/how-the-runtime-locates-assemblies.md)
