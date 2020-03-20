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
# <a name="alwaysflowimpersonationpolicy-element"></a><span data-ttu-id="bdb89-102">\<Elemento>alwaysFlowImpersonationPolicy</span><span class="sxs-lookup"><span data-stu-id="bdb89-102">\<alwaysFlowImpersonationPolicy> Element</span></span>
<span data-ttu-id="bdb89-103">Specifica che l'identità di Windows passa sempre attraverso punti asincroni, indipendentemente dalla modalità di rappresentazione.</span><span class="sxs-lookup"><span data-stu-id="bdb89-103">Specifies that the Windows identity always flows across asynchronous points, regardless of how impersonation was performed.</span></span>  
  
<span data-ttu-id="bdb89-104">[**\<>di configurazione**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="bdb89-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="bdb89-105">&nbsp;&nbsp;[**\<>di runtime**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="bdb89-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="bdb89-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<alwaysFlowImpersonationPolicy>**</span><span class="sxs-lookup"><span data-stu-id="bdb89-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<alwaysFlowImpersonationPolicy>**</span></span>\  
  
## <a name="syntax"></a><span data-ttu-id="bdb89-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bdb89-107">Syntax</span></span>  
  
```xml  
<alwaysFlowImpersonationPolicy
  enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bdb89-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="bdb89-108">Attributes and Elements</span></span>  
 <span data-ttu-id="bdb89-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="bdb89-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bdb89-110">Attributes</span><span class="sxs-lookup"><span data-stu-id="bdb89-110">Attributes</span></span>  
  
|<span data-ttu-id="bdb89-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="bdb89-111">Attribute</span></span>|<span data-ttu-id="bdb89-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bdb89-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="bdb89-113">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="bdb89-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="bdb89-114">Indica se l'identità Windows passa attraverso punti asincroni.</span><span class="sxs-lookup"><span data-stu-id="bdb89-114">Indicates whether the Windows identity flows across asynchronous points.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="bdb89-115">Attributo enabled</span><span class="sxs-lookup"><span data-stu-id="bdb89-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="bdb89-116">valore</span><span class="sxs-lookup"><span data-stu-id="bdb89-116">Value</span></span>|<span data-ttu-id="bdb89-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bdb89-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="bdb89-118">L'identità Windows non passa attraverso punti asincroni, a meno <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A>che la rappresentazione non venga eseguita tramite metodi gestiti come .</span><span class="sxs-lookup"><span data-stu-id="bdb89-118">The Windows identity does not flow across asynchronous points, unless the impersonation is performed through managed methods such as <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A>.</span></span> <span data-ttu-id="bdb89-119">Questa è la modalità predefinita.</span><span class="sxs-lookup"><span data-stu-id="bdb89-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="bdb89-120">L'identità Windows passa sempre attraverso punti asincroni, indipendentemente dalla modalità di rappresentazione.</span><span class="sxs-lookup"><span data-stu-id="bdb89-120">The Windows identity always flows across asynchronous points, regardless of how impersonation was performed.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bdb89-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="bdb89-121">Child Elements</span></span>  
 <span data-ttu-id="bdb89-122">No.</span><span class="sxs-lookup"><span data-stu-id="bdb89-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="bdb89-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="bdb89-123">Parent Elements</span></span>  
  
|<span data-ttu-id="bdb89-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="bdb89-124">Element</span></span>|<span data-ttu-id="bdb89-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bdb89-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="bdb89-126">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="bdb89-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="bdb89-127">Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="bdb89-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bdb89-128">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="bdb89-128">Remarks</span></span>  
 <span data-ttu-id="bdb89-129">In .NET Framework versioni 1.0 e 1.1, l'identità di Windows non passa attraverso punti asincroni.</span><span class="sxs-lookup"><span data-stu-id="bdb89-129">In the .NET Framework versions 1.0 and 1.1, the Windows identity does not flow across asynchronous points.</span></span> <span data-ttu-id="bdb89-130">In .NET Framework versione 2.0 <xref:System.Threading.ExecutionContext> è disponibile un oggetto che contiene informazioni sul thread attualmente in esecuzione e lo passa attraverso punti asincroni all'interno di un dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="bdb89-130">In the .NET Framework version 2.0, there is an <xref:System.Threading.ExecutionContext> object that contains information about the currently executing thread, and flows it across asynchronous points within an application domain.</span></span> <span data-ttu-id="bdb89-131">Il <xref:System.Security.Principal.WindowsIdentity> flussi anche come parte delle informazioni che passa attraverso i punti asincroni, a condizione che la rappresentazione è stata ottenuta utilizzando metodi gestiti come <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A> e non attraverso altri mezzi, ad esempio platform invoke ai metodi nativi.</span><span class="sxs-lookup"><span data-stu-id="bdb89-131">The <xref:System.Security.Principal.WindowsIdentity> also flows as part of the information that flows across the asynchronous points, provided the impersonation was achieved using managed methods such as <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A> and not through other means such as platform invoke to native methods.</span></span> <span data-ttu-id="bdb89-132">Questo elemento viene utilizzato per specificare che l'identità Windows passa attraverso punti asincroni, indipendentemente da come è stata raggiunta la rappresentazione.</span><span class="sxs-lookup"><span data-stu-id="bdb89-132">This element is used to specify that the Windows identity does flow across asynchronous points, regardless of how the impersonation was achieved.</span></span>  
  
 <span data-ttu-id="bdb89-133">È possibile modificare questo comportamento predefinito in altri due modi:You can alter this default behavior in two other ways:</span><span class="sxs-lookup"><span data-stu-id="bdb89-133">You can alter this default behavior in two other ways:</span></span>  
  
1. <span data-ttu-id="bdb89-134">Nel codice gestito in base al thread.</span><span class="sxs-lookup"><span data-stu-id="bdb89-134">In managed code on a per-thread basis.</span></span>  
  
     <span data-ttu-id="bdb89-135">È possibile sopprimere il flusso in <xref:System.Threading.ExecutionContext> <xref:System.Security.SecurityContext> base al <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>thread <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType>modificando <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> le impostazioni e utilizzando il metodo , o .</span><span class="sxs-lookup"><span data-stu-id="bdb89-135">You can suppress the flow on a per-thread basis by modifying the <xref:System.Threading.ExecutionContext> and <xref:System.Security.SecurityContext> settings by using the <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>, <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType>, or <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> method.</span></span>  
  
2. <span data-ttu-id="bdb89-136">Nella chiamata all'interfaccia di hosting non gestita per caricare Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="bdb89-136">In the call to the unmanaged hosting interface to load the common language runtime (CLR).</span></span>  
  
     <span data-ttu-id="bdb89-137">Se viene utilizzata un'interfaccia di hosting non gestita (anziché un semplice eseguibile gestito) per caricare CLR, è possibile specificare un flag speciale nella chiamata alla funzione [CorBindToRuntimeEx](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) .</span><span class="sxs-lookup"><span data-stu-id="bdb89-137">If an unmanaged hosting interface (instead of a simple managed executable) is used to load the CLR, you can specify a special flag in the call to the [CorBindToRuntimeEx Function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) function.</span></span> <span data-ttu-id="bdb89-138">Per attivare la modalità di `flags` compatibilità per l'intero `STARTUP_ALWAYSFLOW_IMPERSONATION`processo, impostare il parametro per la [funzione CorBindToRuntimeEx](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) su .</span><span class="sxs-lookup"><span data-stu-id="bdb89-138">To enable the compatibility mode for the entire process, set the `flags` parameter for [CorBindToRuntimeEx Function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) to `STARTUP_ALWAYSFLOW_IMPERSONATION`.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="bdb89-139">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="bdb89-139">Configuration File</span></span>  
 <span data-ttu-id="bdb89-140">In un'applicazione .NET Framework questo elemento può essere utilizzato solo nel file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="bdb89-140">In a .NET Framework application, this element can be used only in the application configuration file.</span></span>  
  
 <span data-ttu-id="bdb89-141">Per un'applicazione ASP.NET, il flusso di rappresentazione può essere configurato \<nel file aspnet.config che si trova nella directory di Windows> .</span><span class="sxs-lookup"><span data-stu-id="bdb89-141">For an ASP.NET application, the impersonation flow can be configured in the aspnet.config file found in the \<Windows Folder>\Microsoft.NET\Framework\vx.x.xxxx directory.</span></span>  
  
 <span data-ttu-id="bdb89-142">ASP.NET per impostazione predefinita disabilita il flusso di rappresentazione nel file aspnet.config utilizzando le seguenti impostazioni di configurazione:</span><span class="sxs-lookup"><span data-stu-id="bdb89-142">ASP.NET by default disables the impersonation flow in the aspnet.config file by using the following configuration settings:</span></span>  
  
```xml
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
      <alwaysFlowImpersonationPolicy enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="bdb89-143">In ASP.NET, se invece si desidera consentire il flusso della rappresentazione, è necessario utilizzare in modo esplicito le impostazioni di configurazione seguenti:In the user, if you want to allow the flow of impersonation instead, you must explicitly use the following configuration settings:</span><span class="sxs-lookup"><span data-stu-id="bdb89-143">In ASP.NET, if you want to allow the flow of impersonation instead, you must explicitly use the following configuration settings:</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="false"/>  
      <alwaysFlowImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="example"></a><span data-ttu-id="bdb89-144">Esempio</span><span class="sxs-lookup"><span data-stu-id="bdb89-144">Example</span></span>  
 <span data-ttu-id="bdb89-145">Nell'esempio seguente viene illustrato come specificare che l'identità Windows passa attraverso punti asincroni, anche quando la rappresentazione viene ottenuta tramite mezzi diversi dai metodi gestiti.</span><span class="sxs-lookup"><span data-stu-id="bdb89-145">The following example shows how to specify that the Windows identity flows across asynchronous points, even when the impersonation is achieved through means other than managed methods.</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <alwaysFlowImpersonationPolicy enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="bdb89-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bdb89-146">See also</span></span>

- [<span data-ttu-id="bdb89-147">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="bdb89-147">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="bdb89-148">Schema del file di configurazione</span><span class="sxs-lookup"><span data-stu-id="bdb89-148">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="bdb89-149">\<elemento legacyImpersonation>Policy</span><span class="sxs-lookup"><span data-stu-id="bdb89-149">\<legacyImpersonationPolicy> Element</span></span>](legacyimpersonationpolicy-element.md)
