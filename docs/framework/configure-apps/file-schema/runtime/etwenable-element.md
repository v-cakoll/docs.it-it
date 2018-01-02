---
title: '&lt;etwEnable&gt; elemento'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- etwEnable element
- <etwEnable> element
ms.assetid: 29dde982-6d8b-4099-8867-ad0d7733f6dc
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1d94d49fcb2c395de5172a730923dbe42f67cf35
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltetwenablegt-element"></a>&lt;etwEnable&gt; elemento
Specifica se abilitare Event Tracing for Windows (ETW) e gli eventi CLR (Common Language Runtime).  
  
 \<configurazione > elemento  
\<runtime > elemento  
\<etwEnabled >  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<etwEnable enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|enabled|Attributo obbligatorio.<br /><br /> Specifica se deve essere abilitato ETW.|  
  
## <a name="enabled-attribute"></a>Attributo enabled  
  
|Valore|Descrizione|  
|-----------|-----------------|  
|true|Attiva ETW. Questo è il valore predefinito per le versioni di Windows a partire con i sistemi operativi Windows Vista e Windows Server 2008.|  
|False|Disabilitare ETW. Questo è il valore predefinito per le versioni precedenti di Windows.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`runtime`|Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.|  
  
## <a name="remarks"></a>Note  
 A partire da Windows Vista, ETW è abilitata per impostazione predefinita. Utilizzare questo elemento consente di disabilitare ETW per un'applicazione. Nelle versioni precedenti di Windows, utilizzare questo elemento per abilitare ETW per un'applicazione.  
  
> [!NOTE]
>  ETW può essere abilitato o disabilitato a livello globale in un server utilizzando un'impostazione del Registro di sistema. Vedere [controllo della registrazione di .NET Framework](../../../../../docs/framework/performance/controlling-logging.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come abilitare la traccia ETW per un'applicazione.  
  
```xml  
<configuration>  
   <runtime>  
      <etwEnable enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Schema delle impostazioni di runtime](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [Schema dei file di configurazione](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [Controllo della registrazione di .NET Framework](../../../../../docs/framework/performance/controlling-logging.md)
