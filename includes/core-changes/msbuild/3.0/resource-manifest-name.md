---
ms.openlocfilehash: f24a29a00a1bff34a452c43716d76bf72ef277b5
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83206220"
---
### <a name="resource-manifest-file-name-change"></a><span data-ttu-id="18a0f-101">Modifica del nome del file manifesto della risorsa</span><span class="sxs-lookup"><span data-stu-id="18a0f-101">Resource manifest file name change</span></span>

<span data-ttu-id="18a0f-102">A partire da .NET Core 3,0, nel caso predefinito, MSBuild genera un nome di file manifesto diverso per i file di risorse.</span><span class="sxs-lookup"><span data-stu-id="18a0f-102">Starting in .NET Core 3.0, in the default case, MSBuild generates a different manifest file name for resource files.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="18a0f-103">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="18a0f-103">Version introduced</span></span>

<span data-ttu-id="18a0f-104">3.0</span><span class="sxs-lookup"><span data-stu-id="18a0f-104">3.0</span></span>

#### <a name="change-description"></a><span data-ttu-id="18a0f-105">Descrizione modifica:</span><span class="sxs-lookup"><span data-stu-id="18a0f-105">Change description</span></span>

<span data-ttu-id="18a0f-106">Prima di .NET Core 3,0, se `LogicalName` `ManifestResourceName` `DependentUpon` per un elemento nel file di progetto non è stato specificato alcun metadati, o `EmbeddedResource` , MSBuild ha generato un nome di file manifesto nel criterio `<RootNamespace>.<ResourceFilePathFromProjectRoot>.resources` .</span><span class="sxs-lookup"><span data-stu-id="18a0f-106">Prior to .NET Core 3.0, if no `LogicalName`, `ManifestResourceName`, or `DependentUpon` metadata was specified for an `EmbeddedResource` item in the project file, MSBuild generated a manifest file name in the pattern `<RootNamespace>.<ResourceFilePathFromProjectRoot>.resources`.</span></span> <span data-ttu-id="18a0f-107">Se `RootNamespace` non è definito nel file di progetto, per impostazione predefinita viene impostato il nome del progetto.</span><span class="sxs-lookup"><span data-stu-id="18a0f-107">If `RootNamespace` is not defined in the project file, it defaults to the project name.</span></span> <span data-ttu-id="18a0f-108">Ad esempio, il nome del manifesto generato per un file di risorse denominato *Form1. resx* nella directory del progetto radice è *MyProject. Form1. resources*.</span><span class="sxs-lookup"><span data-stu-id="18a0f-108">For example, the generated manifest name for a resource file named *Form1.resx* in the root project directory was *MyProject.Form1.resources*.</span></span>

<span data-ttu-id="18a0f-109">A partire da .NET Core 3,0, se un file di risorse è posizionato con un file di origine con lo stesso nome, ad esempio *Form1. resx* e *Form1.cs*, MSBuild usa le informazioni sul tipo del file di origine per generare il nome del file manifesto nel modello `<Namespace>.<ClassName>.resources` .</span><span class="sxs-lookup"><span data-stu-id="18a0f-109">Starting in .NET Core 3.0, if a resource file is colocated with a source file of the same name (for example, *Form1.resx* and *Form1.cs*), MSBuild uses type information from the source file to generate the manifest file name in the pattern `<Namespace>.<ClassName>.resources`.</span></span> <span data-ttu-id="18a0f-110">Lo spazio dei nomi e il nome della classe vengono estratti dal primo tipo nel file di origine con percorso condiviso.</span><span class="sxs-lookup"><span data-stu-id="18a0f-110">The namespace and class name are extracted from the first type in the colocated source file.</span></span> <span data-ttu-id="18a0f-111">Ad esempio, il nome del manifesto generato per un file di risorse denominato *Form1. resx* che si trova in un file di origine denominato *Form1.cs* è *MyNamespace. Form1. resources*.</span><span class="sxs-lookup"><span data-stu-id="18a0f-111">For example, the generated manifest name for a resource file named *Form1.resx* that's colocated with a source file named *Form1.cs* is *MyNamespace.Form1.resources*.</span></span> <span data-ttu-id="18a0f-112">La cosa importante da notare è che la prima parte del nome file è diversa rispetto alle versioni precedenti di .NET Core (*MyNamespace* anziché *MyProject*).</span><span class="sxs-lookup"><span data-stu-id="18a0f-112">The key thing to note is that the first part of the file name is different to prior versions of .NET Core (*MyNamespace* instead of *MyProject*).</span></span>

> [!NOTE]
> <span data-ttu-id="18a0f-113">Se si dispone `LogicalName` di `ManifestResourceName` metadati, o `DependentUpon` specificati in un `EmbeddedResource` elemento nel file di progetto, questa modifica non influisce sul file di risorse.</span><span class="sxs-lookup"><span data-stu-id="18a0f-113">If you have `LogicalName`, `ManifestResourceName`, or `DependentUpon` metadata specified on an `EmbeddedResource` item in the project file, then this change does not affect that resource file.</span></span>

<span data-ttu-id="18a0f-114">Questa modifica di rilievo è stata introdotta con l'aggiunta della `EmbeddedResourceUseDependentUponConvention` proprietà ai progetti .NET Core.</span><span class="sxs-lookup"><span data-stu-id="18a0f-114">This breaking change was introduced with the addition of the `EmbeddedResourceUseDependentUponConvention` property to .NET Core projects.</span></span> <span data-ttu-id="18a0f-115">Per impostazione predefinita, i file di risorse non sono elencati in modo esplicito in un file di progetto .NET Core, quindi non hanno `DependentUpon` metadati per specificare come assegnare un nome al file con *estensione resources* generato.</span><span class="sxs-lookup"><span data-stu-id="18a0f-115">By default, resource files aren't explicitly listed in a .NET Core project file, so they have no `DependentUpon` metadata to specify how to name the generated *.resources* file.</span></span> <span data-ttu-id="18a0f-116">Quando `EmbeddedResourceUseDependentUponConvention` è impostato su `true` , ovvero il valore predefinito, MSBuild cerca un file di origine con percorso condiviso ed estrae uno spazio dei nomi e un nome di classe da tale file.</span><span class="sxs-lookup"><span data-stu-id="18a0f-116">When `EmbeddedResourceUseDependentUponConvention` is set to `true`, which is the default, MSBuild looks for a colocated source file and extracts a namespace and class name from that file.</span></span> <span data-ttu-id="18a0f-117">Se si imposta `EmbeddedResourceUseDependentUponConvention` su `false` , MSBuild genera il nome del manifesto in base al comportamento precedente, che combina `RootNamespace` e il percorso del file relativo.</span><span class="sxs-lookup"><span data-stu-id="18a0f-117">If you set `EmbeddedResourceUseDependentUponConvention` to `false`, MSBuild generates the manifest name according to the previous behavior, which combines `RootNamespace` and the relative file path.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="18a0f-118">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="18a0f-118">Recommended action</span></span>

<span data-ttu-id="18a0f-119">Nella maggior parte dei casi, non è richiesta alcuna azione da parte dello sviluppatore e l'app dovrebbe continuare a funzionare.</span><span class="sxs-lookup"><span data-stu-id="18a0f-119">In most cases, no action is required on the part of the developer, and your app should continue to work.</span></span> <span data-ttu-id="18a0f-120">Tuttavia, se questa modifica interrompe l'app, è possibile eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="18a0f-120">However, if this change breaks your app, you can either:</span></span>

- <span data-ttu-id="18a0f-121">Modificare il codice in modo che preveda il nuovo nome del manifesto.</span><span class="sxs-lookup"><span data-stu-id="18a0f-121">Change your code to expect the new manifest name.</span></span>

- <span data-ttu-id="18a0f-122">Rifiutare esplicitamente la nuova convenzione di denominazione impostando `EmbeddedResourceUseDependentUponConvention` su `false` nel file di progetto.</span><span class="sxs-lookup"><span data-stu-id="18a0f-122">Opt out of the new naming convention by setting `EmbeddedResourceUseDependentUponConvention` to `false` in your project file.</span></span>

  ```xml
  <PropertyGroup>
    <EmbeddedResourceUseDependentUponConvention>false</EmbeddedResourceUseDependentUponConvention>
  </PropertyGroup>
  ```

#### <a name="category"></a><span data-ttu-id="18a0f-123">Categoria</span><span class="sxs-lookup"><span data-stu-id="18a0f-123">Category</span></span>

<span data-ttu-id="18a0f-124">MSBuild</span><span class="sxs-lookup"><span data-stu-id="18a0f-124">MSBuild</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="18a0f-125">API interessate</span><span class="sxs-lookup"><span data-stu-id="18a0f-125">Affected APIs</span></span>

<span data-ttu-id="18a0f-126">N/D</span><span class="sxs-lookup"><span data-stu-id="18a0f-126">N/A</span></span>
