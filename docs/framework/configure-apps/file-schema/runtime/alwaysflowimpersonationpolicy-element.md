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
# <a name="alwaysflowimpersonationpolicy-element"></a><span data-ttu-id="0563a-102">\<Elemento > alwaysFlowImpersonationPolicy</span><span class="sxs-lookup"><span data-stu-id="0563a-102">\<alwaysFlowImpersonationPolicy> Element</span></span>
<span data-ttu-id="0563a-103">Specifica che l'identità di Windows passa sempre attraverso punti asincroni, indipendentemente dalla modalità di rappresentazione.</span><span class="sxs-lookup"><span data-stu-id="0563a-103">Specifies that the Windows identity always flows across asynchronous points, regardless of how impersonation was performed.</span></span>  
  
<span data-ttu-id="0563a-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="0563a-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="0563a-105">&nbsp;&nbsp;[ **\<> di runtime**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="0563a-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="0563a-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<alwaysFlowImpersonationPolicy>** </span><span class="sxs-lookup"><span data-stu-id="0563a-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<alwaysFlowImpersonationPolicy>**</span></span>\  
  
## <a name="syntax"></a><span data-ttu-id="0563a-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0563a-107">Syntax</span></span>  
  
```xml  
<alwaysFlowImpersonationPolicy    
  enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0563a-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="0563a-108">Attributes and Elements</span></span>  
 <span data-ttu-id="0563a-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="0563a-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0563a-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="0563a-110">Attributes</span></span>  
  
|<span data-ttu-id="0563a-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="0563a-111">Attribute</span></span>|<span data-ttu-id="0563a-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0563a-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="0563a-113">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="0563a-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="0563a-114">Indica se l'identità di Windows scorre tra punti asincroni.</span><span class="sxs-lookup"><span data-stu-id="0563a-114">Indicates whether the Windows identity flows across asynchronous points.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="0563a-115">Attributo enabled</span><span class="sxs-lookup"><span data-stu-id="0563a-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="0563a-116">Valore</span><span class="sxs-lookup"><span data-stu-id="0563a-116">Value</span></span>|<span data-ttu-id="0563a-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0563a-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="0563a-118">L'identità Windows non viene propagata tra punti asincroni, a meno che la rappresentazione non venga eseguita tramite metodi gestiti <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A>, ad esempio.</span><span class="sxs-lookup"><span data-stu-id="0563a-118">The Windows identity does not flow across asynchronous points, unless the impersonation is performed through managed methods such as <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A>.</span></span> <span data-ttu-id="0563a-119">Questa è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="0563a-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="0563a-120">L'identità Windows scorre sempre tra punti asincroni, indipendentemente dal modo in cui è stata eseguita la rappresentazione.</span><span class="sxs-lookup"><span data-stu-id="0563a-120">The Windows identity always flows across asynchronous points, regardless of how impersonation was performed.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0563a-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="0563a-121">Child Elements</span></span>  
 <span data-ttu-id="0563a-122">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="0563a-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0563a-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="0563a-123">Parent Elements</span></span>  
  
|<span data-ttu-id="0563a-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="0563a-124">Element</span></span>|<span data-ttu-id="0563a-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0563a-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="0563a-126">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="0563a-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="0563a-127">Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="0563a-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0563a-128">Note</span><span class="sxs-lookup"><span data-stu-id="0563a-128">Remarks</span></span>  
 <span data-ttu-id="0563a-129">Nelle versioni .NET Framework 1,0 e 1,1, l'identità Windows non viene propagata tra punti asincroni.</span><span class="sxs-lookup"><span data-stu-id="0563a-129">In the .NET Framework versions 1.0 and 1.1, the Windows identity does not flow across asynchronous points.</span></span> <span data-ttu-id="0563a-130">In .NET Framework versione 2,0 è presente un <xref:System.Threading.ExecutionContext> oggetto che contiene informazioni sul thread attualmente in esecuzione e lo trasmette attraverso punti asincroni all'interno di un dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0563a-130">In the .NET Framework version 2.0, there is an <xref:System.Threading.ExecutionContext> object that contains information about the currently executing thread, and flows it across asynchronous points within an application domain.</span></span> <span data-ttu-id="0563a-131">Il <xref:System.Security.Principal.WindowsIdentity> flusso viene inoltre eseguito come parte delle informazioni che passano tra i punti asincroni, a condizione che la rappresentazione sia stata realizzata utilizzando metodi <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A> gestiti come e non tramite altri strumenti, ad esempio Platform Invoke ai metodi nativi.</span><span class="sxs-lookup"><span data-stu-id="0563a-131">The <xref:System.Security.Principal.WindowsIdentity> also flows as part of the information that flows across the asynchronous points, provided the impersonation was achieved using managed methods such as <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A> and not through other means such as platform invoke to native methods.</span></span> <span data-ttu-id="0563a-132">Questo elemento viene utilizzato per specificare che l'identità Windows viene propagata tra punti asincroni, indipendentemente dal modo in cui è stata eseguita la rappresentazione.</span><span class="sxs-lookup"><span data-stu-id="0563a-132">This element is used to specify that the Windows identity does flow across asynchronous points, regardless of how the impersonation was achieved.</span></span>  
  
 <span data-ttu-id="0563a-133">È possibile modificare questo comportamento predefinito in altri due modi:</span><span class="sxs-lookup"><span data-stu-id="0563a-133">You can alter this default behavior in two other ways:</span></span>  
  
1. <span data-ttu-id="0563a-134">Nel codice gestito in base al thread.</span><span class="sxs-lookup"><span data-stu-id="0563a-134">In managed code on a per-thread basis.</span></span>  
  
     <span data-ttu-id="0563a-135">È possibile disattivare il flusso in base ai singoli thread <xref:System.Threading.ExecutionContext> modificando le impostazioni e <xref:System.Security.SecurityContext> usando il <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>metodo, <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType>o <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="0563a-135">You can suppress the flow on a per-thread basis by modifying the <xref:System.Threading.ExecutionContext> and <xref:System.Security.SecurityContext> settings by using the <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>, <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType>, or <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> method.</span></span>  
  
2. <span data-ttu-id="0563a-136">Nella chiamata all'interfaccia host non gestita per caricare il Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="0563a-136">In the call to the unmanaged hosting interface to load the common language runtime (CLR).</span></span>  
  
     <span data-ttu-id="0563a-137">Se per il caricamento di CLR viene utilizzata un'interfaccia di hosting non gestita, anziché un semplice eseguibile gestito, è possibile specificare un flag speciale nella chiamata alla funzione [funzione CorBindToRuntimeEx](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) .</span><span class="sxs-lookup"><span data-stu-id="0563a-137">If an unmanaged hosting interface (instead of a simple managed executable) is used to load the CLR, you can specify a special flag in the call to the [CorBindToRuntimeEx Function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) function.</span></span> <span data-ttu-id="0563a-138">Per abilitare la modalità di compatibilità per l'intero processo, impostare `flags` il parametro per la [funzione CorBindToRuntimeEx](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) su `STARTUP_ALWAYSFLOW_IMPERSONATION`.</span><span class="sxs-lookup"><span data-stu-id="0563a-138">To enable the compatibility mode for the entire process, set the `flags` parameter for [CorBindToRuntimeEx Function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) to `STARTUP_ALWAYSFLOW_IMPERSONATION`.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="0563a-139">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="0563a-139">Configuration File</span></span>  
 <span data-ttu-id="0563a-140">In un'applicazione .NET Framework, questo elemento può essere utilizzato solo nel file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0563a-140">In a .NET Framework application, this element can be used only in the application configuration file.</span></span>  
  
 <span data-ttu-id="0563a-141">Per un'applicazione ASP.NET, il flusso di rappresentazione può essere configurato nel file Aspnet. config presente nella \<cartella Windows > directory \Microsoft.NET\Framework\vx.x.xxxx.</span><span class="sxs-lookup"><span data-stu-id="0563a-141">For an ASP.NET application, the impersonation flow can be configured in the aspnet.config file found in the \<Windows Folder>\Microsoft.NET\Framework\vx.x.xxxx directory.</span></span>  
  
 <span data-ttu-id="0563a-142">Per impostazione predefinita, ASP.NET Disabilita il flusso di rappresentazione nel file Aspnet. config usando le impostazioni di configurazione seguenti:</span><span class="sxs-lookup"><span data-stu-id="0563a-142">ASP.NET by default disables the impersonation flow in the aspnet.config file by using the following configuration settings:</span></span>  
  
```xml
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
      <alwaysFlowImpersonationPolicy enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="0563a-143">In ASP.NET, se invece si desidera consentire il flusso di rappresentazione, è necessario utilizzare in modo esplicito le impostazioni di configurazione seguenti:</span><span class="sxs-lookup"><span data-stu-id="0563a-143">In ASP.NET, if you want to allow the flow of impersonation instead, you must explicitly use the following configuration settings:</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="false"/>  
      <alwaysFlowImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="example"></a><span data-ttu-id="0563a-144">Esempio</span><span class="sxs-lookup"><span data-stu-id="0563a-144">Example</span></span>  
 <span data-ttu-id="0563a-145">Nell'esempio seguente viene illustrato come specificare che l'identità di Windows scorre tra punti asincroni, anche quando la rappresentazione viene eseguita tramite mezzi diversi dai metodi gestiti.</span><span class="sxs-lookup"><span data-stu-id="0563a-145">The following example shows how to specify that the Windows identity flows across asynchronous points, even when the impersonation is achieved through means other than managed methods.</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <alwaysFlowImpersonationPolicy enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="0563a-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0563a-146">See also</span></span>

- [<span data-ttu-id="0563a-147">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="0563a-147">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="0563a-148">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="0563a-148">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="0563a-149">\<Elemento > legacyImpersonationPolicy</span><span class="sxs-lookup"><span data-stu-id="0563a-149">\<legacyImpersonationPolicy> Element</span></span>](legacyimpersonationpolicy-element.md)
