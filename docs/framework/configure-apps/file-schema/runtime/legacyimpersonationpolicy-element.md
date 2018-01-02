---
title: '&lt;legacyImpersonationPolicy&gt; elemento'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#legacyImpersonationPolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/legacyImpersonationPolicy
helpviewer_keywords:
- <legacyImpersonationPolicy> element
- legacyImpersonationPolicy element
ms.assetid: 6e00af10-42f3-4235-8415-1bb2db78394e
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: caeede11d8128af00beb5b1b3426e8c4a5406520
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltlegacyimpersonationpolicygt-element"></a><span data-ttu-id="9ef0b-102">&lt;legacyImpersonationPolicy&gt; elemento</span><span class="sxs-lookup"><span data-stu-id="9ef0b-102">&lt;legacyImpersonationPolicy&gt; Element</span></span>
<span data-ttu-id="9ef0b-103">Specifica che l'identità di Windows non passa attraverso punti asincroni, indipendentemente dalle impostazioni di flusso per il contesto di esecuzione nel thread corrente.</span><span class="sxs-lookup"><span data-stu-id="9ef0b-103">Specifies that the Windows identity does not flow across asynchronous points, regardless of the flow settings for the execution context on the current thread.</span></span>  
  
 <span data-ttu-id="9ef0b-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="9ef0b-104">\<configuration></span></span>  
<span data-ttu-id="9ef0b-105">\<runtime ></span><span class="sxs-lookup"><span data-stu-id="9ef0b-105">\<runtime></span></span>  
<span data-ttu-id="9ef0b-106">\<legacyImpersonationPolicy ></span><span class="sxs-lookup"><span data-stu-id="9ef0b-106">\<legacyImpersonationPolicy></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ef0b-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9ef0b-107">Syntax</span></span>  
  
```xml  
<legacyImpersonationPolicy    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9ef0b-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="9ef0b-108">Attributes and Elements</span></span>  
 <span data-ttu-id="9ef0b-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="9ef0b-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9ef0b-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="9ef0b-110">Attributes</span></span>  
  
|<span data-ttu-id="9ef0b-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="9ef0b-111">Attribute</span></span>|<span data-ttu-id="9ef0b-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9ef0b-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="9ef0b-113">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="9ef0b-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="9ef0b-114">Specifica che il <xref:System.Security.Principal.WindowsIdentity> non passa attraverso punti asincroni, indipendentemente dal valore di <xref:System.Threading.ExecutionContext> flusso impostazioni sul thread corrente.</span><span class="sxs-lookup"><span data-stu-id="9ef0b-114">Specifies that the <xref:System.Security.Principal.WindowsIdentity> does not flow across asynchronous points, regardless of the <xref:System.Threading.ExecutionContext> flow settings on the current thread.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="9ef0b-115">Attributo enabled</span><span class="sxs-lookup"><span data-stu-id="9ef0b-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="9ef0b-116">Valore</span><span class="sxs-lookup"><span data-stu-id="9ef0b-116">Value</span></span>|<span data-ttu-id="9ef0b-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9ef0b-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="9ef0b-118"><xref:System.Security.Principal.WindowsIdentity>passano attraverso punti asincroni varia a seconda di <xref:System.Threading.ExecutionContext> flusso le impostazioni per il thread corrente.</span><span class="sxs-lookup"><span data-stu-id="9ef0b-118"><xref:System.Security.Principal.WindowsIdentity> flows across asynchronous points depending upon the <xref:System.Threading.ExecutionContext> flow settings for the current thread.</span></span> <span data-ttu-id="9ef0b-119">Questa è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="9ef0b-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="9ef0b-120"><xref:System.Security.Principal.WindowsIdentity>non passa attraverso punti asincroni, indipendentemente dal valore di <xref:System.Threading.ExecutionContext> flusso impostazioni sul thread corrente.</span><span class="sxs-lookup"><span data-stu-id="9ef0b-120"><xref:System.Security.Principal.WindowsIdentity> does not flow across asynchronous points, regardless of the <xref:System.Threading.ExecutionContext> flow settings on the current thread.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9ef0b-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="9ef0b-121">Child Elements</span></span>  
 <span data-ttu-id="9ef0b-122">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="9ef0b-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9ef0b-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="9ef0b-123">Parent Elements</span></span>  
  
|<span data-ttu-id="9ef0b-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="9ef0b-124">Element</span></span>|<span data-ttu-id="9ef0b-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9ef0b-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="9ef0b-126">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9ef0b-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="9ef0b-127">Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="9ef0b-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9ef0b-128">Note</span><span class="sxs-lookup"><span data-stu-id="9ef0b-128">Remarks</span></span>  
 <span data-ttu-id="9ef0b-129">In .NET Framework versioni 1.0 e 1.1, il <xref:System.Security.Principal.WindowsIdentity> non passa attraverso punti asincroni definiti dall'utente.</span><span class="sxs-lookup"><span data-stu-id="9ef0b-129">In the .NET Framework versions 1.0 and 1.1, the <xref:System.Security.Principal.WindowsIdentity> does not flow across any user-defined asynchronous points.</span></span> <span data-ttu-id="9ef0b-130">A partire da .NET Framework versione 2.0, è un <xref:System.Threading.ExecutionContext> oggetto che contiene informazioni sui thread attualmente in esecuzione e passa attraverso punti asincroni all'interno di un dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="9ef0b-130">Starting with the .NET Framework version 2.0, there is an <xref:System.Threading.ExecutionContext> object that contains information about the currently executing thread, and it flows across asynchronous points within an application domain.</span></span> <span data-ttu-id="9ef0b-131">Il <xref:System.Security.Principal.WindowsIdentity> è incluso in questo contesto di esecuzione e pertanto anche passano attraverso i punti asincroni, il che significa che se esiste un contesto di rappresentazione, flusso includerà anche.</span><span class="sxs-lookup"><span data-stu-id="9ef0b-131">The <xref:System.Security.Principal.WindowsIdentity> is included in this execution context and therefore also flows across the asynchronous points, which means that if an impersonation context exists, it will flow as well.</span></span>  
  
 <span data-ttu-id="9ef0b-132">A partire da .NET Framework 2.0, è possibile utilizzare il `<legacyImpersonationPolicy>` elemento per specificare che <xref:System.Security.Principal.WindowsIdentity> non passa attraverso punti asincroni.</span><span class="sxs-lookup"><span data-stu-id="9ef0b-132">Starting with the .NET Framework 2.0, you can use the `<legacyImpersonationPolicy>` element to specify that  <xref:System.Security.Principal.WindowsIdentity> does not flow across asynchronous points.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9ef0b-133">Common language runtime (CLR) è a conoscenza della rappresentazione di operazioni eseguite utilizzando solo codice gestito, non della rappresentazione eseguita all'esterno di codice gestito, ad esempio mediante platform invoke a codice non gestito o tramite chiamate dirette alle funzioni Win32.</span><span class="sxs-lookup"><span data-stu-id="9ef0b-133">The common language runtime (CLR) is aware of impersonation operations performed using only managed code, not of impersonation performed outside of managed code, such as through platform invoke to unmanaged code or through direct calls to Win32 functions.</span></span> <span data-ttu-id="9ef0b-134">Solo gestito <xref:System.Security.Principal.WindowsIdentity> oggetti possono attraversare i punti asincroni, a meno che il `alwaysFlowImpersonationPolicy` elemento è stato impostato su true (`<alwaysFlowImpersonationPolicy enabled="true"/>`).</span><span class="sxs-lookup"><span data-stu-id="9ef0b-134">Only managed <xref:System.Security.Principal.WindowsIdentity> objects can flow across asynchronous points, unless the `alwaysFlowImpersonationPolicy` element has been set to true (`<alwaysFlowImpersonationPolicy enabled="true"/>`).</span></span> <span data-ttu-id="9ef0b-135">L'impostazione di `alwaysFlowImpersonationPolicy` elemento su true specifica che l'identità di Windows è sempre passate attraverso punti asincroni, indipendentemente dalla modalità di rappresentazione.</span><span class="sxs-lookup"><span data-stu-id="9ef0b-135">Setting the `alwaysFlowImpersonationPolicy` element to true specifies that the Windows identity always flows across asynchronous points, regardless of how impersonation was performed.</span></span> <span data-ttu-id="9ef0b-136">Per ulteriori informazioni sul flusso della rappresentazione non gestita attraverso punti asincroni, vedere [ \<alwaysFlowImpersonationPolicy > elemento](../../../../../docs/framework/configure-apps/file-schema/runtime/alwaysflowimpersonationpolicy-element.md).</span><span class="sxs-lookup"><span data-stu-id="9ef0b-136">For more information on flowing unmanaged impersonation across asynchronous points, see [\<alwaysFlowImpersonationPolicy> Element](../../../../../docs/framework/configure-apps/file-schema/runtime/alwaysflowimpersonationpolicy-element.md).</span></span>  
  
 <span data-ttu-id="9ef0b-137">È possibile modificare questo comportamento predefinito in altri due modi:</span><span class="sxs-lookup"><span data-stu-id="9ef0b-137">You can alter this default behavior in two other ways:</span></span>  
  
1.  <span data-ttu-id="9ef0b-138">Nel codice gestito in base al thread.</span><span class="sxs-lookup"><span data-stu-id="9ef0b-138">In managed code on a per-thread basis.</span></span>  
  
     <span data-ttu-id="9ef0b-139">È possibile eliminare il flusso in base al thread modificando il <xref:System.Threading.ExecutionContext> e <xref:System.Security.SecurityContext> impostazioni utilizzando il <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>, <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType> o <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> metodo.</span><span class="sxs-lookup"><span data-stu-id="9ef0b-139">You can suppress the flow on a per-thread basis by modifying the <xref:System.Threading.ExecutionContext> and <xref:System.Security.SecurityContext> settings by using the <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>, <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType> or <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> method.</span></span>  
  
2.  <span data-ttu-id="9ef0b-140">Nella chiamata all'interfaccia di hosting non gestita caricare common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="9ef0b-140">In the call to the unmanaged hosting interface to load the common language runtime (CLR).</span></span>  
  
     <span data-ttu-id="9ef0b-141">Se un'interfaccia di hosting non gestita (anziché un semplice eseguibile gestito) viene utilizzata per caricare Common Language Runtime, è possibile specificare un flag speciale nella chiamata al [funzione CorBindToRuntimeEx](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) (funzione).</span><span class="sxs-lookup"><span data-stu-id="9ef0b-141">If an unmanaged hosting interface (instead of a simple managed executable) is used to load the CLR, you can specify a special flag in the call to the [CorBindToRuntimeEx Function](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) function.</span></span> <span data-ttu-id="9ef0b-142">Per abilitare la modalità di compatibilità per l'intero processo, impostare il `flags` parametro per [funzione CorBindToRuntimeEx](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) su STARTUP_LEGACY_IMPERSONATION.</span><span class="sxs-lookup"><span data-stu-id="9ef0b-142">To enable the compatibility mode for the entire process, set the `flags` parameter for [CorBindToRuntimeEx Function](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) to STARTUP_LEGACY_IMPERSONATION.</span></span>  
  
 <span data-ttu-id="9ef0b-143">Per ulteriori informazioni, vedere il [ \<alwaysFlowImpersonationPolicy > elemento](../../../../../docs/framework/configure-apps/file-schema/runtime/alwaysflowimpersonationpolicy-element.md).</span><span class="sxs-lookup"><span data-stu-id="9ef0b-143">For more information, see the [\<alwaysFlowImpersonationPolicy> Element](../../../../../docs/framework/configure-apps/file-schema/runtime/alwaysflowimpersonationpolicy-element.md).</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="9ef0b-144">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="9ef0b-144">Configuration File</span></span>  
 <span data-ttu-id="9ef0b-145">In un'applicazione .NET Framework, questo elemento può essere usato solo nel file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="9ef0b-145">In a .NET Framework application, this element can be used only in the application configuration file.</span></span>  
  
 <span data-ttu-id="9ef0b-146">Per un'applicazione ASP.NET, il flusso delle rappresentazioni può essere configurato nel file Aspnet. config nel \<cartella Windows > directory \Microsoft.NET\Framework\vx.x.xxxx.</span><span class="sxs-lookup"><span data-stu-id="9ef0b-146">For an ASP.NET application, the impersonation flow can be configured in the aspnet.config file found in the \<Windows Folder>\Microsoft.NET\Framework\vx.x.xxxx directory.</span></span>  
  
 <span data-ttu-id="9ef0b-147">ASP.NET per impostazione predefinita disabilita il flusso delle rappresentazioni nel file Aspnet. config utilizzando le impostazioni di configurazione seguenti:</span><span class="sxs-lookup"><span data-stu-id="9ef0b-147">ASP.NET by default disables the impersonation flow in the aspnet.config file by using the following configuration settings:</span></span>  
  
```  
configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
      <alwaysFlowImpersonationPolicy enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="9ef0b-148">In ASP.NET, se si desidera consentire il flusso delle rappresentazioni, invece, è necessario utilizzare in modo esplicito le impostazioni di configurazione seguenti:</span><span class="sxs-lookup"><span data-stu-id="9ef0b-148">In ASP.NET, if you want to allow the flow of impersonation instead, you must explicitly use the following configuration settings:</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="false"/>  
      <alwaysFlowImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="example"></a><span data-ttu-id="9ef0b-149">Esempio</span><span class="sxs-lookup"><span data-stu-id="9ef0b-149">Example</span></span>  
 <span data-ttu-id="9ef0b-150">Nell'esempio seguente viene illustrato come specificare il comportamento legacy che non propaga l'identità Windows attraverso punti asincroni.</span><span class="sxs-lookup"><span data-stu-id="9ef0b-150">The following example shows how to specify the legacy behavior that does not flow the Windows identity across asynchronous points.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="9ef0b-151">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9ef0b-151">See Also</span></span>  
 [<span data-ttu-id="9ef0b-152">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="9ef0b-152">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="9ef0b-153">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="9ef0b-153">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="9ef0b-154">\<alwaysFlowImpersonationPolicy > elemento</span><span class="sxs-lookup"><span data-stu-id="9ef0b-154">\<alwaysFlowImpersonationPolicy> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/alwaysflowimpersonationpolicy-element.md)
