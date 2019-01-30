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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a731a54771f3ac589031e856539ba0c21ca22778
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55270489"
---
# <a name="legacyimpersonationpolicy-element"></a>\<legacyImpersonationPolicy > elemento
Specifica che l'identità di Windows non passa attraverso punti asincroni, indipendentemente dalle impostazioni di flusso per il contesto di esecuzione nel thread corrente.  
  
 \<configuration>  
\<runtime>  
\<legacyImpersonationPolicy>  
  
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
|`enabled`|Attributo obbligatorio.<br /><br /> Specifica che il <xref:System.Security.Principal.WindowsIdentity> non passa attraverso punti asincroni, indipendentemente il <xref:System.Threading.ExecutionContext> flusso impostazioni sul thread corrente.|  
  
## <a name="enabled-attribute"></a>Attributo enabled  
  
|Valore|Descrizione|  
|-----------|-----------------|  
|`false`|<xref:System.Security.Principal.WindowsIdentity> passano attraverso punti asincroni, a seconda di <xref:System.Threading.ExecutionContext> flusso le impostazioni per il thread corrente. Questa è l'impostazione predefinita.|  
|`true`|<xref:System.Security.Principal.WindowsIdentity> non passa attraverso punti asincroni, indipendentemente il <xref:System.Threading.ExecutionContext> flusso impostazioni sul thread corrente.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`runtime`|Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.|  
  
## <a name="remarks"></a>Note  
 In .NET Framework versioni 1.0 e 1.1 la <xref:System.Security.Principal.WindowsIdentity> non passa attraverso punti asincroni definiti dall'utente. A partire da .NET Framework versione 2.0, è un <xref:System.Threading.ExecutionContext> oggetto che contiene informazioni relative al thread attualmente in esecuzione che passa attraverso punti asincroni all'interno di un dominio dell'applicazione. Il <xref:System.Security.Principal.WindowsIdentity> è incluso in questo contesto di esecuzione e pertanto anche viene trasmesso attraverso punti asincroni, il che significa che se esiste un contesto di rappresentazione, trasmetterà anche.  
  
 A partire da .NET Framework 2.0, è possibile usare la `<legacyImpersonationPolicy>` elemento per specificare che <xref:System.Security.Principal.WindowsIdentity> non passa attraverso punti asincroni.  
  
> [!NOTE]
>  Common language runtime (CLR) è a conoscenza della rappresentazione operazioni eseguite usando solo codice gestito, non della rappresentazione eseguita all'esterno di codice gestito, ad esempio tramite platform invoke a codice non gestito o tramite le chiamate dirette a funzioni Win32. Solo gestito <xref:System.Security.Principal.WindowsIdentity> gli oggetti possono passa attraverso punti asincroni, a meno che il `alwaysFlowImpersonationPolicy` elemento è stato impostato su true (`<alwaysFlowImpersonationPolicy enabled="true"/>`). L'impostazione di `alwaysFlowImpersonationPolicy` elemento su true, specifica che l'identità di Windows passa sempre attraverso punti asincroni, indipendentemente dal modo in cui è stata eseguita la rappresentazione. Per altre informazioni sul flusso della rappresentazione non gestita attraverso punti asincroni, vedere [ \<alwaysFlowImpersonationPolicy > elemento](../../../../../docs/framework/configure-apps/file-schema/runtime/alwaysflowimpersonationpolicy-element.md).  
  
 È possibile modificare questo comportamento predefinito in altri due modi:  
  
1.  Nel codice gestito in un singolo thread.  
  
     È possibile eliminare il flusso di un singolo thread modificando la <xref:System.Threading.ExecutionContext> e <xref:System.Security.SecurityContext> le impostazioni tramite il <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>, <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType> o <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> (metodo).  
  
2.  Nella chiamata all'interfaccia di hosting non gestita a caricare common language runtime (CLR).  
  
     Se un'interfaccia di hosting non gestita (anziché un semplice eseguibile gestito) consente di caricare Common Language Runtime, è possibile specificare un flag speciale nella chiamata ai [funzione CorBindToRuntimeEx](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) (funzione). Per abilitare la modalità di compatibilità per l'intero processo, impostare il `flags` parametro per [funzione CorBindToRuntimeEx](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) su STARTUP_LEGACY_IMPERSONATION.  
  
 Per altre informazioni, vedere la [ \<alwaysFlowImpersonationPolicy > elemento](../../../../../docs/framework/configure-apps/file-schema/runtime/alwaysflowimpersonationpolicy-element.md).  
  
## <a name="configuration-file"></a>File di configurazione  
 In un'applicazione .NET Framework, questo elemento può essere usato solo nel file di configurazione dell'applicazione.  
  
 Per un'applicazione ASP.NET, il flusso delle rappresentazioni può essere configurato nel file ASPNET nel \<cartella Windows > \Microsoft.NET\Framework\vx.x.xxxx directory.  
  
 Per impostazione predefinita ASP.NET così disabilitato il flusso di rappresentazione nel file Aspnet. config usando le impostazioni di configurazione seguenti:  
  
``` xml
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
 Nell'esempio seguente viene illustrato come specificare il comportamento legacy che non propaga l'identità Windows attraverso punti asincroni.  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche
- [Schema delle impostazioni di runtime](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [Schema dei file di configurazione](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [\<alwaysFlowImpersonationPolicy > elemento](../../../../../docs/framework/configure-apps/file-schema/runtime/alwaysflowimpersonationpolicy-element.md)
