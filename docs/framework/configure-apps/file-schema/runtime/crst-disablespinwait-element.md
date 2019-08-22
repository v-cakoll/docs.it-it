---
title: < elemento > Crst_DisableSpinWait
ms.date: 04/18/2019
f1_keywords:
- Crst_DisableSpinWait
helpviewer_keywords:
- Crst_DisableSpinWait element
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a52dd671f1fbf6fda5bdc92c0935784181eb4b03
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663833"
---
# <a name="crst_disablespinwait-element"></a>\<Elemento > Crst_DisableSpinWait

Specifica se disabilitare lo spin-waiting per una sezione critica in caso di conflitto.  
  
 \<configuration>  
\<runtime>  
\<> Crst_DisableSpinWait  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<Crst_DisableSpinWait enabled="true | false"/>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi

Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|**enabled**|Specifica se la rotazione in attesa di sezioni critiche quando sono in conflitto è disabilitata.|  
  
## <a name="enabled-attribute"></a>Attributo enabled  
  
|Valore|Descrizione|  
|-----------|-----------------|  
|1|Disabilitare la rotazione in attesa quando non è possibile acquisire una sezione critica.|  
|0|Non disabilitare la rotazione in attesa quando non è possibile acquisire una sezione critica. Rappresenta il valore predefinito.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`runtime`|Contiene informazioni sulle varie impostazioni di configurazione del runtime.|  
  
## <a name="example"></a>Esempio  

Nell'esempio seguente viene disabilitata la rotazione in attesa nelle sezioni critiche quando è in conflitto.  
  
```xml  
<configuration>  
   <runtime>  
      <Crst_DisableSpinWait enabled="1"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche

- [Schema delle impostazioni di runtime](index.md)
- [Schema dei file di configurazione](../index.md)
