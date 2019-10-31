---
title: <shadowCopyVerifyByTimestamp> Elemento
ms.date: 03/30/2017
helpviewer_keywords:
- <shadowCopyTimeStampVerification> element
- shadowCopyTimeStampVerification element
ms.assetid: 2f1648e5-997b-435e-a4f9-d236c574c66c
ms.openlocfilehash: 160f14c856735e1ceac8635506aea52454faea43
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73115733"
---
# <a name="shadowcopyverifybytimestamp-element"></a>Elemento \<shadowCopyVerifyByTimestamp>
Specifica se la copia shadow usa il comportamento di avvio predefinito introdotto nel .NET Framework 4 o Ripristina il comportamento di avvio delle versioni precedenti del .NET Framework.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp; &nbsp;[ **\<runtime >** ](runtime-element.md) \
&nbsp;&nbsp;&nbsp;&nbsp; **\<shadowCopyVerifyByTimestamp >**  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<shadowCopyVerifyByTimestamp enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|enabled|Attributo obbligatorio.<br /><br /> Specifica se i domini applicazione che usano la copia shadow confrontano i timestamp dell'assembly al momento dell'avvio, per determinare se un assembly è stato aggiornato prima della copia shadow dell'assembly.|  
  
## <a name="enabled-attribute"></a>Attributo enabled  
  
|Value|Descrizione|  
|-----------|-----------------|  
|true|All'avvio, copia solo gli assembly che sono stati aggiornati dopo l'ultima copia nella directory della copia shadow. Si tratta dell'impostazione predefinita per il .NET Framework 4.|  
|False|Ripristina il comportamento di avvio delle versioni precedenti del .NET Framework, ovvero la copia di tutti i file all'avvio.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuna.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`runtime`|Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.|  
  
## <a name="remarks"></a>Note  
 A partire da .NET Framework 4, gli assembly vengono replicati solo se i timestamp indicano che sono stati modificati dopo l'ultima copia nella directory della copia shadow. Ciò migliora i tempi di avvio per molte applicazioni che usano la copia shadow, come descritto in assembly per la [Copia Shadow](../../../app-domains/shadow-copy-assemblies.md). Le applicazioni con una percentuale e una frequenza elevate di aggiornamenti dell'assembly non possono trarre vantaggio da questa modifica nel comportamento. In tal caso, è possibile utilizzare questo elemento per ripristinare il comportamento delle versioni precedenti di .NET Framework.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come disabilitare il comportamento di avvio predefinito della copia shadow nella .NET Framework 4 e ripristinare il comportamento di avvio delle versioni precedenti del .NET Framework.  
  
```xml  
<configuration>  
   <runtime>  
      <shadowCopyVerifyByTimestamp enabled="false" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche

- [Schema delle impostazioni di runtime](index.md)
- [Schema dei file di configurazione](../index.md)
- [Creazione di copie replicate di assembly](../../../app-domains/shadow-copy-assemblies.md)
