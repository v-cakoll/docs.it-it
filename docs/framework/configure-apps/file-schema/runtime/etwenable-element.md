---
title: <etwEnable> Elemento
ms.date: 03/30/2017
helpviewer_keywords:
- etwEnable element
- <etwEnable> element
ms.assetid: 29dde982-6d8b-4099-8867-ad0d7733f6dc
ms.openlocfilehash: 14cea171a4a25e148ea32f75a8ef09b83a4ec8ad
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73117389"
---
# <a name="etwenable-element"></a>\<elemento > etwEnable
Specifica se abilitare Event Tracing for Windows (ETW) e gli eventi CLR (Common Language Runtime).  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp; &nbsp;[ **\<runtime >** ](runtime-element.md) \
&nbsp;&nbsp;&nbsp;&nbsp; **\<etwEnabled >**  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<etwEnable enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|enabled|Attributo obbligatorio.<br /><br /> Specifica se ETW deve essere abilitato.|  
  
## <a name="enabled-attribute"></a>Attributo enabled  
  
|Value|Descrizione|  
|-----------|-----------------|  
|true|Abilita ETW. Si tratta dell'impostazione predefinita per le versioni di Windows che iniziano con i sistemi operativi Windows Vista e Windows Server 2008.|  
|False|Disabilitare ETW. Si tratta dell'impostazione predefinita per le versioni precedenti di Windows.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuna.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`runtime`|Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.|  
  
## <a name="remarks"></a>Note  
 A partire da Windows Vista, ETW è abilitato per impostazione predefinita. Utilizzare questo elemento per disabilitare ETW per un'applicazione. Nelle versioni precedenti di Windows, utilizzare questo elemento per abilitare ETW per un'applicazione.  
  
> [!NOTE]
> ETW può essere abilitato o disabilitato a livello globale in un server tramite un'impostazione del registro di sistema. Vedere [controllo .NET Framework registrazione](../../../performance/controlling-logging.md).  
  
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

- [Schema delle impostazioni di runtime](index.md)
- [Schema dei file di configurazione](../index.md)
- [Controllo della registrazione di .NET Framework](../../../performance/controlling-logging.md)
