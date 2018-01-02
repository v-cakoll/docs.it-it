---
title: '&lt;NetFx40_PInvokeStackResilience&gt; elemento'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- <NetFx40_PInvokeStackResilience> element
- NetFx40_PInvokeStackResilience element
ms.assetid: 39fb1588-72a4-4479-af74-0605233b68bd
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b17816ee6134dc6b3074256093c0cba07419baf5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltnetfx40pinvokestackresiliencegt-element"></a>&lt;NetFx40_PInvokeStackResilience&gt; elemento
Specifica se il runtime corregge automaticamente le dichiarazioni platform invoke non corrette in fase di esecuzione, al costo di transizioni più lente tra codice gestito e quello non gestito.  
  
 \<configuration>  
\<runtime >  
<NetFx40_PInvokeStackResilience>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<NetFx40_PInvokeStackResilience  enabled="1|0"/>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`enabled`|Attributo obbligatorio.<br /><br /> Specifica se il runtime rileva la piattaforma corretta dichiarazioni invoke e consente di correggere automaticamente lo stack in fase di esecuzione su piattaforme a 32 bit.|  
  
## <a name="enabled-attribute"></a>Attributo enabled  
  
|Valore|Descrizione|  
|-----------|-----------------|  
|`0`|Il runtime Usa introdotto nell'architettura di marshalling di interoperabilità più veloce la [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], che non rileva e Correggi dichiarazioni platform invoke errate. Questa è l'impostazione predefinita.|  
|`1`|Dichiarazioni di richiamo il runtime utilizza transizioni più lente che rileva e Correggi piattaforma non corretta.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`runtime`|Contiene informazioni sulle opzioni di inizializzazione in fase di esecuzione.|  
  
## <a name="remarks"></a>Note  
 Questo elemento consente gli scambi più veloce il marshalling di interoperabilità per dichiarazioni di richiamo di resilienza in fase di esecuzione per la piattaforma non corretta.  
  
 A partire dal [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], un'architettura di marshalling di interoperabilità semplificata fornisce un miglioramento significativo delle prestazioni per le transizioni da codice gestito a codice non gestito. Nelle versioni precedenti di .NET Framework, la piattaforma non corretto a livello rilevato marshalling richiamare dichiarazioni in piattaforme a 32 bit e corrette automaticamente lo stack. La nuova architettura di marshalling elimina questo passaggio. Di conseguenza, le transizioni sono molto veloci, ma una dichiarazione platform invoke errata può causare un errore del programma.  
  
 Per consentire un facile rilevare le dichiarazioni non corrette durante lo sviluppo, è stato migliorato l'esperienza di debug di Visual Studio. Il [pInvokeStackImbalance](../../../../../docs/framework/debug-trace-profile/pinvokestackimbalance-mda.md) assistente al debug gestito (MDA) notifica della piattaforma non corretta invoke dichiarazioni quando l'applicazione è in esecuzione con il debugger collegato.  
  
 Per scenari in cui l'applicazione utilizza componenti che non è possibile ricompilare e che sono dichiarazioni platform invoke errate, è possibile utilizzare il `NetFx40_PInvokeStackResilience` elemento. Aggiunta di questo elemento al file di configurazione dell'applicazione con `enabled="1"` opts in una modalità di compatibilità con il comportamento delle versioni precedenti di .NET Framework, al costo di transizioni più lente. Gli assembly che sono stati compilati con le versioni precedenti di .NET Framework vengono scelti automaticamente in questa modalità di compatibilità e non è necessario questo elemento.  
  
## <a name="configuration-file"></a>File di configurazione  
 Questo elemento può essere usato solo nel file di configurazione dell'applicazione.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente viene illustrata la modalità per acconsentire esplicitamente una maggiore flessibilità rispetto corretto dichiarazioni platform invoke per un'applicazione, al costo di transizioni più lente tra codice gestito e.  
  
```xml  
<configuration>  
   <runtime>  
      <NetFx40_PInvokeStackResilience enabled="1"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Schema delle impostazioni di runtime](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [Schema dei file di configurazione](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [pInvokeStackImbalance](../../../../../docs/framework/debug-trace-profile/pinvokestackimbalance-mda.md)
