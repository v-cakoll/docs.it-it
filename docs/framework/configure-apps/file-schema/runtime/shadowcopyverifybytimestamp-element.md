---
title: <shadowCopyVerifyByTimestamp> Elemento
ms.date: 03/30/2017
helpviewer_keywords:
- <shadowCopyTimeStampVerification> element
- shadowCopyTimeStampVerification element
ms.assetid: 2f1648e5-997b-435e-a4f9-d236c574c66c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4187d266d82783ebb72073c1da92faff95352884
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2019
ms.locfileid: "66489384"
---
# <a name="shadowcopyverifybytimestamp-element"></a>Elemento \<shadowCopyVerifyByTimestamp>
Specifica se la copia shadow Usa il comportamento di avvio predefinito introdotto in .NET Framework 4 o Ripristina il comportamento di avvio delle versioni precedenti di .NET Framework.  
  
 \<configurazione > elemento  
\<runtime > elemento  
Elemento \<shadowCopyVerifyByTimestamp>  
  
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
|true|All'avvio, copia solo gli assembly che sono stati aggiornati dall'ultimo sono stati copiati nella directory della copia shadow. Questo è il valore predefinito di .NET Framework 4.|  
|False|Ripristina il comportamento di avvio delle versioni precedenti di .NET Framework, che consiste nel copiare tutti i file all'avvio.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`runtime`|Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.|  
  
## <a name="remarks"></a>Note  
 A partire da .NET Framework 4, gli assembly vengono replicati solo se i timestamp indicano che essi siano state modificate dall'ultima sono stati copiati nella directory della copia shadow. Migliora i tempi di avvio per molte applicazioni che usano la copia shadow, come descritto in [copie replicate di assembly](../../../../../docs/framework/app-domains/shadow-copy-assemblies.md). Le applicazioni con una percentuale e una frequenza elevate di aggiornamenti dell'assembly non possono trarre vantaggio da questa modifica nel comportamento. In tal caso, è possibile utilizzare questo elemento per ripristinare il comportamento delle versioni precedenti di .NET Framework.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come disabilitare il comportamento di avvio predefiniti della copia shadow in .NET Framework 4 e ripristinare il comportamento di avvio delle versioni precedenti di .NET Framework.  
  
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
