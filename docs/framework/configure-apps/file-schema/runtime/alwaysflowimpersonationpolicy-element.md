---
title: <alwaysFlowImpersonationPolicy> Elemento
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/alwaysFlowImpersonationPolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#alwaysFlowImpersonationPolicy
helpviewer_keywords:
- alwaysFlowImpersonationPolicy element
- <alwaysFlowImpersonationPolicy> element
ms.assetid: ee622801-9e46-470b-85ab-88c4b1dd2ee1
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 60c61e5b7c176f88e8f2c2e717e60ae40f43fbf6
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55255259"
---
# <a name="alwaysflowimpersonationpolicy-element"></a>\<alwaysFlowImpersonationPolicy > elemento
Specifica che l'identità di Windows passa sempre attraverso punti asincroni, indipendentemente dalla modalità di rappresentazione.  
  
 \<configuration>  
\<runtime>  
\<alwaysFlowImpersonationPolicy>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<alwaysFlowImpersonationPolicy    
  enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`enabled`|Attributo obbligatorio.<br /><br /> Indica se l'identità di Windows passa attraverso punti asincroni.|  
  
## <a name="enabled-attribute"></a>Attributo enabled  
  
|Valore|Descrizione|  
|-----------|-----------------|  
|`false`|Il Windows identità non passa attraverso punti asincroni, a meno che non viene eseguita la rappresentazione tramite, ad esempio i metodi gestiti <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A>. Questa è l'impostazione predefinita.|  
|`true`|L'identità di Windows passa sempre attraverso punti asincroni, indipendentemente dal modo in cui è stata eseguita la rappresentazione.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`runtime`|Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.|  
  
## <a name="remarks"></a>Note  
 Nelle versioni 1.0 e 1.1 di .NET Framework, l'identità di Windows non passa attraverso punti asincroni. In .NET Framework versione 2.0, è presente un <xref:System.Threading.ExecutionContext> oggetto che contiene informazioni relative al thread attualmente in esecuzione e passa attraverso punti asincroni all'interno di un dominio dell'applicazione. Il <xref:System.Security.Principal.WindowsIdentity> inoltre i flussi come parte delle informazioni che passano attraverso punti asincroni, purché la rappresentazione è stata ottenuta usando metodi gestiti, ad esempio <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A> e non tramite altri mezzi, ad esempio platform invoke a metodi nativi. Questo elemento viene usato per specificare che l'identità di Windows passa attraverso punti asincroni, indipendentemente dal modo in cui è stata ottenuta la rappresentazione.  
  
 È possibile modificare questo comportamento predefinito in altri due modi:  
  
1.  Nel codice gestito in un singolo thread.  
  
     È possibile eliminare il flusso di un singolo thread modificando la <xref:System.Threading.ExecutionContext> e <xref:System.Security.SecurityContext> le impostazioni tramite il <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>, <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType>, o <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> (metodo).  
  
2.  Nella chiamata all'interfaccia di hosting non gestita a caricare common language runtime (CLR).  
  
     Se un'interfaccia di hosting non gestita (anziché un semplice eseguibile gestito) consente di caricare Common Language Runtime, è possibile specificare un flag speciale nella chiamata ai [funzione CorBindToRuntimeEx](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) (funzione). Per abilitare la modalità di compatibilità per l'intero processo, impostare il `flags` parametro per [funzione CorBindToRuntimeEx](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) a `STARTUP_ALWAYSFLOW_IMPERSONATION`.  
  
## <a name="configuration-file"></a>File di configurazione  
 In un'applicazione .NET Framework, questo elemento può essere usato solo nel file di configurazione dell'applicazione.  
  
 Per un'applicazione ASP.NET, il flusso delle rappresentazioni può essere configurato nel file ASPNET nel \<cartella Windows > \Microsoft.NET\Framework\vx.x.xxxx directory.  
  
 Per impostazione predefinita ASP.NET così disabilitato il flusso di rappresentazione nel file Aspnet. config usando le impostazioni di configurazione seguenti:  
  
```xml
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
      <alwaysFlowImpersonationPolicy enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
 In ASP.NET, se si vuole consentire il flusso delle rappresentazioni in alternativa, è necessario utilizzare in modo esplicito le impostazioni di configurazione seguenti:  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="false"/>  
      <alwaysFlowImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come specificare che l'identità di Windows passa attraverso punti asincroni, anche quando la rappresentazione viene ottenuta tramite metodi gestiti.  
  
```xml  
<configuration>  
  <runtime>  
    <alwaysFlowImpersonationPolicy enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche
- [Schema delle impostazioni di runtime](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [Schema dei file di configurazione](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [\<legacyImpersonationPolicy > elemento](../../../../../docs/framework/configure-apps/file-schema/runtime/legacyimpersonationpolicy-element.md)
