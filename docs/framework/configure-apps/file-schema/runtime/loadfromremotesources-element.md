---
title: <loadFromRemoteSources> Elemento
ms.date: 05/24/2018
helpviewer_keywords:
- loadFromRemoteSources element
- <loadFromRemoteSources> element
ms.assetid: 006d1280-2ac3-4db6-a984-a3d4e275046a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2268d07fb643621c944ef9bf561156b5332aaafc
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920710"
---
# <a name="loadfromremotesources-element"></a><span data-ttu-id="c7e72-102">\<elemento > loadFromRemoteSources</span><span class="sxs-lookup"><span data-stu-id="c7e72-102">\<loadFromRemoteSources> element</span></span>
<span data-ttu-id="c7e72-103">Specifica se agli assembly caricati da origini remote deve essere concessa l'attendibilità totale in .NET Framework 4 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="c7e72-103">Specifies whether assemblies loaded from remote sources should be granted full trust in .NET Framework 4 and later.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c7e72-104">Se è stato indirizzato a questo articolo a causa di un messaggio di errore nell'elenco errori del progetto di Visual Studio o di [un errore di compilazione, vedere Procedura: Usare un assembly dal Web in Visual Studio](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ee890038(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="c7e72-104">If you were directed to this article because of an error message in the Visual Studio project error list or a build error, see [How to: Use an Assembly from the Web in Visual Studio](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ee890038(v=vs.100)).</span></span>  
  
 <span data-ttu-id="c7e72-105">\<configuration></span><span class="sxs-lookup"><span data-stu-id="c7e72-105">\<configuration></span></span>  
<span data-ttu-id="c7e72-106">\<runtime></span><span class="sxs-lookup"><span data-stu-id="c7e72-106">\<runtime></span></span>  
<span data-ttu-id="c7e72-107">\<loadFromRemoteSources></span><span class="sxs-lookup"><span data-stu-id="c7e72-107">\<loadFromRemoteSources></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7e72-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c7e72-108">Syntax</span></span>  
  
```xml  
<loadFromRemoteSources    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c7e72-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="c7e72-109">Attributes and elements</span></span>
 <span data-ttu-id="c7e72-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="c7e72-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c7e72-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="c7e72-111">Attributes</span></span>  
  
|<span data-ttu-id="c7e72-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="c7e72-112">Attribute</span></span>|<span data-ttu-id="c7e72-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c7e72-113">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="c7e72-114">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="c7e72-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="c7e72-115">Specifica se a un assembly caricato da un'origine remota deve essere concessa l'attendibilità totale.</span><span class="sxs-lookup"><span data-stu-id="c7e72-115">Specifies whether an assembly that is loaded from a remote source should be granted full trust.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="c7e72-116">attributo enabled</span><span class="sxs-lookup"><span data-stu-id="c7e72-116">enabled attribute</span></span>  
  
|<span data-ttu-id="c7e72-117">Value</span><span class="sxs-lookup"><span data-stu-id="c7e72-117">Value</span></span>|<span data-ttu-id="c7e72-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c7e72-118">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="c7e72-119">Non concedere l'attendibilità totale alle applicazioni da origini remote.</span><span class="sxs-lookup"><span data-stu-id="c7e72-119">Do not grant full trust to applications from remote sources.</span></span> <span data-ttu-id="c7e72-120">Questa è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="c7e72-120">This is the default.</span></span>|  
|`true`|<span data-ttu-id="c7e72-121">Concedere l'attendibilità totale alle applicazioni dalle origini remote.</span><span class="sxs-lookup"><span data-stu-id="c7e72-121">Grant full trust to applications from remote sources.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c7e72-122">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="c7e72-122">Child elements</span></span>  
 <span data-ttu-id="c7e72-123">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="c7e72-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c7e72-124">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="c7e72-124">Parent elements</span></span>  
  
|<span data-ttu-id="c7e72-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="c7e72-125">Element</span></span>|<span data-ttu-id="c7e72-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c7e72-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="c7e72-127">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c7e72-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="c7e72-128">Contiene informazioni sulle opzioni di inizializzazione in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="c7e72-128">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c7e72-129">Note</span><span class="sxs-lookup"><span data-stu-id="c7e72-129">Remarks</span></span>

<span data-ttu-id="c7e72-130">In .NET Framework 3,5 e versioni precedenti, se si carica un assembly da una posizione remota, il codice nell'assembly viene eseguito in attendibilità parziale con un set di concessioni che dipende dalla zona da cui viene caricato.</span><span class="sxs-lookup"><span data-stu-id="c7e72-130">In the .NET Framework 3.5 and earlier versions, if you load an assembly from a remote location, code in the assembly runs in partial trust with a grant set that depends on the zone from which it is loaded.</span></span> <span data-ttu-id="c7e72-131">Ad esempio, se si carica un assembly da un sito Web, questo viene caricato nell'area Internet e viene concesso il set di autorizzazioni Internet.</span><span class="sxs-lookup"><span data-stu-id="c7e72-131">For example, if you load an assembly from a website, it is loaded into the Internet zone and granted the Internet permission set.</span></span> <span data-ttu-id="c7e72-132">In altre parole, viene eseguito in una sandbox Internet.</span><span class="sxs-lookup"><span data-stu-id="c7e72-132">In other words, it executes in an Internet sandbox.</span></span>

<span data-ttu-id="c7e72-133">A partire da .NET Framework 4, il criterio di sicurezza dall'accesso di codice (CAS) è disabilitato e gli assembly vengono caricati in attendibilità totale.</span><span class="sxs-lookup"><span data-stu-id="c7e72-133">Starting with the .NET Framework 4, code access security (CAS) policy is disabled and assemblies are loaded in full trust.</span></span> <span data-ttu-id="c7e72-134">In genere, in questo modo si concede l'attendibilità totale agli <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> assembly caricati con il metodo che in precedenza era stato creato mediante sandbox.</span><span class="sxs-lookup"><span data-stu-id="c7e72-134">Ordinarily, this would grant full trust to assemblies loaded with the <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> method that previously had been sandboxed.</span></span> <span data-ttu-id="c7e72-135">Per evitare questo problema, la possibilità di eseguire il codice negli assembly caricati da un'origine remota è disabilitata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="c7e72-135">To prevent this, the ability to run code in assemblies loaded from a remote source is disabled by default.</span></span> <span data-ttu-id="c7e72-136">Per impostazione predefinita, se si tenta di caricare un assembly remoto, <xref:System.IO.FileLoadException> viene generata un'eccezione con un messaggio di eccezione simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="c7e72-136">By default, if you attempt to load a remote assembly, a <xref:System.IO.FileLoadException> with an exception message like the following is thrown:</span></span>

```text
System.IO.FileNotFoundException: Could not load file or assembly 'file:assem.dll' or one of its dependencies. Operation is not supported. 
(Exception from HRESULT: 0x80131515)
File name: 'file:assem.dll' ---> 
System.NotSupportedException: An attempt was made to load an assembly from a network location which would have caused the assembly 
to be sandboxed in previous versions of the .NET Framework. This release of the .NET Framework does not enable CAS policy by default, 
so this load may be dangerous. If this load is not intended to sandbox the assembly, please enable the loadFromRemoteSources switch. 
```

<span data-ttu-id="c7e72-137">Per caricare l'assembly ed eseguire il codice, è necessario eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c7e72-137">To load the assembly and execute its code, you must either:</span></span>

- <span data-ttu-id="c7e72-138">Creare in modo esplicito un sandbox per l'assembly [(vedere Procedura: Eseguire codice parzialmente attendibile in un](../../../misc/how-to-run-partially-trusted-code-in-a-sandbox.md)oggetto sandbox.</span><span class="sxs-lookup"><span data-stu-id="c7e72-138">Explicitly create a sandbox for the assembly (see [How to: Run Partially Trusted Code in a Sandbox](../../../misc/how-to-run-partially-trusted-code-in-a-sandbox.md)).</span></span>

- <span data-ttu-id="c7e72-139">Eseguire il codice dell'assembly in attendibilità totale.</span><span class="sxs-lookup"><span data-stu-id="c7e72-139">Run the assembly's code in full trust.</span></span> <span data-ttu-id="c7e72-140">A tale scopo, configurare l' `<loadFromRemoteSources>` elemento.</span><span class="sxs-lookup"><span data-stu-id="c7e72-140">You do this by configuring the `<loadFromRemoteSources>` element.</span></span> <span data-ttu-id="c7e72-141">Consente di specificare che gli assembly eseguiti in attendibilità parziale nelle versioni precedenti del .NET Framework ora vengono eseguiti con attendibilità totale in .NET Framework 4 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="c7e72-141">It lets you specify that the assemblies that run in partial trust in earlier versions of the .NET Framework now run in full trust in the .NET Framework 4 and later versions.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c7e72-142">Se l'assembly non deve essere eseguito con attendibilità totale, non impostare questo elemento di configurazione.</span><span class="sxs-lookup"><span data-stu-id="c7e72-142">If the assembly should not run in full trust, do not set this configuration element.</span></span> <span data-ttu-id="c7e72-143"><xref:System.AppDomain> In alternativa, creare un oggetto sandbox in cui caricare l'assembly.</span><span class="sxs-lookup"><span data-stu-id="c7e72-143">Instead, create a sandboxed <xref:System.AppDomain> in which to load the assembly.</span></span>

<span data-ttu-id="c7e72-144">L' `enabled` attributo per l' `<loadFromRemoteSources>` elemento è efficace solo quando la sicurezza dall'accesso di codice (CAS) è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="c7e72-144">The `enabled` attribute for the `<loadFromRemoteSources>` element is effective only when code access security (CAS) is disabled.</span></span> <span data-ttu-id="c7e72-145">Per impostazione predefinita, il criterio CAS è disabilitato in .NET Framework 4 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="c7e72-145">By default, CAS policy is disabled in the .NET Framework 4 and later versions.</span></span> <span data-ttu-id="c7e72-146">Se si imposta `enabled` su `true`, agli assembly remoti viene concessa l'attendibilità totale.</span><span class="sxs-lookup"><span data-stu-id="c7e72-146">If you set `enabled` to `true`, remote assemblies are granted full trust.</span></span>

<span data-ttu-id="c7e72-147">Se `enabled` non è impostato su `true`, viene <xref:System.IO.FileLoadException> generata un'eccezione in una delle condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c7e72-147">If `enabled` is not set to `true`, a <xref:System.IO.FileLoadException> is thrown under the either of the following conditions:</span></span>

- <span data-ttu-id="c7e72-148">Il comportamento di sandboxing del dominio corrente è diverso dal relativo comportamento nella .NET Framework 3,5.</span><span class="sxs-lookup"><span data-stu-id="c7e72-148">The sandboxing behavior of the current domain is different from its behavior in the .NET Framework 3.5.</span></span> <span data-ttu-id="c7e72-149">Questa operazione richiede che i criteri CAS siano disabilitati e che il dominio corrente non venga creato mediante sandbox.</span><span class="sxs-lookup"><span data-stu-id="c7e72-149">This requires CAS policy to be disabled, and the current domain not to be sandboxed.</span></span>

- <span data-ttu-id="c7e72-150">L'assembly da caricare non è dalla `MyComputer` zona.</span><span class="sxs-lookup"><span data-stu-id="c7e72-150">The assembly being loaded is not from the `MyComputer` zone.</span></span>

<span data-ttu-id="c7e72-151">L'impostazione `<loadFromRemoteSources>` dell'elemento `true` su impedisce che venga generata questa eccezione.</span><span class="sxs-lookup"><span data-stu-id="c7e72-151">Setting the `<loadFromRemoteSources>` element to `true` prevents this exception from being thrown.</span></span> <span data-ttu-id="c7e72-152">Consente di specificare che non si basano sulla Common Language Runtime per eseguire la sandbox degli assembly caricati per la sicurezza e che è possibile eseguirli con attendibilità totale.</span><span class="sxs-lookup"><span data-stu-id="c7e72-152">It enables you to specify that you are not relying on the common language runtime to sandbox the loaded assemblies for security, and that they can be allowed to execute in full trust.</span></span>

## <a name="notes"></a><span data-ttu-id="c7e72-153">Note</span><span class="sxs-lookup"><span data-stu-id="c7e72-153">Notes</span></span>

- <span data-ttu-id="c7e72-154">In .NET Framework 4,5 e versioni successive, gli assembly sulle condivisioni di rete locali vengono eseguiti in attendibilità totale per impostazione predefinita. non è necessario abilitare l' `<loadFromRemoteSources>` elemento.</span><span class="sxs-lookup"><span data-stu-id="c7e72-154">In the .NET Framework 4.5 and later versions, assemblies on local network shares run in full trust by default; you do not have to enable the `<loadFromRemoteSources>` element.</span></span>

- <span data-ttu-id="c7e72-155">Se un'applicazione è stata copiata dal Web, viene contrassegnata da Windows come applicazione Web, anche se risiede nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="c7e72-155">If an application has been copied from the web, it is flagged by Windows as being a web application, even if it resides on the local computer.</span></span> <span data-ttu-id="c7e72-156">È possibile modificare la designazione cambiando le proprietà del file oppure è possibile utilizzare l' `<loadFromRemoteSources>` elemento per concedere l'attendibilità totale dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="c7e72-156">You can change that designation by changing its file properties, or you can use the `<loadFromRemoteSources>` element to grant the assembly full trust.</span></span> <span data-ttu-id="c7e72-157">In alternativa, è possibile usare il <xref:System.Reflection.Assembly.UnsafeLoadFrom%2A> metodo per caricare un assembly locale segnalato dal sistema operativo come caricato dal Web.</span><span class="sxs-lookup"><span data-stu-id="c7e72-157">As an alternative, you can use the <xref:System.Reflection.Assembly.UnsafeLoadFrom%2A> method to load a local assembly that the operating system has flagged as having been loaded from the web.</span></span>

- <span data-ttu-id="c7e72-158">È possibile ottenere un <xref:System.IO.FileLoadException> oggetto in un'applicazione in esecuzione in un'applicazione Windows Virtual PC.</span><span class="sxs-lookup"><span data-stu-id="c7e72-158">You may get a <xref:System.IO.FileLoadException> in an application that is running in a Windows Virtual PC application.</span></span> <span data-ttu-id="c7e72-159">Questo problema può verificarsi quando si tenta di caricare un file dalle cartelle collegate nel computer host.</span><span class="sxs-lookup"><span data-stu-id="c7e72-159">This can happen when you try to load a file from linked folders on the hosting computer.</span></span> <span data-ttu-id="c7e72-160">Può inoltre verificarsi quando si tenta di caricare un file da una cartella collegata tramite [Servizi Desktop remoto](https://go.microsoft.com/fwlink/?LinkId=182775) (Servizi terminal).</span><span class="sxs-lookup"><span data-stu-id="c7e72-160">It can also occur when you try to load a file from a folder linked over [Remote Desktop Services](https://go.microsoft.com/fwlink/?LinkId=182775) (Terminal Services).</span></span> <span data-ttu-id="c7e72-161">Per evitare l'eccezione, impostare `enabled` su `true`.</span><span class="sxs-lookup"><span data-stu-id="c7e72-161">To avoid the exception, set `enabled` to `true`.</span></span>

## <a name="configuration-file"></a><span data-ttu-id="c7e72-162">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="c7e72-162">Configuration file</span></span>

<span data-ttu-id="c7e72-163">Questo elemento viene in genere usato nel file di configurazione dell'applicazione, ma può essere usato in altri file di configurazione a seconda del contesto.</span><span class="sxs-lookup"><span data-stu-id="c7e72-163">This element is typically used in the application configuration file, but can be used in other configuration files depending upon the context.</span></span> <span data-ttu-id="c7e72-164">Per ulteriori informazioni, vedere l'articolo [utilizzi più impliciti dei criteri CAS: loadFromRemoteSources](https://go.microsoft.com/fwlink/p/?LinkId=266839) nel Blog sulla sicurezza di .NET.</span><span class="sxs-lookup"><span data-stu-id="c7e72-164">For more information, see the article [More Implicit Uses of CAS Policy: loadFromRemoteSources](https://go.microsoft.com/fwlink/p/?LinkId=266839) in the .NET Security blog.</span></span>  

## <a name="example"></a><span data-ttu-id="c7e72-165">Esempio</span><span class="sxs-lookup"><span data-stu-id="c7e72-165">Example</span></span>

<span data-ttu-id="c7e72-166">Nell'esempio seguente viene illustrato come concedere l'attendibilità totale agli assembly caricati da origini remote.</span><span class="sxs-lookup"><span data-stu-id="c7e72-166">The following example shows how to grant full trust to assemblies loaded from remote sources.</span></span>

```xml
<configuration>  
   <runtime>  
      <loadFromRemoteSources enabled="true"/>  
   </runtime>  
</configuration>  
```

## <a name="see-also"></a><span data-ttu-id="c7e72-167">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c7e72-167">See also</span></span>

- [<span data-ttu-id="c7e72-168">Utilizzi più impliciti dei criteri CAS: loadFromRemoteSources</span><span class="sxs-lookup"><span data-stu-id="c7e72-168">More Implicit Uses of CAS Policy: loadFromRemoteSources</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=266839)
- [<span data-ttu-id="c7e72-169">Procedura: Eseguire codice parzialmente attendibile in un oggetto sandbox</span><span class="sxs-lookup"><span data-stu-id="c7e72-169">How to: Run Partially Trusted Code in a Sandbox</span></span>](../../../misc/how-to-run-partially-trusted-code-in-a-sandbox.md)
- [<span data-ttu-id="c7e72-170">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="c7e72-170">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="c7e72-171">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="c7e72-171">Configuration File Schema</span></span>](../index.md)
- <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType>
