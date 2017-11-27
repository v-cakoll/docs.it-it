---
title: '&lt;legacyCorruptedStateExceptionsPolicy&gt; elemento'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- <legacyCorruptedStateExceptionsPolicy> element
- legacyCorruptedStateExceptionsPolicy element
ms.assetid: e0a55ddc-bfa8-4f3e-ac14-d1fc3330e4bb
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e4379f6f38c886504905483cefd7c7a6bbd519ff
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ltlegacycorruptedstateexceptionspolicygt-element"></a>&lt;legacyCorruptedStateExceptionsPolicy&gt; elemento
Specifica se common language runtime consente al codice gestito rilevare le violazioni di accesso e le altre eccezioni stato danneggiato.  
  
 \<configuration>  
\<runtime >  
\<legacyCorruptedStateExceptionsPolicy >  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<legacyCorruptedStateExceptionsPolicy enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`enabled`|Attributo obbligatorio.<br /><br /> Specifica che l'applicazione verrà intercettare le eccezioni di stato danneggiato, ad esempio le violazioni di accesso.|  
  
## <a name="enabled-attribute"></a>Attributo enabled  
  
|Valore|Descrizione|  
|-----------|-----------------|  
|`false`|L'applicazione non rileva le eccezioni di stato danneggiato, ad esempio le violazioni di accesso. Questa è l'impostazione predefinita.|  
|`true`|L'applicazione rileva le eccezioni di stato danneggiato, ad esempio le violazioni di accesso.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`runtime`|Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.|  
  
## <a name="remarks"></a>Note  
 In .NET Framework versione 3.5 e versioni precedenti, common language runtime consente al codice gestito intercettare le eccezioni che sono state generate gli stati processo danneggiato. Una violazione di accesso è un esempio di questo tipo di eccezione.  
  
 A partire dal [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)]gestita codice non rileva più questi tipi di eccezioni in `catch` blocchi. Tuttavia, è possibile eseguire l'override di questa modifica e mantenere la gestione delle eccezioni di stato danneggiato in due modi:  
  
-   Impostare il `<legacyCorruptedStateExceptionsPolicy>` dell'elemento `enabled` attributo `true`. Questa impostazione di configurazione viene applicata all'intero processo e influisce su tutti i metodi.  
  
 -oppure-  
  
-   Applicare il <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute?displayProperty=nameWithType> attributo al metodo che contiene le eccezioni `catch` blocco.  
  
 È disponibile solo in questo elemento di configurazione di [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] e versioni successive.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come specificare che l'applicazione deve ripristinare il comportamento prima di [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)]e rilevare tutte le eccezioni di stato danneggiato.  
  
```xml  
<configuration>  
   <runtime>  
      <legacyCorruptedStateExceptionsPolicy enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute>  
 [Schema delle impostazioni di runtime](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [Schema dei file di configurazione](../../../../../docs/framework/configure-apps/file-schema/index.md)
