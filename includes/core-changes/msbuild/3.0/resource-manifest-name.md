---
ms.openlocfilehash: 16ee73bfc0ab33b04ea3e2fa6d0eec521a9b8634
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "78968071"
---
### <a name="resource-manifest-file-names"></a><span data-ttu-id="c744c-101">Nomi dei file manifesto delle risorse</span><span class="sxs-lookup"><span data-stu-id="c744c-101">Resource manifest file names</span></span>

<span data-ttu-id="c744c-102">A partire da .NET Core 3.0, il nome del file manifesto della risorsa generato è stato modificato.</span><span class="sxs-lookup"><span data-stu-id="c744c-102">Starting in .NET Core 3.0, the generated resource manifest file name has changed.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="c744c-103">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="c744c-103">Version introduced</span></span>

<span data-ttu-id="c744c-104">3.0</span><span class="sxs-lookup"><span data-stu-id="c744c-104">3.0</span></span>

#### <a name="change-description"></a><span data-ttu-id="c744c-105">Descrizione modifica:</span><span class="sxs-lookup"><span data-stu-id="c744c-105">Change description</span></span>

<span data-ttu-id="c744c-106">Prima di .NET Core 3.0, quando i metadati [DependentUpon](/visualstudio/msbuild/common-msbuild-project-items#compile) venivano impostati per un file di risorse (*.resx*) nel file di progetto MSBuild, il nome del manifesto generato era *Namespace.Classname.resources*.</span><span class="sxs-lookup"><span data-stu-id="c744c-106">Prior to .NET Core 3.0, when [DependentUpon](/visualstudio/msbuild/common-msbuild-project-items#compile) metadata was set for a resource (*.resx*) file in the MSBuild project file, the generated manifest name was *Namespace.Classname.resources*.</span></span> <span data-ttu-id="c744c-107">Quando [DependentUpon](/visualstudio/msbuild/common-msbuild-project-items#compile) non è stato impostato, il nome del manifesto generato è *Namespace.Classname.FolderPathRelativeToRoot.Culture.resources*.</span><span class="sxs-lookup"><span data-stu-id="c744c-107">When [DependentUpon](/visualstudio/msbuild/common-msbuild-project-items#compile) was not set, the generated manifest name was *Namespace.Classname.FolderPathRelativeToRoot.Culture.resources*.</span></span>

<span data-ttu-id="c744c-108">A partire da .NET Core 3.0, quando un file *resx* viene collocato con un file di origine con lo stesso nome, ad esempio nelle app Windows Form, il nome del manifesto della risorsa viene generato dal nome completo del primo tipo nel file di origine.</span><span class="sxs-lookup"><span data-stu-id="c744c-108">Starting in .NET Core 3.0, when a *.resx* file is colocated with a source file of the same name, for example, in Windows Forms apps, the resource manifest name is generated from the full name of the first type in the source file.</span></span> <span data-ttu-id="c744c-109">Ad esempio, se *Type.cs* è collocato tra *Type.resx*, il nome del manifesto generato è *Namespace.Classname.resources*.</span><span class="sxs-lookup"><span data-stu-id="c744c-109">For example, if *Type.cs* is colocated with *Type.resx*, the generated manifest name is *Namespace.Classname.resources*.</span></span> <span data-ttu-id="c744c-110">Tuttavia, se si modifica uno `EmbeddedResource` degli attributi della proprietà per il file *RESX,* il nome del file manifesto generato potrebbe essere diverso:</span><span class="sxs-lookup"><span data-stu-id="c744c-110">However, if you modify any of the attributes on the `EmbeddedResource` property for the *.resx* file, the generated manifest file name may be different:</span></span>

- <span data-ttu-id="c744c-111">Se `LogicalName` l'attributo nella `EmbeddedResource` proprietà è impostato, tale valore viene utilizzato come nome del file manifesto della risorsa.</span><span class="sxs-lookup"><span data-stu-id="c744c-111">If the `LogicalName` attribute on the `EmbeddedResource` property is set, that value is used as the resource manifest file name.</span></span>

  <span data-ttu-id="c744c-112">Esempi:</span><span class="sxs-lookup"><span data-stu-id="c744c-112">Examples:</span></span>

  ```xml
  <EmbeddedResource Include="X.resx" LogicalName="SomeName.resources" />
  -or-
  <EmbeddedResource Include="X.fr-FR.resx" LogicalName="SomeName.resources" />
  ```

  <span data-ttu-id="c744c-113">**Nome del file manifesto**di risorsa generato : *SomeName.resources* (indipendentemente dal nome del file *RESX* o dalle impostazioni cultura o da qualsiasi altro metadati).</span><span class="sxs-lookup"><span data-stu-id="c744c-113">**Generated resource manifest file name**: *SomeName.resources* (regardless of the *.resx* file name or culture or any other metadata).</span></span>

- <span data-ttu-id="c744c-114">Se `LogicalName` non è impostato, ma l'attributo `ManifestResourceName` della proprietà è impostato, il `EmbeddedResource` relativo valore, combinato con l'estensione di file *resources*, viene utilizzato come nome del file manifesto della risorsa.</span><span class="sxs-lookup"><span data-stu-id="c744c-114">If `LogicalName` is not set, but the `ManifestResourceName` attribute on the `EmbeddedResource` property is set, its value, combined with the file extension *.resources*, is used as the resource manifest file name.</span></span>

  <span data-ttu-id="c744c-115">Esempi:</span><span class="sxs-lookup"><span data-stu-id="c744c-115">Examples:</span></span>

  ```xml
  <EmbeddedResource Include="X.resx" ManifestResourceName="SomeName" />
  -or-
  <EmbeddedResource Include="X.fr-FR.resx" ManifestResourceName="SomeName.fr-FR" />
  ```

  <span data-ttu-id="c744c-116">**Nome del file manifesto della risorsa generato**: *SomeName.resources* o *SomeName.fr-FR.resources*.</span><span class="sxs-lookup"><span data-stu-id="c744c-116">**Generated resource manifest file name**: *SomeName.resources* or *SomeName.fr-FR.resources*.</span></span>

- <span data-ttu-id="c744c-117">Se le regole precedenti non sono `DependentUpon` valide `EmbeddedResource` e l'attributo dell'elemento è impostato su un file di origine, il nome del tipo della prima classe nel file di origine viene utilizzato nel nome del file manifesto della risorsa.</span><span class="sxs-lookup"><span data-stu-id="c744c-117">If the previous rules don't apply, and the `DependentUpon` attribute on the `EmbeddedResource` element is set to a source file, the type name of the first class in the source file is used in the resource manifest file name.</span></span> <span data-ttu-id="c744c-118">Più specificamente, il nome del file generato è *Namespace.Classname\[. Cultura].resources*.</span><span class="sxs-lookup"><span data-stu-id="c744c-118">More specifically, the generated file name is *Namespace.Classname\[.Culture].resources*.</span></span>

  <span data-ttu-id="c744c-119">Esempi:</span><span class="sxs-lookup"><span data-stu-id="c744c-119">Examples:</span></span>

  ```xml
  <EmbeddedResource Include="X.resx" DependentUpon="MyTypes.cs">
  -or-
  <EmbeddedResource Include="X.fr-FR.resx" DependentUpon="MyTypes.cs">
  ```

  <span data-ttu-id="c744c-120">Nome del manifesto della **risorsa generato:** *Namespace.Classname.resources* `Namespace.Classname` o *Namespace.Classname.fr-FR.resources* (dove è il nome della prima classe *nellMyTypes.cs*).</span><span class="sxs-lookup"><span data-stu-id="c744c-120">**Generated resource manifest file name**: *Namespace.Classname.resources* or *Namespace.Classname.fr-FR.resources* (where `Namespace.Classname` is the name of the first class in *MyTypes.cs*).</span></span>

- <span data-ttu-id="c744c-121">Se le regole precedenti non `EmbeddedResourceUseDependentUponConvention` `true` sono applicabili, è (l'impostazione predefinita per .NET Core) e c'è un file di origine collocato con un file *RESX* con lo stesso nome di file di base, il file *RESX* viene reso dipendente dal file di origine corrispondente e il nome generato è lo stesso della regola precedente.</span><span class="sxs-lookup"><span data-stu-id="c744c-121">If the previous rules don't apply, `EmbeddedResourceUseDependentUponConvention` is `true` (the default for .NET Core), and there's a source file colocated with a *.resx* file that has the same base file name, the *.resx* file is made dependent upon the matching source file, and the generated name is the same as in the previous rule.</span></span> <span data-ttu-id="c744c-122">Si tratta della regola "impostazioni predefinite" per i progetti .NET Core.This is the "default settings" rule for .NET Core projects.</span><span class="sxs-lookup"><span data-stu-id="c744c-122">This is the "default settings" rule for .NET Core projects.</span></span>
  
  <span data-ttu-id="c744c-123">Esempi:</span><span class="sxs-lookup"><span data-stu-id="c744c-123">Examples:</span></span>
  
  <span data-ttu-id="c744c-124">I file *MyTypes.cs* e *MyTypes.resx* o *MyTypes.fr-FR.resx* sono presenti nella stessa cartella.</span><span class="sxs-lookup"><span data-stu-id="c744c-124">Files *MyTypes.cs* and *MyTypes.resx* or *MyTypes.fr-FR.resx* exist in the same folder.</span></span>
  
  <span data-ttu-id="c744c-125">Nome del manifesto della **risorsa generato:** *Namespace.Classname.resources* `Namespace.Classname` o *Namespace.Classname.fr-FR.resources* (dove è il nome della prima classe *nellMyTypes.cs*).</span><span class="sxs-lookup"><span data-stu-id="c744c-125">**Generated resource manifest file name**: *Namespace.Classname.resources* or *Namespace.Classname.fr-FR.resources* (where `Namespace.Classname` is the name of the first class in *MyTypes.cs*).</span></span>

- <span data-ttu-id="c744c-126">Se nessuna delle regole precedenti è applicabile, il nome del file manifesto della risorsa generato è *RootNamespace.RelativePathWithDotsForSlashes.\[ Cultura.] risorse*.</span><span class="sxs-lookup"><span data-stu-id="c744c-126">If none of the previous rules apply, the generated resource manifest file name is *RootNamespace.RelativePathWithDotsForSlashes.\[Culture.]resources*.</span></span> <span data-ttu-id="c744c-127">Il percorso relativo è `Link` il `EmbeddedResource` valore dell'attributo dell'elemento se è impostato.</span><span class="sxs-lookup"><span data-stu-id="c744c-127">The relative path is the value of the `Link` attribute of the `EmbeddedResource` element if it's set.</span></span> <span data-ttu-id="c744c-128">In caso contrario, il `Identity` percorso relativo è il valore dell'attributo dell'elemento. `EmbeddedResource`</span><span class="sxs-lookup"><span data-stu-id="c744c-128">Otherwise, the relative path is the value of the `Identity` attribute of the `EmbeddedResource` element.</span></span> <span data-ttu-id="c744c-129">In Visual Studio, questo è il percorso dalla radice del progetto al file in Esplora soluzioni.</span><span class="sxs-lookup"><span data-stu-id="c744c-129">In Visual Studio, this is the path from the project root to the file in Solution Explorer.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="c744c-130">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="c744c-130">Recommended action</span></span>

<span data-ttu-id="c744c-131">Se non si è soddisfatti dei nomi di manifesto generati, è possibile:If you're insatisfied with the generated manifest names, you can:</span><span class="sxs-lookup"><span data-stu-id="c744c-131">If you're unsatisfied with the generated manifest names, you can:</span></span>

- <span data-ttu-id="c744c-132">Modificare i metadati del file di risorse in base a una delle regole di denominazione descritte in precedenza.</span><span class="sxs-lookup"><span data-stu-id="c744c-132">Modify your resource file metadata according to one of the previously described naming rules.</span></span>

- <span data-ttu-id="c744c-133">`EmbeddedResourceUseDependentUponConvention` Impostare `false` su nel file di progetto per rifiutare completamente esplicitamente la nuova convenzione:</span><span class="sxs-lookup"><span data-stu-id="c744c-133">Set `EmbeddedResourceUseDependentUponConvention` to `false` in your project file to opt out of the new convention entirely:</span></span>

   ```xml
   <EmbeddedResourceUseDependentUponConvention>false</EmbeddedResourceUseDependentUponConvention>
   ```

   > [!NOTE]
   > <span data-ttu-id="c744c-134">Se `LogicalName` sono `ManifestResourceName` presenti gli attributi or, i relativi valori verranno comunque utilizzati per il nome del file generato.</span><span class="sxs-lookup"><span data-stu-id="c744c-134">If the `LogicalName` or `ManifestResourceName` attributes are present, their values will still be used for the generated file name.</span></span>

#### <a name="category"></a><span data-ttu-id="c744c-135">Category</span><span class="sxs-lookup"><span data-stu-id="c744c-135">Category</span></span>

<span data-ttu-id="c744c-136">MSBuild</span><span class="sxs-lookup"><span data-stu-id="c744c-136">MSBuild</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="c744c-137">API interessate</span><span class="sxs-lookup"><span data-stu-id="c744c-137">Affected APIs</span></span>

<span data-ttu-id="c744c-138">N/D</span><span class="sxs-lookup"><span data-stu-id="c744c-138">N/A</span></span>
