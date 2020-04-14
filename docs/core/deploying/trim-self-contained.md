---
title: Tagliare le applicazioni autonome
description: Scopri come tagliare le app autonome per ridurne le dimensioni. .NET Core raggruppa il runtime con un'app pubblicata in modo autonomo e in genere include più tempo di runtime.
author: jamshedd
ms.author: jamshedd
ms.date: 04/03/2020
ms.openlocfilehash: bb8ac88c5e16b7fd20a7670e4ad76dbe4b44da1b
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2020
ms.locfileid: "81242912"
---
# <a name="trim-self-contained-deployments-and-executables"></a><span data-ttu-id="5b3ad-104">Trimming delle distribuzioni autonome e degli eseguibili</span><span class="sxs-lookup"><span data-stu-id="5b3ad-104">Trim self-contained deployments and executables</span></span>

<span data-ttu-id="5b3ad-105">Quando si pubblica un'applicazione autonoma, il runtime di .NET Core viene fornito insieme all'applicazione.</span><span class="sxs-lookup"><span data-stu-id="5b3ad-105">When publishing an application self-contained, the .NET Core runtime is bundled together with the application.</span></span> <span data-ttu-id="5b3ad-106">Questo raggruppamento aggiunge una quantità significativa di contenuto all'applicazione in pacchetto.</span><span class="sxs-lookup"><span data-stu-id="5b3ad-106">This bundling adds a significant amount of content to your packaged application.</span></span> <span data-ttu-id="5b3ad-107">Quando si tratta di distribuire l'applicazione, le dimensioni sono spesso un fattore importante.</span><span class="sxs-lookup"><span data-stu-id="5b3ad-107">When it comes to deploying your application, size is often an important factor.</span></span> <span data-ttu-id="5b3ad-108">Mantenere le dimensioni dell'applicazione del pacchetto il più piccolo possibile è in genere un obiettivo per gli sviluppatori di applicazioni.</span><span class="sxs-lookup"><span data-stu-id="5b3ad-108">Keeping the size of the package application as small as possible is typically a goal for application developers.</span></span>

<span data-ttu-id="5b3ad-109">A seconda della complessità dell'applicazione, è necessario solo un sottoinsieme del runtime per eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="5b3ad-109">Depending on the complexity of the application, only a subset of the runtime is required to run the application.</span></span> <span data-ttu-id="5b3ad-110">Queste parti inutilizzate del runtime non sono necessarie e possono essere tagliate dall'applicazione in pacchetto.</span><span class="sxs-lookup"><span data-stu-id="5b3ad-110">These unused parts of the runtime are unnecessary and can be trimmed from the packaged application.</span></span>

<span data-ttu-id="5b3ad-111">La funzionalità di taglio funziona esaminando i file binari dell'applicazione per individuare e compilare un grafico degli assembly di runtime necessari.</span><span class="sxs-lookup"><span data-stu-id="5b3ad-111">The trimming feature works by examining the application binaries to discover and build a graph of the required runtime assemblies.</span></span> <span data-ttu-id="5b3ad-112">Gli assembly di runtime rimanenti a cui non viene fatto riferimento sono esclusi.</span><span class="sxs-lookup"><span data-stu-id="5b3ad-112">The remaining runtime assemblies that aren't referenced are excluded.</span></span>

> [!NOTE]
> <span data-ttu-id="5b3ad-113">Il taglio è una funzionalità sperimentale in .NET Core 3.1 ed è disponibile _solo_ per le applicazioni pubblicate autonome.</span><span class="sxs-lookup"><span data-stu-id="5b3ad-113">Trimming is an experimental feature in .NET Core 3.1 and is _only_ available to applications that are published self-contained.</span></span>

## <a name="prevent-assemblies-from-being-trimmed"></a><span data-ttu-id="5b3ad-114">Impedire la rifila degli assiemi</span><span class="sxs-lookup"><span data-stu-id="5b3ad-114">Prevent assemblies from being trimmed</span></span>

<span data-ttu-id="5b3ad-115">Esistono scenari in cui la funzionalità di taglio non riuscirà a rilevare i riferimenti.</span><span class="sxs-lookup"><span data-stu-id="5b3ad-115">There are scenarios in which the trimming functionality will fail to detect references.</span></span> <span data-ttu-id="5b3ad-116">Ad esempio, quando la reflection viene utilizzata in un assembly di runtime, dall'applicazione o da una libreria a cui fa riferimento l'applicazione, all'assembly non viene fatto riferimento direttamente.</span><span class="sxs-lookup"><span data-stu-id="5b3ad-116">For example, when reflection is used on a runtime assembly, either by your application or a library that is referenced by your application, the assembly isn't directly referenced.</span></span> <span data-ttu-id="5b3ad-117">Il taglio non è a conoscenza di questi riferimenti indiretti ed escludela dalla cartella pubblicata.</span><span class="sxs-lookup"><span data-stu-id="5b3ad-117">Trimming is unaware of these indirect references and would exclude the library from the published folder.</span></span>

<span data-ttu-id="5b3ad-118">Quando il codice fa riferimento indirettamente a un assembly tramite reflection, `<TrimmerRootAssembly>` è possibile impedire che l'assembly venga tagliato con l'impostazione.</span><span class="sxs-lookup"><span data-stu-id="5b3ad-118">When the code is indirectly referencing an assembly through reflection, you can prevent the assembly from being trimmed with the `<TrimmerRootAssembly>` setting.</span></span> <span data-ttu-id="5b3ad-119">Nell'esempio seguente viene illustrato `System.Security` come impedire che un assieme denominato assembly venga tagliato:</span><span class="sxs-lookup"><span data-stu-id="5b3ad-119">The following example shows how to prevent an assembly called `System.Security` assembly from being trimmed:</span></span>

```xml
<ItemGroup>
    <TrimmerRootAssembly Include="System.Security" />
</ItemGroup>
```

## <a name="trim-your-app---cli"></a><span data-ttu-id="5b3ad-120">Tagliare l'app - CLI</span><span class="sxs-lookup"><span data-stu-id="5b3ad-120">Trim your app - CLI</span></span>

<span data-ttu-id="5b3ad-121">Tagliare l'applicazione utilizzando il comando [dotnet publish.](../tools/dotnet-publish.md)</span><span class="sxs-lookup"><span data-stu-id="5b3ad-121">Trim your application using the [dotnet publish](../tools/dotnet-publish.md) command.</span></span> <span data-ttu-id="5b3ad-122">Quando pubblichi l'app, imposta le tre impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5b3ad-122">When you publish your app, set the following three settings:</span></span>

- <span data-ttu-id="5b3ad-123">Pubblica come autonomo:`--self-contained true`</span><span class="sxs-lookup"><span data-stu-id="5b3ad-123">Publish as self-contained: `--self-contained true`</span></span>
- <span data-ttu-id="5b3ad-124">Disabilitare la pubblicazione su file singolo:`-p:PublishSingleFile=false`</span><span class="sxs-lookup"><span data-stu-id="5b3ad-124">Disable single-file publishing: `-p:PublishSingleFile=false`</span></span>
- <span data-ttu-id="5b3ad-125">Abilita taglio:`p:PublishTrimmed=true`</span><span class="sxs-lookup"><span data-stu-id="5b3ad-125">Enable trimming: `p:PublishTrimmed=true`</span></span>

<span data-ttu-id="5b3ad-126">L'esempio seguente pubblica un'app per Windows 10 come autonoma e taglia l'output.</span><span class="sxs-lookup"><span data-stu-id="5b3ad-126">The following example publishes an app for Windows 10 as self-contained and trims the output.</span></span>

```dotnetcli
dotnet publish -c Release -r win10-x64 --self-contained true -p:PublishSingleFile=false -p:PublishTrimmed=true
```

<span data-ttu-id="5b3ad-127">Per altre informazioni, vedere [Pubblicare app .NET Core con l'interfaccia della riga di comando di .NET Core .NET .](deploy-with-cli.md)</span><span class="sxs-lookup"><span data-stu-id="5b3ad-127">For more information, see [Publish .NET Core apps with .NET Core CLI](deploy-with-cli.md).</span></span>

## <a name="trim-your-app---visual-studio"></a><span data-ttu-id="5b3ad-128">Tagliare il taglio dell'app - Visual Studio</span><span class="sxs-lookup"><span data-stu-id="5b3ad-128">Trim your app - Visual Studio</span></span>

<span data-ttu-id="5b3ad-129">Visual Studio crea profili di pubblicazione riutilizzabili che controllano la modalità di pubblicazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="5b3ad-129">Visual Studio creates reusable publishing profiles that control how your application is published.</span></span>

01. <span data-ttu-id="5b3ad-130">Nel riquadro **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto che si desidera pubblicare.</span><span class="sxs-lookup"><span data-stu-id="5b3ad-130">On the **Solution Explorer** pane, right-click on the project you want to publish.</span></span> <span data-ttu-id="5b3ad-131">Selezionare **Pubblica...**.</span><span class="sxs-lookup"><span data-stu-id="5b3ad-131">Select **Publish...**.</span></span>

    :::image type="content" source="media/trim-self-contained/visual-studio-solution-explorer.png" alt-text="Esplora soluzioni con un menu di scelta rapida che evidenzia l'opzione Pubblica.Solution Explorer with a right-click menu highlighting the Publish option.":::

    <span data-ttu-id="5b3ad-133">Se non si dispone già di un profilo di pubblicazione, seguire le istruzioni per crearne uno e scegliere il tipo di destinazione **Cartella.**</span><span class="sxs-lookup"><span data-stu-id="5b3ad-133">If you don't already have a publishing profile, follow the instructions to create one and choose the **Folder** target-type.</span></span>

01. <span data-ttu-id="5b3ad-134">Scegliere **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="5b3ad-134">Choose **Edit**.</span></span>

    :::image type="content" source="media/trim-self-contained/visual-studio-publish-edit-settings.png" alt-text="Profilo di pubblicazione di Visual Studio con pulsante Modifica.":::

01. <span data-ttu-id="5b3ad-136">Nella finestra di dialogo **Impostazioni profilo,** impostare le seguenti opzioni:</span><span class="sxs-lookup"><span data-stu-id="5b3ad-136">In the **Profile settings** dialog, set the following options:</span></span>

    - <span data-ttu-id="5b3ad-137">Impostare **Modalità di distribuzione** su **Self-contained**.</span><span class="sxs-lookup"><span data-stu-id="5b3ad-137">Set **Deployment mode** to **Self-contained**.</span></span>
    - <span data-ttu-id="5b3ad-138">Impostare Runtime di **destinazione** sulla piattaforma in cui si desidera eseguire la pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="5b3ad-138">Set **Target runtime** to the platform you want to publish to.</span></span>
    - <span data-ttu-id="5b3ad-139">Selezionare **Taglia assiemi inutilizzati (in anteprima)**.</span><span class="sxs-lookup"><span data-stu-id="5b3ad-139">Select **Trim unused assemblies (in preview)**.</span></span>

    <span data-ttu-id="5b3ad-140">Scegliere **Salva** per salvare le impostazioni e tornare alla finestra di dialogo **Pubblica.**</span><span class="sxs-lookup"><span data-stu-id="5b3ad-140">Choose **Save** to save the settings and return to the **Publish** dialog.</span></span>

    :::image type="content" source="media/trim-self-contained/visual-studio-publish-properties.png" alt-text="Finestra di dialogo Impostazioni profilo con la modalità di distribuzione, il runtime di destinazione e le opzioni di taglio degli assiemi inutilizzati evidenziate.":::

01. <span data-ttu-id="5b3ad-142">Scegliere **Pubblica** per pubblicare l'app tagliata.</span><span class="sxs-lookup"><span data-stu-id="5b3ad-142">Choose **Publish** to publish your app trimmed.</span></span>

<span data-ttu-id="5b3ad-143">Per ulteriori informazioni, consultate [Pubblicare app .NET Core con Visual Studio.](deploy-with-vs.md)</span><span class="sxs-lookup"><span data-stu-id="5b3ad-143">For more information, see [Publish .NET Core apps with Visual Studio](deploy-with-vs.md).</span></span>

## <a name="trim-your-app---visual-studio-for-mac"></a><span data-ttu-id="5b3ad-144">Tagliare il taglio dell'app - Visual Studio per Mac</span><span class="sxs-lookup"><span data-stu-id="5b3ad-144">Trim your app - Visual Studio for Mac</span></span>

<span data-ttu-id="5b3ad-145">Visual Studio per Mac non fornisce opzioni per tagliare l'app durante la pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="5b3ad-145">Visual Studio for Mac doesn't provide options to trim your app during publish.</span></span> <span data-ttu-id="5b3ad-146">Dovrai pubblicare manualmente seguendo le istruzioni della sezione [Tagliare l'app - CLI.](#trim-your-app---cli)</span><span class="sxs-lookup"><span data-stu-id="5b3ad-146">You'll need to publish manually by following the instructions from the [Trim your app - CLI](#trim-your-app---cli) section.</span></span> <span data-ttu-id="5b3ad-147">Per altre informazioni, vedere [Pubblicare app .NET Core con l'interfaccia della riga di comando di .NET Core .NET .](deploy-with-cli.md)</span><span class="sxs-lookup"><span data-stu-id="5b3ad-147">For more information, see [Publish .NET Core apps with .NET Core CLI](deploy-with-cli.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="5b3ad-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5b3ad-148">See also</span></span>

- <span data-ttu-id="5b3ad-149">[Distribuzione dell'applicazione .NET Core](index.md).</span><span class="sxs-lookup"><span data-stu-id="5b3ad-149">[.NET Core application deployment](index.md).</span></span>
- <span data-ttu-id="5b3ad-150">[Pubblicare app .NET Core con l'interfaccia della riga di comando di .NET Core.](deploy-with-cli.md)</span><span class="sxs-lookup"><span data-stu-id="5b3ad-150">[Publish .NET Core apps with .NET Core CLI](deploy-with-cli.md).</span></span>
- <span data-ttu-id="5b3ad-151">[Pubblicare app .NET Core con Visual Studio](deploy-with-vs.md).</span><span class="sxs-lookup"><span data-stu-id="5b3ad-151">[Publish .NET Core apps with Visual Studio](deploy-with-vs.md).</span></span>
- <span data-ttu-id="5b3ad-152">[dotnet comando di pubblicazione](../tools/dotnet-publish.md).</span><span class="sxs-lookup"><span data-stu-id="5b3ad-152">[dotnet publish command](../tools/dotnet-publish.md).</span></span>
