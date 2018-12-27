---
title: '&lt;shadowCopyVerifyByTimestamp&gt; elemento'
ms.date: 03/30/2017
helpviewer_keywords:
- <shadowCopyTimeStampVerification> element
- shadowCopyTimeStampVerification element
ms.assetid: 2f1648e5-997b-435e-a4f9-d236c574c66c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a97c8708c7d57d1a8f5335ef19e8e74cb6487276
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/19/2018
ms.locfileid: "53610905"
---
# <a name="ltshadowcopyverifybytimestampgt-element"></a>&lt;shadowCopyVerifyByTimestamp&gt; elemento
Specifica se la copia shadow usa il comportamento di avvio predefinito introdotto in [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] o ripristina il comportamento di avvio delle versioni precedenti di .NET Framework.  
  
 \<configurazione > elemento  
\<runtime > elemento  
\<shadowCopyVerifyByTimestamp > elemento  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<shadowCopyVerifyByTimestamp enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|enabled|Attributo obbligatorio.<br /><br /> Specifica se i domini applicazione che usano la copia shadow confrontare assembly timestamp all'avvio, per determinare se un assembly è stato aggiornato prima della copia shadow dell'assembly.|  
  
## <a name="enabled-attribute"></a>Attributo enabled  
  
|Valore|Descrizione|  
|-----------|-----------------|  
|true|All'avvio, copia solo gli assembly che sono stati aggiornati dall'ultimo sono stati copiati nella directory della copia shadow. Questo è il valore predefinito per il [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)].|  
|False|Ripristina il comportamento di avvio delle versioni precedenti di .NET Framework, che consiste nel copiare tutti i file all'avvio.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`runtime`|Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.|  
  
## <a name="remarks"></a>Note  
 A partire dal [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], gli assembly vengono replicati solo se i timestamp indicano che essi siano state modificate dall'ultima sono stati copiati nella directory della copia shadow. Migliora i tempi di avvio per molte applicazioni che usano la copia shadow, come descritto in [copie replicate di assembly](../../../../../docs/framework/app-domains/shadow-copy-assemblies.md). Le applicazioni con una percentuale e una frequenza elevate di aggiornamenti dell'assembly non possono trarre vantaggio da questa modifica nel comportamento. In tal caso, è possibile utilizzare questo elemento per ripristinare il comportamento delle versioni precedenti di .NET Framework.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come disabilitare il comportamento di avvio predefiniti della copia shadow nel [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)]e ripristinare il comportamento di avvio delle versioni precedenti di .NET Framework.  
  
```xml  
<configuration>  
   <runtime>  
      <shadowCopyVerifyByTimestamp enabled="false" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche  
- [Schema delle impostazioni di runtime](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
- [Schema dei file di configurazione](../../../../../docs/framework/configure-apps/file-schema/index.md)  
- [Creazione di copie replicate di assembly](../../../../../docs/framework/app-domains/shadow-copy-assemblies.md)
