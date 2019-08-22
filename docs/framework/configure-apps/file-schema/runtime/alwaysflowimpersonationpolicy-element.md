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
ms.openlocfilehash: b42c141362d99090db922d3a6b429f05592130cd
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/21/2019
ms.locfileid: "69659021"
---
# <a name="alwaysflowimpersonationpolicy-element"></a><span data-ttu-id="3aeb5-102">\<Elemento > alwaysFlowImpersonationPolicy</span><span class="sxs-lookup"><span data-stu-id="3aeb5-102">\<alwaysFlowImpersonationPolicy> Element</span></span>
<span data-ttu-id="3aeb5-103">Specifica che l'identità di Windows passa sempre attraverso punti asincroni, indipendentemente dalla modalità di rappresentazione.</span><span class="sxs-lookup"><span data-stu-id="3aeb5-103">Specifies that the Windows identity always flows across asynchronous points, regardless of how impersonation was performed.</span></span>  
  
 <span data-ttu-id="3aeb5-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="3aeb5-104">\<configuration></span></span>  
<span data-ttu-id="3aeb5-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="3aeb5-105">\<runtime></span></span>  
<span data-ttu-id="3aeb5-106">\<alwaysFlowImpersonationPolicy></span><span class="sxs-lookup"><span data-stu-id="3aeb5-106">\<alwaysFlowImpersonationPolicy></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3aeb5-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3aeb5-107">Syntax</span></span>  
  
```xml  
<alwaysFlowImpersonationPolicy    
  enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3aeb5-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="3aeb5-108">Attributes and Elements</span></span>  
 <span data-ttu-id="3aeb5-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="3aeb5-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3aeb5-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="3aeb5-110">Attributes</span></span>  
  
|<span data-ttu-id="3aeb5-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="3aeb5-111">Attribute</span></span>|<span data-ttu-id="3aeb5-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3aeb5-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="3aeb5-113">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="3aeb5-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="3aeb5-114">Indica se l'identità di Windows scorre tra punti asincroni.</span><span class="sxs-lookup"><span data-stu-id="3aeb5-114">Indicates whether the Windows identity flows across asynchronous points.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="3aeb5-115">Attributo enabled</span><span class="sxs-lookup"><span data-stu-id="3aeb5-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="3aeb5-116">Valore</span><span class="sxs-lookup"><span data-stu-id="3aeb5-116">Value</span></span>|<span data-ttu-id="3aeb5-117">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="3aeb5-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="3aeb5-118">L'identità Windows non viene propagata tra punti asincroni, a meno che la rappresentazione non venga eseguita tramite metodi gestiti <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A>, ad esempio.</span><span class="sxs-lookup"><span data-stu-id="3aeb5-118">The Windows identity does not flow across asynchronous points, unless the impersonation is performed through managed methods such as <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A>.</span></span> <span data-ttu-id="3aeb5-119">Questa è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="3aeb5-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="3aeb5-120">L'identità Windows scorre sempre tra punti asincroni, indipendentemente dal modo in cui è stata eseguita la rappresentazione.</span><span class="sxs-lookup"><span data-stu-id="3aeb5-120">The Windows identity always flows across asynchronous points, regardless of how impersonation was performed.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3aeb5-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="3aeb5-121">Child Elements</span></span>  
 <span data-ttu-id="3aeb5-122">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="3aeb5-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3aeb5-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="3aeb5-123">Parent Elements</span></span>  
  
|<span data-ttu-id="3aeb5-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="3aeb5-124">Element</span></span>|<span data-ttu-id="3aeb5-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3aeb5-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="3aeb5-126">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3aeb5-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="3aeb5-127">Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="3aeb5-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3aeb5-128">Note</span><span class="sxs-lookup"><span data-stu-id="3aeb5-128">Remarks</span></span>  
 <span data-ttu-id="3aeb5-129">Nelle versioni .NET Framework 1,0 e 1,1, l'identità Windows non viene propagata tra punti asincroni.</span><span class="sxs-lookup"><span data-stu-id="3aeb5-129">In the .NET Framework versions 1.0 and 1.1, the Windows identity does not flow across asynchronous points.</span></span> <span data-ttu-id="3aeb5-130">In .NET Framework versione 2,0 è presente un <xref:System.Threading.ExecutionContext> oggetto che contiene informazioni sul thread attualmente in esecuzione e lo trasmette attraverso punti asincroni all'interno di un dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="3aeb5-130">In the .NET Framework version 2.0, there is an <xref:System.Threading.ExecutionContext> object that contains information about the currently executing thread, and flows it across asynchronous points within an application domain.</span></span> <span data-ttu-id="3aeb5-131">Il <xref:System.Security.Principal.WindowsIdentity> flusso viene inoltre eseguito come parte delle informazioni che passano tra i punti asincroni, a condizione che la rappresentazione sia stata realizzata utilizzando metodi <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A> gestiti come e non tramite altri strumenti, ad esempio Platform Invoke ai metodi nativi.</span><span class="sxs-lookup"><span data-stu-id="3aeb5-131">The <xref:System.Security.Principal.WindowsIdentity> also flows as part of the information that flows across the asynchronous points, provided the impersonation was achieved using managed methods such as <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A> and not through other means such as platform invoke to native methods.</span></span> <span data-ttu-id="3aeb5-132">Questo elemento viene utilizzato per specificare che l'identità Windows viene propagata tra punti asincroni, indipendentemente dal modo in cui è stata eseguita la rappresentazione.</span><span class="sxs-lookup"><span data-stu-id="3aeb5-132">This element is used to specify that the Windows identity does flow across asynchronous points, regardless of how the impersonation was achieved.</span></span>  
  
 <span data-ttu-id="3aeb5-133">È possibile modificare questo comportamento predefinito in altri due modi:</span><span class="sxs-lookup"><span data-stu-id="3aeb5-133">You can alter this default behavior in two other ways:</span></span>  
  
1. <span data-ttu-id="3aeb5-134">Nel codice gestito in base al thread.</span><span class="sxs-lookup"><span data-stu-id="3aeb5-134">In managed code on a per-thread basis.</span></span>  
  
     <span data-ttu-id="3aeb5-135">È possibile disattivare il flusso in base ai singoli thread <xref:System.Threading.ExecutionContext> modificando le impostazioni e <xref:System.Security.SecurityContext> usando il <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>metodo, <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType>o <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="3aeb5-135">You can suppress the flow on a per-thread basis by modifying the <xref:System.Threading.ExecutionContext> and <xref:System.Security.SecurityContext> settings by using the <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>, <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType>, or <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> method.</span></span>  
  
2. <span data-ttu-id="3aeb5-136">Nella chiamata all'interfaccia host non gestita per caricare il Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="3aeb5-136">In the call to the unmanaged hosting interface to load the common language runtime (CLR).</span></span>  
  
     <span data-ttu-id="3aeb5-137">Se per il caricamento di CLR viene utilizzata un'interfaccia di hosting non gestita, anziché un semplice eseguibile gestito, è possibile specificare un flag speciale nella chiamata alla funzione [funzione CorBindToRuntimeEx](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) .</span><span class="sxs-lookup"><span data-stu-id="3aeb5-137">If an unmanaged hosting interface (instead of a simple managed executable) is used to load the CLR, you can specify a special flag in the call to the [CorBindToRuntimeEx Function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) function.</span></span> <span data-ttu-id="3aeb5-138">Per abilitare la modalità di compatibilità per l'intero processo, impostare `flags` il parametro per la [funzione CorBindToRuntimeEx](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) su `STARTUP_ALWAYSFLOW_IMPERSONATION`.</span><span class="sxs-lookup"><span data-stu-id="3aeb5-138">To enable the compatibility mode for the entire process, set the `flags` parameter for [CorBindToRuntimeEx Function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) to `STARTUP_ALWAYSFLOW_IMPERSONATION`.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="3aeb5-139">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="3aeb5-139">Configuration File</span></span>  
 <span data-ttu-id="3aeb5-140">In un'applicazione .NET Framework, questo elemento può essere utilizzato solo nel file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="3aeb5-140">In a .NET Framework application, this element can be used only in the application configuration file.</span></span>  
  
 <span data-ttu-id="3aeb5-141">Per un'applicazione ASP.NET, il flusso di rappresentazione può essere configurato nel file Aspnet. config presente nella \<cartella Windows > directory \Microsoft.NET\Framework\vx.x.xxxx.</span><span class="sxs-lookup"><span data-stu-id="3aeb5-141">For an ASP.NET application, the impersonation flow can be configured in the aspnet.config file found in the \<Windows Folder>\Microsoft.NET\Framework\vx.x.xxxx directory.</span></span>  
  
 <span data-ttu-id="3aeb5-142">Per impostazione predefinita, ASP.NET Disabilita il flusso di rappresentazione nel file Aspnet. config usando le impostazioni di configurazione seguenti:</span><span class="sxs-lookup"><span data-stu-id="3aeb5-142">ASP.NET by default disables the impersonation flow in the aspnet.config file by using the following configuration settings:</span></span>  
  
```xml
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
      <alwaysFlowImpersonationPolicy enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="3aeb5-143">In ASP.NET, se invece si desidera consentire il flusso di rappresentazione, è necessario utilizzare in modo esplicito le impostazioni di configurazione seguenti:</span><span class="sxs-lookup"><span data-stu-id="3aeb5-143">In ASP.NET, if you want to allow the flow of impersonation instead, you must explicitly use the following configuration settings:</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="false"/>  
      <alwaysFlowImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="example"></a><span data-ttu-id="3aeb5-144">Esempio</span><span class="sxs-lookup"><span data-stu-id="3aeb5-144">Example</span></span>  
 <span data-ttu-id="3aeb5-145">Nell'esempio seguente viene illustrato come specificare che l'identità di Windows scorre tra punti asincroni, anche quando la rappresentazione viene eseguita tramite mezzi diversi dai metodi gestiti.</span><span class="sxs-lookup"><span data-stu-id="3aeb5-145">The following example shows how to specify that the Windows identity flows across asynchronous points, even when the impersonation is achieved through means other than managed methods.</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <alwaysFlowImpersonationPolicy enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3aeb5-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3aeb5-146">See also</span></span>

- [<span data-ttu-id="3aeb5-147">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="3aeb5-147">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="3aeb5-148">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="3aeb5-148">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="3aeb5-149">\<Elemento > legacyImpersonationPolicy</span><span class="sxs-lookup"><span data-stu-id="3aeb5-149">\<legacyImpersonationPolicy> Element</span></span>](legacyimpersonationpolicy-element.md)
