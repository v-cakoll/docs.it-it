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
ms.openlocfilehash: 164492eb1abc7329481f158963118b47d2c4aebc
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252855"
---
# <a name="alwaysflowimpersonationpolicy-element"></a>\<Elemento > alwaysFlowImpersonationPolicy
Specifica che l'identità di Windows passa sempre attraverso punti asincroni, indipendentemente dalla modalità di rappresentazione.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<> di runtime**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp; **\<alwaysFlowImpersonationPolicy>** \  
  
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
|`enabled`|Attributo obbligatorio.<br /><br /> Indica se l'identità di Windows scorre tra punti asincroni.|  
  
## <a name="enabled-attribute"></a>Attributo enabled  
  
|Valore|Descrizione|  
|-----------|-----------------|  
|`false`|L'identità Windows non viene propagata tra punti asincroni, a meno che la rappresentazione non venga eseguita tramite metodi gestiti <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A>, ad esempio. Questa è l'impostazione predefinita.|  
|`true`|L'identità Windows scorre sempre tra punti asincroni, indipendentemente dal modo in cui è stata eseguita la rappresentazione.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`runtime`|Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.|  
  
## <a name="remarks"></a>Note  
 Nelle versioni .NET Framework 1,0 e 1,1, l'identità Windows non viene propagata tra punti asincroni. In .NET Framework versione 2,0 è presente un <xref:System.Threading.ExecutionContext> oggetto che contiene informazioni sul thread attualmente in esecuzione e lo trasmette attraverso punti asincroni all'interno di un dominio dell'applicazione. Il <xref:System.Security.Principal.WindowsIdentity> flusso viene inoltre eseguito come parte delle informazioni che passano tra i punti asincroni, a condizione che la rappresentazione sia stata realizzata utilizzando metodi <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A> gestiti come e non tramite altri strumenti, ad esempio Platform Invoke ai metodi nativi. Questo elemento viene utilizzato per specificare che l'identità Windows viene propagata tra punti asincroni, indipendentemente dal modo in cui è stata eseguita la rappresentazione.  
  
 È possibile modificare questo comportamento predefinito in altri due modi:  
  
1. Nel codice gestito in base al thread.  
  
     È possibile disattivare il flusso in base ai singoli thread <xref:System.Threading.ExecutionContext> modificando le impostazioni e <xref:System.Security.SecurityContext> usando il <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>metodo, <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType>o <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> .  
  
2. Nella chiamata all'interfaccia host non gestita per caricare il Common Language Runtime (CLR).  
  
     Se per il caricamento di CLR viene utilizzata un'interfaccia di hosting non gestita, anziché un semplice eseguibile gestito, è possibile specificare un flag speciale nella chiamata alla funzione [funzione CorBindToRuntimeEx](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) . Per abilitare la modalità di compatibilità per l'intero processo, impostare `flags` il parametro per la [funzione CorBindToRuntimeEx](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) su `STARTUP_ALWAYSFLOW_IMPERSONATION`.  
  
## <a name="configuration-file"></a>File di configurazione  
 In un'applicazione .NET Framework, questo elemento può essere utilizzato solo nel file di configurazione dell'applicazione.  
  
 Per un'applicazione ASP.NET, il flusso di rappresentazione può essere configurato nel file Aspnet. config presente nella \<cartella Windows > directory \Microsoft.NET\Framework\vx.x.xxxx.  
  
 Per impostazione predefinita, ASP.NET Disabilita il flusso di rappresentazione nel file Aspnet. config usando le impostazioni di configurazione seguenti:  
  
```xml
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
      <alwaysFlowImpersonationPolicy enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
 In ASP.NET, se invece si desidera consentire il flusso di rappresentazione, è necessario utilizzare in modo esplicito le impostazioni di configurazione seguenti:  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="false"/>  
      <alwaysFlowImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come specificare che l'identità di Windows scorre tra punti asincroni, anche quando la rappresentazione viene eseguita tramite mezzi diversi dai metodi gestiti.  
  
```xml  
<configuration>  
  <runtime>  
    <alwaysFlowImpersonationPolicy enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche

- [Schema delle impostazioni di runtime](index.md)
- [Schema dei file di configurazione](../index.md)
- [\<Elemento > legacyImpersonationPolicy](legacyimpersonationpolicy-element.md)
