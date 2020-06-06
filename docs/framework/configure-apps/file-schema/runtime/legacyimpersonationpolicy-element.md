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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79154104"
---
# <a name="legacyimpersonationpolicy-element"></a>\<legacyImpersonationPolicy> Elemento
Specifica che l'identità di Windows non passa attraverso punti asincroni, indipendentemente dalle impostazioni di flusso per il contesto di esecuzione nel thread corrente.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<legacyImpersonationPolicy>**  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<legacyImpersonationPolicy
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`enabled`|Attributo obbligatorio.<br /><br /> Specifica che l'oggetto non <xref:System.Security.Principal.WindowsIdentity> scorre tra punti asincroni, indipendentemente dalle <xref:System.Threading.ExecutionContext> impostazioni del flusso sul thread corrente.|  
  
## <a name="enabled-attribute"></a>Attributo enabled  
  
|Valore|Description|  
|-----------|-----------------|  
|`false`|<xref:System.Security.Principal.WindowsIdentity>scorre tra punti asincroni a seconda delle <xref:System.Threading.ExecutionContext> impostazioni del flusso per il thread corrente. Questo è il valore predefinito.|  
|`true`|<xref:System.Security.Principal.WindowsIdentity>non viene propagata tra punti asincroni, indipendentemente dalle <xref:System.Threading.ExecutionContext> impostazioni del flusso sul thread corrente.|  
  
### <a name="child-elements"></a>Elementi figlio  
 No.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`runtime`|Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.|  
  
## <a name="remarks"></a>Commenti  
 Nelle versioni .NET Framework 1,0 e 1,1, non passa <xref:System.Security.Principal.WindowsIdentity> tra i punti asincroni definiti dall'utente. A partire da .NET Framework versione 2,0, è presente un <xref:System.Threading.ExecutionContext> oggetto che contiene informazioni sul thread attualmente in esecuzione e viene trasmesso tra punti asincroni all'interno di un dominio dell'applicazione. L'oggetto <xref:System.Security.Principal.WindowsIdentity> è incluso in questo contesto di esecuzione e, di conseguenza, fluisce anche tra i punti asincroni, il che significa che se esiste un contesto di rappresentazione, verrà trasmesso anche il flusso.  
  
 A partire da .NET Framework 2,0, è possibile usare l' `<legacyImpersonationPolicy>` elemento per specificare che non <xref:System.Security.Principal.WindowsIdentity> scorre tra punti asincroni.  
  
> [!NOTE]
> Il Common Language Runtime (CLR) rileva le operazioni di rappresentazione eseguite utilizzando solo codice gestito, non la rappresentazione eseguita all'esterno del codice gestito, ad esempio tramite platform invoke al codice non gestito o tramite chiamate dirette alle funzioni Win32. Solo <xref:System.Security.Principal.WindowsIdentity> gli oggetti gestiti possono fluire tra punti asincroni, a meno che l' `alwaysFlowImpersonationPolicy` elemento non sia impostato su true ( `<alwaysFlowImpersonationPolicy enabled="true"/>` ). Impostando l' `alwaysFlowImpersonationPolicy` elemento su true, viene specificato che l'identità di Windows scorre sempre tra punti asincroni, indipendentemente dal modo in cui è stata eseguita la rappresentazione. Per ulteriori informazioni sulla propagazione della rappresentazione non gestita tra punti asincroni, vedere [ \<alwaysFlowImpersonationPolicy> elemento](alwaysflowimpersonationpolicy-element.md).  
  
 È possibile modificare questo comportamento predefinito in altri due modi:  
  
1. Nel codice gestito in base al thread.  
  
     È possibile disattivare il flusso in base ai singoli thread modificando le <xref:System.Threading.ExecutionContext> Impostazioni e <xref:System.Security.SecurityContext> usando il <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType> <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType> metodo, o <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> .  
  
2. Nella chiamata all'interfaccia host non gestita per caricare il Common Language Runtime (CLR).  
  
     Se per il caricamento di CLR viene utilizzata un'interfaccia di hosting non gestita, anziché un semplice eseguibile gestito, è possibile specificare un flag speciale nella chiamata alla funzione [funzione CorBindToRuntimeEx](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) . Per abilitare la modalità di compatibilità per l'intero processo, impostare il `flags` parametro per la [funzione CorBindToRuntimeEx](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) su STARTUP_LEGACY_IMPERSONATION.  
  
 Per ulteriori informazioni, vedere l' [ \<alwaysFlowImpersonationPolicy> elemento](alwaysflowimpersonationpolicy-element.md).  
  
## <a name="configuration-file"></a>File di configurazione  
 In un'applicazione .NET Framework, questo elemento può essere utilizzato solo nel file di configurazione dell'applicazione.  
  
 Per un'applicazione ASP.NET, il flusso di rappresentazione può essere configurato nel file Aspnet. config presente nella \<Windows Folder> directory \Microsoft.NET\Framework\vx.x.xxxx  
  
 Per impostazione predefinita, ASP.NET Disabilita il flusso di rappresentazione nel file Aspnet. config usando le impostazioni di configurazione seguenti:  
  
``` xml
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
 Nell'esempio seguente viene illustrato come specificare il comportamento legacy che non fluisce sull'identità di Windows tra punti asincroni.  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedi anche

- [Schema delle impostazioni di runtime](index.md)
- [Schema del file di configurazione](../index.md)
- [\<alwaysFlowImpersonationPolicy>Elemento](alwaysflowimpersonationpolicy-element.md)
