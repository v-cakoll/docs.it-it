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
ms.openlocfilehash: 18a027bc09f2400a10a06efdc4c5355686bcb56d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73116537"
---
# <a name="legacyimpersonationpolicy-element"></a><span data-ttu-id="0ef91-102">\<elemento > legacyImpersonationPolicy</span><span class="sxs-lookup"><span data-stu-id="0ef91-102">\<legacyImpersonationPolicy> Element</span></span>
<span data-ttu-id="0ef91-103">Specifica che l'identità di Windows non passa attraverso punti asincroni, indipendentemente dalle impostazioni di flusso per il contesto di esecuzione nel thread corrente.</span><span class="sxs-lookup"><span data-stu-id="0ef91-103">Specifies that the Windows identity does not flow across asynchronous points, regardless of the flow settings for the execution context on the current thread.</span></span>  
  
<span data-ttu-id="0ef91-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="0ef91-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="0ef91-105">&nbsp; &nbsp;[ **\<runtime >** ](runtime-element.md) </span><span class="sxs-lookup"><span data-stu-id="0ef91-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="0ef91-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<legacyImpersonationPolicy >**</span><span class="sxs-lookup"><span data-stu-id="0ef91-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<legacyImpersonationPolicy>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ef91-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0ef91-107">Syntax</span></span>  
  
```xml  
<legacyImpersonationPolicy    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0ef91-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="0ef91-108">Attributes and Elements</span></span>  
 <span data-ttu-id="0ef91-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="0ef91-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0ef91-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="0ef91-110">Attributes</span></span>  
  
|<span data-ttu-id="0ef91-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="0ef91-111">Attribute</span></span>|<span data-ttu-id="0ef91-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0ef91-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="0ef91-113">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="0ef91-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="0ef91-114">Specifica che il <xref:System.Security.Principal.WindowsIdentity> non viene propagata tra punti asincroni, indipendentemente dalle impostazioni del flusso <xref:System.Threading.ExecutionContext> sul thread corrente.</span><span class="sxs-lookup"><span data-stu-id="0ef91-114">Specifies that the <xref:System.Security.Principal.WindowsIdentity> does not flow across asynchronous points, regardless of the <xref:System.Threading.ExecutionContext> flow settings on the current thread.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="0ef91-115">Attributo enabled</span><span class="sxs-lookup"><span data-stu-id="0ef91-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="0ef91-116">Value</span><span class="sxs-lookup"><span data-stu-id="0ef91-116">Value</span></span>|<span data-ttu-id="0ef91-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0ef91-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="0ef91-118"><xref:System.Security.Principal.WindowsIdentity> scorre tra punti asincroni a seconda delle impostazioni del flusso di <xref:System.Threading.ExecutionContext> per il thread corrente.</span><span class="sxs-lookup"><span data-stu-id="0ef91-118"><xref:System.Security.Principal.WindowsIdentity> flows across asynchronous points depending upon the <xref:System.Threading.ExecutionContext> flow settings for the current thread.</span></span> <span data-ttu-id="0ef91-119">Questa è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="0ef91-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="0ef91-120"><xref:System.Security.Principal.WindowsIdentity> non viene propagata tra punti asincroni, indipendentemente dalle impostazioni del flusso <xref:System.Threading.ExecutionContext> sul thread corrente.</span><span class="sxs-lookup"><span data-stu-id="0ef91-120"><xref:System.Security.Principal.WindowsIdentity> does not flow across asynchronous points, regardless of the <xref:System.Threading.ExecutionContext> flow settings on the current thread.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0ef91-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="0ef91-121">Child Elements</span></span>  
 <span data-ttu-id="0ef91-122">Nessuna.</span><span class="sxs-lookup"><span data-stu-id="0ef91-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0ef91-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="0ef91-123">Parent Elements</span></span>  
  
|<span data-ttu-id="0ef91-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="0ef91-124">Element</span></span>|<span data-ttu-id="0ef91-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0ef91-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="0ef91-126">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="0ef91-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="0ef91-127">Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="0ef91-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0ef91-128">Note</span><span class="sxs-lookup"><span data-stu-id="0ef91-128">Remarks</span></span>  
 <span data-ttu-id="0ef91-129">Nelle versioni .NET Framework 1,0 e 1,1, il <xref:System.Security.Principal.WindowsIdentity> non viene propagata tra i punti asincroni definiti dall'utente.</span><span class="sxs-lookup"><span data-stu-id="0ef91-129">In the .NET Framework versions 1.0 and 1.1, the <xref:System.Security.Principal.WindowsIdentity> does not flow across any user-defined asynchronous points.</span></span> <span data-ttu-id="0ef91-130">A partire da .NET Framework versione 2,0, è presente un oggetto <xref:System.Threading.ExecutionContext> che contiene informazioni sul thread attualmente in esecuzione e viene trasmesso tra punti asincroni all'interno di un dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0ef91-130">Starting with the .NET Framework version 2.0, there is an <xref:System.Threading.ExecutionContext> object that contains information about the currently executing thread, and it flows across asynchronous points within an application domain.</span></span> <span data-ttu-id="0ef91-131">Il <xref:System.Security.Principal.WindowsIdentity> è incluso in questo contesto di esecuzione e, di conseguenza, fluisce anche tra i punti asincroni, il che significa che se esiste un contesto di rappresentazione, viene trasmesso anche il flusso.</span><span class="sxs-lookup"><span data-stu-id="0ef91-131">The <xref:System.Security.Principal.WindowsIdentity> is included in this execution context and therefore also flows across the asynchronous points, which means that if an impersonation context exists, it will flow as well.</span></span>  
  
 <span data-ttu-id="0ef91-132">A partire da .NET Framework 2,0, è possibile usare l'elemento `<legacyImpersonationPolicy>` per specificare che <xref:System.Security.Principal.WindowsIdentity> non scorre tra punti asincroni.</span><span class="sxs-lookup"><span data-stu-id="0ef91-132">Starting with the .NET Framework 2.0, you can use the `<legacyImpersonationPolicy>` element to specify that  <xref:System.Security.Principal.WindowsIdentity> does not flow across asynchronous points.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0ef91-133">Il Common Language Runtime (CLR) rileva le operazioni di rappresentazione eseguite utilizzando solo codice gestito, non la rappresentazione eseguita all'esterno del codice gestito, ad esempio tramite platform invoke al codice non gestito o tramite chiamate dirette alle funzioni Win32.</span><span class="sxs-lookup"><span data-stu-id="0ef91-133">The common language runtime (CLR) is aware of impersonation operations performed using only managed code, not of impersonation performed outside of managed code, such as through platform invoke to unmanaged code or through direct calls to Win32 functions.</span></span> <span data-ttu-id="0ef91-134">Solo gli oggetti <xref:System.Security.Principal.WindowsIdentity> gestiti possono fluire tra punti asincroni, a meno che l'elemento `alwaysFlowImpersonationPolicy` non sia stato impostato su true (`<alwaysFlowImpersonationPolicy enabled="true"/>`).</span><span class="sxs-lookup"><span data-stu-id="0ef91-134">Only managed <xref:System.Security.Principal.WindowsIdentity> objects can flow across asynchronous points, unless the `alwaysFlowImpersonationPolicy` element has been set to true (`<alwaysFlowImpersonationPolicy enabled="true"/>`).</span></span> <span data-ttu-id="0ef91-135">Se si imposta l'elemento `alwaysFlowImpersonationPolicy` su true, viene specificato che l'identità di Windows scorre sempre tra punti asincroni, indipendentemente dal modo in cui è stata eseguita la rappresentazione.</span><span class="sxs-lookup"><span data-stu-id="0ef91-135">Setting the `alwaysFlowImpersonationPolicy` element to true specifies that the Windows identity always flows across asynchronous points, regardless of how impersonation was performed.</span></span> <span data-ttu-id="0ef91-136">Per ulteriori informazioni sulla propagazione della rappresentazione non gestita tra punti asincroni, vedere [\<elemento alwaysFlowImpersonationPolicy >](alwaysflowimpersonationpolicy-element.md).</span><span class="sxs-lookup"><span data-stu-id="0ef91-136">For more information on flowing unmanaged impersonation across asynchronous points, see [\<alwaysFlowImpersonationPolicy> Element](alwaysflowimpersonationpolicy-element.md).</span></span>  
  
 <span data-ttu-id="0ef91-137">È possibile modificare questo comportamento predefinito in altri due modi:</span><span class="sxs-lookup"><span data-stu-id="0ef91-137">You can alter this default behavior in two other ways:</span></span>  
  
1. <span data-ttu-id="0ef91-138">Nel codice gestito in base al thread.</span><span class="sxs-lookup"><span data-stu-id="0ef91-138">In managed code on a per-thread basis.</span></span>  
  
     <span data-ttu-id="0ef91-139">È possibile disattivare il flusso in base ai singoli thread modificando le impostazioni <xref:System.Threading.ExecutionContext> e <xref:System.Security.SecurityContext> usando il metodo <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>, <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType> o <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="0ef91-139">You can suppress the flow on a per-thread basis by modifying the <xref:System.Threading.ExecutionContext> and <xref:System.Security.SecurityContext> settings by using the <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>, <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType> or <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> method.</span></span>  
  
2. <span data-ttu-id="0ef91-140">Nella chiamata all'interfaccia host non gestita per caricare il Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="0ef91-140">In the call to the unmanaged hosting interface to load the common language runtime (CLR).</span></span>  
  
     <span data-ttu-id="0ef91-141">Se per il caricamento di CLR viene utilizzata un'interfaccia di hosting non gestita, anziché un semplice eseguibile gestito, è possibile specificare un flag speciale nella chiamata alla funzione [funzione CorBindToRuntimeEx](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) .</span><span class="sxs-lookup"><span data-stu-id="0ef91-141">If an unmanaged hosting interface (instead of a simple managed executable) is used to load the CLR, you can specify a special flag in the call to the [CorBindToRuntimeEx Function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) function.</span></span> <span data-ttu-id="0ef91-142">Per abilitare la modalità di compatibilità per l'intero processo, impostare il parametro `flags` per la [funzione CorBindToRuntimeEx](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) su STARTUP_LEGACY_IMPERSONATION.</span><span class="sxs-lookup"><span data-stu-id="0ef91-142">To enable the compatibility mode for the entire process, set the `flags` parameter for [CorBindToRuntimeEx Function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) to STARTUP_LEGACY_IMPERSONATION.</span></span>  
  
 <span data-ttu-id="0ef91-143">Per ulteriori informazioni, vedere l' [elemento\<alwaysFlowImpersonationPolicy >](alwaysflowimpersonationpolicy-element.md).</span><span class="sxs-lookup"><span data-stu-id="0ef91-143">For more information, see the [\<alwaysFlowImpersonationPolicy> Element](alwaysflowimpersonationpolicy-element.md).</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="0ef91-144">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="0ef91-144">Configuration File</span></span>  
 <span data-ttu-id="0ef91-145">In un'applicazione .NET Framework, questo elemento può essere utilizzato solo nel file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0ef91-145">In a .NET Framework application, this element can be used only in the application configuration file.</span></span>  
  
 <span data-ttu-id="0ef91-146">Per un'applicazione ASP.NET, il flusso di rappresentazione può essere configurato nel file Aspnet. config presente nella cartella \<Windows > directory \Microsoft.NET\Framework\vx.x.xxxx.</span><span class="sxs-lookup"><span data-stu-id="0ef91-146">For an ASP.NET application, the impersonation flow can be configured in the aspnet.config file found in the \<Windows Folder>\Microsoft.NET\Framework\vx.x.xxxx directory.</span></span>  
  
 <span data-ttu-id="0ef91-147">Per impostazione predefinita, ASP.NET Disabilita il flusso di rappresentazione nel file Aspnet. config usando le impostazioni di configurazione seguenti:</span><span class="sxs-lookup"><span data-stu-id="0ef91-147">ASP.NET by default disables the impersonation flow in the aspnet.config file by using the following configuration settings:</span></span>  
  
``` xml
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
      <alwaysFlowImpersonationPolicy enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="0ef91-148">In ASP.NET, se invece si desidera consentire il flusso di rappresentazione, è necessario utilizzare in modo esplicito le impostazioni di configurazione seguenti:</span><span class="sxs-lookup"><span data-stu-id="0ef91-148">In ASP.NET, if you want to allow the flow of impersonation instead, you must explicitly use the following configuration settings:</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="false"/>  
      <alwaysFlowImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="example"></a><span data-ttu-id="0ef91-149">Esempio</span><span class="sxs-lookup"><span data-stu-id="0ef91-149">Example</span></span>  
 <span data-ttu-id="0ef91-150">Nell'esempio seguente viene illustrato come specificare il comportamento legacy che non fluisce sull'identità di Windows tra punti asincroni.</span><span class="sxs-lookup"><span data-stu-id="0ef91-150">The following example shows how to specify the legacy behavior that does not flow the Windows identity across asynchronous points.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="0ef91-151">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0ef91-151">See also</span></span>

- [<span data-ttu-id="0ef91-152">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="0ef91-152">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="0ef91-153">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="0ef91-153">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="0ef91-154">\<elemento > alwaysFlowImpersonationPolicy</span><span class="sxs-lookup"><span data-stu-id="0ef91-154">\<alwaysFlowImpersonationPolicy> Element</span></span>](alwaysflowimpersonationpolicy-element.md)
