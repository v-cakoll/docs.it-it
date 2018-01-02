---
title: '&lt;UseSmallInternalThreadStacks&gt; elemento'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- UseSmallInternalThreadStacks element
- <UseSmallInternalThreadStacks> element
ms.assetid: 1e3f6ec0-1cac-4e1c-9c81-17d948ae5874
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c96537cad59034578d1284f7dc432e5775f3730b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltusesmallinternalthreadstacksgt-element"></a>&lt;UseSmallInternalThreadStacks&gt; elemento
Le richieste che common language runtime (CLR) ridurre la memoria utilizzano specificando le dimensioni dello stack esplicita quando crea determinati thread che utilizza internamente, anziché utilizzare la dimensione predefinita per tali thread.  
  
 \<configurazione > elemento  
\<runtime > elemento  
\<UseSmallInternalThreadStacks > elemento  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<UseSmallInternalThreadStacks enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|enabled|Attributo obbligatorio.<br /><br /> Specifica se richiedere che le dimensioni dello stack esplicita uso CLR anziché la dimensione predefinita quando si crea determinati thread che utilizza internamente. Le dimensioni dello stack esplicita sono inferiori alle dimensioni dello stack predefinito di 1 MB.|  
  
## <a name="enabled-attribute"></a>Attributo enabled  
  
|Valore|Descrizione|  
|-----------|-----------------|  
|true|Le dimensioni dello stack esplicita della richiesta.|  
|false|Utilizzare la dimensione predefinita. Questo è il valore predefinito per il [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)].|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`runtime`|Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.|  
  
## <a name="remarks"></a>Note  
 Questo elemento di configurazione viene utilizzato per richiedere l'utilizzo ridotto della memoria virtuale in un processo, poiché le dimensioni di esplicita di thread usati da CLR per i thread interni, se la richiesta è stata rispettata, sono inferiori alle dimensioni predefinite.  
  
> [!IMPORTANT]
>  Questo elemento di configurazione è una richiesta di CLR anziché un requisito assoluto. Nel [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], la richiesta viene rispettata solo per x86 architettura. Questo elemento potrebbe essere ignorato completamente nelle versioni future di CLR o sostituito da dimensioni dello stack esplicite che vengono sempre utilizzate per thread interni selezionati.  
  
 Specificare che questo elemento di configurazione negozia l'affidabilità di minore utilizzo della memoria virtuale se CLR soddisfa la richiesta, perché le dimensioni dello stack più piccole potrebbe potenzialmente stack overflow più probabile.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come richiedere che il Common Language Runtime Usa dimensioni esplicite dello stack per determinati thread che utilizza internamente.  
  
```xml  
<configuration>  
   <runtime>  
      <UseSmallInternalThreadStacks enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Schema delle impostazioni di runtime](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [Schema dei file di configurazione](../../../../../docs/framework/configure-apps/file-schema/index.md)
