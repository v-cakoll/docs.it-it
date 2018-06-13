---
title: '&lt;avvio&gt; elemento'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/startup
- http://schemas.microsoft.com/.NetConfiguration/v2.0#startup
helpviewer_keywords:
- container tags, <startup> element
- <startup> element
- startup element
ms.assetid: 536acfd8-f827-452f-838a-e14fa3b87621
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 60699f0335bb35589341558800cfd64503d0aa0a
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32748425"
---
# <a name="ltstartupgt-element"></a>&lt;avvio&gt; elemento
Specifica informazioni di avvio di common language runtime.  
  
 \<configuration>  
\<startup>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<startup useLegacyV2RuntimeActivationPolicy="true|false" >   
</startup>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`useLegacyV2RuntimeActivationPolicy`|Attributo facoltativo.<br /><br /> Specifica se abilitare la [!INCLUDE[dnprdnext](../../../../../includes/dnprdnext-md.md)] criteri di attivazione di runtime o utilizzare il [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] criteri di attivazione.|  
  
## <a name="uselegacyv2runtimeactivationpolicy-attribute"></a>Attributo useLegacyV2RuntimeActivationPolicy  
  
|Valore|Descrizione|  
|-----------|-----------------|  
|`true`|Abilitare [!INCLUDE[dnprdnext](../../../../../includes/dnprdnext-md.md)] criteri di attivazione di runtime per il runtime scelto, ovvero per associare le tecniche di attivazione di runtime legacy (come il [funzione CorBindToRuntimeEx](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)) al runtime scelto dal file di configurazione invece di coprendo li in CLR versione 2.0. Di conseguenza, se CLR versione 4 o versioni successive viene scelto dal file di configurazione, l'assembly in modalità mista creati con versioni precedenti di .NET Framework vengono caricati con la versione CLR selezionata. Impostando questo valore impedisce il caricamento nello stesso processo, in modo efficace la disabilitazione della funzionalità di side-by-side in-process CLR versione 1.1 o CLR versione 2.0.|  
|`false`|Usare i criteri di attivazione predefinito per il [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] e versioni successive, ovvero per consentire di tecniche di attivazione per caricare la versione 1.1 o 2.0 di CLR nel processo di runtime legacy. L'impostazione di questo valore impedisce il caricamento in .NET Framework 4 o versioni successive, a meno che non sono state compilate con .NET Framework 4 o versione successiva degli assembly in modalità mista. Questo valore è il valore predefinito.|  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<requiredRuntime>](../../../../../docs/framework/configure-apps/file-schema/startup/requiredruntime-element.md)|Specifica che l'applicazione supporta solo la versione 1.0 di Common Language Runtime. Nelle applicazioni compilate con la versione 1.1 o successiva devono utilizzare il  **\<supportedRuntime >** elemento.|  
|[\<supportedRuntime>](../../../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md)|Specifica le versioni di Common Language Runtime supportate dall'applicazione.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
  
## <a name="remarks"></a>Note  
 Il  **\<supportedRuntime >** elemento deve essere utilizzato da tutte le applicazioni compilate con la versione 1.1 o successiva del runtime. Nelle applicazioni compilate per supportare esclusivamente la versione 1.0 del runtime è necessario utilizzare il  **\<requiredRuntime >** elemento.  
  
 Il codice di avvio per un'applicazione ospitata in Microsoft Internet Explorer ignora il  **\<avvio >** elemento e i relativi elementi figlio.  
  
## <a name="the-uselegacyv2runtimeactivationpolicy-attribute"></a>L'attributo useLegacyV2RuntimeActivationPolicy  
 Questo attributo è utile se l'applicazione utilizza i percorsi di attivazione legacy, ad esempio il [funzione CorBindToRuntimeEx](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md), e si desidera attivare la versione 4 di CLR anziché una versione precedente, tali percorsi o se l'applicazione compilato con la [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] ma ha una dipendenza su un assembly in modalità mista compilato con una versione precedente di .NET Framework. In tali scenari, impostare l'attributo su `true`.  
  
> [!NOTE]
>  Impostare l'attributo su `true` impedisce il caricamento nello stesso processo, in modo efficace la disabilitazione della funzionalità di side-by-side in-process CLR versione 1.1 o CLR versione 2.0 (vedere [esecuzione Side-by-Side per l'interoperabilità COM](http://msdn.microsoft.com/library/4302318c-3586-49bf-8620-b9a39cdf4a32)).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come specificare la versione di runtime in un file di configurazione.  
  
```xml  
<!-- When used with version 1.0 of the .NET Framework runtime -->  
<configuration>  
   <startup>  
      <requiredRuntime version="v1.0.3705" safemode="true"/>  
   </startup>  
</configuration>  
<!-- When used with version 1.1 (or later) of the runtime -->  
<configuration>  
   <startup>  
      <supportedRuntime version="v1.1.4322"/>  
      <supportedRuntime version="v1.0.3705"/>  
   </startup>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Schema delle impostazioni di avvio](../../../../../docs/framework/configure-apps/file-schema/startup/index.md)  
 [Schema dei file di configurazione](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [\<PaveOver> Specifica della versione di runtime da usare](http://msdn.microsoft.com/library/c376208d-980d-42b4-865b-fbe0d9cc97c2)  
 [Esecuzione side-by-Side per l'interoperabilità COM](http://msdn.microsoft.com/library/4302318c-3586-49bf-8620-b9a39cdf4a32)  
 [In-Process Side-by-Side Execution](../../../../../docs/framework/deployment/in-process-side-by-side-execution.md) (Esecuzione side-by-side In-Process)
