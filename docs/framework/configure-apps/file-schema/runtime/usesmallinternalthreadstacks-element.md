---
title: <UseSmallInternalThreadStacks> Elemento
ms.date: 03/30/2017
helpviewer_keywords:
- UseSmallInternalThreadStacks element
- <UseSmallInternalThreadStacks> element
ms.assetid: 1e3f6ec0-1cac-4e1c-9c81-17d948ae5874
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b9833d768b84faaf6e1dcf8c9cb8b00b92adc3d1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61673986"
---
# <a name="usesmallinternalthreadstacks-element"></a>\<UseSmallInternalThreadStacks > elemento
Le richieste che common language runtime (CLR) ridurre la memoria usano specificando le dimensioni dello stack esplicite quando crea determinati thread usati internamente, invece di usare le dimensioni predefinite dello stack per tali thread.  
  
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
|enabled|Attributo obbligatorio.<br /><br /> Specifica se richiedere che le dimensioni dello stack esplicita utilizzare CLR anziché le dimensioni predefinite dello stack quando crea determinati thread usati internamente. Le dimensioni dello stack esplicita sono inferiori alle dimensioni dello stack predefinito pari a 1 MB.|  
  
## <a name="enabled-attribute"></a>Attributo enabled  
  
|Valore|Descrizione|  
|-----------|-----------------|  
|true|Le dimensioni dello stack esplicita della richiesta.|  
|False|Usare le dimensioni predefinite dello stack. Questo è il valore predefinito per il [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)].|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`runtime`|Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.|  
  
## <a name="remarks"></a>Note  
 Questo elemento di configurazione viene usato per richiedere l'utilizzo ridotto della memoria virtuale in un processo, perché le dimensioni di thread espliciti usati da CLR per i thread interni, se la richiesta verrà rispettata, sono inferiori alle dimensioni predefinite.  
  
> [!IMPORTANT]
>  Questo elemento di configurazione è una richiesta a Common Language Runtime anziché a un requisito assoluto. Nel [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], la richiesta verrà rispettata solo per x86 architettura. Questo elemento potrebbe essere completamente ignorato nelle versioni future di CLR o sostituito da dimensioni dello stack esplicite che vengono sempre utilizzate per i thread interno selezionato.  
  
 Specifica di che questo elemento di configurazione è necessaria una affidabilità per l'utilizzo di memoria virtuale più piccolo se CLR soddisfa la richiesta, perché di dimensioni inferiori dello stack potrebbe potenzialmente stack overflow più probabile.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come richiedere che il CLR Usa dimensioni esplicite dello stack per determinati thread usati internamente.  
  
```xml  
<configuration>  
   <runtime>  
      <UseSmallInternalThreadStacks enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche

- [Schema delle impostazioni di runtime](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [Schema dei file di configurazione](../../../../../docs/framework/configure-apps/file-schema/index.md)
