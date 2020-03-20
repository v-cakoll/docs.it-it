---
title: <loadFromRemoteSources> Elemento
ms.date: 05/24/2018
helpviewer_keywords:
- loadFromRemoteSources element
- <loadFromRemoteSources> element
ms.assetid: 006d1280-2ac3-4db6-a984-a3d4e275046a
ms.openlocfilehash: a0dcffe378cdd09de0fbd8f0a6ef0635c033fd9c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154062"
---
# <a name="loadfromremotesources-element"></a><span data-ttu-id="39943-102">\<elemento> loadFromRemoteSources</span><span class="sxs-lookup"><span data-stu-id="39943-102">\<loadFromRemoteSources> element</span></span>
<span data-ttu-id="39943-103">Specifica se agli assembly caricati da origini remote deve essere concessa l'attendibilità totale in .NET Framework 4 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="39943-103">Specifies whether assemblies loaded from remote sources should be granted full trust in .NET Framework 4 and later.</span></span>
  
> [!NOTE]
> <span data-ttu-id="39943-104">Se si è stati indirizzati a questo articolo a causa di un messaggio di errore nell'elenco degli errori del progetto di Visual Studio o di un errore di compilazione, vedere [procedura: utilizzare un assembly dal Web in Visual Studio](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ee890038(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="39943-104">If you were directed to this article because of an error message in the Visual Studio project error list or a build error, see [How to: Use an Assembly from the Web in Visual Studio](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ee890038(v=vs.100)).</span></span>  
  
<span data-ttu-id="39943-105">[**\<>di configurazione**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="39943-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="39943-106">&nbsp;&nbsp;[**\<>di runtime**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="39943-106">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="39943-107">&nbsp;&nbsp;&nbsp;&nbsp;**\<>loadFromRemoteSources**</span><span class="sxs-lookup"><span data-stu-id="39943-107">&nbsp;&nbsp;&nbsp;&nbsp;**\<loadFromRemoteSources>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39943-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="39943-108">Syntax</span></span>  
  
```xml  
<loadFromRemoteSources
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="39943-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="39943-109">Attributes and elements</span></span>
 <span data-ttu-id="39943-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="39943-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="39943-111">Attributes</span><span class="sxs-lookup"><span data-stu-id="39943-111">Attributes</span></span>  
  
|<span data-ttu-id="39943-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="39943-112">Attribute</span></span>|<span data-ttu-id="39943-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="39943-113">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="39943-114">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="39943-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="39943-115">Specifica se a un assembly caricato da un'origine remota deve essere concessa l'attendibilità totale.</span><span class="sxs-lookup"><span data-stu-id="39943-115">Specifies whether an assembly that is loaded from a remote source should be granted full trust.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="39943-116">attributo enabled</span><span class="sxs-lookup"><span data-stu-id="39943-116">enabled attribute</span></span>  
  
|<span data-ttu-id="39943-117">valore</span><span class="sxs-lookup"><span data-stu-id="39943-117">Value</span></span>|<span data-ttu-id="39943-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="39943-118">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="39943-119">Non concedere l'attendibilità totale alle applicazioni provenienti da origini remote.</span><span class="sxs-lookup"><span data-stu-id="39943-119">Do not grant full trust to applications from remote sources.</span></span> <span data-ttu-id="39943-120">Questa è la modalità predefinita.</span><span class="sxs-lookup"><span data-stu-id="39943-120">This is the default.</span></span>|  
|`true`|<span data-ttu-id="39943-121">Concedere l'attendibilità totale alle applicazioni da origini remote.</span><span class="sxs-lookup"><span data-stu-id="39943-121">Grant full trust to applications from remote sources.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="39943-122">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="39943-122">Child elements</span></span>  
 <span data-ttu-id="39943-123">No.</span><span class="sxs-lookup"><span data-stu-id="39943-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="39943-124">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="39943-124">Parent elements</span></span>  
  
|<span data-ttu-id="39943-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="39943-125">Element</span></span>|<span data-ttu-id="39943-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="39943-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="39943-127">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="39943-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="39943-128">Contiene informazioni sulle opzioni di inizializzazione in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="39943-128">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="39943-129">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="39943-129">Remarks</span></span>

<span data-ttu-id="39943-130">In .NET Framework 3.5 e versioni precedenti, se si carica un assembly da una posizione remota, il codice nell'assembly viene eseguito in attendibilità parziale con un set di concessioni che dipende dalla zona da cui viene caricato.</span><span class="sxs-lookup"><span data-stu-id="39943-130">In the .NET Framework 3.5 and earlier versions, if you load an assembly from a remote location, code in the assembly runs in partial trust with a grant set that depends on the zone from which it is loaded.</span></span> <span data-ttu-id="39943-131">Ad esempio, se si carica un assembly da un sito Web, questo viene caricato nell'area Internet e viene concesso il set di autorizzazioni Internet.</span><span class="sxs-lookup"><span data-stu-id="39943-131">For example, if you load an assembly from a website, it is loaded into the Internet zone and granted the Internet permission set.</span></span> <span data-ttu-id="39943-132">In altre parole, viene eseguito in una sandbox Internet.</span><span class="sxs-lookup"><span data-stu-id="39943-132">In other words, it executes in an Internet sandbox.</span></span>

<span data-ttu-id="39943-133">A partire da .NET Framework 4.NET Framework 4, i criteri di sicurezza dall'accesso di codice sono disabilitati e gli assembly vengono caricati con attendibilità totale.</span><span class="sxs-lookup"><span data-stu-id="39943-133">Starting with the .NET Framework 4, code access security (CAS) policy is disabled and assemblies are loaded in full trust.</span></span> <span data-ttu-id="39943-134">In genere, ciò concedelrebbe l'attendibilità totale agli assembly caricati con il <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> metodo che in precedenza era stato sottoposto a sandbox.</span><span class="sxs-lookup"><span data-stu-id="39943-134">Ordinarily, this would grant full trust to assemblies loaded with the <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> method that previously had been sandboxed.</span></span> <span data-ttu-id="39943-135">Per evitare questo problema, la possibilità di eseguire codice negli assembly caricati da un'origine remota è disabilitata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="39943-135">To prevent this, the ability to run code in assemblies loaded from a remote source is disabled by default.</span></span> <span data-ttu-id="39943-136">Per impostazione predefinita, se si tenta <xref:System.IO.FileLoadException> di caricare un assembly remoto, viene generato un messaggio di eccezione simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="39943-136">By default, if you attempt to load a remote assembly, a <xref:System.IO.FileLoadException> with an exception message like the following is thrown:</span></span>

```text
System.IO.FileNotFoundException: Could not load file or assembly 'file:assem.dll' or one of its dependencies. Operation is not supported.
(Exception from HRESULT: 0x80131515)
File name: 'file:assem.dll' --->
System.NotSupportedException: An attempt was made to load an assembly from a network location which would have caused the assembly
to be sandboxed in previous versions of the .NET Framework. This release of the .NET Framework does not enable CAS policy by default,
so this load may be dangerous. If this load is not intended to sandbox the assembly, please enable the loadFromRemoteSources switch.
```

<span data-ttu-id="39943-137">Per caricare l'assembly ed eseguirne il codice, è necessario:</span><span class="sxs-lookup"><span data-stu-id="39943-137">To load the assembly and execute its code, you must either:</span></span>

- <span data-ttu-id="39943-138">Creare in modo esplicito una sandbox per l'assembly (vedere [Procedura: eseguire codice parzialmente attendibile in una sandbox](../../../misc/how-to-run-partially-trusted-code-in-a-sandbox.md)).</span><span class="sxs-lookup"><span data-stu-id="39943-138">Explicitly create a sandbox for the assembly (see [How to: Run Partially Trusted Code in a Sandbox](../../../misc/how-to-run-partially-trusted-code-in-a-sandbox.md)).</span></span>

- <span data-ttu-id="39943-139">Eseguire il codice dell'assembly con attendibilità totale.</span><span class="sxs-lookup"><span data-stu-id="39943-139">Run the assembly's code in full trust.</span></span> <span data-ttu-id="39943-140">A tale scopo, `<loadFromRemoteSources>` configurare l'elemento.</span><span class="sxs-lookup"><span data-stu-id="39943-140">You do this by configuring the `<loadFromRemoteSources>` element.</span></span> <span data-ttu-id="39943-141">Consente di specificare che gli assembly eseguiti in attendibilità parziale nelle versioni precedenti di .NET Framework vengono ora eseguiti in attendibilità totale in .NET Framework 4 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="39943-141">It lets you specify that the assemblies that run in partial trust in earlier versions of the .NET Framework now run in full trust in the .NET Framework 4 and later versions.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="39943-142">Se l'assembly non deve essere eseguito con attendibilità totale, non impostare questo elemento di configurazione.</span><span class="sxs-lookup"><span data-stu-id="39943-142">If the assembly should not run in full trust, do not set this configuration element.</span></span> <span data-ttu-id="39943-143">Creare invece una <xref:System.AppDomain> sandbox in cui caricare l'assieme.</span><span class="sxs-lookup"><span data-stu-id="39943-143">Instead, create a sandboxed <xref:System.AppDomain> in which to load the assembly.</span></span>

<span data-ttu-id="39943-144">`enabled` L'attributo `<loadFromRemoteSources>` per l'elemento è valido solo quando la sicurezza dall'accesso di codice (CAS) è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="39943-144">The `enabled` attribute for the `<loadFromRemoteSources>` element is effective only when code access security (CAS) is disabled.</span></span> <span data-ttu-id="39943-145">Per impostazione predefinita, i criteri CAS sono disabilitati in .NET Framework 4 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="39943-145">By default, CAS policy is disabled in the .NET Framework 4 and later versions.</span></span> <span data-ttu-id="39943-146">Se si `enabled` `true`imposta su , agli assembly remoti viene concessa l'attendibilità totale.</span><span class="sxs-lookup"><span data-stu-id="39943-146">If you set `enabled` to `true`, remote assemblies are granted full trust.</span></span>

<span data-ttu-id="39943-147">Se `enabled` non è `true`impostato <xref:System.IO.FileLoadException> su , viene generata una eccezione in una delle seguenti condizioni:</span><span class="sxs-lookup"><span data-stu-id="39943-147">If `enabled` is not set to `true`, a <xref:System.IO.FileLoadException> is thrown under the either of the following conditions:</span></span>

- <span data-ttu-id="39943-148">Il comportamento sandbox del dominio corrente è diverso dal comportamento in .NET Framework 3.5.</span><span class="sxs-lookup"><span data-stu-id="39943-148">The sandboxing behavior of the current domain is different from its behavior in the .NET Framework 3.5.</span></span> <span data-ttu-id="39943-149">Ciò richiede la disabilitazione dei criteri CAS e il dominio corrente non deve essere inmodale.</span><span class="sxs-lookup"><span data-stu-id="39943-149">This requires CAS policy to be disabled, and the current domain not to be sandboxed.</span></span>

- <span data-ttu-id="39943-150">L'assembly caricato non `MyComputer` proviene dalla zona.</span><span class="sxs-lookup"><span data-stu-id="39943-150">The assembly being loaded is not from the `MyComputer` zone.</span></span>

<span data-ttu-id="39943-151">L'impostazione `true` dell'elemento su impedisce la `<loadFromRemoteSources>` creazione di questa eccezione.</span><span class="sxs-lookup"><span data-stu-id="39943-151">Setting the `<loadFromRemoteSources>` element to `true` prevents this exception from being thrown.</span></span> <span data-ttu-id="39943-152">Consente di specificare che non si basa su Common Language Runtime per inserire in modalità sandbox gli assembly caricati per la sicurezza e che possono essere autorizzati a eseguire in attendibilità totale.</span><span class="sxs-lookup"><span data-stu-id="39943-152">It enables you to specify that you are not relying on the common language runtime to sandbox the loaded assemblies for security, and that they can be allowed to execute in full trust.</span></span>

## <a name="notes"></a><span data-ttu-id="39943-153">Note</span><span class="sxs-lookup"><span data-stu-id="39943-153">Notes</span></span>

- <span data-ttu-id="39943-154">In .NET Framework 4.5 e versioni successive, gli assembly nelle condivisioni di rete locali vengono eseguiti con attendibilità totale per impostazione predefinita. non è necessario abilitare l'elemento. `<loadFromRemoteSources>`</span><span class="sxs-lookup"><span data-stu-id="39943-154">In the .NET Framework 4.5 and later versions, assemblies on local network shares run in full trust by default; you do not have to enable the `<loadFromRemoteSources>` element.</span></span>

- <span data-ttu-id="39943-155">Se un'applicazione è stata copiata dal Web, viene contrassegnata da Windows come applicazione Web, anche se risiede nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="39943-155">If an application has been copied from the web, it is flagged by Windows as being a web application, even if it resides on the local computer.</span></span> <span data-ttu-id="39943-156">È possibile modificare tale designazione modificandone le proprietà `<loadFromRemoteSources>` del file oppure utilizzare l'elemento per concedere all'assembly l'attendibilità totale.</span><span class="sxs-lookup"><span data-stu-id="39943-156">You can change that designation by changing its file properties, or you can use the `<loadFromRemoteSources>` element to grant the assembly full trust.</span></span> <span data-ttu-id="39943-157">In alternativa, è possibile <xref:System.Reflection.Assembly.UnsafeLoadFrom%2A> utilizzare il metodo per caricare un assembly locale contrassegnato come caricato dal Web.</span><span class="sxs-lookup"><span data-stu-id="39943-157">As an alternative, you can use the <xref:System.Reflection.Assembly.UnsafeLoadFrom%2A> method to load a local assembly that the operating system has flagged as having been loaded from the web.</span></span>

- <span data-ttu-id="39943-158">È possibile <xref:System.IO.FileLoadException> ottenere un in un'applicazione in esecuzione in un'applicazione Windows Virtual PC.</span><span class="sxs-lookup"><span data-stu-id="39943-158">You may get a <xref:System.IO.FileLoadException> in an application that is running in a Windows Virtual PC application.</span></span> <span data-ttu-id="39943-159">Ciò può verificarsi quando si tenta di caricare un file da cartelle collegate sul computer host.</span><span class="sxs-lookup"><span data-stu-id="39943-159">This can happen when you try to load a file from linked folders on the hosting computer.</span></span> <span data-ttu-id="39943-160">Può verificarsi anche quando si tenta di caricare un file da una cartella collegata tramite [Servizi Desktop remoto](/windows/win32/termserv/terminal-services-portal) (Servizi terminal).</span><span class="sxs-lookup"><span data-stu-id="39943-160">It can also occur when you try to load a file from a folder linked over [Remote Desktop Services](/windows/win32/termserv/terminal-services-portal) (Terminal Services).</span></span> <span data-ttu-id="39943-161">Per evitare l'eccezione, impostare `enabled` su `true`.</span><span class="sxs-lookup"><span data-stu-id="39943-161">To avoid the exception, set `enabled` to `true`.</span></span>

## <a name="configuration-file"></a><span data-ttu-id="39943-162">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="39943-162">Configuration file</span></span>

<span data-ttu-id="39943-163">Questo elemento viene in genere utilizzato nel file di configurazione dell'applicazione, ma può essere utilizzato in altri file di configurazione a seconda del contesto.</span><span class="sxs-lookup"><span data-stu-id="39943-163">This element is typically used in the application configuration file, but can be used in other configuration files depending upon the context.</span></span> <span data-ttu-id="39943-164">Per altre informazioni, vedere l'articolo [Altri utilizzi impliciti di Criteri CA: loadFromRemoteSources](https://docs.microsoft.com/archive/blogs/shawnfa/more-implicit-uses-of-cas-policy-loadfromremotesources) nel blog sulla sicurezza di .NET.</span><span class="sxs-lookup"><span data-stu-id="39943-164">For more information, see the article [More Implicit Uses of CAS Policy: loadFromRemoteSources](https://docs.microsoft.com/archive/blogs/shawnfa/more-implicit-uses-of-cas-policy-loadfromremotesources) in the .NET Security blog.</span></span>  

## <a name="example"></a><span data-ttu-id="39943-165">Esempio</span><span class="sxs-lookup"><span data-stu-id="39943-165">Example</span></span>

<span data-ttu-id="39943-166">Nell'esempio seguente viene illustrato come concedere l'attendibilità totale agli assembly caricati da origini remote.</span><span class="sxs-lookup"><span data-stu-id="39943-166">The following example shows how to grant full trust to assemblies loaded from remote sources.</span></span>

```xml
<configuration>  
   <runtime>  
      <loadFromRemoteSources enabled="true"/>  
   </runtime>  
</configuration>  
```

## <a name="see-also"></a><span data-ttu-id="39943-167">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="39943-167">See also</span></span>

- [<span data-ttu-id="39943-168">Usi più impliciti dei criteri CAS: loadFromRemoteSources</span><span class="sxs-lookup"><span data-stu-id="39943-168">More Implicit Uses of CAS Policy: loadFromRemoteSources</span></span>](https://docs.microsoft.com/archive/blogs/shawnfa/more-implicit-uses-of-cas-policy-loadfromremotesources)
- [<span data-ttu-id="39943-169">Procedura: eseguire codice parzialmente attendibile in un oggetto sandbox</span><span class="sxs-lookup"><span data-stu-id="39943-169">How to: Run Partially Trusted Code in a Sandbox</span></span>](../../../misc/how-to-run-partially-trusted-code-in-a-sandbox.md)
- [<span data-ttu-id="39943-170">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="39943-170">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="39943-171">Schema del file di configurazione</span><span class="sxs-lookup"><span data-stu-id="39943-171">Configuration File Schema</span></span>](../index.md)
- <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType>
