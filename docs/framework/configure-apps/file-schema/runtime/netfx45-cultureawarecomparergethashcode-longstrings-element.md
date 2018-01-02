---
title: '&lt;NetFx45_CultureAwareComparerGetHashCode_LongStrings&gt; elemento'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- NetFx45_CultureAwareComparerGetHashCode_LongStrings element
- <NetFx45_CultureAwareComparerGetHashCode_LongStrings> element
- GetHashCode method
- hash codes, calculating
ms.assetid: 3a5f38d1-ebc8-44de-aaeb-2929f6e6b48f
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1c370bc9ea5f8c3cdbf8690c7e22788b1224f4df
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltnetfx45cultureawarecomparergethashcodelongstringsgt-element"></a>&lt;NetFx45_CultureAwareComparerGetHashCode_LongStrings&gt; elemento
Specifica se il runtime utilizza una quantità di memoria fissa per calcolare i codici hash per il metodo <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType>.  
  
 \<configuration>  
\<runtime >  
<NetFx45_CultureAwareComparerGetHashCode_LongStrings>  
  
## <a name="syntax"></a>Sintassi  
  
```xml
<NetFx45_CultureAwareComparerGetHashCode_LongStrings enabled="0|1">  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`enabled`|Attributo obbligatorio.<br /><br /> Specifica se tramite Common Language Runtime viene allocata una quantità di memoria fissa durante il calcolo dei codici hash.|  
  
## <a name="enabled-attribute"></a>Attributo enabled  
  
|Valore|Descrizione|  
|-----------|-----------------|  
|0|Specifica se tramite Common Language Runtime viene allocata una quantità di memoria variabile al metodo <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> per il calcolo dei codici hash. Questa è l'impostazione predefinita.|  
|1|Specifica se tramite Common Language Runtime viene allocata una quantità di memoria fissa al metodo <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> per il calcolo dei codici hash.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`runtime`|Contiene informazioni sulle opzioni di inizializzazione in fase di esecuzione.|  
  
## <a name="remarks"></a>Note  
 Per impostazione predefinita, tramite Common Language Runtime viene allocata una quantità di memoria variabile per il metodo <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> e <xref:System.ArgumentException> può essere generata quando il metodo tenta di calcolare il codice hash di stringhe di dimensioni considerevoli (oltre diversi milioni di caratteri). Aggiungendo questo elemento a un file di configurazione dell'applicazione e impostando il relativo attributo `enabled` su "1", è possibile specificare che il metodo <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> utilizza un algoritmo alternativo che alloca una quantità di memoria fissa per il calcolo di codici hash.  
  
> [!IMPORTANT]
>  L'elemento di `<NetFx45_CultureAwareComparerGetHashCode_LongStrings>` non viene utilizzato in [!INCLUDE[win8](../../../../../includes/win8-md.md)] e versioni successive.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType>  
 [Schema delle impostazioni di runtime](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [Schema dei file di configurazione](../../../../../docs/framework/configure-apps/file-schema/index.md)
