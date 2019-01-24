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
ms.openlocfilehash: fcad683ace327caf06a4a9a6ef5b7cf1d9a9334f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54596436"
---
# <a name="ltalwaysflowimpersonationpolicygt-element"></a><span data-ttu-id="7cd27-102">&lt;alwaysFlowImpersonationPolicy&gt; elemento</span><span class="sxs-lookup"><span data-stu-id="7cd27-102">&lt;alwaysFlowImpersonationPolicy&gt; Element</span></span>
<span data-ttu-id="7cd27-103">Specifica che l'identità di Windows passa sempre attraverso punti asincroni, indipendentemente dalla modalità di rappresentazione.</span><span class="sxs-lookup"><span data-stu-id="7cd27-103">Specifies that the Windows identity always flows across asynchronous points, regardless of how impersonation was performed.</span></span>  
  
 <span data-ttu-id="7cd27-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="7cd27-104">\<configuration></span></span>  
<span data-ttu-id="7cd27-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="7cd27-105">\<runtime></span></span>  
<span data-ttu-id="7cd27-106">\<alwaysFlowImpersonationPolicy></span><span class="sxs-lookup"><span data-stu-id="7cd27-106">\<alwaysFlowImpersonationPolicy></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7cd27-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7cd27-107">Syntax</span></span>  
  
```xml  
<alwaysFlowImpersonationPolicy    
  enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7cd27-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="7cd27-108">Attributes and Elements</span></span>  
 <span data-ttu-id="7cd27-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="7cd27-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7cd27-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="7cd27-110">Attributes</span></span>  
  
|<span data-ttu-id="7cd27-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="7cd27-111">Attribute</span></span>|<span data-ttu-id="7cd27-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7cd27-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="7cd27-113">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="7cd27-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="7cd27-114">Indica se l'identità di Windows passa attraverso punti asincroni.</span><span class="sxs-lookup"><span data-stu-id="7cd27-114">Indicates whether the Windows identity flows across asynchronous points.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="7cd27-115">Attributo enabled</span><span class="sxs-lookup"><span data-stu-id="7cd27-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="7cd27-116">Valore</span><span class="sxs-lookup"><span data-stu-id="7cd27-116">Value</span></span>|<span data-ttu-id="7cd27-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7cd27-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="7cd27-118">Il Windows identità non passa attraverso punti asincroni, a meno che non viene eseguita la rappresentazione tramite, ad esempio i metodi gestiti <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A>.</span><span class="sxs-lookup"><span data-stu-id="7cd27-118">The Windows identity does not flow across asynchronous points, unless the impersonation is performed through managed methods such as <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A>.</span></span> <span data-ttu-id="7cd27-119">Questa è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="7cd27-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="7cd27-120">L'identità di Windows passa sempre attraverso punti asincroni, indipendentemente dal modo in cui è stata eseguita la rappresentazione.</span><span class="sxs-lookup"><span data-stu-id="7cd27-120">The Windows identity always flows across asynchronous points, regardless of how impersonation was performed.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7cd27-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="7cd27-121">Child Elements</span></span>  
 <span data-ttu-id="7cd27-122">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="7cd27-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7cd27-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="7cd27-123">Parent Elements</span></span>  
  
|<span data-ttu-id="7cd27-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="7cd27-124">Element</span></span>|<span data-ttu-id="7cd27-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7cd27-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="7cd27-126">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7cd27-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="7cd27-127">Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="7cd27-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7cd27-128">Note</span><span class="sxs-lookup"><span data-stu-id="7cd27-128">Remarks</span></span>  
 <span data-ttu-id="7cd27-129">Nelle versioni 1.0 e 1.1 di .NET Framework, l'identità di Windows non passa attraverso punti asincroni.</span><span class="sxs-lookup"><span data-stu-id="7cd27-129">In the .NET Framework versions 1.0 and 1.1, the Windows identity does not flow across asynchronous points.</span></span> <span data-ttu-id="7cd27-130">In .NET Framework versione 2.0, è presente un <xref:System.Threading.ExecutionContext> oggetto che contiene informazioni relative al thread attualmente in esecuzione e passa attraverso punti asincroni all'interno di un dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="7cd27-130">In the .NET Framework version 2.0, there is an <xref:System.Threading.ExecutionContext> object that contains information about the currently executing thread, and flows it across asynchronous points within an application domain.</span></span> <span data-ttu-id="7cd27-131">Il <xref:System.Security.Principal.WindowsIdentity> inoltre i flussi come parte delle informazioni che passano attraverso punti asincroni, purché la rappresentazione è stata ottenuta usando metodi gestiti, ad esempio <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A> e non tramite altri mezzi, ad esempio platform invoke a metodi nativi.</span><span class="sxs-lookup"><span data-stu-id="7cd27-131">The <xref:System.Security.Principal.WindowsIdentity> also flows as part of the information that flows across the asynchronous points, provided the impersonation was achieved using managed methods such as <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A> and not through other means such as platform invoke to native methods.</span></span> <span data-ttu-id="7cd27-132">Questo elemento viene usato per specificare che l'identità di Windows passa attraverso punti asincroni, indipendentemente dal modo in cui è stata ottenuta la rappresentazione.</span><span class="sxs-lookup"><span data-stu-id="7cd27-132">This element is used to specify that the Windows identity does flow across asynchronous points, regardless of how the impersonation was achieved.</span></span>  
  
 <span data-ttu-id="7cd27-133">È possibile modificare questo comportamento predefinito in altri due modi:</span><span class="sxs-lookup"><span data-stu-id="7cd27-133">You can alter this default behavior in two other ways:</span></span>  
  
1.  <span data-ttu-id="7cd27-134">Nel codice gestito in un singolo thread.</span><span class="sxs-lookup"><span data-stu-id="7cd27-134">In managed code on a per-thread basis.</span></span>  
  
     <span data-ttu-id="7cd27-135">È possibile eliminare il flusso di un singolo thread modificando la <xref:System.Threading.ExecutionContext> e <xref:System.Security.SecurityContext> le impostazioni tramite il <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>, <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType>, o <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> (metodo).</span><span class="sxs-lookup"><span data-stu-id="7cd27-135">You can suppress the flow on a per-thread basis by modifying the <xref:System.Threading.ExecutionContext> and <xref:System.Security.SecurityContext> settings by using the <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>, <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType>, or <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> method.</span></span>  
  
2.  <span data-ttu-id="7cd27-136">Nella chiamata all'interfaccia di hosting non gestita a caricare common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="7cd27-136">In the call to the unmanaged hosting interface to load the common language runtime (CLR).</span></span>  
  
     <span data-ttu-id="7cd27-137">Se un'interfaccia di hosting non gestita (anziché un semplice eseguibile gestito) consente di caricare Common Language Runtime, è possibile specificare un flag speciale nella chiamata ai [funzione CorBindToRuntimeEx](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) (funzione).</span><span class="sxs-lookup"><span data-stu-id="7cd27-137">If an unmanaged hosting interface (instead of a simple managed executable) is used to load the CLR, you can specify a special flag in the call to the [CorBindToRuntimeEx Function](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) function.</span></span> <span data-ttu-id="7cd27-138">Per abilitare la modalità di compatibilità per l'intero processo, impostare il `flags` parametro per [funzione CorBindToRuntimeEx](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) a `STARTUP_ALWAYSFLOW_IMPERSONATION`.</span><span class="sxs-lookup"><span data-stu-id="7cd27-138">To enable the compatibility mode for the entire process, set the `flags` parameter for [CorBindToRuntimeEx Function](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) to `STARTUP_ALWAYSFLOW_IMPERSONATION`.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="7cd27-139">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="7cd27-139">Configuration File</span></span>  
 <span data-ttu-id="7cd27-140">In un'applicazione .NET Framework, questo elemento può essere usato solo nel file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="7cd27-140">In a .NET Framework application, this element can be used only in the application configuration file.</span></span>  
  
 <span data-ttu-id="7cd27-141">Per un'applicazione ASP.NET, il flusso delle rappresentazioni può essere configurato nel file ASPNET nel \<cartella Windows > \Microsoft.NET\Framework\vx.x.xxxx directory.</span><span class="sxs-lookup"><span data-stu-id="7cd27-141">For an ASP.NET application, the impersonation flow can be configured in the aspnet.config file found in the \<Windows Folder>\Microsoft.NET\Framework\vx.x.xxxx directory.</span></span>  
  
 <span data-ttu-id="7cd27-142">Per impostazione predefinita ASP.NET così disabilitato il flusso di rappresentazione nel file Aspnet. config usando le impostazioni di configurazione seguenti:</span><span class="sxs-lookup"><span data-stu-id="7cd27-142">ASP.NET by default disables the impersonation flow in the aspnet.config file by using the following configuration settings:</span></span>  
  
```xml
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
      <alwaysFlowImpersonationPolicy enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="7cd27-143">In ASP.NET, se si vuole consentire il flusso delle rappresentazioni in alternativa, è necessario utilizzare in modo esplicito le impostazioni di configurazione seguenti:</span><span class="sxs-lookup"><span data-stu-id="7cd27-143">In ASP.NET, if you want to allow the flow of impersonation instead, you must explicitly use the following configuration settings:</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="false"/>  
      <alwaysFlowImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="example"></a><span data-ttu-id="7cd27-144">Esempio</span><span class="sxs-lookup"><span data-stu-id="7cd27-144">Example</span></span>  
 <span data-ttu-id="7cd27-145">Nell'esempio seguente viene illustrato come specificare che l'identità di Windows passa attraverso punti asincroni, anche quando la rappresentazione viene ottenuta tramite metodi gestiti.</span><span class="sxs-lookup"><span data-stu-id="7cd27-145">The following example shows how to specify that the Windows identity flows across asynchronous points, even when the impersonation is achieved through means other than managed methods.</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <alwaysFlowImpersonationPolicy enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="7cd27-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7cd27-146">See also</span></span>
- [<span data-ttu-id="7cd27-147">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="7cd27-147">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="7cd27-148">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="7cd27-148">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="7cd27-149">\<legacyImpersonationPolicy > elemento</span><span class="sxs-lookup"><span data-stu-id="7cd27-149">\<legacyImpersonationPolicy> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/legacyimpersonationpolicy-element.md)
