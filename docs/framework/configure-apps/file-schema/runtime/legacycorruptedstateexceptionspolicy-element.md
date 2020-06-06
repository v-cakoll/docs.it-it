---
title: <legacyCorruptedStateExceptionsPolicy> Elemento
ms.date: 03/30/2017
helpviewer_keywords:
- <legacyCorruptedStateExceptionsPolicy> element
- legacyCorruptedStateExceptionsPolicy element
ms.assetid: e0a55ddc-bfa8-4f3e-ac14-d1fc3330e4bb
ms.openlocfilehash: d1d29a37999a01f3e370897a1052f4f94435a218
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "73116463"
---
# <a name="legacycorruptedstateexceptionspolicy-element"></a>\<legacyCorruptedStateExceptionsPolicy> Elemento
Specifica se il Common Language Runtime consente al codice gestito di intercettare le violazioni di accesso e altre eccezioni di stato danneggiate.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<legacyCorruptedStateExceptionsPolicy>**  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<legacyCorruptedStateExceptionsPolicy enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`enabled`|Attributo obbligatorio.<br /><br /> Specifica che l'applicazione rileverà gli errori di eccezioni di stato danneggiato, ad esempio le violazioni di accesso.|  
  
## <a name="enabled-attribute"></a>Attributo enabled  
  
|Valore|Description|  
|-----------|-----------------|  
|`false`|L'applicazione non rileverà gli errori di eccezione di stato danneggiato, ad esempio le violazioni di accesso. Questo è il valore predefinito.|  
|`true`|L'applicazione rileverà gli errori di eccezioni di stato danneggiato, ad esempio le violazioni di accesso.|  
  
### <a name="child-elements"></a>Elementi figlio  
 No.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`runtime`|Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.|  
  
## <a name="remarks"></a>Commenti  
 Nel .NET Framework versione 3,5 e versioni precedenti, il Common Language Runtime codice gestito consentito per intercettare le eccezioni generate da Stati di processo danneggiati. Una violazione di accesso è un esempio di questo tipo di eccezione.  
  
 A partire da .NET Framework 4, il codice gestito non rileva più questi tipi di eccezioni nei `catch` blocchi. Tuttavia, è possibile eseguire l'override di questa modifica e mantenere la gestione delle eccezioni di stato danneggiate in due modi:  
  
- Impostare l' `<legacyCorruptedStateExceptionsPolicy>` attributo dell'elemento `enabled` su `true` . Questa impostazione di configurazione viene applicata processwide e influiscono su tutti i metodi.  
  
 -oppure-  
  
- Applicare l' <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute?displayProperty=nameWithType> attributo al metodo che contiene il blocco Exceptions `catch` .  
  
 Questo elemento di configurazione è disponibile solo in .NET Framework 4 e versioni successive.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come specificare che l'applicazione deve ripristinare il comportamento prima del .NET Framework 4 e rilevare tutti gli errori di eccezioni di stato danneggiato.  
  
```xml  
<configuration>  
   <runtime>  
      <legacyCorruptedStateExceptionsPolicy enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedi anche

- <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute>
- [Schema delle impostazioni di runtime](index.md)
- [Schema del file di configurazione](../index.md)
