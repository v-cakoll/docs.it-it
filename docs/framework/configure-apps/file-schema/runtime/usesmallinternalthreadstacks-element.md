---
title: <UseSmallInternalThreadStacks> Elemento
ms.date: 03/30/2017
helpviewer_keywords:
- UseSmallInternalThreadStacks element
- <UseSmallInternalThreadStacks> element
ms.assetid: 1e3f6ec0-1cac-4e1c-9c81-17d948ae5874
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 74678089bb1b19295983064eb7ad54fbf0a1e361
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663382"
---
# <a name="usesmallinternalthreadstacks-element"></a>\<Elemento > UseSmallInternalThreadStacks
Richiede che i Common Language Runtime (CLR) riducano l'utilizzo della memoria specificando dimensioni dello stack esplicite quando vengono creati determinati thread utilizzati internamente, anziché utilizzare le dimensioni predefinite dello stack per quei thread.  
  
 \<Configuration >-elemento  
\<Elemento runtime >  
\<Elemento > UseSmallInternalThreadStacks  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<UseSmallInternalThreadStacks enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|enabled|Attributo obbligatorio.<br /><br /> Specifica se richiedere che CLR usi dimensioni dello stack esplicite invece delle dimensioni predefinite dello stack quando crea determinati thread che usa internamente. Le dimensioni dello stack esplicite sono inferiori alle dimensioni predefinite dello stack di 1 MB.|  
  
## <a name="enabled-attribute"></a>Attributo enabled  
  
|Valore|Descrizione|  
|-----------|-----------------|  
|true|Richiedere dimensioni dello stack esplicite.|  
|false|Utilizzare le dimensioni predefinite dello stack. Si tratta dell'impostazione predefinita per il .NET Framework 4.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`runtime`|Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.|  
  
## <a name="remarks"></a>Note  
 Questo elemento di configurazione viene utilizzato per richiedere un utilizzo ridotto della memoria virtuale in un processo, perché le dimensioni dei thread esplicite utilizzate da CLR per i thread interni, se la richiesta viene rispettata, sono inferiori alle dimensioni predefinite.  
  
> [!IMPORTANT]
>  Questo elemento di configurazione è una richiesta a CLR anziché a un requisito assoluto. Nel .NET Framework 4, la richiesta viene rispettata solo per l'architettura x86. Questo elemento potrebbe essere ignorato completamente nelle versioni future di CLR o sostituito dalle dimensioni dello stack esplicite che vengono sempre utilizzate per i thread interni selezionati.  
  
 La specifica di questo elemento di configurazione consente di compromettere l'affidabilità per un utilizzo di memoria virtuale inferiore se CLR rispetta la richiesta, perché le dimensioni dello stack più piccole potrebbero causare un overflow più probabile dello stack.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come richiedere che CLR utilizzi dimensioni dello stack esplicite per determinati thread utilizzati internamente.  
  
```xml  
<configuration>  
   <runtime>  
      <UseSmallInternalThreadStacks enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche

- [Schema delle impostazioni di runtime](index.md)
- [Schema dei file di configurazione](../index.md)
