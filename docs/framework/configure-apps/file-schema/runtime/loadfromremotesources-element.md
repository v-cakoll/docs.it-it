---
title: <loadFromRemoteSources> Elemento
ms.date: 05/24/2018
helpviewer_keywords:
- loadFromRemoteSources element
- <loadFromRemoteSources> element
ms.assetid: 006d1280-2ac3-4db6-a984-a3d4e275046a
ms.openlocfilehash: a0dcffe378cdd09de0fbd8f0a6ef0635c033fd9c
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79154062"
---
# <a name="loadfromremotesources-element"></a><span data-ttu-id="83ca6-102">Elemento \<loadFromRemoteSources></span><span class="sxs-lookup"><span data-stu-id="83ca6-102">\<loadFromRemoteSources> element</span></span>
<span data-ttu-id="83ca6-103">Specifica se agli assembly caricati da origini remote deve essere concessa l'attendibilità totale in .NET Framework 4 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="83ca6-103">Specifies whether assemblies loaded from remote sources should be granted full trust in .NET Framework 4 and later.</span></span>
  
> [!NOTE]
> <span data-ttu-id="83ca6-104">Se è stato indirizzato a questo articolo a causa di un messaggio di errore nell'elenco errori del progetto di Visual Studio o di un errore di compilazione, vedere [procedura: usare un assembly dal Web in Visual Studio](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ee890038(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="83ca6-104">If you were directed to this article because of an error message in the Visual Studio project error list or a build error, see [How to: Use an Assembly from the Web in Visual Studio](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ee890038(v=vs.100)).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<loadFromRemoteSources>**  
  
## <a name="syntax"></a><span data-ttu-id="83ca6-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="83ca6-105">Syntax</span></span>  
  
```xml  
<loadFromRemoteSources
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="83ca6-106">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="83ca6-106">Attributes and elements</span></span>
 <span data-ttu-id="83ca6-107">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="83ca6-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="83ca6-108">Attributi</span><span class="sxs-lookup"><span data-stu-id="83ca6-108">Attributes</span></span>  
  
|<span data-ttu-id="83ca6-109">Attributo</span><span class="sxs-lookup"><span data-stu-id="83ca6-109">Attribute</span></span>|<span data-ttu-id="83ca6-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="83ca6-110">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="83ca6-111">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="83ca6-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="83ca6-112">Specifica se a un assembly caricato da un'origine remota deve essere concessa l'attendibilità totale.</span><span class="sxs-lookup"><span data-stu-id="83ca6-112">Specifies whether an assembly that is loaded from a remote source should be granted full trust.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="83ca6-113">attributo enabled</span><span class="sxs-lookup"><span data-stu-id="83ca6-113">enabled attribute</span></span>  
  
|<span data-ttu-id="83ca6-114">Valore</span><span class="sxs-lookup"><span data-stu-id="83ca6-114">Value</span></span>|<span data-ttu-id="83ca6-115">Description</span><span class="sxs-lookup"><span data-stu-id="83ca6-115">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="83ca6-116">Non concedere l'attendibilità totale alle applicazioni da origini remote.</span><span class="sxs-lookup"><span data-stu-id="83ca6-116">Do not grant full trust to applications from remote sources.</span></span> <span data-ttu-id="83ca6-117">Questo è il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="83ca6-117">This is the default.</span></span>|  
|`true`|<span data-ttu-id="83ca6-118">Concedere l'attendibilità totale alle applicazioni dalle origini remote.</span><span class="sxs-lookup"><span data-stu-id="83ca6-118">Grant full trust to applications from remote sources.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="83ca6-119">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="83ca6-119">Child elements</span></span>  
 <span data-ttu-id="83ca6-120">No.</span><span class="sxs-lookup"><span data-stu-id="83ca6-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="83ca6-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="83ca6-121">Parent elements</span></span>  
  
|<span data-ttu-id="83ca6-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="83ca6-122">Element</span></span>|<span data-ttu-id="83ca6-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="83ca6-123">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="83ca6-124">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="83ca6-124">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="83ca6-125">Contiene informazioni sulle opzioni di inizializzazione in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="83ca6-125">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="83ca6-126">Commenti</span><span class="sxs-lookup"><span data-stu-id="83ca6-126">Remarks</span></span>

<span data-ttu-id="83ca6-127">In .NET Framework 3,5 e versioni precedenti, se si carica un assembly da una posizione remota, il codice nell'assembly viene eseguito in attendibilità parziale con un set di concessioni che dipende dalla zona da cui viene caricato.</span><span class="sxs-lookup"><span data-stu-id="83ca6-127">In the .NET Framework 3.5 and earlier versions, if you load an assembly from a remote location, code in the assembly runs in partial trust with a grant set that depends on the zone from which it is loaded.</span></span> <span data-ttu-id="83ca6-128">Ad esempio, se si carica un assembly da un sito Web, questo viene caricato nell'area Internet e viene concesso il set di autorizzazioni Internet.</span><span class="sxs-lookup"><span data-stu-id="83ca6-128">For example, if you load an assembly from a website, it is loaded into the Internet zone and granted the Internet permission set.</span></span> <span data-ttu-id="83ca6-129">In altre parole, viene eseguito in una sandbox Internet.</span><span class="sxs-lookup"><span data-stu-id="83ca6-129">In other words, it executes in an Internet sandbox.</span></span>

<span data-ttu-id="83ca6-130">A partire da .NET Framework 4, il criterio di sicurezza dall'accesso di codice (CAS) è disabilitato e gli assembly vengono caricati in attendibilità totale.</span><span class="sxs-lookup"><span data-stu-id="83ca6-130">Starting with the .NET Framework 4, code access security (CAS) policy is disabled and assemblies are loaded in full trust.</span></span> <span data-ttu-id="83ca6-131">In genere, in questo modo si concede l'attendibilità totale agli assembly caricati con il <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> metodo che in precedenza era stato creato mediante sandbox.</span><span class="sxs-lookup"><span data-stu-id="83ca6-131">Ordinarily, this would grant full trust to assemblies loaded with the <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> method that previously had been sandboxed.</span></span> <span data-ttu-id="83ca6-132">Per evitare questo problema, la possibilità di eseguire il codice negli assembly caricati da un'origine remota è disabilitata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="83ca6-132">To prevent this, the ability to run code in assemblies loaded from a remote source is disabled by default.</span></span> <span data-ttu-id="83ca6-133">Per impostazione predefinita, se si tenta di caricare un assembly remoto, <xref:System.IO.FileLoadException> viene generata un'eccezione con un messaggio di eccezione simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="83ca6-133">By default, if you attempt to load a remote assembly, a <xref:System.IO.FileLoadException> with an exception message like the following is thrown:</span></span>

```text
System.IO.FileNotFoundException: Could not load file or assembly 'file:assem.dll' or one of its dependencies. Operation is not supported.
(Exception from HRESULT: 0x80131515)
File name: 'file:assem.dll' --->
System.NotSupportedException: An attempt was made to load an assembly from a network location which would have caused the assembly
to be sandboxed in previous versions of the .NET Framework. This release of the .NET Framework does not enable CAS policy by default,
so this load may be dangerous. If this load is not intended to sandbox the assembly, please enable the loadFromRemoteSources switch.
```

<span data-ttu-id="83ca6-134">Per caricare l'assembly ed eseguire il codice, è necessario eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="83ca6-134">To load the assembly and execute its code, you must either:</span></span>

- <span data-ttu-id="83ca6-135">Creare in modo esplicito un sandbox per l'assembly. vedere [procedura: eseguire codice parzialmente attendibile in un ambiente sandbox](../../../misc/how-to-run-partially-trusted-code-in-a-sandbox.md).</span><span class="sxs-lookup"><span data-stu-id="83ca6-135">Explicitly create a sandbox for the assembly (see [How to: Run Partially Trusted Code in a Sandbox](../../../misc/how-to-run-partially-trusted-code-in-a-sandbox.md)).</span></span>

- <span data-ttu-id="83ca6-136">Eseguire il codice dell'assembly in attendibilità totale.</span><span class="sxs-lookup"><span data-stu-id="83ca6-136">Run the assembly's code in full trust.</span></span> <span data-ttu-id="83ca6-137">A tale scopo, configurare l' `<loadFromRemoteSources>` elemento.</span><span class="sxs-lookup"><span data-stu-id="83ca6-137">You do this by configuring the `<loadFromRemoteSources>` element.</span></span> <span data-ttu-id="83ca6-138">Consente di specificare che gli assembly eseguiti in attendibilità parziale nelle versioni precedenti del .NET Framework ora vengono eseguiti con attendibilità totale in .NET Framework 4 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="83ca6-138">It lets you specify that the assemblies that run in partial trust in earlier versions of the .NET Framework now run in full trust in the .NET Framework 4 and later versions.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="83ca6-139">Se l'assembly non deve essere eseguito con attendibilità totale, non impostare questo elemento di configurazione.</span><span class="sxs-lookup"><span data-stu-id="83ca6-139">If the assembly should not run in full trust, do not set this configuration element.</span></span> <span data-ttu-id="83ca6-140">In alternativa, creare un oggetto sandbox <xref:System.AppDomain> in cui caricare l'assembly.</span><span class="sxs-lookup"><span data-stu-id="83ca6-140">Instead, create a sandboxed <xref:System.AppDomain> in which to load the assembly.</span></span>

<span data-ttu-id="83ca6-141">L' `enabled` attributo per l' `<loadFromRemoteSources>` elemento è efficace solo quando la sicurezza dall'accesso di codice (CAS) è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="83ca6-141">The `enabled` attribute for the `<loadFromRemoteSources>` element is effective only when code access security (CAS) is disabled.</span></span> <span data-ttu-id="83ca6-142">Per impostazione predefinita, il criterio CAS è disabilitato in .NET Framework 4 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="83ca6-142">By default, CAS policy is disabled in the .NET Framework 4 and later versions.</span></span> <span data-ttu-id="83ca6-143">Se si imposta `enabled` su `true` , agli assembly remoti viene concessa l'attendibilità totale.</span><span class="sxs-lookup"><span data-stu-id="83ca6-143">If you set `enabled` to `true`, remote assemblies are granted full trust.</span></span>

<span data-ttu-id="83ca6-144">Se `enabled` non è impostato su `true` , <xref:System.IO.FileLoadException> viene generata un'eccezione in una delle condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="83ca6-144">If `enabled` is not set to `true`, a <xref:System.IO.FileLoadException> is thrown under the either of the following conditions:</span></span>

- <span data-ttu-id="83ca6-145">Il comportamento di sandboxing del dominio corrente è diverso dal relativo comportamento nella .NET Framework 3,5.</span><span class="sxs-lookup"><span data-stu-id="83ca6-145">The sandboxing behavior of the current domain is different from its behavior in the .NET Framework 3.5.</span></span> <span data-ttu-id="83ca6-146">Questa operazione richiede che i criteri CAS siano disabilitati e che il dominio corrente non venga creato mediante sandbox.</span><span class="sxs-lookup"><span data-stu-id="83ca6-146">This requires CAS policy to be disabled, and the current domain not to be sandboxed.</span></span>

- <span data-ttu-id="83ca6-147">L'assembly da caricare non è dalla `MyComputer` zona.</span><span class="sxs-lookup"><span data-stu-id="83ca6-147">The assembly being loaded is not from the `MyComputer` zone.</span></span>

<span data-ttu-id="83ca6-148">L'impostazione dell' `<loadFromRemoteSources>` elemento su `true` impedisce che venga generata questa eccezione.</span><span class="sxs-lookup"><span data-stu-id="83ca6-148">Setting the `<loadFromRemoteSources>` element to `true` prevents this exception from being thrown.</span></span> <span data-ttu-id="83ca6-149">Consente di specificare che non si basano sulla Common Language Runtime per eseguire la sandbox degli assembly caricati per la sicurezza e che è possibile eseguirli con attendibilità totale.</span><span class="sxs-lookup"><span data-stu-id="83ca6-149">It enables you to specify that you are not relying on the common language runtime to sandbox the loaded assemblies for security, and that they can be allowed to execute in full trust.</span></span>

## <a name="notes"></a><span data-ttu-id="83ca6-150">Note</span><span class="sxs-lookup"><span data-stu-id="83ca6-150">Notes</span></span>

- <span data-ttu-id="83ca6-151">In .NET Framework 4,5 e versioni successive, gli assembly sulle condivisioni di rete locali vengono eseguiti in attendibilità totale per impostazione predefinita. non è necessario abilitare l' `<loadFromRemoteSources>` elemento.</span><span class="sxs-lookup"><span data-stu-id="83ca6-151">In the .NET Framework 4.5 and later versions, assemblies on local network shares run in full trust by default; you do not have to enable the `<loadFromRemoteSources>` element.</span></span>

- <span data-ttu-id="83ca6-152">Se un'applicazione è stata copiata dal Web, viene contrassegnata da Windows come applicazione Web, anche se risiede nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="83ca6-152">If an application has been copied from the web, it is flagged by Windows as being a web application, even if it resides on the local computer.</span></span> <span data-ttu-id="83ca6-153">È possibile modificare la designazione cambiando le proprietà del file oppure è possibile utilizzare l' `<loadFromRemoteSources>` elemento per concedere l'attendibilità totale dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="83ca6-153">You can change that designation by changing its file properties, or you can use the `<loadFromRemoteSources>` element to grant the assembly full trust.</span></span> <span data-ttu-id="83ca6-154">In alternativa, è possibile usare il <xref:System.Reflection.Assembly.UnsafeLoadFrom%2A> metodo per caricare un assembly locale segnalato dal sistema operativo come caricato dal Web.</span><span class="sxs-lookup"><span data-stu-id="83ca6-154">As an alternative, you can use the <xref:System.Reflection.Assembly.UnsafeLoadFrom%2A> method to load a local assembly that the operating system has flagged as having been loaded from the web.</span></span>

- <span data-ttu-id="83ca6-155">È possibile ottenere un oggetto <xref:System.IO.FileLoadException> in un'applicazione in esecuzione in un'applicazione Windows Virtual PC.</span><span class="sxs-lookup"><span data-stu-id="83ca6-155">You may get a <xref:System.IO.FileLoadException> in an application that is running in a Windows Virtual PC application.</span></span> <span data-ttu-id="83ca6-156">Questo problema può verificarsi quando si tenta di caricare un file dalle cartelle collegate nel computer host.</span><span class="sxs-lookup"><span data-stu-id="83ca6-156">This can happen when you try to load a file from linked folders on the hosting computer.</span></span> <span data-ttu-id="83ca6-157">Può inoltre verificarsi quando si tenta di caricare un file da una cartella collegata tramite [Servizi Desktop remoto](/windows/win32/termserv/terminal-services-portal) (Servizi terminal).</span><span class="sxs-lookup"><span data-stu-id="83ca6-157">It can also occur when you try to load a file from a folder linked over [Remote Desktop Services](/windows/win32/termserv/terminal-services-portal) (Terminal Services).</span></span> <span data-ttu-id="83ca6-158">Per evitare l'eccezione, impostare `enabled` su `true` .</span><span class="sxs-lookup"><span data-stu-id="83ca6-158">To avoid the exception, set `enabled` to `true`.</span></span>

## <a name="configuration-file"></a><span data-ttu-id="83ca6-159">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="83ca6-159">Configuration file</span></span>

<span data-ttu-id="83ca6-160">Questo elemento viene in genere usato nel file di configurazione dell'applicazione, ma può essere usato in altri file di configurazione a seconda del contesto.</span><span class="sxs-lookup"><span data-stu-id="83ca6-160">This element is typically used in the application configuration file, but can be used in other configuration files depending upon the context.</span></span> <span data-ttu-id="83ca6-161">Per ulteriori informazioni, vedere l'articolo [utilizzi più impliciti dei criteri CAS: loadFromRemoteSources](https://docs.microsoft.com/archive/blogs/shawnfa/more-implicit-uses-of-cas-policy-loadfromremotesources) nel Blog sulla sicurezza di .NET.</span><span class="sxs-lookup"><span data-stu-id="83ca6-161">For more information, see the article [More Implicit Uses of CAS Policy: loadFromRemoteSources](https://docs.microsoft.com/archive/blogs/shawnfa/more-implicit-uses-of-cas-policy-loadfromremotesources) in the .NET Security blog.</span></span>  

## <a name="example"></a><span data-ttu-id="83ca6-162">Esempio</span><span class="sxs-lookup"><span data-stu-id="83ca6-162">Example</span></span>

<span data-ttu-id="83ca6-163">Nell'esempio seguente viene illustrato come concedere l'attendibilità totale agli assembly caricati da origini remote.</span><span class="sxs-lookup"><span data-stu-id="83ca6-163">The following example shows how to grant full trust to assemblies loaded from remote sources.</span></span>

```xml
<configuration>  
   <runtime>  
      <loadFromRemoteSources enabled="true"/>  
   </runtime>  
</configuration>  
```

## <a name="see-also"></a><span data-ttu-id="83ca6-164">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="83ca6-164">See also</span></span>

- [<span data-ttu-id="83ca6-165">Utilizzi più impliciti dei criteri CAS: loadFromRemoteSources</span><span class="sxs-lookup"><span data-stu-id="83ca6-165">More Implicit Uses of CAS Policy: loadFromRemoteSources</span></span>](https://docs.microsoft.com/archive/blogs/shawnfa/more-implicit-uses-of-cas-policy-loadfromremotesources)
- [<span data-ttu-id="83ca6-166">Procedura: eseguire codice parzialmente attendibile in un oggetto sandbox</span><span class="sxs-lookup"><span data-stu-id="83ca6-166">How to: Run Partially Trusted Code in a Sandbox</span></span>](../../../misc/how-to-run-partially-trusted-code-in-a-sandbox.md)
- [<span data-ttu-id="83ca6-167">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="83ca6-167">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="83ca6-168">Schema del file di configurazione</span><span class="sxs-lookup"><span data-stu-id="83ca6-168">Configuration File Schema</span></span>](../index.md)
- <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType>
