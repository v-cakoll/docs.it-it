---
title: <loadFromRemoteSources> Elemento
ms.date: 05/24/2018
helpviewer_keywords:
- loadFromRemoteSources element
- <loadFromRemoteSources> element
ms.assetid: 006d1280-2ac3-4db6-a984-a3d4e275046a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ebb32a74f5413f9c927a84ababf2d60d20e0b024
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55269692"
---
# <a name="loadfromremotesources-element"></a><span data-ttu-id="30b77-102">\<loadFromRemoteSources > elemento</span><span class="sxs-lookup"><span data-stu-id="30b77-102">\<loadFromRemoteSources> element</span></span>
<span data-ttu-id="30b77-103">Specifica se gli assembly caricati da origini remote devono essere concessa l'attendibilità in .NET Framework 4 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="30b77-103">Specifies whether assemblies loaded from remote sources should be granted full trust in .NET Framework 4 and later.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="30b77-104">Se a causa di un messaggio di errore nell'elenco di errori di progetto Visual Studio o un errore di compilazione, si viene reindirizzati a questo argomento, vedere [come: Usare un Assembly dal Web in Visual Studio](https://msdn.microsoft.com/library/d8635b63-89a0-41aa-90f4-f351b2111070).</span><span class="sxs-lookup"><span data-stu-id="30b77-104">If you were directed to this topic because of an error message in the Visual Studio project error list or a build error, see [How to: Use an Assembly from the Web in Visual Studio](https://msdn.microsoft.com/library/d8635b63-89a0-41aa-90f4-f351b2111070).</span></span>  
  
 <span data-ttu-id="30b77-105">\<configuration></span><span class="sxs-lookup"><span data-stu-id="30b77-105">\<configuration></span></span>  
<span data-ttu-id="30b77-106">\<runtime></span><span class="sxs-lookup"><span data-stu-id="30b77-106">\<runtime></span></span>  
<span data-ttu-id="30b77-107">\<loadFromRemoteSources></span><span class="sxs-lookup"><span data-stu-id="30b77-107">\<loadFromRemoteSources></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30b77-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="30b77-108">Syntax</span></span>  
  
```xml  
<loadFromRemoteSources    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="30b77-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="30b77-109">Attributes and elements</span></span>
 <span data-ttu-id="30b77-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="30b77-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="30b77-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="30b77-111">Attributes</span></span>  
  
|<span data-ttu-id="30b77-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="30b77-112">Attribute</span></span>|<span data-ttu-id="30b77-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="30b77-113">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="30b77-114">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="30b77-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="30b77-115">Specifica se un assembly caricato da un'origine remota deve essere concessa attendibilità totale.</span><span class="sxs-lookup"><span data-stu-id="30b77-115">Specifies whether an assembly that is loaded from a remote source should be granted full trust.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="30b77-116">attributo Enabled</span><span class="sxs-lookup"><span data-stu-id="30b77-116">enabled attribute</span></span>  
  
|<span data-ttu-id="30b77-117">Valore</span><span class="sxs-lookup"><span data-stu-id="30b77-117">Value</span></span>|<span data-ttu-id="30b77-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="30b77-118">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="30b77-119">Non concedere l'attendibilità totale alle applicazioni da origini remote.</span><span class="sxs-lookup"><span data-stu-id="30b77-119">Do not grant full trust to applications from remote sources.</span></span> <span data-ttu-id="30b77-120">Questa è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="30b77-120">This is the default.</span></span>|  
|`true`|<span data-ttu-id="30b77-121">Concedere l'attendibilità totale alle applicazioni da origini remote.</span><span class="sxs-lookup"><span data-stu-id="30b77-121">Grant full trust to applications from remote sources.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="30b77-122">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="30b77-122">Child elements</span></span>  
 <span data-ttu-id="30b77-123">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="30b77-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="30b77-124">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="30b77-124">Parent elements</span></span>  
  
|<span data-ttu-id="30b77-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="30b77-125">Element</span></span>|<span data-ttu-id="30b77-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="30b77-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="30b77-127">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="30b77-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="30b77-128">Contiene informazioni sulle opzioni di inizializzazione in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="30b77-128">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="30b77-129">Note</span><span class="sxs-lookup"><span data-stu-id="30b77-129">Remarks</span></span>

<span data-ttu-id="30b77-130">In .NET Framework 3.5 e versioni precedenti, se si carica un assembly da una posizione remota, il codice nell'assembly viene eseguito in attendibilità parziale con un set di concessioni che varia a seconda della zona da cui viene caricato.</span><span class="sxs-lookup"><span data-stu-id="30b77-130">In the .NET Framework 3.5 and earlier versions, if you load an assembly from a remote location, code in the assembly runs in partial trust with a grant set that depends on the zone from which it is loaded.</span></span> <span data-ttu-id="30b77-131">Ad esempio, se si carica un assembly da un sito Web, viene caricato nella zona Internet e concesso il set di autorizzazioni Internet.</span><span class="sxs-lookup"><span data-stu-id="30b77-131">For example, if you load an assembly from a website, it is loaded into the Internet zone and granted the Internet permission set.</span></span> <span data-ttu-id="30b77-132">In altre parole, viene eseguito in una sandbox di Internet.</span><span class="sxs-lookup"><span data-stu-id="30b77-132">In other words, it executes in an Internet sandbox.</span></span>

<span data-ttu-id="30b77-133">A partire da .NET Framework 4, criteri di sicurezza dall'accesso di codice sono disabilitato e gli assembly vengono caricati con attendibilità totale.</span><span class="sxs-lookup"><span data-stu-id="30b77-133">Starting with the .NET Framework 4, code access security (CAS) policy is disabled and assemblies are loaded in full trust.</span></span> <span data-ttu-id="30b77-134">In genere, ciò potrebbe concedere l'attendibilità per gli assembly caricati con il <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> metodo che in precedenza era stato creato mediante sandbox.</span><span class="sxs-lookup"><span data-stu-id="30b77-134">Ordinarily, this would grant full trust to assemblies loaded with the <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> method that previously had been sandboxed.</span></span> <span data-ttu-id="30b77-135">Per evitare questo problema, la possibilità di eseguire il codice negli assembly caricati da un'origine remota è disabilitata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="30b77-135">To prevent this, the ability to run code in assemblies loaded from a remote source is disabled by default.</span></span> <span data-ttu-id="30b77-136">Per impostazione predefinita, se si tenta di caricare un assembly remoto, un <xref:System.IO.FileLoadException> con un messaggio di eccezione, ad esempio, viene generata la seguente:</span><span class="sxs-lookup"><span data-stu-id="30b77-136">By default, if you attempt to load a remote assembly, a <xref:System.IO.FileLoadException> with an exception message like the following is thrown:</span></span>

```text
System.IO.FileNotFoundException: Could not load file or assembly 'file:assem.dll' or one of its dependencies. Operation is not supported. 
(Exception from HRESULT: 0x80131515)
File name: 'file:assem.dll' ---> 
System.NotSupportedException: An attempt was made to load an assembly from a network location which would have caused the assembly 
to be sandboxed in previous versions of the .NET Framework. This release of the .NET Framework does not enable CAS policy by default, 
so this load may be dangerous. If this load is not intended to sandbox the assembly, please enable the loadFromRemoteSources switch. 
```

<span data-ttu-id="30b77-137">Per caricare l'assembly ed eseguire il codice, è necessario:</span><span class="sxs-lookup"><span data-stu-id="30b77-137">To load the assembly and execute its code, you must either:</span></span>

- <span data-ttu-id="30b77-138">Creare in modo esplicito un ambiente sandbox per l'assembly (vedere [come: Eseguire codice parzialmente attendibile in un ambiente Sandbox](../../../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md)).</span><span class="sxs-lookup"><span data-stu-id="30b77-138">Explicitly create a sandbox for the assembly (see [How to: Run Partially Trusted Code in a Sandbox](../../../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md)).</span></span>

- <span data-ttu-id="30b77-139">Eseguire il codice dell'assembly con attendibilità totale.</span><span class="sxs-lookup"><span data-stu-id="30b77-139">Run the assembly's code in full trust.</span></span> <span data-ttu-id="30b77-140">A tale scopo, la configurazione di `<loadFromRemoteSources>` elemento.</span><span class="sxs-lookup"><span data-stu-id="30b77-140">You do this by configuring the `<loadFromRemoteSources>` element.</span></span> <span data-ttu-id="30b77-141">Consente di specificare che gli assembly eseguiti in attendibilità parziale in versioni precedenti di .NET Framework ora eseguito con attendibilità totale in .NET Framework 4 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="30b77-141">It lets you specify that the assemblies that run in partial trust in earlier versions of the .NET Framework now run in full trust in the .NET Framework 4 and later versions.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="30b77-142">Se l'assembly non deve essere eseguito con attendibilità totale, non impostare questo elemento di configurazione.</span><span class="sxs-lookup"><span data-stu-id="30b77-142">If the assembly should not run in full trust, do not set this configuration element.</span></span> <span data-ttu-id="30b77-143">In alternativa, creare un sandbox <xref:System.AppDomain> in cui caricare l'assembly.</span><span class="sxs-lookup"><span data-stu-id="30b77-143">Instead, create a sandboxed <xref:System.AppDomain> in which to load the assembly.</span></span>

<span data-ttu-id="30b77-144">Il `enabled` dell'attributo per il `<loadFromRemoteSources>` elemento è efficace solo quando è disabilitato sicurezza dall'accesso di codice (CAS).</span><span class="sxs-lookup"><span data-stu-id="30b77-144">The `enabled` attribute for the `<loadFromRemoteSources>` element is effective only when code access security (CAS) is disabled.</span></span> <span data-ttu-id="30b77-145">Per impostazione predefinita, tali criteri sono disabilitati in .NET Framework 4 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="30b77-145">By default, CAS policy is disabled in the .NET Framework 4 and later versions.</span></span> <span data-ttu-id="30b77-146">Se si imposta `enabled` a `true`, agli assembly remoti viene concessa l'attendibilità totale.</span><span class="sxs-lookup"><span data-stu-id="30b77-146">If you set `enabled` to `true`, remote assemblies are granted full trust.</span></span>

<span data-ttu-id="30b77-147">Se `enabled` non è impostata su `true`, un <xref:System.IO.FileLoadException> viene generata in presenza delle condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="30b77-147">If `enabled` is not set to `true`, a <xref:System.IO.FileLoadException> is thrown under the either of the following conditions:</span></span>

- <span data-ttu-id="30b77-148">Il comportamento di sandboxing del dominio corrente è diverso dal comportamento in .NET Framework 3.5.</span><span class="sxs-lookup"><span data-stu-id="30b77-148">The sandboxing behavior of the current domain is different from its behavior in the .NET Framework 3.5.</span></span> <span data-ttu-id="30b77-149">Ciò richiede criteri CAS deve essere disabilitata e il dominio corrente non deve essere creata mediante sandbox.</span><span class="sxs-lookup"><span data-stu-id="30b77-149">This requires CAS policy to be disabled, and the current domain not to be sandboxed.</span></span>

- <span data-ttu-id="30b77-150">Il caricamento dell'assembly non proviene dal `MyComputer` zona.</span><span class="sxs-lookup"><span data-stu-id="30b77-150">The assembly being loaded is not from the `MyComputer` zone.</span></span>

<span data-ttu-id="30b77-151">Impostando il `<loadFromRemoteSources>` elemento `true` impedisce che venga generata questa eccezione.</span><span class="sxs-lookup"><span data-stu-id="30b77-151">Setting the `<loadFromRemoteSources>` element to `true` prevents this exception from being thrown.</span></span> <span data-ttu-id="30b77-152">Consente di specificare che non fare affidamento sul common language runtime a sandbox gli assembly caricati per la sicurezza e che può essere autorizzato per l'esecuzione in attendibilità totale.</span><span class="sxs-lookup"><span data-stu-id="30b77-152">It enables you to specify that you are not relying on the common language runtime to sandbox the loaded assemblies for security, and that they can be allowed to execute in full trust.</span></span>

## <a name="notes"></a><span data-ttu-id="30b77-153">Note</span><span class="sxs-lookup"><span data-stu-id="30b77-153">Notes</span></span>

- <span data-ttu-id="30b77-154">In .NET Framework 4.5 e versioni successive, assembly nelle condivisioni di rete locale vengono eseguiti con attendibilità totale per impostazione predefinita. non è necessario abilitare il `<loadFromRemoteSources>` elemento.</span><span class="sxs-lookup"><span data-stu-id="30b77-154">In the .NET Framework 4.5 and later versions, assemblies on local network shares run in full trust by default; you do not have to enable the `<loadFromRemoteSources>` element.</span></span>

- <span data-ttu-id="30b77-155">Se un'applicazione è stata copiata dal web, questa viene contrassegnata da Windows come un'applicazione web, anche se si trova nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="30b77-155">If an application has been copied from the web, it is flagged by Windows as being a web application, even if it resides on the local computer.</span></span> <span data-ttu-id="30b77-156">È possibile modificare tale designazione modificandone le proprietà di file, oppure è possibile usare il `<loadFromRemoteSources>` elemento da concedere all'assembly con attendibilità totale.</span><span class="sxs-lookup"><span data-stu-id="30b77-156">You can change that designation by changing its file properties, or you can use the `<loadFromRemoteSources>` element to grant the assembly full trust.</span></span> <span data-ttu-id="30b77-157">In alternativa, è possibile usare il <xref:System.Reflection.Assembly.UnsafeLoadFrom%2A> per caricare un assembly locale che il sistema operativo ha contrassegnato come se fosse stato caricato dal web.</span><span class="sxs-lookup"><span data-stu-id="30b77-157">As an alternative, you can use the <xref:System.Reflection.Assembly.UnsafeLoadFrom%2A> method to load a local assembly that the operating system has flagged as having been loaded from the web.</span></span>

- <span data-ttu-id="30b77-158">È possibile che venga visualizzato un <xref:System.IO.FileLoadException> in un'applicazione in esecuzione in un'applicazione Windows Virtual PC.</span><span class="sxs-lookup"><span data-stu-id="30b77-158">You may get a <xref:System.IO.FileLoadException> in an application that is running in a Windows Virtual PC application.</span></span> <span data-ttu-id="30b77-159">Questa situazione può verificarsi quando si prova a caricare un file da cartelle collegate al computer host.</span><span class="sxs-lookup"><span data-stu-id="30b77-159">This can happen when you try to load a file from linked folders on the hosting computer.</span></span> <span data-ttu-id="30b77-160">Può verificarsi anche quando si prova a caricare un file da una cartella collegata a [Servizi Desktop remoto](https://go.microsoft.com/fwlink/?LinkId=182775) (servizi Terminal).</span><span class="sxs-lookup"><span data-stu-id="30b77-160">It can also occur when you try to load a file from a folder linked over [Remote Desktop Services](https://go.microsoft.com/fwlink/?LinkId=182775) (Terminal Services).</span></span> <span data-ttu-id="30b77-161">Per evitare l'eccezione, impostare `enabled` a `true`.</span><span class="sxs-lookup"><span data-stu-id="30b77-161">To avoid the exception, set `enabled` to `true`.</span></span>

## <a name="configuration-file"></a><span data-ttu-id="30b77-162">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="30b77-162">Configuration file</span></span>

<span data-ttu-id="30b77-163">Questo elemento viene in genere usato nel file di configurazione dell'applicazione, ma può essere usato in altri file di configurazione a seconda del contesto.</span><span class="sxs-lookup"><span data-stu-id="30b77-163">This element is typically used in the application configuration file, but can be used in other configuration files depending upon the context.</span></span> <span data-ttu-id="30b77-164">Per altre informazioni, vedere l'articolo [altre implicita Usa del criterio CAS: loadFromRemoteSources](https://go.microsoft.com/fwlink/p/?LinkId=266839) nel blog .NET Security.</span><span class="sxs-lookup"><span data-stu-id="30b77-164">For more information, see the article [More Implicit Uses of CAS Policy: loadFromRemoteSources](https://go.microsoft.com/fwlink/p/?LinkId=266839) in the .NET Security blog.</span></span>  

## <a name="example"></a><span data-ttu-id="30b77-165">Esempio</span><span class="sxs-lookup"><span data-stu-id="30b77-165">Example</span></span>

<span data-ttu-id="30b77-166">Nell'esempio seguente viene illustrato come concedere l'attendibilità totale per gli assembly caricati da origini remote.</span><span class="sxs-lookup"><span data-stu-id="30b77-166">The following example shows how to grant full trust to assemblies loaded from remote sources.</span></span>

```xml
<configuration>  
   <runtime>  
      <loadFromRemoteSources enabled="true"/>  
   </runtime>  
</configuration>  
```

## <a name="see-also"></a><span data-ttu-id="30b77-167">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="30b77-167">See also</span></span>

- [<span data-ttu-id="30b77-168">Utilizzi più impliciti dei criteri CAS: loadFromRemoteSources</span><span class="sxs-lookup"><span data-stu-id="30b77-168">More Implicit Uses of CAS Policy: loadFromRemoteSources</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=266839)
- [<span data-ttu-id="30b77-169">Procedura: Eseguire codice parzialmente attendibile in un oggetto Sandbox</span><span class="sxs-lookup"><span data-stu-id="30b77-169">How to: Run Partially Trusted Code in a Sandbox</span></span>](../../../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md)
- [<span data-ttu-id="30b77-170">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="30b77-170">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="30b77-171">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="30b77-171">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType>
