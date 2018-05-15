---
title: '&lt;loadFromRemoteSources&gt; elemento'
ms.date: 03/30/2017
helpviewer_keywords:
- loadFromRemoteSources element
- <loadFromRemoteSources> element
ms.assetid: 006d1280-2ac3-4db6-a984-a3d4e275046a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f0d442f71a0e2fc7deacd9aaa02cfba7b66f2349
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="ltloadfromremotesourcesgt-element"></a><span data-ttu-id="d07e4-102">&lt;loadFromRemoteSources&gt; elemento</span><span class="sxs-lookup"><span data-stu-id="d07e4-102">&lt;loadFromRemoteSources&gt; Element</span></span>
<span data-ttu-id="d07e4-103">Specifica se gli assembly da origini remote devono essere concesso l'attendibilità totale.</span><span class="sxs-lookup"><span data-stu-id="d07e4-103">Specifies whether assemblies from remote sources should be granted full trust.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d07e4-104">Se si viene indirizzati a questo argomento, a causa di un messaggio di errore nell'elenco di errori di progetto Visual Studio o un errore di compilazione, vedere [procedura: utilizzare un Assembly dal Web in Visual Studio](http://msdn.microsoft.com/library/d8635b63-89a0-41aa-90f4-f351b2111070).</span><span class="sxs-lookup"><span data-stu-id="d07e4-104">If you were directed to this topic because of an error message in the Visual Studio project error list or a build error, see [How to: Use an Assembly from the Web in Visual Studio](http://msdn.microsoft.com/library/d8635b63-89a0-41aa-90f4-f351b2111070).</span></span>  
  
 <span data-ttu-id="d07e4-105">\<configuration></span><span class="sxs-lookup"><span data-stu-id="d07e4-105">\<configuration></span></span>  
<span data-ttu-id="d07e4-106">\<runtime></span><span class="sxs-lookup"><span data-stu-id="d07e4-106">\<runtime></span></span>  
<span data-ttu-id="d07e4-107">\<loadFromRemoteSources></span><span class="sxs-lookup"><span data-stu-id="d07e4-107">\<loadFromRemoteSources></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d07e4-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d07e4-108">Syntax</span></span>  
  
```xml  
<loadFromRemoteSources    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d07e4-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="d07e4-109">Attributes and Elements</span></span>  
 <span data-ttu-id="d07e4-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="d07e4-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d07e4-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="d07e4-111">Attributes</span></span>  
  
|<span data-ttu-id="d07e4-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="d07e4-112">Attribute</span></span>|<span data-ttu-id="d07e4-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d07e4-113">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="d07e4-114">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="d07e4-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="d07e4-115">Specifica se un assembly caricato da origini remote deve essere concessa l'attendibilità totale.</span><span class="sxs-lookup"><span data-stu-id="d07e4-115">Specifies whether an assembly that is loaded from remote sources should be granted full trust.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="d07e4-116">Attributo enabled</span><span class="sxs-lookup"><span data-stu-id="d07e4-116">enabled Attribute</span></span>  
  
|<span data-ttu-id="d07e4-117">Valore</span><span class="sxs-lookup"><span data-stu-id="d07e4-117">Value</span></span>|<span data-ttu-id="d07e4-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d07e4-118">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="d07e4-119">Non concedere l'attendibilità totale alle applicazioni provenienti da origini remote.</span><span class="sxs-lookup"><span data-stu-id="d07e4-119">Do not grant full trust to applications from remote sources.</span></span> <span data-ttu-id="d07e4-120">Questa è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="d07e4-120">This is the default.</span></span>|  
|`true`|<span data-ttu-id="d07e4-121">Concedere l'attendibilità totale alle applicazioni provenienti da origini remote.</span><span class="sxs-lookup"><span data-stu-id="d07e4-121">Grant full trust to applications from remote sources.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d07e4-122">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="d07e4-122">Child Elements</span></span>  
 <span data-ttu-id="d07e4-123">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="d07e4-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d07e4-124">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="d07e4-124">Parent Elements</span></span>  
  
|<span data-ttu-id="d07e4-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="d07e4-125">Element</span></span>|<span data-ttu-id="d07e4-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d07e4-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="d07e4-127">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d07e4-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="d07e4-128">Contiene informazioni sulle opzioni di inizializzazione in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="d07e4-128">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d07e4-129">Note</span><span class="sxs-lookup"><span data-stu-id="d07e4-129">Remarks</span></span>  
 <span data-ttu-id="d07e4-130">In .NET Framework versione 3.5 e versioni precedenti, se un assembly caricato da una posizione remota, l'assembly parzialmente attendibile con un set di concessioni che dipende dalla zona in cui è stato caricato.</span><span class="sxs-lookup"><span data-stu-id="d07e4-130">In the .NET Framework version 3.5 and earlier versions, if you loaded an assembly from a remote location, the assembly would run partially trusted with a grant set that depended on the zone in which it was loaded.</span></span> <span data-ttu-id="d07e4-131">Ad esempio, se un assembly caricato da un sito Web, è stato caricato nella zona Internet e concesso il set di autorizzazioni Internet.</span><span class="sxs-lookup"><span data-stu-id="d07e4-131">For example, if you loaded an assembly from a website, it was loaded into the Internet zone and granted the Internet permission set.</span></span> <span data-ttu-id="d07e4-132">In altre parole, eseguita in un ambiente sandbox Internet.</span><span class="sxs-lookup"><span data-stu-id="d07e4-132">In other words, it executed in an Internet sandbox.</span></span> <span data-ttu-id="d07e4-133">Se si tenta di eseguire tale assembly nel [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] e versioni successive, viene generata un'eccezione; è necessario creare esplicitamente una sandbox per l'assembly (vedere [procedura: eseguire codice parzialmente attendibile in un ambiente Sandbox](../../../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md)), oppure eseguirlo con attendibilità totale.</span><span class="sxs-lookup"><span data-stu-id="d07e4-133">If you try to run that assembly in the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] and later versions, an exception is thrown; you must either explicitly create a sandbox for the assembly (see [How to: Run Partially Trusted Code in a Sandbox](../../../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md)), or run it in full trust.</span></span>  
  
 <span data-ttu-id="d07e4-134">Il `<loadFromRemoteSources>` elemento consente specificare che devono essere eseguiti gli assembly che si sarebbero verificati parzialmente attendibile in versioni precedenti di .NET Framework con attendibilità totale nel [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="d07e4-134">The `<loadFromRemoteSources>` element lets you specify that the assemblies that would have run partially trusted in earlier versions of the .NET Framework are to be run fully trusted in the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] and later versions.</span></span> <span data-ttu-id="d07e4-135">Per impostazione predefinita, assembly remoti a non eseguire il [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="d07e4-135">By default, remote assemblies do not run in the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] and later.</span></span> <span data-ttu-id="d07e4-136">Per eseguire un assembly remoto, è necessario eseguirla come completamente attendibile o creare una sandbox <xref:System.AppDomain> in cui si desidera eseguirlo.</span><span class="sxs-lookup"><span data-stu-id="d07e4-136">To run a remote assembly, you must either run it as fully trusted or create a sandboxed <xref:System.AppDomain> in which to run it.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d07e4-137">Nel [!INCLUDE[net_v45](../../../../../includes/net-v45-md.md)], gli assembly nelle condivisioni di rete locale vengono eseguiti con attendibilità totale per impostazione predefinita; non è necessario abilitare il `<loadFromRemoteSources>` elemento.</span><span class="sxs-lookup"><span data-stu-id="d07e4-137">In the [!INCLUDE[net_v45](../../../../../includes/net-v45-md.md)], assemblies on local network shares are run as full trust by default; you do not have to enable the `<loadFromRemoteSources>` element.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d07e4-138">Se un'applicazione è stata copiata dal web, questa viene contrassegnata da Windows come un'applicazione web, anche se si trova nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="d07e4-138">If an application has been copied from the web, it is flagged by Windows as being a web application, even if it resides on the local computer.</span></span> <span data-ttu-id="d07e4-139">È possibile modificare tale designazione modificando le proprietà del file, oppure è possibile utilizzare il `<loadFromRemoteSources>` elemento da concedere all'assembly con attendibilità totale.</span><span class="sxs-lookup"><span data-stu-id="d07e4-139">You can change that designation by changing the file properties, or you can use the `<loadFromRemoteSources>` element to grant the assembly full trust.</span></span> <span data-ttu-id="d07e4-140">In alternativa, è possibile utilizzare il <xref:System.Reflection.Assembly.UnsafeLoadFrom%2A> per caricare un assembly locale che il sistema operativo è contrassegnato come se fosse stato caricato dal web.</span><span class="sxs-lookup"><span data-stu-id="d07e4-140">As an alternative, you can use the <xref:System.Reflection.Assembly.UnsafeLoadFrom%2A> method to load a local assembly that the operating system has flagged as having been loaded from the web.</span></span>  
  
 <span data-ttu-id="d07e4-141">Il `enabled` attributo per questo elemento è efficace solo quando sicurezza dall'accesso di codice (CAS) è disabilitato.</span><span class="sxs-lookup"><span data-stu-id="d07e4-141">The `enabled` attribute for this element is effective only when code access security (CAS) is disabled.</span></span> <span data-ttu-id="d07e4-142">Per impostazione predefinita, le autorità di certificazione è disattivato nel [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="d07e4-142">By default, CAS policy is disabled in the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] and later versions.</span></span> <span data-ttu-id="d07e4-143">Se si imposta `enabled` a `true`, le applicazioni remote vengono concessa l'attendibilità.</span><span class="sxs-lookup"><span data-stu-id="d07e4-143">If you set `enabled` to `true`, remote applications are granted full trust.</span></span>  
  
 <span data-ttu-id="d07e4-144">Se `<loadFromRemoteSources>``enabled` non è impostata su `true`, viene generata un'eccezione nelle condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="d07e4-144">If `<loadFromRemoteSources>``enabled` is not set to `true`, an exception is thrown under the following conditions:</span></span>  
  
-   <span data-ttu-id="d07e4-145">Il comportamento di sandboxing del dominio corrente è diverso dal comportamento nel [!INCLUDE[net_v35_short](../../../../../includes/net-v35-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d07e4-145">The sandboxing behavior of the current domain is different from its behavior in the [!INCLUDE[net_v35_short](../../../../../includes/net-v35-short-md.md)].</span></span> <span data-ttu-id="d07e4-146">Sono necessari criteri Autorità di certificazione deve essere disabilitata e il dominio corrente non deve essere creata mediante sandbox.</span><span class="sxs-lookup"><span data-stu-id="d07e4-146">This requires CAS policy to be disabled, and the current domain not to be sandboxed.</span></span>  
  
-   <span data-ttu-id="d07e4-147">Il caricamento dell'assembly non è il `MyComputer` zona.</span><span class="sxs-lookup"><span data-stu-id="d07e4-147">The assembly being loaded is not from the `MyComputer` zone.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d07e4-148">È possibile ottenere un <xref:System.IO.FileLoadException> in un'applicazione Windows Virtual PC quando si tenta di caricare un file dalle cartelle collegate sul computer host.</span><span class="sxs-lookup"><span data-stu-id="d07e4-148">You may get a <xref:System.IO.FileLoadException> in a Windows Virtual PC application when you try to load a file from linked folders on the hosting computer.</span></span> <span data-ttu-id="d07e4-149">Questo errore può verificarsi anche quando si tenta di caricare un file da una cartella collegata tramite [Servizi Desktop remoto](http://go.microsoft.com/fwlink/?LinkId=182775) (servizi Terminal).</span><span class="sxs-lookup"><span data-stu-id="d07e4-149">This error may also occur when you try to load a file from a folder linked over [Remote Desktop Services](http://go.microsoft.com/fwlink/?LinkId=182775) (Terminal Services).</span></span> <span data-ttu-id="d07e4-150">Per evitare l'eccezione, impostare `enabled` a `true`.</span><span class="sxs-lookup"><span data-stu-id="d07e4-150">To avoid the exception, set `enabled` to `true`.</span></span>  
  
 <span data-ttu-id="d07e4-151">L'impostazione di `<loadFromRemoteSources>` elemento `true` impedisce che venga generata questa eccezione.</span><span class="sxs-lookup"><span data-stu-id="d07e4-151">Setting the `<loadFromRemoteSources>` element to `true` prevents this exception from being thrown.</span></span> <span data-ttu-id="d07e4-152">Consente di specificare che non si in common language runtime per la sandbox gli assembly caricati per la sicurezza e che può concedere l'esecuzione con attendibilità totale.</span><span class="sxs-lookup"><span data-stu-id="d07e4-152">It enables you to specify that you are not relying on the common language runtime to sandbox the loaded assemblies for security, and that they can be allowed to execute as full trust.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d07e4-153">Se l'assembly non deve essere eseguito con attendibilità totale, non impostare questo elemento di configurazione.</span><span class="sxs-lookup"><span data-stu-id="d07e4-153">If the assembly should not run in full trust, do not set this configuration element.</span></span> <span data-ttu-id="d07e4-154">In alternativa, creare una sandbox <xref:System.AppDomain> in cui caricare l'assembly.</span><span class="sxs-lookup"><span data-stu-id="d07e4-154">Instead, create a sandboxed <xref:System.AppDomain> in which to load the assembly.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="d07e4-155">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="d07e4-155">Configuration File</span></span>  
 <span data-ttu-id="d07e4-156">Questo elemento viene in genere utilizzato nel file di configurazione dell'applicazione, ma può essere utilizzato in altri file di configurazione in base al contesto.</span><span class="sxs-lookup"><span data-stu-id="d07e4-156">This element is typically used in the application configuration file, but can be used in other configuration files depending upon the context.</span></span> <span data-ttu-id="d07e4-157">Per ulteriori informazioni, vedere l'articolo [più implicita Usa di questi criteri: loadFromRemoteSources](http://go.microsoft.com/fwlink/p/?LinkId=266839) nel blog di sicurezza di .NET.</span><span class="sxs-lookup"><span data-stu-id="d07e4-157">For more information, see the article [More Implicit Uses of CAS Policy: loadFromRemoteSources](http://go.microsoft.com/fwlink/p/?LinkId=266839) in the .NET Security blog.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d07e4-158">Esempio</span><span class="sxs-lookup"><span data-stu-id="d07e4-158">Example</span></span>  
 <span data-ttu-id="d07e4-159">Nell'esempio seguente viene illustrato come concedere l'attendibilità totale alle applicazioni provenienti da origini remote.</span><span class="sxs-lookup"><span data-stu-id="d07e4-159">The following example shows how to grant full trust to applications from remote sources.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <loadFromRemoteSources enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d07e4-160">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d07e4-160">See Also</span></span>  
 [<span data-ttu-id="d07e4-161">Più impliciti utilizzi di questi criteri: loadFromRemoteSources</span><span class="sxs-lookup"><span data-stu-id="d07e4-161">More Implicit Uses of CAS Policy: loadFromRemoteSources</span></span>](http://go.microsoft.com/fwlink/p/?LinkId=266839)  
 [<span data-ttu-id="d07e4-162">Procedura: eseguire codice parzialmente attendibile in un oggetto sandbox</span><span class="sxs-lookup"><span data-stu-id="d07e4-162">How to: Run Partially Trusted Code in a Sandbox</span></span>](../../../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md)  
 [<span data-ttu-id="d07e4-163">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="d07e4-163">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="d07e4-164">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="d07e4-164">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
