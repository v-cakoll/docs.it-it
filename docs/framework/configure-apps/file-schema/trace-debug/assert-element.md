---
title: <assert> Elemento
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/assert
- http://schemas.microsoft.com/.NetConfiguration/v2.0#assert
helpviewer_keywords:
- <assert> element
- assert element
ms.assetid: ef4c3229-b151-4d85-8091-e6456af9b935
ms.openlocfilehash: 30ec24aefcf8c4d1e110238a2c60a958eded5545
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699393"
---
# <a name="assert-element"></a>Elemento > \<assert
Specifica se visualizzare una finestra di messaggio quando si chiama il metodo <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>. Specifica anche il nome del file in cui scrivere i messaggi.  
  
[ **\<configuration>** ](../configuration-element.md)  
&nbsp; @ no__t-1[ **\<system. diagnostics >** ](system-diagnostics-element.md)  
&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 **\<assert >**  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<assert assertuienabled="true|false" logfilename="file name"/>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`assertuienabled`|Attributo facoltativo.<br /><br /> Specifica se visualizzare una finestra di messaggio quando il metodo **debug. Assert** restituisce **false**.|  
|`logfilename`|Attributo facoltativo.<br /><br /> Specifica il nome del file in cui scrivere il messaggio se **debug. Assert** restituisce **false**.|  
  
## <a name="assertuienabled-attribute"></a>Attributo AssertUiEnabled  
  
|Value|Descrizione|  
|-----------|-----------------|  
|`true`|Consente di visualizzare la finestra di messaggio. Questa è l'impostazione predefinita.|  
|`false`|La finestra di messaggio non viene visualizzata.|  
  
### <a name="child-elements"></a>Elementi figlio  
 No.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`system.diagnostics`|Specifica i listener di traccia per raccogliere, archiviare e indirizzare i messaggi, oltre al livello di impostazione di un'opzione di traccia.|  
  
## <a name="remarks"></a>Note  
 Entrambi gli attributi nell'elemento **> \<assert** sono facoltativi. È possibile disabilitare le finestre di messaggio senza specificare un file in cui scrivere i messaggi. in alternativa, è possibile specificare un file in cui scrivere i messaggi lasciando abilitate le finestre di messaggio.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come disabilitare la visualizzazione di finestre di messaggio quando si chiama **debug. Assert** e si scrivono i messaggi in `c:\log.txt`.  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <assert assertuienabled="false" logfilename="c:\log.txt"/>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Diagnostics.Debug>
- [Schema delle impostazioni di traccia e debug](index.md)
