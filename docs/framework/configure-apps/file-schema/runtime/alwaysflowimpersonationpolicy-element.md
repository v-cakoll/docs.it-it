---
title: '&lt;alwaysFlowImpersonationPolicy&gt; elemento'
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
ms.openlocfilehash: 5cc704bbf8631936dbbeb3539ea5ed0d8499f378
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32752273"
---
# <a name="ltalwaysflowimpersonationpolicygt-element"></a><span data-ttu-id="f3ebd-102">&lt;alwaysFlowImpersonationPolicy&gt; elemento</span><span class="sxs-lookup"><span data-stu-id="f3ebd-102">&lt;alwaysFlowImpersonationPolicy&gt; Element</span></span>
<span data-ttu-id="f3ebd-103">Specifica che l'identità di Windows passa sempre attraverso punti asincroni, indipendentemente dalla modalità di rappresentazione.</span><span class="sxs-lookup"><span data-stu-id="f3ebd-103">Specifies that the Windows identity always flows across asynchronous points, regardless of how impersonation was performed.</span></span>  
  
 <span data-ttu-id="f3ebd-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="f3ebd-104">\<configuration></span></span>  
<span data-ttu-id="f3ebd-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="f3ebd-105">\<runtime></span></span>  
<span data-ttu-id="f3ebd-106">\<alwaysFlowImpersonationPolicy></span><span class="sxs-lookup"><span data-stu-id="f3ebd-106">\<alwaysFlowImpersonationPolicy></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3ebd-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f3ebd-107">Syntax</span></span>  
  
```xml  
<alwaysFlowImpersonationPolicy    
  enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f3ebd-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="f3ebd-108">Attributes and Elements</span></span>  
 <span data-ttu-id="f3ebd-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="f3ebd-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f3ebd-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="f3ebd-110">Attributes</span></span>  
  
|<span data-ttu-id="f3ebd-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="f3ebd-111">Attribute</span></span>|<span data-ttu-id="f3ebd-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f3ebd-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="f3ebd-113">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="f3ebd-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="f3ebd-114">Indica se l'identità Windows passa attraverso punti asincroni.</span><span class="sxs-lookup"><span data-stu-id="f3ebd-114">Indicates whether the Windows identity flows across asynchronous points.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="f3ebd-115">Attributo enabled</span><span class="sxs-lookup"><span data-stu-id="f3ebd-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="f3ebd-116">Valore</span><span class="sxs-lookup"><span data-stu-id="f3ebd-116">Value</span></span>|<span data-ttu-id="f3ebd-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f3ebd-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="f3ebd-118">Le finestre di identità non passa attraverso punti asincroni, a meno che non viene eseguita la rappresentazione tramite metodi gestiti, ad esempio <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A>.</span><span class="sxs-lookup"><span data-stu-id="f3ebd-118">The Windows identity does not flow across asynchronous points, unless the impersonation is performed through managed methods such as <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A>.</span></span> <span data-ttu-id="f3ebd-119">Questa è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="f3ebd-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="f3ebd-120">L'identità di Windows è sempre passate attraverso punti asincroni, indipendentemente dalla modalità di rappresentazione.</span><span class="sxs-lookup"><span data-stu-id="f3ebd-120">The Windows identity always flows across asynchronous points, regardless of how impersonation was performed.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f3ebd-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="f3ebd-121">Child Elements</span></span>  
 <span data-ttu-id="f3ebd-122">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="f3ebd-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f3ebd-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="f3ebd-123">Parent Elements</span></span>  
  
|<span data-ttu-id="f3ebd-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="f3ebd-124">Element</span></span>|<span data-ttu-id="f3ebd-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f3ebd-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="f3ebd-126">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f3ebd-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="f3ebd-127">Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="f3ebd-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f3ebd-128">Note</span><span class="sxs-lookup"><span data-stu-id="f3ebd-128">Remarks</span></span>  
 <span data-ttu-id="f3ebd-129">Nelle versioni di .NET Framework 1.0 e 1.1, l'identità di Windows non passa attraverso punti asincroni.</span><span class="sxs-lookup"><span data-stu-id="f3ebd-129">In the .NET Framework versions 1.0 and 1.1, the Windows identity does not flow across asynchronous points.</span></span> <span data-ttu-id="f3ebd-130">In .NET Framework versione 2.0 è un <xref:System.Threading.ExecutionContext> oggetto che contiene informazioni sul thread attualmente in esecuzione e passa attraverso punti asincroni all'interno di un dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="f3ebd-130">In the .NET Framework version 2.0, there is an <xref:System.Threading.ExecutionContext> object that contains information about the currently executing thread, and flows it across asynchronous points within an application domain.</span></span> <span data-ttu-id="f3ebd-131">Il <xref:System.Security.Principal.WindowsIdentity> anche flussi come parte delle informazioni che passano attraverso i punti asincroni, purché la rappresentazione è stata ottenuta usando metodi gestiti, ad esempio <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A> e non tramite altri mezzi, ad esempio platform invoke a metodi nativi.</span><span class="sxs-lookup"><span data-stu-id="f3ebd-131">The <xref:System.Security.Principal.WindowsIdentity> also flows as part of the information that flows across the asynchronous points, provided the impersonation was achieved using managed methods such as <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A> and not through other means such as platform invoke to native methods.</span></span> <span data-ttu-id="f3ebd-132">Questo elemento viene usato per specificare che l'identità Windows passa attraverso punti asincroni, indipendentemente dal modo in cui è stata ottenuta la rappresentazione.</span><span class="sxs-lookup"><span data-stu-id="f3ebd-132">This element is used to specify that the Windows identity does flow across asynchronous points, regardless of how the impersonation was achieved.</span></span>  
  
 <span data-ttu-id="f3ebd-133">È possibile modificare questo comportamento predefinito in altri due modi:</span><span class="sxs-lookup"><span data-stu-id="f3ebd-133">You can alter this default behavior in two other ways:</span></span>  
  
1.  <span data-ttu-id="f3ebd-134">Nel codice gestito in base al thread.</span><span class="sxs-lookup"><span data-stu-id="f3ebd-134">In managed code on a per-thread basis.</span></span>  
  
     <span data-ttu-id="f3ebd-135">È possibile eliminare il flusso in base al thread modificando il <xref:System.Threading.ExecutionContext> e <xref:System.Security.SecurityContext> impostazioni utilizzando il <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>, <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType>, o <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> metodo.</span><span class="sxs-lookup"><span data-stu-id="f3ebd-135">You can suppress the flow on a per-thread basis by modifying the <xref:System.Threading.ExecutionContext> and <xref:System.Security.SecurityContext> settings by using the <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>, <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType>, or <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> method.</span></span>  
  
2.  <span data-ttu-id="f3ebd-136">Nella chiamata all'interfaccia di hosting non gestita caricare common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="f3ebd-136">In the call to the unmanaged hosting interface to load the common language runtime (CLR).</span></span>  
  
     <span data-ttu-id="f3ebd-137">Se un'interfaccia di hosting non gestita (anziché un semplice eseguibile gestito) viene utilizzata per caricare Common Language Runtime, è possibile specificare un flag speciale nella chiamata al [funzione CorBindToRuntimeEx](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) (funzione).</span><span class="sxs-lookup"><span data-stu-id="f3ebd-137">If an unmanaged hosting interface (instead of a simple managed executable) is used to load the CLR, you can specify a special flag in the call to the [CorBindToRuntimeEx Function](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) function.</span></span> <span data-ttu-id="f3ebd-138">Per abilitare la modalità di compatibilità per l'intero processo, impostare il `flags` parametro per [funzione CorBindToRuntimeEx](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) a `STARTUP_ALWAYSFLOW_IMPERSONATION`.</span><span class="sxs-lookup"><span data-stu-id="f3ebd-138">To enable the compatibility mode for the entire process, set the `flags` parameter for [CorBindToRuntimeEx Function](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) to `STARTUP_ALWAYSFLOW_IMPERSONATION`.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="f3ebd-139">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="f3ebd-139">Configuration File</span></span>  
 <span data-ttu-id="f3ebd-140">In un'applicazione .NET Framework, questo elemento può essere usato solo nel file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="f3ebd-140">In a .NET Framework application, this element can be used only in the application configuration file.</span></span>  
  
 <span data-ttu-id="f3ebd-141">Per un'applicazione ASP.NET, il flusso delle rappresentazioni può essere configurato nel file Aspnet. config nel \<cartella Windows > directory \Microsoft.NET\Framework\vx.x.xxxx.</span><span class="sxs-lookup"><span data-stu-id="f3ebd-141">For an ASP.NET application, the impersonation flow can be configured in the aspnet.config file found in the \<Windows Folder>\Microsoft.NET\Framework\vx.x.xxxx directory.</span></span>  
  
 <span data-ttu-id="f3ebd-142">ASP.NET per impostazione predefinita disabilita il flusso delle rappresentazioni nel file Aspnet. config utilizzando le impostazioni di configurazione seguenti:</span><span class="sxs-lookup"><span data-stu-id="f3ebd-142">ASP.NET by default disables the impersonation flow in the aspnet.config file by using the following configuration settings:</span></span>  
  
```xml
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
      <alwaysFlowImpersonationPolicy enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="f3ebd-143">In ASP.NET, se si desidera consentire il flusso delle rappresentazioni, invece, è necessario utilizzare in modo esplicito le impostazioni di configurazione seguenti:</span><span class="sxs-lookup"><span data-stu-id="f3ebd-143">In ASP.NET, if you want to allow the flow of impersonation instead, you must explicitly use the following configuration settings:</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="false"/>  
      <alwaysFlowImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="example"></a><span data-ttu-id="f3ebd-144">Esempio</span><span class="sxs-lookup"><span data-stu-id="f3ebd-144">Example</span></span>  
 <span data-ttu-id="f3ebd-145">Nell'esempio seguente viene illustrato come specificare che l'identità Windows passa attraverso punti asincroni, anche quando la rappresentazione viene ottenuta tramite metodi gestiti.</span><span class="sxs-lookup"><span data-stu-id="f3ebd-145">The following example shows how to specify that the Windows identity flows across asynchronous points, even when the impersonation is achieved through means other than managed methods.</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <alwaysFlowImpersonationPolicy enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f3ebd-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f3ebd-146">See Also</span></span>  
 [<span data-ttu-id="f3ebd-147">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="f3ebd-147">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="f3ebd-148">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="f3ebd-148">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="f3ebd-149">\<legacyImpersonationPolicy > elemento</span><span class="sxs-lookup"><span data-stu-id="f3ebd-149">\<legacyImpersonationPolicy> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/legacyimpersonationpolicy-element.md)
