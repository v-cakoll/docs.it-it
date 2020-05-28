---
title: Esempio di migrazione a .NET Core 3.1
description: Viene illustrato come eseguire la migrazione di applicazioni di esempio destinate a .NET Framework a .NET Core 3,1.
ms.date: 05/12/2020
ms.openlocfilehash: 5e8b1219cf4bd89ada5b71a60ef27eaabb94997c
ms.sourcegitcommit: ee5b798427f81237a3c23d1fd81fff7fdc21e8d3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/28/2020
ms.locfileid: "84144270"
---
# <a name="example-of-migrating-to-net-core-31"></a><span data-ttu-id="95dee-103">Esempio di migrazione a .NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="95dee-103">Example of migrating to .NET Core 3.1</span></span>

<span data-ttu-id="95dee-104">In questo capitolo vengono presentate linee guida pratiche che consentono di eseguire la migrazione dell'applicazione esistente da .NET Framework a .NET Core.</span><span class="sxs-lookup"><span data-stu-id="95dee-104">In this chapter, we present practical guidelines to help you perform a migration of your existing application from .NET Framework to .NET Core.</span></span>

<span data-ttu-id="95dee-105">Viene presentato un processo ben strutturato che è possibile seguire e le considerazioni più importanti da tenere in considerazione per ogni passaggio.</span><span class="sxs-lookup"><span data-stu-id="95dee-105">We present a well-structured process you can follow and the most important things to consider on each step.</span></span>

<span data-ttu-id="95dee-106">Viene quindi documentato un processo di migrazione dettagliato per un'applicazione desktop di esempio, sia da WinForms che da versioni WPF.</span><span class="sxs-lookup"><span data-stu-id="95dee-106">We then document a step-by-step migration process for a sample desktop application, both from WinForms and WPF versions.</span></span>

## <a name="migration-process-overview"></a><span data-ttu-id="95dee-107">Panoramica del processo di migrazione</span><span class="sxs-lookup"><span data-stu-id="95dee-107">Migration process overview</span></span>

<span data-ttu-id="95dee-108">Il processo di migrazione è costituito da quattro passaggi sequenziali:</span><span class="sxs-lookup"><span data-stu-id="95dee-108">The migration process consists of four sequential steps:</span></span>

1. <span data-ttu-id="95dee-109">**Preparazione**: comprendere le dipendenze che il progetto deve avere un'idea del futuro.</span><span class="sxs-lookup"><span data-stu-id="95dee-109">**Preparation**: Understand the dependencies the project has to have an idea of what's ahead.</span></span> <span data-ttu-id="95dee-110">In questo passaggio il progetto corrente viene portato a uno stato che semplifica il punto di avvio per la migrazione.</span><span class="sxs-lookup"><span data-stu-id="95dee-110">In this step, you take the current project into a state that simplifies the startup point for the migration.</span></span>

2. <span data-ttu-id="95dee-111">**Esegui la migrazione del file di progetto:** i progetti .NET Core usano il nuovo formato di progetto in stile SDK.</span><span class="sxs-lookup"><span data-stu-id="95dee-111">**Migrate Project File:** .NET Core projects use the new SDK-style project format.</span></span> <span data-ttu-id="95dee-112">Creare un nuovo file di progetto con questo formato o aggiornare quello necessario per usare lo stile SDK.</span><span class="sxs-lookup"><span data-stu-id="95dee-112">Create a new project file with this format or update the one you have to use the SDK style.</span></span>

3. <span data-ttu-id="95dee-113">**Correzione del codice e della compilazione:** Compilare il codice in .NET Core che indirizza le differenze a livello di API tra .NET Framework e .NET Core.</span><span class="sxs-lookup"><span data-stu-id="95dee-113">**Fix code and build:** Build the code in .NET Core addressing API-level differences between .NET Framework and .NET Core.</span></span> <span data-ttu-id="95dee-114">Se necessario, aggiornare i pacchetti di terze parti a quelli che supportano .NET Core.</span><span class="sxs-lookup"><span data-stu-id="95dee-114">If needed, update third-party packages to the ones that support .NET Core.</span></span>

4. <span data-ttu-id="95dee-115">**Esecuzione e test:** Potrebbero esserci differenze che non vengono visualizzate fino alla fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="95dee-115">**Run and test:** There might be differences that don't show up until run time.</span></span> <span data-ttu-id="95dee-116">Quindi, non dimenticare di eseguire l'applicazione e verificare che tutto funzioni come previsto.</span><span class="sxs-lookup"><span data-stu-id="95dee-116">So, don't forget to run the application and test that everything works as expected.</span></span>

### <a name="preparation"></a><span data-ttu-id="95dee-117">Preparazione</span><span class="sxs-lookup"><span data-stu-id="95dee-117">Preparation</span></span>

#### <a name="migrate-packagesconfig-file"></a><span data-ttu-id="95dee-118">Esegui la migrazione del file Packages. config</span><span class="sxs-lookup"><span data-stu-id="95dee-118">Migrate packages.config file</span></span>

<span data-ttu-id="95dee-119">In un'applicazione .NET Framework tutti i riferimenti ai pacchetti esterni vengono dichiarati nel file *packages. config* .</span><span class="sxs-lookup"><span data-stu-id="95dee-119">In a .NET Framework application, all references to external packages are declared in the *packages.config* file.</span></span> <span data-ttu-id="95dee-120">In .NET Core non è più necessario usare il file *packages. config* .</span><span class="sxs-lookup"><span data-stu-id="95dee-120">In .NET Core, there's no longer the need to use the *packages.config* file.</span></span> <span data-ttu-id="95dee-121">Usare invece la proprietà [PackageReference](../../core/project-sdk/msbuild-props.md#packagereference) all'interno del file di progetto per specificare i pacchetti NuGet per l'app.</span><span class="sxs-lookup"><span data-stu-id="95dee-121">Instead, use the [PackageReference](../../core/project-sdk/msbuild-props.md#packagereference) property inside the project file to specify the NuGet packages for your app.</span></span>

<span data-ttu-id="95dee-122">Quindi, è necessario eseguire la transizione da un formato a un altro.</span><span class="sxs-lookup"><span data-stu-id="95dee-122">So, you need to transition from one format to another.</span></span> <span data-ttu-id="95dee-123">È possibile eseguire l'aggiornamento manualmente, prendendo le dipendenze contenute nel file *packages. config* e eseguendone la migrazione al file di progetto con il `PackageReference` formato.</span><span class="sxs-lookup"><span data-stu-id="95dee-123">You can do the update manually, taking the dependencies contained in the *packages.config* file and migrating them to the project file with the `PackageReference` format.</span></span> <span data-ttu-id="95dee-124">In alternativa, è possibile consentire a Visual Studio di eseguire il lavoro per l'utente: fare clic con il pulsante destro del mouse sul file *packages. config* e selezionare l'opzione **migrate Packages. config to PackageReference** .</span><span class="sxs-lookup"><span data-stu-id="95dee-124">Or, you can let Visual Studio do the work for you: right-click on the *packages.config* file and select the **Migrate packages.config to PackageReference** option.</span></span>

#### <a name="verify-every-dependency-compatibility-in-net-core"></a><span data-ttu-id="95dee-125">Verificare la compatibilità di tutte le dipendenze in .NET Core</span><span class="sxs-lookup"><span data-stu-id="95dee-125">Verify every dependency compatibility in .NET Core</span></span>

<span data-ttu-id="95dee-126">Dopo aver eseguito la migrazione dei riferimenti ai pacchetti, è necessario controllare la compatibilità di ogni riferimento.</span><span class="sxs-lookup"><span data-stu-id="95dee-126">Once you've migrated the package references, you must check each reference for compatibility.</span></span> <span data-ttu-id="95dee-127">È possibile esplorare le dipendenze di ogni pacchetto NuGet usato dall'applicazione in [NuGet.org](https://www.nuget.org/). Se il pacchetto ha .NET Standard dipendenze, funzionerà in .NET Core perché .NET Core 3,1 [supporta](../../standard/net-standard.md#net-implementation-support) tutte le versioni di .NET standard.</span><span class="sxs-lookup"><span data-stu-id="95dee-127">You can explore the dependencies of each NuGet package your application is using on [nuget.org](https://www.nuget.org/). If the package has .NET Standard dependencies, then it's going to work on .NET Core because .NET Core 3.1 [supports](../../standard/net-standard.md#net-implementation-support) all versions of .NET Standard.</span></span> <span data-ttu-id="95dee-128">Nell'immagine seguente vengono illustrate le dipendenze per il `Castle.Windsor` pacchetto:</span><span class="sxs-lookup"><span data-stu-id="95dee-128">The following image shows the dependencies for the `Castle.Windsor` package:</span></span>

![Screenshot delle dipendenze NuGet per il pacchetto Castle. Windsor](./media/example-migration-core/nuget-dependencies.png)

<span data-ttu-id="95dee-130">Per controllare la compatibilità dei pacchetti, è possibile utilizzare lo strumento <https://fuget.org> che offre informazioni più dettagliate sulle versioni e sulle dipendenze.</span><span class="sxs-lookup"><span data-stu-id="95dee-130">To check the package compatibility, you can use the tool <https://fuget.org> that offers a more detailed information about versions and dependencies.</span></span>

<span data-ttu-id="95dee-131">Forse il progetto fa riferimento a versioni precedenti del pacchetto che non supportano .NET Core, ma è possibile trovare versioni più recenti che lo supportano.</span><span class="sxs-lookup"><span data-stu-id="95dee-131">Maybe the project is referencing older package versions that don't support .NET Core, but you might find newer versions that do support it.</span></span> <span data-ttu-id="95dee-132">Pertanto, l'aggiornamento dei pacchetti a versioni più recenti è in genere una raccomandazione efficace.</span><span class="sxs-lookup"><span data-stu-id="95dee-132">So, updating packages to newer versions is generally a good recommendation.</span></span> <span data-ttu-id="95dee-133">Tuttavia, è necessario tenere presente che l'aggiornamento della versione del pacchetto può introdurre alcune modifiche di rilievo che forzano l'aggiornamento del codice.</span><span class="sxs-lookup"><span data-stu-id="95dee-133">However, you should consider that updating the package version can introduce some breaking changes that would force you to update your code.</span></span>

<span data-ttu-id="95dee-134">Cosa accade se non si trova una versione compatibile?</span><span class="sxs-lookup"><span data-stu-id="95dee-134">What happens if you don't find a compatible version?</span></span> <span data-ttu-id="95dee-135">Cosa accade se non si vuole aggiornare la versione di un pacchetto a causa di queste modifiche di rilievo?</span><span class="sxs-lookup"><span data-stu-id="95dee-135">What if you just don't want to update the version of a package because of these breaking changes?</span></span> <span data-ttu-id="95dee-136">Non preoccuparti perché è possibile dipendere da .NET Framework pacchetti da un'applicazione .NET Core.</span><span class="sxs-lookup"><span data-stu-id="95dee-136">Don't worry because it's possible to depend on .NET Framework packages from a .NET Core application.</span></span> <span data-ttu-id="95dee-137">Non dimenticare di testarlo ampiamente perché può causare errori di run-time se il pacchetto esterno chiama un'API che non è disponibile in .NET Core.</span><span class="sxs-lookup"><span data-stu-id="95dee-137">Don't forget to test it extensively because it can cause run-time errors if the external package calls an API that isn't available on .NET Core.</span></span> <span data-ttu-id="95dee-138">Questa operazione è molto importante quando si usa un pacchetto obsoleto che non verrà aggiornato ed è possibile semplicemente ridestinarlo per lavorare a .NET Core.</span><span class="sxs-lookup"><span data-stu-id="95dee-138">This is great for when you're using an old package that isn't going to be updated and you can just retarget to work on the .NET Core.</span></span>

#### <a name="check-for-api-compatibility"></a><span data-ttu-id="95dee-139">Verifica la compatibilità delle API</span><span class="sxs-lookup"><span data-stu-id="95dee-139">Check for API compatibility</span></span>

<span data-ttu-id="95dee-140">Poiché la superficie dell'API in .NET Framework e .NET Core è simile, ma non identica, è necessario verificare quali API sono disponibili in .NET Core e quali non lo sono.</span><span class="sxs-lookup"><span data-stu-id="95dee-140">Since the API surface in .NET Framework and .NET Core is similar but not identical, you must check which APIs are available on .NET Core and which aren't.</span></span> <span data-ttu-id="95dee-141">È possibile usare lo strumento .NET Portability Analyzer per visualizzare le API usate che non sono presenti in .NET Core.</span><span class="sxs-lookup"><span data-stu-id="95dee-141">You can use the .NET Portability Analyzer tool to surface APIs used that aren't present on .NET Core.</span></span> <span data-ttu-id="95dee-142">Esamina il livello binario dell'app, estrae tutte le API chiamate e quindi elenca le API non disponibili nel Framework di destinazione (in questo caso, .NET Core 3,1).</span><span class="sxs-lookup"><span data-stu-id="95dee-142">It looks at the binary level of your app, extracts all the APIs that are called, and then lists which APIs aren't available on your target framework (.NET Core 3.1 in this case).</span></span>

<span data-ttu-id="95dee-143">Per ulteriori informazioni su questo strumento, vedere:</span><span class="sxs-lookup"><span data-stu-id="95dee-143">You can find more information about this tool at:</span></span>

<https://docs.microsoft.com/dotnet/standard/analyzers/portability-analyzer>

<span data-ttu-id="95dee-144">Un aspetto interessante di questo strumento è costituito dal modo in cui vengono evidenziate solo le differenze dal codice e non dal codice dei pacchetti esterni, che non è possibile modificare.</span><span class="sxs-lookup"><span data-stu-id="95dee-144">An interesting aspect of this tool is that it only surfaces the differences from your own code and not code from external packages, which you can't change.</span></span> <span data-ttu-id="95dee-145">Tenere presente che la maggior parte di questi pacchetti è stata aggiornata per renderli compatibili con .NET Core.</span><span class="sxs-lookup"><span data-stu-id="95dee-145">Remember you should have updated most of these packages to make them work with .NET Core.</span></span>

### <a name="migrate-project-file"></a><span data-ttu-id="95dee-146">Esegui migrazione del file di progetto</span><span class="sxs-lookup"><span data-stu-id="95dee-146">Migrate project file</span></span>

#### <a name="create-the-new-net-core-project"></a><span data-ttu-id="95dee-147">Creare il nuovo progetto .NET Core</span><span class="sxs-lookup"><span data-stu-id="95dee-147">Create the new .NET Core project</span></span>

<span data-ttu-id="95dee-148">Nella maggior parte dei casi, è consigliabile aggiornare il progetto esistente al nuovo formato di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="95dee-148">In most of the cases, you'll want to update your existing project to the new .NET Core format.</span></span> <span data-ttu-id="95dee-149">Tuttavia, è anche possibile creare un nuovo progetto mantenendo quello precedente.</span><span class="sxs-lookup"><span data-stu-id="95dee-149">However, you can also create a new project while maintaining the old one.</span></span> <span data-ttu-id="95dee-150">Lo svantaggio principale dell'aggiornamento del vecchio progetto è la perdita del supporto della finestra di progettazione, che può rivelarsi importante.</span><span class="sxs-lookup"><span data-stu-id="95dee-150">The main drawback from updating the old project is that you lose designer support, which may be important for you.</span></span> <span data-ttu-id="95dee-151">Se si vuole proseguire con la finestra di progettazione, è necessario creare un nuovo progetto .NET Core in parallelo con quello precedente e condividere gli asset.</span><span class="sxs-lookup"><span data-stu-id="95dee-151">If you want to keep using the designer, you must create a new .NET Core project in parallel with the old one and share assets.</span></span> <span data-ttu-id="95dee-152">Se è necessario modificare gli elementi dell'interfaccia utente nella finestra di progettazione, è possibile passare al progetto precedente a tale scopo.</span><span class="sxs-lookup"><span data-stu-id="95dee-152">If you need to modify UI elements in the designer, you can switch to the old project to do that.</span></span> <span data-ttu-id="95dee-153">Poiché gli asset sono collegati, verranno aggiornati anche nel progetto .NET Core.</span><span class="sxs-lookup"><span data-stu-id="95dee-153">And since assets are linked, they'll be updated in the .NET Core project as well.</span></span>

<span data-ttu-id="95dee-154">Il [progetto di tipo SDK](../../core/project-sdk/msbuild-props.md) per .NET Core è molto più semplice del formato di progetto di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="95dee-154">The [SDK-style project](../../core/project-sdk/msbuild-props.md) for .NET Core is a lot simpler than .NET Framework's project format.</span></span> <span data-ttu-id="95dee-155">Oltre alle voci citate in precedenza `PackageReference` , non è necessario eseguire molte altre operazioni.</span><span class="sxs-lookup"><span data-stu-id="95dee-155">And apart from the previously mentioned `PackageReference` entries, you won't need to do much more.</span></span> <span data-ttu-id="95dee-156">Il nuovo formato di progetto include alcune estensioni [di file per impostazione predefinita](../../core/tools/csproj.md#default-compilation-includes-in-net-core-projects), ad esempio `.cs` `.xaml` i file e, senza la necessità di includerle in modo esplicito nel file di progetto.</span><span class="sxs-lookup"><span data-stu-id="95dee-156">The new project format includes certain file extensions [by default](../../core/tools/csproj.md#default-compilation-includes-in-net-core-projects), such as `.cs` and `.xaml` files, without the need to explicitly include them in the project file.</span></span>

#### <a name="assemblyinfo-considerations"></a><span data-ttu-id="95dee-157">Considerazioni su Assembly.info</span><span class="sxs-lookup"><span data-stu-id="95dee-157">Assembly.info considerations</span></span>

<span data-ttu-id="95dee-158">Gli attributi vengono generati automaticamente nei progetti .NET Core.</span><span class="sxs-lookup"><span data-stu-id="95dee-158">Attributes are autogenerated on .NET Core projects.</span></span> <span data-ttu-id="95dee-159">Se il progetto contiene un file *AssemblyInfo.cs* , le definizioni verranno duplicate, che causeranno conflitti di compilazione.</span><span class="sxs-lookup"><span data-stu-id="95dee-159">If the project contains an *AssemblyInfo.cs* file, the definitions will be duplicated, which will cause compilation conflicts.</span></span> <span data-ttu-id="95dee-160">È possibile eliminare il file *AssemblyInfo.cs* precedente o disabilitare la generazione di autogenerazione aggiungendo la voce seguente al file di progetto .NET Core:</span><span class="sxs-lookup"><span data-stu-id="95dee-160">You can delete the older *AssemblyInfo.cs* file or disable autogeneration by adding the following entry to the .NET Core project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">
  <PropertyGroup>
    <GenerateAssemblyInfo>false</GenerateAssemblyInfo>
  </PropertyGroup>
</Project>
```

#### <a name="resources"></a><span data-ttu-id="95dee-161">Risorse</span><span class="sxs-lookup"><span data-stu-id="95dee-161">Resources</span></span>

<span data-ttu-id="95dee-162">Le risorse incorporate sono incluse automaticamente, ma le risorse non sono, quindi è necessario eseguire la migrazione delle risorse nel nuovo file di progetto.</span><span class="sxs-lookup"><span data-stu-id="95dee-162">Embedded resources are included automatically but resources aren't, so you need to migrate the resources to the new project file.</span></span>

#### <a name="package-references"></a><span data-ttu-id="95dee-163">Riferimenti ai pacchetti</span><span class="sxs-lookup"><span data-stu-id="95dee-163">Package references</span></span>

<span data-ttu-id="95dee-164">Con l'opzione **migrate Packages. config to PackageReference** è possibile spostare facilmente i riferimenti al pacchetto esterno nel nuovo formato come indicato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="95dee-164">With the **Migrate packages.config to PackageReference** option, you can easily move your external package references to the new format as previously mentioned.</span></span>

#### <a name="update-package-references"></a><span data-ttu-id="95dee-165">Aggiornare i riferimenti del pacchetto</span><span class="sxs-lookup"><span data-stu-id="95dee-165">Update package references</span></span>

<span data-ttu-id="95dee-166">Aggiornare le versioni dei pacchetti risultanti compatibili, come illustrato nella sezione precedente.</span><span class="sxs-lookup"><span data-stu-id="95dee-166">Update the versions of the packages you've found to be compatible, as shown in the previous section.</span></span>

### <a name="fix-the-code-and-build"></a><span data-ttu-id="95dee-167">Correggere il codice e compilare</span><span class="sxs-lookup"><span data-stu-id="95dee-167">Fix the code and build</span></span>

#### <a name="microsoftwindowscompatibility"></a><span data-ttu-id="95dee-168">Microsoft. Windows. Compatibility</span><span class="sxs-lookup"><span data-stu-id="95dee-168">Microsoft.Windows.Compatibility</span></span>

<span data-ttu-id="95dee-169">Se l'applicazione dipende da API non disponibili in .NET Core, ad esempio registro di sistema, ACL o WCF, è necessario includere un riferimento al `Microsoft.Windows.Compatibility` pacchetto per aggiungere queste API specifiche di Windows.</span><span class="sxs-lookup"><span data-stu-id="95dee-169">If your application depends on APIs that aren't available on .NET Core, such as Registry, ACLs, or WCF, you have to include a reference to the `Microsoft.Windows.Compatibility` package to add these Windows-specific APIs.</span></span> <span data-ttu-id="95dee-170">Funzionano in .NET Core, ma non sono inclusi perché non sono multipiattaforma.</span><span class="sxs-lookup"><span data-stu-id="95dee-170">They work on .NET Core but aren't included as they aren't cross-platform.</span></span>

<span data-ttu-id="95dee-171">È disponibile uno strumento chiamato analizzatore API ( <https://docs.microsoft.com/dotnet/standard/analyzers/api-analyzer> ) che consente di identificare le API che non sono compatibili con il codice.</span><span class="sxs-lookup"><span data-stu-id="95dee-171">There's a tool called API Analyzer (<https://docs.microsoft.com/dotnet/standard/analyzers/api-analyzer>) that helps you identify APIs that aren't compatible with your code.</span></span>

#### <a name="use-if-directives"></a><span data-ttu-id="95dee-172">USA \# direttive if</span><span class="sxs-lookup"><span data-stu-id="95dee-172">Use \#if directives</span></span>

<span data-ttu-id="95dee-173">Se sono necessari percorsi di esecuzione diversi quando la destinazione è .NET Framework e .NET Core, è necessario usare le costanti di compilazione.</span><span class="sxs-lookup"><span data-stu-id="95dee-173">If you need different execution paths when targeting .NET Framework and .NET Core, you should use compilation constants.</span></span> <span data-ttu-id="95dee-174">Aggiungere alcune \# direttive if al codice per avere la stessa codebase per entrambe le destinazioni.</span><span class="sxs-lookup"><span data-stu-id="95dee-174">Add some \#if directives to your code to keep the same code base for both targets.</span></span>

#### <a name="technologies-not-available-on-net-core"></a><span data-ttu-id="95dee-175">Tecnologie non disponibili in .NET Core</span><span class="sxs-lookup"><span data-stu-id="95dee-175">Technologies not available on .NET Core</span></span>

<span data-ttu-id="95dee-176">Alcune tecnologie non sono disponibili in .NET Core, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="95dee-176">Some technologies aren't available on .NET Core, such as:</span></span>

* <span data-ttu-id="95dee-177">AppDomain</span><span class="sxs-lookup"><span data-stu-id="95dee-177">AppDomains</span></span>
* <span data-ttu-id="95dee-178">Comunicazione remota</span><span class="sxs-lookup"><span data-stu-id="95dee-178">Remoting</span></span>
* <span data-ttu-id="95dee-179">Sicurezza dall'accesso di codice</span><span class="sxs-lookup"><span data-stu-id="95dee-179">Code Access Security</span></span>
* <span data-ttu-id="95dee-180">Server WCF</span><span class="sxs-lookup"><span data-stu-id="95dee-180">WCF Server</span></span>
* <span data-ttu-id="95dee-181">Flusso di lavoro di Windows</span><span class="sxs-lookup"><span data-stu-id="95dee-181">Windows Workflow</span></span>

<span data-ttu-id="95dee-182">Per questo motivo è necessario trovare una sostituzione per queste tecnologie se vengono usate nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="95dee-182">That's why you need to find a replacement for these technologies if you're using them in your application.</span></span> <span data-ttu-id="95dee-183">Per ulteriori informazioni, vedere l'articolo relativo alle [tecnologie .NET Framework non disponibili in .NET Core](../../core/porting/net-framework-tech-unavailable.md) .</span><span class="sxs-lookup"><span data-stu-id="95dee-183">For more information, see the [.NET Framework technologies unavailable on .NET Core](../../core/porting/net-framework-tech-unavailable.md) article.</span></span>

#### <a name="regenerate-autogenerated-clients"></a><span data-ttu-id="95dee-184">Rigenera client generati automaticamente</span><span class="sxs-lookup"><span data-stu-id="95dee-184">Regenerate autogenerated clients</span></span>

<span data-ttu-id="95dee-185">Se l'applicazione usa codice generato automaticamente, ad esempio un client WCF, potrebbe essere necessario rigenerare questo codice per definire .NET Core come destinazione.</span><span class="sxs-lookup"><span data-stu-id="95dee-185">If your application uses autogenerated code, such as a WCF client, you may need to regenerate this code to target .NET Core.</span></span> <span data-ttu-id="95dee-186">In alcuni casi, è possibile trovare alcuni riferimenti mancanti poiché potrebbero non essere inclusi come parte del set di assembly .NET Core predefiniti.</span><span class="sxs-lookup"><span data-stu-id="95dee-186">Sometimes, you can find some missing references since they may not be included as part of the default .NET Core assemblies set.</span></span> <span data-ttu-id="95dee-187">Usando uno strumento come <https://apisof.net/> , è possibile individuare facilmente l'assembly in cui risiede il riferimento mancante e aggiungerlo da NuGet.</span><span class="sxs-lookup"><span data-stu-id="95dee-187">Using a tool like <https://apisof.net/>, you can easily locate the assembly the missing reference lives in and add it from NuGet.</span></span>

#### <a name="rolling-back-package-versions"></a><span data-ttu-id="95dee-188">Rollback delle versioni del pacchetto</span><span class="sxs-lookup"><span data-stu-id="95dee-188">Rolling back package versions</span></span>

<span data-ttu-id="95dee-189">Come regola generale, è stato precedentemente indicato che è consigliabile aggiornare ogni singola versione del pacchetto in modo che sia compatibile con .NET Core.</span><span class="sxs-lookup"><span data-stu-id="95dee-189">As a general rule, we've previously stated that you better update every single package version to be compatible with .NET Core.</span></span> <span data-ttu-id="95dee-190">Tuttavia, è possibile trovare che la destinazione di una versione aggiornata e compatibile di un assembly non viene addebitata.</span><span class="sxs-lookup"><span data-stu-id="95dee-190">However, you can find that targeting an updated and compatible version of an assembly just doesn't pay off.</span></span> <span data-ttu-id="95dee-191">Se il costo della modifica non è accettabile, è possibile prendere in considerazione la possibilità di eseguire il rollback delle versioni dei pacchetti mantenendo quelle utilizzate in .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="95dee-191">If the cost of change isn't acceptable, you can consider rolling back package versions keeping the ones you use on .NET Framework.</span></span> <span data-ttu-id="95dee-192">Sebbene non siano destinati a .NET Core, dovrebbero funzionare correttamente a meno che non chiamino alcune API non supportate.</span><span class="sxs-lookup"><span data-stu-id="95dee-192">Although they may not be targeting .NET Core, they should work well unless they call some unsupported APIs.</span></span>

### <a name="run-and-test"></a><span data-ttu-id="95dee-193">Esecuzione e test</span><span class="sxs-lookup"><span data-stu-id="95dee-193">Run and test</span></span>

<span data-ttu-id="95dee-194">Quando l'applicazione viene compilata senza errori, è possibile avviare l'ultimo passaggio della migrazione testando tutte le funzionalità.</span><span class="sxs-lookup"><span data-stu-id="95dee-194">Once you have your application building with no errors, you can start the last step of the migration by testing every functionality.</span></span>

<span data-ttu-id="95dee-195">In questo passaggio finale è possibile trovare diversi problemi a seconda della complessità dell'applicazione e delle dipendenze e delle API in uso.</span><span class="sxs-lookup"><span data-stu-id="95dee-195">In this final step, you can find several different issues depending on the complexity of your application and the dependencies and APIs you're using.</span></span>

<span data-ttu-id="95dee-196">Ad esempio, se si usano i file di configurazione (*app. config*), potrebbero verificarsi alcuni errori in fase di esecuzione, come le sezioni di configurazione non presenti.</span><span class="sxs-lookup"><span data-stu-id="95dee-196">For example, if you use configuration files (*app.config*), you may find some errors at run time like Configuration Sections not present.</span></span> <span data-ttu-id="95dee-197">Usare il `Microsoft.Extensions.Configuration` pacchetto NuGet per correggere l'errore.</span><span class="sxs-lookup"><span data-stu-id="95dee-197">Using the `Microsoft.Extensions.Configuration` NuGet package should fix that error.</span></span>

<span data-ttu-id="95dee-198">Un altro motivo per gli errori è l'uso `BeginInvoke` dei `EndInvoke` metodi e perché non sono supportati in .NET Core.</span><span class="sxs-lookup"><span data-stu-id="95dee-198">Another reason for errors is the use of the `BeginInvoke` and `EndInvoke` methods because they aren't supported on .NET Core.</span></span> <span data-ttu-id="95dee-199">Non sono supportati in .NET Core perché hanno una dipendenza dalla comunicazione remota, che non esiste in .NET Core.</span><span class="sxs-lookup"><span data-stu-id="95dee-199">They aren't supported on .NET Core because they have a dependency on Remoting, which doesn't exist on .NET Core.</span></span> <span data-ttu-id="95dee-200">Per risolvere questo problema, provare a usare la `await` parola chiave (se disponibile) o il <xref:System.Threading.Tasks.Task.Run%2A?displayProperty=nameWithType> metodo.</span><span class="sxs-lookup"><span data-stu-id="95dee-200">To solve this issue, try to use the `await` keyword (when available) or the <xref:System.Threading.Tasks.Task.Run%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="95dee-201">È possibile usare gli analizzatori di compatibilità per identificare API e modelli di codice nel codice che potrebbero causare problemi in fase di esecuzione con .NET Core.</span><span class="sxs-lookup"><span data-stu-id="95dee-201">You can use compatibility analyzers to let you identify APIs and code patterns in your code that can potentially cause problems at run time with .NET Core.</span></span> <span data-ttu-id="95dee-202">Passare a <https://github.com/dotnet/platform-compat> e usare l'analizzatore di API .NET nel progetto.</span><span class="sxs-lookup"><span data-stu-id="95dee-202">Go to <https://github.com/dotnet/platform-compat> and use the .NET API analyzer on your project.</span></span>

## <a name="migrating-a-windows-forms-application"></a><span data-ttu-id="95dee-203">Migrazione di un Windows Forms Application</span><span class="sxs-lookup"><span data-stu-id="95dee-203">Migrating a Windows Forms application</span></span>

<span data-ttu-id="95dee-204">Per presentare un processo completo di migrazione di una Windows Forms Application, è stato scelto di eseguire la migrazione dell'applicazione di esempio eShop disponibile all'indirizzo <https://github.com/dotnet-architecture/eShopModernizing/tree/master/eShopLegacyNTier/src/eShopWinForms> .</span><span class="sxs-lookup"><span data-stu-id="95dee-204">To showcase a complete migration process of a Windows Forms application, we've chosen to migrate the eShop sample application available at <https://github.com/dotnet-architecture/eShopModernizing/tree/master/eShopLegacyNTier/src/eShopWinForms>.</span></span> <span data-ttu-id="95dee-205">È possibile trovare il risultato completo della migrazione in <https://github.com/dotnet-architecture/eShopModernizing/tree/master/eShopModernizedNTier/src/eShopWinForms> .</span><span class="sxs-lookup"><span data-stu-id="95dee-205">You can find the complete result of the migration at <https://github.com/dotnet-architecture/eShopModernizing/tree/master/eShopModernizedNTier/src/eShopWinForms>.</span></span>

<span data-ttu-id="95dee-206">Questa applicazione mostra un catalogo di prodotti e consente all'utente di spostarsi, filtrare e cercare i prodotti.</span><span class="sxs-lookup"><span data-stu-id="95dee-206">This application shows a product catalog and allows the user to navigate, filter, and search for products.</span></span> <span data-ttu-id="95dee-207">Dal punto di vista dell'architettura, l'app si basa su un servizio WCF esterno che funge da facciata per un database back-end.</span><span class="sxs-lookup"><span data-stu-id="95dee-207">From an architecture point of view, the app relies on an external WCF service that serves as a façade to a back-end database.</span></span>

<span data-ttu-id="95dee-208">È possibile visualizzare la finestra principale dell'applicazione nell'immagine seguente:</span><span class="sxs-lookup"><span data-stu-id="95dee-208">You can see the main application window in the following picture:</span></span>

![Finestra principale dell'applicazione](./media/example-migration-core/main-application-window.png)

<span data-ttu-id="95dee-210">Se si apre il file di progetto con *estensione csproj* , è possibile visualizzare una schermata simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="95dee-210">If you open the *.csproj* project file, you can see something like this:</span></span>

![Screenshot del contenuto del file csproj](./media/example-migration-core/csproj-file.png)

<span data-ttu-id="95dee-212">Come indicato in precedenza, il progetto .NET Core ha uno stile più compatto ed è necessario eseguire la migrazione della struttura del progetto al nuovo stile .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="95dee-212">As previously mentioned, .NET Core project has a more compact style and you need to migrate the project structure to the new .NET Core SDK style.</span></span>

<span data-ttu-id="95dee-213">Nella Esplora soluzioni fare clic con il pulsante destro del mouse sul progetto Windows Forms e scegliere **Scarica**  >  **modifica**progetto.</span><span class="sxs-lookup"><span data-stu-id="95dee-213">In the Solution Explorer, right click on the Windows Forms project and select **Unload Project** > **Edit**.</span></span>

<span data-ttu-id="95dee-214">A questo punto è possibile aggiornare il file con estensione csproj.</span><span class="sxs-lookup"><span data-stu-id="95dee-214">Now you can update the .csproj file.</span></span> <span data-ttu-id="95dee-215">L'intero contenuto verrà eliminato e sostituito con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="95dee-215">You'll delete the entire content and replace it with the following code:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">
    <PropertyGroup>
        <OutputType>WinExe</OutputType>
        <TargetFramework>netcoreapp3.1</TargetFramework>
        <UseWindowsForms>true</UseWindowsForms>
        <GenerateAssemblyInfo>false</GenerateAssemblyInfo>
    </PropertyGroup>
</Project>
```

<span data-ttu-id="95dee-216">Salvare e ricaricare il progetto.</span><span class="sxs-lookup"><span data-stu-id="95dee-216">Save and reload the project.</span></span> <span data-ttu-id="95dee-217">A questo punto è stato completato l'aggiornamento del file di progetto e il progetto è destinato a .NET Core.</span><span class="sxs-lookup"><span data-stu-id="95dee-217">You're now done updating the project file and the project is targeting the .NET Core.</span></span>

<span data-ttu-id="95dee-218">Se si compila il progetto a questo punto, sono presenti alcuni errori correlati al riferimento al client WCF.</span><span class="sxs-lookup"><span data-stu-id="95dee-218">If you compile the project at this point, you'll find some errors related to the WCF client reference.</span></span> <span data-ttu-id="95dee-219">Poiché questo codice viene generato automaticamente, è necessario rigenerarlo per la destinazione di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="95dee-219">Since this code is autogenerated, you must regenerate it to target .NET Core.</span></span>

![Screenshot degli errori di compilazione in Visual Studio](./media/example-migration-core/winforms-compilation-errors.png)

<span data-ttu-id="95dee-221">Eliminare il file *Reference.cs* e generare un nuovo client del servizio.</span><span class="sxs-lookup"><span data-stu-id="95dee-221">Delete the *Reference.cs* file and generate a new Service Client.</span></span>

<span data-ttu-id="95dee-222">Fare clic con il pulsante destro del mouse su **servizi connessi** e selezionare l'opzione **Aggiungi servizio connesso** .</span><span class="sxs-lookup"><span data-stu-id="95dee-222">Right-click on **Connected Services** and select the **Add Connected Service** option.</span></span>

![Screenshot del menu Servizi connessi con l'opzione Aggiungi servizio connesso selezionata](./media/example-migration-core/add-connected-service.png)

<span data-ttu-id="95dee-224">Viene visualizzata la finestra Servizi connessi.</span><span class="sxs-lookup"><span data-stu-id="95dee-224">The Connected Services window opens.</span></span> <span data-ttu-id="95dee-225">Selezionare l'opzione **Microsoft WCF Web Service** .</span><span class="sxs-lookup"><span data-stu-id="95dee-225">Select the **Microsoft WCF Web Service** option.</span></span>

![Screenshot della finestra di Servizi connessi](./media/example-migration-core/connected-services-window.png)

<span data-ttu-id="95dee-227">Se il servizio WCF si trova nella stessa soluzione di questo esempio, è possibile selezionare l'opzione **Discover** invece di specificare un URL del servizio.</span><span class="sxs-lookup"><span data-stu-id="95dee-227">If you have the WCF Service in the same solution as we have in this example, you can select the **Discover** option instead of specifying a service URL.</span></span>

![Screenshot della finestra di riferimento per la configurazione del servizio Web WCF](./media/example-migration-core/configure-wcf-reference.png)

<span data-ttu-id="95dee-229">Una volta individuato il servizio, lo strumento riflette il contratto API implementato dal servizio.</span><span class="sxs-lookup"><span data-stu-id="95dee-229">Once the service is located, the tool reflects the API contract implemented by the service.</span></span> <span data-ttu-id="95dee-230">Modificare il nome dello spazio dei nomi in `eShopServiceReference` modo che sia come illustrato nell'immagine seguente:</span><span class="sxs-lookup"><span data-stu-id="95dee-230">Change the name of the namespace to be `eShopServiceReference` as shown in the following image:</span></span>

![Screenshot del contratto API e dello spazio dei nomi modificato](./media/example-migration-core/api-contract-namespace.png)

<span data-ttu-id="95dee-232">Selezionare il pulsante **fine** .</span><span class="sxs-lookup"><span data-stu-id="95dee-232">Select the **Finish** button.</span></span> <span data-ttu-id="95dee-233">Dopo un certo periodo di tempo, verrà visualizzato il codice generato.</span><span class="sxs-lookup"><span data-stu-id="95dee-233">After a while, you'll see the generated code.</span></span>

<span data-ttu-id="95dee-234">Verranno visualizzati tre file generati automaticamente:</span><span class="sxs-lookup"><span data-stu-id="95dee-234">You should see three autogenerated files:</span></span>

1. <span data-ttu-id="95dee-235">*Introduzione*: un collegamento a GitHub per fornire alcune informazioni su WCF.</span><span class="sxs-lookup"><span data-stu-id="95dee-235">*Getting Started*: a link to GitHub to provide some information on WCF.</span></span>
2. <span data-ttu-id="95dee-236">*ConnectedService. JSON*: parametri di configurazione per la connessione al servizio.</span><span class="sxs-lookup"><span data-stu-id="95dee-236">*ConnectedService.json*: configuration parameters to connect to the service.</span></span>
3. <span data-ttu-id="95dee-237">*Reference.cs*: codice client WCF effettivo.</span><span class="sxs-lookup"><span data-stu-id="95dee-237">*Reference.cs*: the actual WCF client code.</span></span>

![Screenshot della finestra di Esplora soluzioni con i tre file generati automaticamente](./media/example-migration-core/autogenerated-files.png)

<span data-ttu-id="95dee-239">Se si compila nuovamente, verranno visualizzati molti errori provenienti dai file con *estensione cs* all'interno della cartella *Helper* .</span><span class="sxs-lookup"><span data-stu-id="95dee-239">If you compile again, you'll see many errors coming from *.cs* files inside the *Helper* folder.</span></span> <span data-ttu-id="95dee-240">Questa cartella era presente nella versione .NET Framework ma non è inclusa nel vecchio *. csproj*.</span><span class="sxs-lookup"><span data-stu-id="95dee-240">This folder was present in the .NET Framework version but not included in the old *.csproj*.</span></span> <span data-ttu-id="95dee-241">Tuttavia, con il nuovo progetto in stile SDK, ogni file di codice presente sotto il percorso del file di progetto è incluso per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="95dee-241">But with the new SDK-style project, every code file present underneath the project file location is included by default.</span></span> <span data-ttu-id="95dee-242">Ovvero il nuovo progetto .NET Core tenta di compilare i file all'interno della cartella *Helper* .</span><span class="sxs-lookup"><span data-stu-id="95dee-242">That is, the new .NET Core project tries to compile the files inside the *Helper* folder.</span></span> <span data-ttu-id="95dee-243">Poiché tale cartella non è necessaria, è possibile eliminarla in modo sicuro.</span><span class="sxs-lookup"><span data-stu-id="95dee-243">Since that folder isn't needed, you can safely delete it.</span></span>

<span data-ttu-id="95dee-244">Se si compila di nuovo il progetto e lo si esegue, non verranno visualizzate le immagini del prodotto.</span><span class="sxs-lookup"><span data-stu-id="95dee-244">If you compile the project again and execute it, you won't see the product images.</span></span> <span data-ttu-id="95dee-245">Il problema è che ora il percorso dei file è leggermente modificato.</span><span class="sxs-lookup"><span data-stu-id="95dee-245">The problem is that now the path to the files has slightly changed.</span></span> <span data-ttu-id="95dee-246">Per risolvere questo problema, è necessario aggiungere un altro livello di profondità nel percorso, aggiornando nel file `CatalogView.cs` la riga:</span><span class="sxs-lookup"><span data-stu-id="95dee-246">To fix this issue, you need to add another level of depth in the path, updating in the file `CatalogView.cs` the line:</span></span>

```csharp
string image_name = Environment.CurrentDirectory + "\\..\\..\\Assets\\Images\\Catalog\\" + catalogItems.Picturefilename;
```

<span data-ttu-id="95dee-247">to</span><span class="sxs-lookup"><span data-stu-id="95dee-247">to</span></span>

```csharp
string image_name = Environment.CurrentDirectory + "\\..\\..\\..\\Assets\\Images\\Catalog\\" + catalogItems.Picturefilename;
```

<span data-ttu-id="95dee-248">Dopo questa modifica, è possibile verificare che l'applicazione venga avviata e venga eseguita come previsto in .NET Core.</span><span class="sxs-lookup"><span data-stu-id="95dee-248">After this change, you can check that the application launches and runs as expected on .NET Core.</span></span>

## <a name="migrating-a-wpf-application"></a><span data-ttu-id="95dee-249">Migrazione di un'applicazione WPF</span><span class="sxs-lookup"><span data-stu-id="95dee-249">Migrating a WPF application</span></span>

<span data-ttu-id="95dee-250">`Shop.ClassicWPF`Per eseguire la migrazione verrà utilizzata l'applicazione di esempio.</span><span class="sxs-lookup"><span data-stu-id="95dee-250">We'll use the `Shop.ClassicWPF` sample application to perform the migration.</span></span> <span data-ttu-id="95dee-251">La figura seguente mostra una schermata dell'app prima della migrazione:</span><span class="sxs-lookup"><span data-stu-id="95dee-251">The following image shows a screenshot of the app before migration:</span></span>

![App di esempio prima della migrazione](./media/example-migration-core/app-before-migration.png)

<span data-ttu-id="95dee-253">Questa applicazione usa un database di SQL Server Express locale per conservare le informazioni sul catalogo di prodotti.</span><span class="sxs-lookup"><span data-stu-id="95dee-253">This application uses a local SQL Server Express database to hold the product catalog information.</span></span> <span data-ttu-id="95dee-254">È possibile accedere a questo database direttamente dall'applicazione WPF.</span><span class="sxs-lookup"><span data-stu-id="95dee-254">This database is accessed directly from the WPF application.</span></span>

<span data-ttu-id="95dee-255">In primo luogo, è necessario aggiornare il file con *estensione csproj* al nuovo stile SDK usato dalle applicazioni .NET Core.</span><span class="sxs-lookup"><span data-stu-id="95dee-255">First, you must update the *.csproj* file to the new SDK style used by .NET Core applications.</span></span> <span data-ttu-id="95dee-256">Si seguiranno gli stessi passaggi descritti nella migrazione del Windows Forms: si scaricherà il progetto, si aprirà il file con *estensione csproj* , ne aggiornerà il contenuto e si ricaricherà il progetto.</span><span class="sxs-lookup"><span data-stu-id="95dee-256">You'll follow the same steps described in the Windows Forms migration: you'll unload the project, open the *.csproj* file, update its contents, and reload the project.</span></span>

<span data-ttu-id="95dee-257">In tal caso, eliminare tutto il contenuto del file con *estensione csproj* e sostituirlo con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="95dee-257">In this case, delete all the content of the *.csproj* file and replace it with the following code:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">
    <PropertyGroup>
        <OutputType>WinExe</OutputType>
        <TargetFramework>netcoreapp3.1</TargetFramework>
        <UseWPF>true</UseWPF>
        <GenerateAssemblyInfo>false</GenerateAssemblyInfo>
    </PropertyGroup>
</Project>
```

<span data-ttu-id="95dee-258">Se si ricarica il progetto e lo si compila, si otterrà l'errore seguente:</span><span class="sxs-lookup"><span data-stu-id="95dee-258">If you reload the project and compile it, you'll get the following error:</span></span>

![Screenshot degli errori di compilazione in Visual Studio](./media/example-migration-core/wpf-compilation-error.png)

<span data-ttu-id="95dee-260">Poiché è stato eliminato tutto il contenuto *. csproj* , è stata persa una specifica del riferimento al progetto presente nel vecchio progetto.</span><span class="sxs-lookup"><span data-stu-id="95dee-260">Since you've deleted all the *.csproj* contents, you've lost a project reference specification present in the old project.</span></span> <span data-ttu-id="95dee-261">È sufficiente aggiungere questa riga al file con *estensione csproj* per includere il riferimento al progetto:</span><span class="sxs-lookup"><span data-stu-id="95dee-261">You just need to add this line to the *.csproj* file to include the project reference back:</span></span>

```xml
<ItemGroup>
    <ProjectReference Include="..\\eShop.SqlProvider\\eShop.SqlProvider.csproj" />
<ItemGroup>
```

<span data-ttu-id="95dee-262">È anche possibile consentire a Visual Studio di aiutarti facendo clic con il pulsante destro del mouse sul nodo **dipendenze** e scegliendo **Aggiungi riferimento al progetto**.</span><span class="sxs-lookup"><span data-stu-id="95dee-262">You can also let Visual Studio help you by right-clicking on the **Dependencies** node and selecting **Add Project Reference**.</span></span> <span data-ttu-id="95dee-263">Selezionare il progetto dalla soluzione e fare clic su **OK**:</span><span class="sxs-lookup"><span data-stu-id="95dee-263">Select the project from the solution and click **OK**:</span></span>

![Screenshot della finestra di dialogo Gestione riferimenti con il progetto eShop. sqlfornir selezionato](./media/example-migration-core/reference-manager.png)

<span data-ttu-id="95dee-265">Una volta aggiunto il riferimento a progetto mancante, l'applicazione viene compilata ed eseguita come previsto in .NET Core.</span><span class="sxs-lookup"><span data-stu-id="95dee-265">Once you add the missing project reference, the application compiles and runs as expected on .NET Core.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="95dee-266">[Precedente](windows-migration.md) 
> [Avanti](deploy-modern-applications.md)</span><span class="sxs-lookup"><span data-stu-id="95dee-266">[Previous](windows-migration.md)
[Next](deploy-modern-applications.md)</span></span>
