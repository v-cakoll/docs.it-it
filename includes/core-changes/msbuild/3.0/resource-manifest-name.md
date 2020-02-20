---
ms.openlocfilehash: 276268d31670b5e7dcd0ae9c0b7a61c3c38ca663
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "77451889"
---
### <a name="resource-manifest-file-names"></a><span data-ttu-id="0cc7a-101">Nomi file manifesto delle risorse</span><span class="sxs-lookup"><span data-stu-id="0cc7a-101">Resource manifest file names</span></span>

<span data-ttu-id="0cc7a-102">A partire da .NET Core 3,0, il nome del file manifesto della risorsa generato è stato modificato.</span><span class="sxs-lookup"><span data-stu-id="0cc7a-102">Starting in .NET Core 3.0, the generated resource manifest file name has changed.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="0cc7a-103">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="0cc7a-103">Version introduced</span></span>

<span data-ttu-id="0cc7a-104">3.0</span><span class="sxs-lookup"><span data-stu-id="0cc7a-104">3.0</span></span>

#### <a name="change-description"></a><span data-ttu-id="0cc7a-105">Descrizione della modifica</span><span class="sxs-lookup"><span data-stu-id="0cc7a-105">Change description</span></span>

<span data-ttu-id="0cc7a-106">Prima di .NET Core 3,0, quando venivano impostati i metadati [DependentUpon](/visualstudio/msbuild/common-msbuild-project-items#compile) per un file di risorse (*resx*) nel file di progetto MSBuild, il nome del manifesto generato era *Namespace. nomeclasse. resources*.</span><span class="sxs-lookup"><span data-stu-id="0cc7a-106">Prior to .NET Core 3.0, when [DependentUpon](/visualstudio/msbuild/common-msbuild-project-items#compile) metadata was set for a resource (*.resx*) file in the MSBuild project file, the generated manifest name was *Namespace.Classname.resources*.</span></span> <span data-ttu-id="0cc7a-107">Quando [DependentUpon](/visualstudio/msbuild/common-msbuild-project-items#compile) non è stato impostato, il nome del manifesto generato è *Namespace. nomeclasse. FolderPathRelativeToRoot. culture. resources*.</span><span class="sxs-lookup"><span data-stu-id="0cc7a-107">When [DependentUpon](/visualstudio/msbuild/common-msbuild-project-items#compile) was not set, the generated manifest name was *Namespace.Classname.FolderPathRelativeToRoot.Culture.resources*.</span></span>

<span data-ttu-id="0cc7a-108">A partire da .NET Core 3,0, quando un file con *estensione resx* è condiviso con un file di origine con lo stesso nome, ad esempio in Windows Forms app, il nome del manifesto della risorsa viene generato dal nome completo del primo tipo nel file di origine.</span><span class="sxs-lookup"><span data-stu-id="0cc7a-108">Starting in .NET Core 3.0, when a *.resx* file is colocated with a source file of the same name, for example, in Windows Forms apps, the resource manifest name is generated from the full name of the first type in the source file.</span></span> <span data-ttu-id="0cc7a-109">Se, ad esempio, *Type.cs* è condiviso con *Type. resx*, il nome del manifesto generato è *Namespace. nomeclasse. resources*.</span><span class="sxs-lookup"><span data-stu-id="0cc7a-109">For example, if *Type.cs* is colocated with *Type.resx*, the generated manifest name is *Namespace.Classname.resources*.</span></span> <span data-ttu-id="0cc7a-110">Tuttavia, se si modifica uno degli attributi della proprietà `EmbeddedResource` per il file con *estensione resx* , il nome del file manifesto generato potrebbe essere diverso:</span><span class="sxs-lookup"><span data-stu-id="0cc7a-110">However, if you modify any of the attributes on the `EmbeddedResource` property for the *.resx* file, the generated manifest file name may be different:</span></span>

- <span data-ttu-id="0cc7a-111">Se viene impostato l'attributo `LogicalName` della proprietà `EmbeddedResource`, tale valore viene usato come nome del file manifesto della risorsa.</span><span class="sxs-lookup"><span data-stu-id="0cc7a-111">If the `LogicalName` attribute on the `EmbeddedResource` property is set, that value is used as the resource manifest file name.</span></span>

  <span data-ttu-id="0cc7a-112">Esempi:</span><span class="sxs-lookup"><span data-stu-id="0cc7a-112">Examples:</span></span>

  ```xml
  <EmbeddedResource Include="X.resx" LogicalName="SomeName.resources" />
  -or-
  <EmbeddedResource Include="X.fr-FR.resx" LogicalName="SomeName.resources" />
  ```

  <span data-ttu-id="0cc7a-113">**Nome file manifesto risorsa generato**: *somename. resources* (indipendentemente dal nome del file con *estensione resx* o dalle impostazioni cultura o da altri metadati).</span><span class="sxs-lookup"><span data-stu-id="0cc7a-113">**Generated resource manifest file name**: *SomeName.resources* (regardless of the *.resx* file name or culture or any other metadata).</span></span>

- <span data-ttu-id="0cc7a-114">Se `LogicalName` non è impostato, ma viene impostato l'attributo `ManifestResourceName` nella proprietà `EmbeddedResource`, il relativo valore, combinato con l'estensione di file *. resources*, viene usato come nome file del manifesto della risorsa.</span><span class="sxs-lookup"><span data-stu-id="0cc7a-114">If `LogicalName` is not set, but the `ManifestResourceName` attribute on the `EmbeddedResource` property is set, its value, combined with the file extension *.resources*, is used as the resource manifest file name.</span></span>

  <span data-ttu-id="0cc7a-115">Esempi:</span><span class="sxs-lookup"><span data-stu-id="0cc7a-115">Examples:</span></span>

  ```xml
  <EmbeddedResource Include="X.resx" ManifestResourceName="SomeName" />
  -or-
  <EmbeddedResource Include="X.fr-FR.resx" ManifestResourceName="SomeName.fr-FR" />
  ```

  <span data-ttu-id="0cc7a-116">**Nome file manifesto risorsa generato**: *somename. resources* o *somename.fr-fr. resources*.</span><span class="sxs-lookup"><span data-stu-id="0cc7a-116">**Generated resource manifest file name**: *SomeName.resources* or *SomeName.fr-FR.resources*.</span></span>

- <span data-ttu-id="0cc7a-117">Se non si applicano le regole precedenti e l'attributo `DependentUpon` sull'elemento `EmbeddedResource` è impostato su un file di origine, nel nome del file manifesto della risorsa viene usato il nome del tipo della prima classe nel file di origine.</span><span class="sxs-lookup"><span data-stu-id="0cc7a-117">If the previous rules don't apply, and the `DependentUpon` attribute on the `EmbeddedResource` element is set to a source file, the type name of the first class in the source file is used in the resource manifest file name.</span></span> <span data-ttu-id="0cc7a-118">In particolare, il nome del file generato è *Namespace. nomeclasse\[. Impostazioni cultura]. resources*.</span><span class="sxs-lookup"><span data-stu-id="0cc7a-118">More specifically, the generated file name is *Namespace.Classname\[.Culture].resources*.</span></span>

  <span data-ttu-id="0cc7a-119">Esempi:</span><span class="sxs-lookup"><span data-stu-id="0cc7a-119">Examples:</span></span>

  ```xml
  <EmbeddedResource Include="X.resx" DependentUpon="MyTypes.cs">
  -or-
  <EmbeddedResource Include="X.fr-FR.resx" DependentUpon="MyTypes.cs">
  ```

  <span data-ttu-id="0cc7a-120">**Nome file manifesto risorsa generato**: *Namespace. nomeclasse. resources* o *Namespace.ClassName.fr-fr. resources* (dove `Namespace.Classname` è il nome della prima classe in *myTypes.cs*).</span><span class="sxs-lookup"><span data-stu-id="0cc7a-120">**Generated resource manifest file name**: *Namespace.Classname.resources* or *Namespace.Classname.fr-FR.resources* (where `Namespace.Classname` is the name of the first class in *MyTypes.cs*).</span></span>

- <span data-ttu-id="0cc7a-121">Se non si applicano le regole precedenti, `EmbeddedResourceUseDependentUponConvention` è `true` (impostazione predefinita per .NET Core) ed è presente un file di origine con un file con estensione *resx* con lo stesso nome file di base, il file con *estensione resx* viene reso dipendente dal file di origine corrispondente e il nome generato è identico a quello della regola precedente.</span><span class="sxs-lookup"><span data-stu-id="0cc7a-121">If the previous rules don't apply, `EmbeddedResourceUseDependentUponConvention` is `true` (the default for .NET Core), and there's a source file colocated with a *.resx* file that has the same base file name, the *.resx* file is made dependent upon the matching source file, and the generated name is the same as in the previous rule.</span></span> <span data-ttu-id="0cc7a-122">Si tratta della regola "impostazioni predefinite" per i progetti .NET Core.</span><span class="sxs-lookup"><span data-stu-id="0cc7a-122">This is the "default settings" rule for .NET Core projects.</span></span>
  
  <span data-ttu-id="0cc7a-123">Esempi:</span><span class="sxs-lookup"><span data-stu-id="0cc7a-123">Examples:</span></span>
  
  <span data-ttu-id="0cc7a-124">I file *myTypes.cs* e *types. resx* o *myTypes.fr-fr. resx* sono presenti nella stessa cartella.</span><span class="sxs-lookup"><span data-stu-id="0cc7a-124">Files *MyTypes.cs* and *MyTypes.resx* or *MyTypes.fr-FR.resx* exist in the same folder.</span></span>
  
  <span data-ttu-id="0cc7a-125">**Nome file manifesto risorsa generato**: *Namespace. nomeclasse. resources* o *Namespace.ClassName.fr-fr. resources* (dove `Namespace.Classname` è il nome della prima classe in *myTypes.cs*).</span><span class="sxs-lookup"><span data-stu-id="0cc7a-125">**Generated resource manifest file name**: *Namespace.Classname.resources* or *Namespace.Classname.fr-FR.resources* (where `Namespace.Classname` is the name of the first class in *MyTypes.cs*).</span></span>
    
- <span data-ttu-id="0cc7a-126">Se nessuna delle regole precedenti è applicabile, il nome del file manifesto della risorsa generato è *RootNamespace. RelativePathWithDotsForSlashes.\[impostazioni cultura.] risorse*.</span><span class="sxs-lookup"><span data-stu-id="0cc7a-126">If none of the previous rules apply, the generated resource manifest file name is *RootNamespace.RelativePathWithDotsForSlashes.\[Culture.]resources*.</span></span> <span data-ttu-id="0cc7a-127">Il percorso relativo è il valore dell'attributo `Link` dell'elemento `EmbeddedResource` se è impostato.</span><span class="sxs-lookup"><span data-stu-id="0cc7a-127">The relative path is the value of the `Link` attribute of the `EmbeddedResource` element if it's set.</span></span> <span data-ttu-id="0cc7a-128">In caso contrario, il percorso relativo è il valore dell'attributo `Identity` dell'elemento `EmbeddedResource`.</span><span class="sxs-lookup"><span data-stu-id="0cc7a-128">Otherwise, the relative path is the value of the `Identity` attribute of the `EmbeddedResource` element.</span></span> <span data-ttu-id="0cc7a-129">In Visual Studio è il percorso dalla radice del progetto al file in Esplora soluzioni.</span><span class="sxs-lookup"><span data-stu-id="0cc7a-129">In Visual Studio, this is the path from the project root to the file in Solution Explorer.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="0cc7a-130">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="0cc7a-130">Recommended action</span></span>

<span data-ttu-id="0cc7a-131">Se non si è soddisfatti dei nomi dei manifesti generati, è possibile:</span><span class="sxs-lookup"><span data-stu-id="0cc7a-131">If you're unsatisfied with the generated manifest names, you can:</span></span>

- <span data-ttu-id="0cc7a-132">Modificare i metadati del file di risorse in base a una delle regole di denominazione descritte in precedenza.</span><span class="sxs-lookup"><span data-stu-id="0cc7a-132">Modify your resource file metadata according to one of the previously described naming rules.</span></span>

- <span data-ttu-id="0cc7a-133">Impostare `EmbeddedResourceUseDependentUponConvention` su `false` nel file di progetto per rifiutare esplicitamente la nuova convenzione:</span><span class="sxs-lookup"><span data-stu-id="0cc7a-133">Set `EmbeddedResourceUseDependentUponConvention` to `false` in your project file to opt out of the new convention entirely:</span></span>

   ```xml
   <EmbeddedResourceUseDependentUponConvention>false</EmbeddedResourceUseDependentUponConvention>
   ```

   > [!NOTE]
   > <span data-ttu-id="0cc7a-134">Se sono presenti gli attributi `LogicalName` o `ManifestResourceName`, i relativi valori verranno comunque utilizzati per il nome del file generato.</span><span class="sxs-lookup"><span data-stu-id="0cc7a-134">If the `LogicalName` or `ManifestResourceName` attributes are present, their values will still be used for the generated file name.</span></span>

#### <a name="category"></a><span data-ttu-id="0cc7a-135">Category</span><span class="sxs-lookup"><span data-stu-id="0cc7a-135">Category</span></span>

<span data-ttu-id="0cc7a-136">MSBuild</span><span class="sxs-lookup"><span data-stu-id="0cc7a-136">MSBuild</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="0cc7a-137">API interessate</span><span class="sxs-lookup"><span data-stu-id="0cc7a-137">Affected APIs</span></span>

<span data-ttu-id="0cc7a-138">N/D</span><span class="sxs-lookup"><span data-stu-id="0cc7a-138">N/A</span></span>
