---
title: <legacyImpersonationPolicy> Elemento
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#legacyImpersonationPolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/legacyImpersonationPolicy
helpviewer_keywords:
- <legacyImpersonationPolicy> element
- legacyImpersonationPolicy element
ms.assetid: 6e00af10-42f3-4235-8415-1bb2db78394e
ms.openlocfilehash: 5e43ead278ecd4049014f4000a2f056b2190f7e5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154104"
---
# <a name="legacyimpersonationpolicy-element"></a>\<elemento legacyImpersonation>Policy
Specifica che l'identità di Windows non passa attraverso punti asincroni, indipendentemente dalle impostazioni di flusso per il contesto di esecuzione nel thread corrente.  
  
[**\<>di configurazione**](../configuration-element.md)\
&nbsp;&nbsp;[**\<>di runtime**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<legacyImpersonationPolicy>**  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<legacyImpersonationPolicy
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributes  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`enabled`|Attributo obbligatorio.<br /><br /> Specifica che <xref:System.Security.Principal.WindowsIdentity> l'oggetto non passa attraverso punti <xref:System.Threading.ExecutionContext> asincroni, indipendentemente dalle impostazioni di flusso nel thread corrente.|  
  
## <a name="enabled-attribute"></a>Attributo enabled  
  
|valore|Descrizione|  
|-----------|-----------------|  
|`false`|<xref:System.Security.Principal.WindowsIdentity>in due punti asincroni in base alle impostazioni del <xref:System.Threading.ExecutionContext> flusso per il thread corrente. Questa è la modalità predefinita.|  
|`true`|<xref:System.Security.Principal.WindowsIdentity>non passa attraverso punti asincroni, <xref:System.Threading.ExecutionContext> indipendentemente dalle impostazioni di flusso nel thread corrente.|  
  
### <a name="child-elements"></a>Elementi figlio  
 No.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`runtime`|Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.|  
  
## <a name="remarks"></a>Osservazioni  
 In .NET Framework versioni 1.0 e <xref:System.Security.Principal.WindowsIdentity> 1.1, il non passa attraverso i punti asincroni definiti dall'utente. A partire da .NET Framework versione 2.0, è disponibile un <xref:System.Threading.ExecutionContext> oggetto che contiene informazioni sul thread attualmente in esecuzione e passa attraverso punti asincroni all'interno di un dominio applicazione. L'oggetto <xref:System.Security.Principal.WindowsIdentity> è incluso in questo contesto di esecuzione e pertanto passa anche attraverso i punti asincroni, il che significa che se esiste un contesto di rappresentazione, verrà eseguito anche il flusso.  
  
 A partire da .NET Framework 2.0, è possibile utilizzare l'elemento `<legacyImpersonationPolicy>` per specificare che <xref:System.Security.Principal.WindowsIdentity> non scorre tra punti asincroni.  
  
> [!NOTE]
> Common Language Runtime (CLR) è a conoscenza delle operazioni di rappresentazione eseguite utilizzando solo codice gestito, non della rappresentazione eseguita all'esterno del codice gestito, ad esempio tramite platform invoke a codice non gestito o chiamate dirette a funzioni Win32. Solo <xref:System.Security.Principal.WindowsIdentity> gli oggetti gestiti possono `alwaysFlowImpersonationPolicy` passare attraverso punti asincroni, a meno che l'elemento non sia stato impostato su true (`<alwaysFlowImpersonationPolicy enabled="true"/>`). L'impostazione dell'elemento `alwaysFlowImpersonationPolicy` su true specifica che l'identità Windows passa sempre attraverso punti asincroni, indipendentemente dalla modalità di rappresentazione. Per ulteriori informazioni sul flusso della rappresentazione non gestita tra punti asincroni, vedere [ \<alwaysFlowImpersonationPolicy> Element](alwaysflowimpersonationpolicy-element.md).  
  
 È possibile modificare questo comportamento predefinito in altri due modi:You can alter this default behavior in two other ways:  
  
1. Nel codice gestito in base al thread.  
  
     È possibile sopprimere il flusso in <xref:System.Threading.ExecutionContext> <xref:System.Security.SecurityContext> base al <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>thread <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType> <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> modificando le impostazioni e utilizzando il metodo o .  
  
2. Nella chiamata all'interfaccia di hosting non gestita per caricare Common Language Runtime (CLR).  
  
     Se viene utilizzata un'interfaccia di hosting non gestita (anziché un semplice eseguibile gestito) per caricare CLR, è possibile specificare un flag speciale nella chiamata alla funzione [CorBindToRuntimeEx](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) . Per abilitare la modalità di `flags` compatibilità per l'intero processo, impostare il parametro per [la funzione CorBindToRuntimeEx](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) su STARTUP_LEGACY_IMPERSONATION.  
  
 Per ulteriori informazioni, vedere [ \<l'elemento> alwaysFlowImpersonationPolicy](alwaysflowimpersonationpolicy-element.md).  
  
## <a name="configuration-file"></a>File di configurazione  
 In un'applicazione .NET Framework questo elemento può essere utilizzato solo nel file di configurazione dell'applicazione.  
  
 Per un'applicazione ASP.NET, il flusso di rappresentazione può essere configurato \<nel file aspnet.config che si trova nella directory di Windows> .  
  
 ASP.NET per impostazione predefinita disabilita il flusso di rappresentazione nel file aspnet.config utilizzando le seguenti impostazioni di configurazione:  
  
``` xml
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
 Nell'esempio seguente viene illustrato come specificare il comportamento legacy che non passa l'identità di Windows tra punti asincroni.  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche

- [Schema delle impostazioni di runtime](index.md)
- [Schema del file di configurazione](../index.md)
- [\<Elemento>alwaysFlowImpersonationPolicy](alwaysflowimpersonationpolicy-element.md)
