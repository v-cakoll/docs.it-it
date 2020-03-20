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
# <a name="legacyimpersonationpolicy-element"></a><span data-ttu-id="bb59f-102">\<elemento legacyImpersonation>Policy</span><span class="sxs-lookup"><span data-stu-id="bb59f-102">\<legacyImpersonationPolicy> Element</span></span>
<span data-ttu-id="bb59f-103">Specifica che l'identità di Windows non passa attraverso punti asincroni, indipendentemente dalle impostazioni di flusso per il contesto di esecuzione nel thread corrente.</span><span class="sxs-lookup"><span data-stu-id="bb59f-103">Specifies that the Windows identity does not flow across asynchronous points, regardless of the flow settings for the execution context on the current thread.</span></span>  
  
<span data-ttu-id="bb59f-104">[**\<>di configurazione**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="bb59f-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="bb59f-105">&nbsp;&nbsp;[**\<>di runtime**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="bb59f-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="bb59f-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<legacyImpersonationPolicy>**</span><span class="sxs-lookup"><span data-stu-id="bb59f-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<legacyImpersonationPolicy>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb59f-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bb59f-107">Syntax</span></span>  
  
```xml  
<legacyImpersonationPolicy
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bb59f-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="bb59f-108">Attributes and Elements</span></span>  
 <span data-ttu-id="bb59f-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="bb59f-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bb59f-110">Attributes</span><span class="sxs-lookup"><span data-stu-id="bb59f-110">Attributes</span></span>  
  
|<span data-ttu-id="bb59f-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="bb59f-111">Attribute</span></span>|<span data-ttu-id="bb59f-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bb59f-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="bb59f-113">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="bb59f-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="bb59f-114">Specifica che <xref:System.Security.Principal.WindowsIdentity> l'oggetto non passa attraverso punti <xref:System.Threading.ExecutionContext> asincroni, indipendentemente dalle impostazioni di flusso nel thread corrente.</span><span class="sxs-lookup"><span data-stu-id="bb59f-114">Specifies that the <xref:System.Security.Principal.WindowsIdentity> does not flow across asynchronous points, regardless of the <xref:System.Threading.ExecutionContext> flow settings on the current thread.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="bb59f-115">Attributo enabled</span><span class="sxs-lookup"><span data-stu-id="bb59f-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="bb59f-116">valore</span><span class="sxs-lookup"><span data-stu-id="bb59f-116">Value</span></span>|<span data-ttu-id="bb59f-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bb59f-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="bb59f-118"><xref:System.Security.Principal.WindowsIdentity>in due punti asincroni in base alle impostazioni del <xref:System.Threading.ExecutionContext> flusso per il thread corrente.</span><span class="sxs-lookup"><span data-stu-id="bb59f-118"><xref:System.Security.Principal.WindowsIdentity> flows across asynchronous points depending upon the <xref:System.Threading.ExecutionContext> flow settings for the current thread.</span></span> <span data-ttu-id="bb59f-119">Questa è la modalità predefinita.</span><span class="sxs-lookup"><span data-stu-id="bb59f-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="bb59f-120"><xref:System.Security.Principal.WindowsIdentity>non passa attraverso punti asincroni, <xref:System.Threading.ExecutionContext> indipendentemente dalle impostazioni di flusso nel thread corrente.</span><span class="sxs-lookup"><span data-stu-id="bb59f-120"><xref:System.Security.Principal.WindowsIdentity> does not flow across asynchronous points, regardless of the <xref:System.Threading.ExecutionContext> flow settings on the current thread.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bb59f-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="bb59f-121">Child Elements</span></span>  
 <span data-ttu-id="bb59f-122">No.</span><span class="sxs-lookup"><span data-stu-id="bb59f-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="bb59f-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="bb59f-123">Parent Elements</span></span>  
  
|<span data-ttu-id="bb59f-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="bb59f-124">Element</span></span>|<span data-ttu-id="bb59f-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bb59f-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="bb59f-126">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="bb59f-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="bb59f-127">Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="bb59f-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bb59f-128">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="bb59f-128">Remarks</span></span>  
 <span data-ttu-id="bb59f-129">In .NET Framework versioni 1.0 e <xref:System.Security.Principal.WindowsIdentity> 1.1, il non passa attraverso i punti asincroni definiti dall'utente.</span><span class="sxs-lookup"><span data-stu-id="bb59f-129">In the .NET Framework versions 1.0 and 1.1, the <xref:System.Security.Principal.WindowsIdentity> does not flow across any user-defined asynchronous points.</span></span> <span data-ttu-id="bb59f-130">A partire da .NET Framework versione 2.0, è disponibile un <xref:System.Threading.ExecutionContext> oggetto che contiene informazioni sul thread attualmente in esecuzione e passa attraverso punti asincroni all'interno di un dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="bb59f-130">Starting with the .NET Framework version 2.0, there is an <xref:System.Threading.ExecutionContext> object that contains information about the currently executing thread, and it flows across asynchronous points within an application domain.</span></span> <span data-ttu-id="bb59f-131">L'oggetto <xref:System.Security.Principal.WindowsIdentity> è incluso in questo contesto di esecuzione e pertanto passa anche attraverso i punti asincroni, il che significa che se esiste un contesto di rappresentazione, verrà eseguito anche il flusso.</span><span class="sxs-lookup"><span data-stu-id="bb59f-131">The <xref:System.Security.Principal.WindowsIdentity> is included in this execution context and therefore also flows across the asynchronous points, which means that if an impersonation context exists, it will flow as well.</span></span>  
  
 <span data-ttu-id="bb59f-132">A partire da .NET Framework 2.0, è possibile utilizzare l'elemento `<legacyImpersonationPolicy>` per specificare che <xref:System.Security.Principal.WindowsIdentity> non scorre tra punti asincroni.</span><span class="sxs-lookup"><span data-stu-id="bb59f-132">Starting with the .NET Framework 2.0, you can use the `<legacyImpersonationPolicy>` element to specify that  <xref:System.Security.Principal.WindowsIdentity> does not flow across asynchronous points.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="bb59f-133">Common Language Runtime (CLR) è a conoscenza delle operazioni di rappresentazione eseguite utilizzando solo codice gestito, non della rappresentazione eseguita all'esterno del codice gestito, ad esempio tramite platform invoke a codice non gestito o chiamate dirette a funzioni Win32.</span><span class="sxs-lookup"><span data-stu-id="bb59f-133">The common language runtime (CLR) is aware of impersonation operations performed using only managed code, not of impersonation performed outside of managed code, such as through platform invoke to unmanaged code or through direct calls to Win32 functions.</span></span> <span data-ttu-id="bb59f-134">Solo <xref:System.Security.Principal.WindowsIdentity> gli oggetti gestiti possono `alwaysFlowImpersonationPolicy` passare attraverso punti asincroni, a meno che l'elemento non sia stato impostato su true (`<alwaysFlowImpersonationPolicy enabled="true"/>`).</span><span class="sxs-lookup"><span data-stu-id="bb59f-134">Only managed <xref:System.Security.Principal.WindowsIdentity> objects can flow across asynchronous points, unless the `alwaysFlowImpersonationPolicy` element has been set to true (`<alwaysFlowImpersonationPolicy enabled="true"/>`).</span></span> <span data-ttu-id="bb59f-135">L'impostazione dell'elemento `alwaysFlowImpersonationPolicy` su true specifica che l'identità Windows passa sempre attraverso punti asincroni, indipendentemente dalla modalità di rappresentazione.</span><span class="sxs-lookup"><span data-stu-id="bb59f-135">Setting the `alwaysFlowImpersonationPolicy` element to true specifies that the Windows identity always flows across asynchronous points, regardless of how impersonation was performed.</span></span> <span data-ttu-id="bb59f-136">Per ulteriori informazioni sul flusso della rappresentazione non gestita tra punti asincroni, vedere [ \<alwaysFlowImpersonationPolicy> Element](alwaysflowimpersonationpolicy-element.md).</span><span class="sxs-lookup"><span data-stu-id="bb59f-136">For more information on flowing unmanaged impersonation across asynchronous points, see [\<alwaysFlowImpersonationPolicy> Element](alwaysflowimpersonationpolicy-element.md).</span></span>  
  
 <span data-ttu-id="bb59f-137">È possibile modificare questo comportamento predefinito in altri due modi:You can alter this default behavior in two other ways:</span><span class="sxs-lookup"><span data-stu-id="bb59f-137">You can alter this default behavior in two other ways:</span></span>  
  
1. <span data-ttu-id="bb59f-138">Nel codice gestito in base al thread.</span><span class="sxs-lookup"><span data-stu-id="bb59f-138">In managed code on a per-thread basis.</span></span>  
  
     <span data-ttu-id="bb59f-139">È possibile sopprimere il flusso in <xref:System.Threading.ExecutionContext> <xref:System.Security.SecurityContext> base al <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>thread <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType> <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> modificando le impostazioni e utilizzando il metodo o .</span><span class="sxs-lookup"><span data-stu-id="bb59f-139">You can suppress the flow on a per-thread basis by modifying the <xref:System.Threading.ExecutionContext> and <xref:System.Security.SecurityContext> settings by using the <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>, <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType> or <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> method.</span></span>  
  
2. <span data-ttu-id="bb59f-140">Nella chiamata all'interfaccia di hosting non gestita per caricare Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="bb59f-140">In the call to the unmanaged hosting interface to load the common language runtime (CLR).</span></span>  
  
     <span data-ttu-id="bb59f-141">Se viene utilizzata un'interfaccia di hosting non gestita (anziché un semplice eseguibile gestito) per caricare CLR, è possibile specificare un flag speciale nella chiamata alla funzione [CorBindToRuntimeEx](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) .</span><span class="sxs-lookup"><span data-stu-id="bb59f-141">If an unmanaged hosting interface (instead of a simple managed executable) is used to load the CLR, you can specify a special flag in the call to the [CorBindToRuntimeEx Function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) function.</span></span> <span data-ttu-id="bb59f-142">Per abilitare la modalità di `flags` compatibilità per l'intero processo, impostare il parametro per [la funzione CorBindToRuntimeEx](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) su STARTUP_LEGACY_IMPERSONATION.</span><span class="sxs-lookup"><span data-stu-id="bb59f-142">To enable the compatibility mode for the entire process, set the `flags` parameter for [CorBindToRuntimeEx Function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) to STARTUP_LEGACY_IMPERSONATION.</span></span>  
  
 <span data-ttu-id="bb59f-143">Per ulteriori informazioni, vedere [ \<l'elemento> alwaysFlowImpersonationPolicy](alwaysflowimpersonationpolicy-element.md).</span><span class="sxs-lookup"><span data-stu-id="bb59f-143">For more information, see the [\<alwaysFlowImpersonationPolicy> Element](alwaysflowimpersonationpolicy-element.md).</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="bb59f-144">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="bb59f-144">Configuration File</span></span>  
 <span data-ttu-id="bb59f-145">In un'applicazione .NET Framework questo elemento può essere utilizzato solo nel file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="bb59f-145">In a .NET Framework application, this element can be used only in the application configuration file.</span></span>  
  
 <span data-ttu-id="bb59f-146">Per un'applicazione ASP.NET, il flusso di rappresentazione può essere configurato \<nel file aspnet.config che si trova nella directory di Windows> .</span><span class="sxs-lookup"><span data-stu-id="bb59f-146">For an ASP.NET application, the impersonation flow can be configured in the aspnet.config file found in the \<Windows Folder>\Microsoft.NET\Framework\vx.x.xxxx directory.</span></span>  
  
 <span data-ttu-id="bb59f-147">ASP.NET per impostazione predefinita disabilita il flusso di rappresentazione nel file aspnet.config utilizzando le seguenti impostazioni di configurazione:</span><span class="sxs-lookup"><span data-stu-id="bb59f-147">ASP.NET by default disables the impersonation flow in the aspnet.config file by using the following configuration settings:</span></span>  
  
``` xml
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
      <alwaysFlowImpersonationPolicy enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="bb59f-148">In ASP.NET, se invece si desidera consentire il flusso della rappresentazione, è necessario utilizzare in modo esplicito le impostazioni di configurazione seguenti:In the user, if you want to allow the flow of impersonation instead, you must explicitly use the following configuration settings:</span><span class="sxs-lookup"><span data-stu-id="bb59f-148">In ASP.NET, if you want to allow the flow of impersonation instead, you must explicitly use the following configuration settings:</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="false"/>  
      <alwaysFlowImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="example"></a><span data-ttu-id="bb59f-149">Esempio</span><span class="sxs-lookup"><span data-stu-id="bb59f-149">Example</span></span>  
 <span data-ttu-id="bb59f-150">Nell'esempio seguente viene illustrato come specificare il comportamento legacy che non passa l'identità di Windows tra punti asincroni.</span><span class="sxs-lookup"><span data-stu-id="bb59f-150">The following example shows how to specify the legacy behavior that does not flow the Windows identity across asynchronous points.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="bb59f-151">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bb59f-151">See also</span></span>

- [<span data-ttu-id="bb59f-152">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="bb59f-152">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="bb59f-153">Schema del file di configurazione</span><span class="sxs-lookup"><span data-stu-id="bb59f-153">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="bb59f-154">\<Elemento>alwaysFlowImpersonationPolicy</span><span class="sxs-lookup"><span data-stu-id="bb59f-154">\<alwaysFlowImpersonationPolicy> Element</span></span>](alwaysflowimpersonationpolicy-element.md)
