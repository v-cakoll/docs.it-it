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
ms.openlocfilehash: 7c8ac37932a528ff0f000cbaab49124dec51b88c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154483"
---
# <a name="alwaysflowimpersonationpolicy-element"></a>\<Elemento>alwaysFlowImpersonationPolicy
Specifica che l'identità di Windows passa sempre attraverso punti asincroni, indipendentemente dalla modalità di rappresentazione.  
  
[**\<>di configurazione**](../configuration-element.md)\
&nbsp;&nbsp;[**\<>di runtime**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<alwaysFlowImpersonationPolicy>**\  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<alwaysFlowImpersonationPolicy
  enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributes  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`enabled`|Attributo obbligatorio.<br /><br /> Indica se l'identità Windows passa attraverso punti asincroni.|  
  
## <a name="enabled-attribute"></a>Attributo enabled  
  
|valore|Descrizione|  
|-----------|-----------------|  
|`false`|L'identità Windows non passa attraverso punti asincroni, a meno <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A>che la rappresentazione non venga eseguita tramite metodi gestiti come . Questa è la modalità predefinita.|  
|`true`|L'identità Windows passa sempre attraverso punti asincroni, indipendentemente dalla modalità di rappresentazione.|  
  
### <a name="child-elements"></a>Elementi figlio  
 No.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`runtime`|Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.|  
  
## <a name="remarks"></a>Osservazioni  
 In .NET Framework versioni 1.0 e 1.1, l'identità di Windows non passa attraverso punti asincroni. In .NET Framework versione 2.0 <xref:System.Threading.ExecutionContext> è disponibile un oggetto che contiene informazioni sul thread attualmente in esecuzione e lo passa attraverso punti asincroni all'interno di un dominio applicazione. Il <xref:System.Security.Principal.WindowsIdentity> flussi anche come parte delle informazioni che passa attraverso i punti asincroni, a condizione che la rappresentazione è stata ottenuta utilizzando metodi gestiti come <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A> e non attraverso altri mezzi, ad esempio platform invoke ai metodi nativi. Questo elemento viene utilizzato per specificare che l'identità Windows passa attraverso punti asincroni, indipendentemente da come è stata raggiunta la rappresentazione.  
  
 È possibile modificare questo comportamento predefinito in altri due modi:You can alter this default behavior in two other ways:  
  
1. Nel codice gestito in base al thread.  
  
     È possibile sopprimere il flusso in <xref:System.Threading.ExecutionContext> <xref:System.Security.SecurityContext> base al <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>thread <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType>modificando <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> le impostazioni e utilizzando il metodo , o .  
  
2. Nella chiamata all'interfaccia di hosting non gestita per caricare Common Language Runtime (CLR).  
  
     Se viene utilizzata un'interfaccia di hosting non gestita (anziché un semplice eseguibile gestito) per caricare CLR, è possibile specificare un flag speciale nella chiamata alla funzione [CorBindToRuntimeEx](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) . Per attivare la modalità di `flags` compatibilità per l'intero `STARTUP_ALWAYSFLOW_IMPERSONATION`processo, impostare il parametro per la [funzione CorBindToRuntimeEx](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) su .  
  
## <a name="configuration-file"></a>File di configurazione  
 In un'applicazione .NET Framework questo elemento può essere utilizzato solo nel file di configurazione dell'applicazione.  
  
 Per un'applicazione ASP.NET, il flusso di rappresentazione può essere configurato \<nel file aspnet.config che si trova nella directory di Windows> .  
  
 ASP.NET per impostazione predefinita disabilita il flusso di rappresentazione nel file aspnet.config utilizzando le seguenti impostazioni di configurazione:  
  
```xml
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
      <alwaysFlowImpersonationPolicy enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
 In ASP.NET, se invece si desidera consentire il flusso della rappresentazione, è necessario utilizzare in modo esplicito le impostazioni di configurazione seguenti:In the user, if you want to allow the flow of impersonation instead, you must explicitly use the following configuration settings:  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="false"/>  
      <alwaysFlowImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come specificare che l'identità Windows passa attraverso punti asincroni, anche quando la rappresentazione viene ottenuta tramite mezzi diversi dai metodi gestiti.  
  
```xml  
<configuration>  
  <runtime>  
    <alwaysFlowImpersonationPolicy enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche

- [Schema delle impostazioni di runtime](index.md)
- [Schema del file di configurazione](../index.md)
- [\<elemento legacyImpersonation>Policy](legacyimpersonationpolicy-element.md)
