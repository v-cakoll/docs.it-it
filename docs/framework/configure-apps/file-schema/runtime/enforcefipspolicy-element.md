---
title: <enforceFIPSPolicy> Elemento
ms.date: 03/30/2017
helpviewer_keywords:
- enforceFIPSPolicy element
- FIPS
- <enforceFIPSPolicy> element
- Federal Information Processing Standards (FIPS)
ms.assetid: c35509c4-35cf-43c0-bb47-75e4208aa24e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b1aa958e15449949a1b7ca740198fff71295b2ad
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59114833"
---
# <a name="enforcefipspolicy-element"></a>\<enforceFIPSPolicy > elemento
Specifica se applicare un requisito di configurazione del computer che specifica che gli algoritmi di crittografia devono essere conformi a FIPS (Federal Information Processing Standards).  
  
 \<configurazione > elemento  
\<runtime > elemento  
\<enforceFIPSPolicy > elemento  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<enforceFIPSPolicy enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|enabled|Attributo obbligatorio.<br /><br /> Specifica se abilitare l'imposizione di un requisito di configurazione di computer che gli algoritmi di crittografia devono essere conformi a FIPS.|  
  
## <a name="enabled-attribute"></a>Attributo enabled  
  
|Valore|Descrizione|  
|-----------|-----------------|  
|`true`|Se il computer è configurato per richiedere gli algoritmi di crittografia per essere conforme a FIPS, tale requisito viene applicato. Se una classe implementa un algoritmo che non è conforme a FIPS, i costruttori o `Create` metodi per la classe generano eccezioni quando vengono eseguite in tale computer. Questa è l'impostazione predefinita.|  
|`false`|Gli algoritmi di crittografia utilizzati dall'applicazione non sono necessari per essere conforme a FIPS, indipendentemente dalla configurazione del computer.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`runtime`|Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.|  
  
## <a name="remarks"></a>Note  
 A partire da .NET Framework 2.0, la creazione di classi che implementano gli algoritmi di crittografia è controllata dalla configurazione del computer. Se il computer è configurato per richiedere gli algoritmi per sia conforme a FIPS e una classe implementa un algoritmo che non è conforme a FIPS, qualsiasi tentativo di creare un'istanza della classe genera un'eccezione. Costruttori di generano una <xref:System.InvalidOperationException> eccezione, e `Create` metodi generano un <xref:System.Reflection.TargetInvocationException> eccezione con un inner <xref:System.InvalidOperationException> eccezione.  
  
 Se l'applicazione viene eseguita nei computer con configurazioni richiedono la conformità agli standard FIPS e l'applicazione usa un algoritmo che non è conforme a FIPS, è possibile utilizzare questo elemento nel file di configurazione per evitare che common language runtime (CLR) da applicare la conformità FIPS. Questo elemento è stato introdotto nel [!INCLUDE[net_v20SP1_long](../../../../../includes/net-v20sp1-long-md.md)].  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come impedire a CLR di applicare la conformità FIPS.  
  
```xml  
<configuration>  
    <runtime>  
        <enforceFIPSPolicy enabled="false"/>  
    </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche

- [Schema delle impostazioni di runtime](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [Schema dei file di configurazione](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [Modello di crittografia](../../../../../docs/standard/security/cryptography-model.md)
