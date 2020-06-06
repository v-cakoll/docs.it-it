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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79154483"
---
# <a name="alwaysflowimpersonationpolicy-element"></a><span data-ttu-id="7015c-102">\<alwaysFlowImpersonationPolicy> Elemento</span><span class="sxs-lookup"><span data-stu-id="7015c-102">\<alwaysFlowImpersonationPolicy> Element</span></span>
<span data-ttu-id="7015c-103">Specifica che l'identità di Windows passa sempre attraverso punti asincroni, indipendentemente dalla modalità di rappresentazione.</span><span class="sxs-lookup"><span data-stu-id="7015c-103">Specifies that the Windows identity always flows across asynchronous points, regardless of how impersonation was performed.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<alwaysFlowImpersonationPolicy>**\  
  
## <a name="syntax"></a><span data-ttu-id="7015c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7015c-104">Syntax</span></span>  
  
```xml  
<alwaysFlowImpersonationPolicy
  enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7015c-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="7015c-105">Attributes and Elements</span></span>  
 <span data-ttu-id="7015c-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="7015c-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7015c-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="7015c-107">Attributes</span></span>  
  
|<span data-ttu-id="7015c-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="7015c-108">Attribute</span></span>|<span data-ttu-id="7015c-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7015c-109">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="7015c-110">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="7015c-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="7015c-111">Indica se l'identità di Windows scorre tra punti asincroni.</span><span class="sxs-lookup"><span data-stu-id="7015c-111">Indicates whether the Windows identity flows across asynchronous points.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="7015c-112">Attributo enabled</span><span class="sxs-lookup"><span data-stu-id="7015c-112">enabled Attribute</span></span>  
  
|<span data-ttu-id="7015c-113">Valore</span><span class="sxs-lookup"><span data-stu-id="7015c-113">Value</span></span>|<span data-ttu-id="7015c-114">Description</span><span class="sxs-lookup"><span data-stu-id="7015c-114">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="7015c-115">L'identità Windows non viene propagata tra punti asincroni, a meno che la rappresentazione non venga eseguita tramite metodi gestiti, ad esempio <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A> .</span><span class="sxs-lookup"><span data-stu-id="7015c-115">The Windows identity does not flow across asynchronous points, unless the impersonation is performed through managed methods such as <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A>.</span></span> <span data-ttu-id="7015c-116">Questo è il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="7015c-116">This is the default.</span></span>|  
|`true`|<span data-ttu-id="7015c-117">L'identità Windows scorre sempre tra punti asincroni, indipendentemente dal modo in cui è stata eseguita la rappresentazione.</span><span class="sxs-lookup"><span data-stu-id="7015c-117">The Windows identity always flows across asynchronous points, regardless of how impersonation was performed.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7015c-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="7015c-118">Child Elements</span></span>  
 <span data-ttu-id="7015c-119">No.</span><span class="sxs-lookup"><span data-stu-id="7015c-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7015c-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="7015c-120">Parent Elements</span></span>  
  
|<span data-ttu-id="7015c-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="7015c-121">Element</span></span>|<span data-ttu-id="7015c-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7015c-122">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="7015c-123">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7015c-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="7015c-124">Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="7015c-124">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7015c-125">Commenti</span><span class="sxs-lookup"><span data-stu-id="7015c-125">Remarks</span></span>  
 <span data-ttu-id="7015c-126">Nelle versioni .NET Framework 1,0 e 1,1, l'identità Windows non viene propagata tra punti asincroni.</span><span class="sxs-lookup"><span data-stu-id="7015c-126">In the .NET Framework versions 1.0 and 1.1, the Windows identity does not flow across asynchronous points.</span></span> <span data-ttu-id="7015c-127">In .NET Framework versione 2,0 è presente un <xref:System.Threading.ExecutionContext> oggetto che contiene informazioni sul thread attualmente in esecuzione e lo trasmette attraverso punti asincroni all'interno di un dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="7015c-127">In the .NET Framework version 2.0, there is an <xref:System.Threading.ExecutionContext> object that contains information about the currently executing thread, and flows it across asynchronous points within an application domain.</span></span> <span data-ttu-id="7015c-128">Il <xref:System.Security.Principal.WindowsIdentity> flusso viene inoltre eseguito come parte delle informazioni che passano tra i punti asincroni, a condizione che la rappresentazione sia stata realizzata utilizzando metodi gestiti come <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A> e non tramite altri strumenti, ad esempio Platform Invoke ai metodi nativi.</span><span class="sxs-lookup"><span data-stu-id="7015c-128">The <xref:System.Security.Principal.WindowsIdentity> also flows as part of the information that flows across the asynchronous points, provided the impersonation was achieved using managed methods such as <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A> and not through other means such as platform invoke to native methods.</span></span> <span data-ttu-id="7015c-129">Questo elemento viene utilizzato per specificare che l'identità Windows viene propagata tra punti asincroni, indipendentemente dal modo in cui è stata eseguita la rappresentazione.</span><span class="sxs-lookup"><span data-stu-id="7015c-129">This element is used to specify that the Windows identity does flow across asynchronous points, regardless of how the impersonation was achieved.</span></span>  
  
 <span data-ttu-id="7015c-130">È possibile modificare questo comportamento predefinito in altri due modi:</span><span class="sxs-lookup"><span data-stu-id="7015c-130">You can alter this default behavior in two other ways:</span></span>  
  
1. <span data-ttu-id="7015c-131">Nel codice gestito in base al thread.</span><span class="sxs-lookup"><span data-stu-id="7015c-131">In managed code on a per-thread basis.</span></span>  
  
     <span data-ttu-id="7015c-132">È possibile disattivare il flusso in base ai singoli thread modificando le <xref:System.Threading.ExecutionContext> Impostazioni e <xref:System.Security.SecurityContext> usando il <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType> <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType> metodo, o <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="7015c-132">You can suppress the flow on a per-thread basis by modifying the <xref:System.Threading.ExecutionContext> and <xref:System.Security.SecurityContext> settings by using the <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>, <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType>, or <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> method.</span></span>  
  
2. <span data-ttu-id="7015c-133">Nella chiamata all'interfaccia host non gestita per caricare il Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="7015c-133">In the call to the unmanaged hosting interface to load the common language runtime (CLR).</span></span>  
  
     <span data-ttu-id="7015c-134">Se per il caricamento di CLR viene utilizzata un'interfaccia di hosting non gestita, anziché un semplice eseguibile gestito, è possibile specificare un flag speciale nella chiamata alla funzione [funzione CorBindToRuntimeEx](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) .</span><span class="sxs-lookup"><span data-stu-id="7015c-134">If an unmanaged hosting interface (instead of a simple managed executable) is used to load the CLR, you can specify a special flag in the call to the [CorBindToRuntimeEx Function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) function.</span></span> <span data-ttu-id="7015c-135">Per abilitare la modalità di compatibilità per l'intero processo, impostare il `flags` parametro per la [funzione CorBindToRuntimeEx](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) su `STARTUP_ALWAYSFLOW_IMPERSONATION` .</span><span class="sxs-lookup"><span data-stu-id="7015c-135">To enable the compatibility mode for the entire process, set the `flags` parameter for [CorBindToRuntimeEx Function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) to `STARTUP_ALWAYSFLOW_IMPERSONATION`.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="7015c-136">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="7015c-136">Configuration File</span></span>  
 <span data-ttu-id="7015c-137">In un'applicazione .NET Framework, questo elemento può essere utilizzato solo nel file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="7015c-137">In a .NET Framework application, this element can be used only in the application configuration file.</span></span>  
  
 <span data-ttu-id="7015c-138">Per un'applicazione ASP.NET, il flusso di rappresentazione può essere configurato nel file Aspnet. config presente nella \<Windows Folder> directory \Microsoft.NET\Framework\vx.x.xxxx</span><span class="sxs-lookup"><span data-stu-id="7015c-138">For an ASP.NET application, the impersonation flow can be configured in the aspnet.config file found in the \<Windows Folder>\Microsoft.NET\Framework\vx.x.xxxx directory.</span></span>  
  
 <span data-ttu-id="7015c-139">Per impostazione predefinita, ASP.NET Disabilita il flusso di rappresentazione nel file Aspnet. config usando le impostazioni di configurazione seguenti:</span><span class="sxs-lookup"><span data-stu-id="7015c-139">ASP.NET by default disables the impersonation flow in the aspnet.config file by using the following configuration settings:</span></span>  
  
```xml
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
      <alwaysFlowImpersonationPolicy enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="7015c-140">In ASP.NET, se invece si desidera consentire il flusso di rappresentazione, è necessario utilizzare in modo esplicito le impostazioni di configurazione seguenti:</span><span class="sxs-lookup"><span data-stu-id="7015c-140">In ASP.NET, if you want to allow the flow of impersonation instead, you must explicitly use the following configuration settings:</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="false"/>  
      <alwaysFlowImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="example"></a><span data-ttu-id="7015c-141">Esempio</span><span class="sxs-lookup"><span data-stu-id="7015c-141">Example</span></span>  
 <span data-ttu-id="7015c-142">Nell'esempio seguente viene illustrato come specificare che l'identità di Windows scorre tra punti asincroni, anche quando la rappresentazione viene eseguita tramite mezzi diversi dai metodi gestiti.</span><span class="sxs-lookup"><span data-stu-id="7015c-142">The following example shows how to specify that the Windows identity flows across asynchronous points, even when the impersonation is achieved through means other than managed methods.</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <alwaysFlowImpersonationPolicy enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="7015c-143">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="7015c-143">See also</span></span>

- [<span data-ttu-id="7015c-144">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="7015c-144">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="7015c-145">Schema del file di configurazione</span><span class="sxs-lookup"><span data-stu-id="7015c-145">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="7015c-146">\<legacyImpersonationPolicy>Elemento</span><span class="sxs-lookup"><span data-stu-id="7015c-146">\<legacyImpersonationPolicy> Element</span></span>](legacyimpersonationpolicy-element.md)
