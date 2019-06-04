---
title: <legacyCorruptedStateExceptionsPolicy> Elemento
ms.date: 03/30/2017
helpviewer_keywords:
- <legacyCorruptedStateExceptionsPolicy> element
- legacyCorruptedStateExceptionsPolicy element
ms.assetid: e0a55ddc-bfa8-4f3e-ac14-d1fc3330e4bb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6191ee2169a85725f0367763874e60c0ceb1d7a4
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2019
ms.locfileid: "66489429"
---
# <a name="legacycorruptedstateexceptionspolicy-element"></a>\<legacyCorruptedStateExceptionsPolicy > elemento
Specifica se common language runtime consente al codice gestito rilevare le violazioni di accesso e altre eccezioni stato danneggiato.  
  
 \<configuration>  
\<runtime>  
\<legacyCorruptedStateExceptionsPolicy>  
  
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
 In .NET Framework versione 3.5 e versioni precedenti, common language runtime consente al codice gestito intercettare le eccezioni che sono state generate gli stati di processo danneggiato. Una violazione di accesso è un esempio di questo tipo di eccezione.  
  
 A partire da .NET Framework 4, il codice gestito non rileva più questi tipi di eccezioni in `catch` blocchi. Tuttavia, è possibile eseguire l'override di questa modifica e mantenere la gestione delle eccezioni stato danneggiato in due modi:  
  
- Impostare il `<legacyCorruptedStateExceptionsPolicy>` dell'elemento `enabled` dell'attributo `true`. Questa impostazione di configurazione viene applicata all'intero processo e influisce su tutti i metodi.  
  
 -oppure-  
  
- Si applicano i <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute?displayProperty=nameWithType> al metodo che contiene le eccezioni `catch` blocco.  
  
 Questo elemento di configurazione è disponibile solo in .NET Framework 4 e versioni successive.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come specificare che l'applicazione deve ripristinare il comportamento prima di .NET Framework 4 e rilevare tutte le eccezioni stato danneggiato.  
  
```xml  
<configuration>  
   <runtime>  
      <legacyCorruptedStateExceptionsPolicy enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute>
- [Schema delle impostazioni di runtime](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [Schema dei file di configurazione](../../../../../docs/framework/configure-apps/file-schema/index.md)
