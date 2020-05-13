---
title: Modalità di generazione dei nomi dei file manifesto da MSBuild
description: Vengono descritti i fattori che influiscono sul nome di un file manifesto di risorsa generato da MSBuild in fase di compilazione.
ms.date: 05/08/2020
ms.topic: conceptual
ms.openlocfilehash: 383bf6a077b0631e70ddaa4721b20e992127a73c
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83232326"
---
# <a name="how-resource-manifest-files-are-named"></a><span data-ttu-id="1660b-103">Come vengono denominati i file manifesto delle risorse</span><span class="sxs-lookup"><span data-stu-id="1660b-103">How resource manifest files are named</span></span>

<span data-ttu-id="1660b-104">Quando MSBuild compila un progetto .NET Core, i file di risorse XML con estensione *resx* sono convertiti in file con estensione *Resources* binari.</span><span class="sxs-lookup"><span data-stu-id="1660b-104">When MSBuild compiles a .NET Core project, XML resource files, which have the *.resx* file extension, are converted into binary *.resources* files.</span></span> <span data-ttu-id="1660b-105">I file binari sono incorporati nell'output del compilatore e possono essere letti da <xref:System.Resources.ResourceManager> .</span><span class="sxs-lookup"><span data-stu-id="1660b-105">The binary files are embedded into the output of the compiler and can be read by the <xref:System.Resources.ResourceManager>.</span></span> <span data-ttu-id="1660b-106">Questo articolo descrive il modo in cui MSBuild sceglie un nome per ogni file con *estensione resources* .</span><span class="sxs-lookup"><span data-stu-id="1660b-106">This article describes how MSBuild chooses a name for each *.resources* file.</span></span>

> [!TIP]
> <span data-ttu-id="1660b-107">Se si aggiunge un elemento di risorsa in modo esplicito al file di progetto ed è [incluso anche con il valore predefinito globs per .NET Core](../project-sdk/overview.md#default-compilation-includes), si otterrà un errore di compilazione.</span><span class="sxs-lookup"><span data-stu-id="1660b-107">If you explicitly add a resource item to your project file, and it's also [included with the default include globs for .NET Core](../project-sdk/overview.md#default-compilation-includes), you will get a build error.</span></span> <span data-ttu-id="1660b-108">Per includere manualmente i file di risorse come `EmbeddedResource` elementi, impostare la `EnableDefaultEmbeddedResourceItems` proprietà su false.</span><span class="sxs-lookup"><span data-stu-id="1660b-108">To manually include resource files as `EmbeddedResource` items, set the `EnableDefaultEmbeddedResourceItems` property to false.</span></span>

## <a name="default-name"></a><span data-ttu-id="1660b-109">Nome predefinito</span><span class="sxs-lookup"><span data-stu-id="1660b-109">Default name</span></span>

<span data-ttu-id="1660b-110">In .NET Core 3,0 e versioni successive, il nome predefinito per un manifesto di risorsa viene usato quando vengono soddisfatte entrambe le condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="1660b-110">In .NET Core 3.0 and later, the default name for a resource manifest is used when both of the following conditions are met:</span></span>

- <span data-ttu-id="1660b-111">Il file di risorse non è incluso in modo esplicito nel file di progetto come `EmbeddedResource` elemento con i `LogicalName` `ManifestResourceName` metadati, o `DependentUpon` .</span><span class="sxs-lookup"><span data-stu-id="1660b-111">The resource file is not explicitly included in the project file as an `EmbeddedResource` item with `LogicalName`, `ManifestResourceName`, or `DependentUpon` metadata.</span></span>
- <span data-ttu-id="1660b-112">La `EmbeddedResourceUseDependentUponConvention` proprietà non è impostata su `false` nel file di progetto.</span><span class="sxs-lookup"><span data-stu-id="1660b-112">The `EmbeddedResourceUseDependentUponConvention` property is not set to `false` in the project file.</span></span> <span data-ttu-id="1660b-113">Per impostazione predefinita, questa proprietà è impostata su `true`.</span><span class="sxs-lookup"><span data-stu-id="1660b-113">By default, this property is set to `true`.</span></span> <span data-ttu-id="1660b-114">Per ulteriori informazioni, vedere [EmbeddedResourceUseDependentUponConvention](../project-sdk/msbuild-props.md#embeddedresourceusedependentuponconvention).</span><span class="sxs-lookup"><span data-stu-id="1660b-114">For more information, see [EmbeddedResourceUseDependentUponConvention](../project-sdk/msbuild-props.md#embeddedresourceusedependentuponconvention).</span></span>

<span data-ttu-id="1660b-115">Se il file di risorse è condiviso con un file di origine (con*estensione cs* o *VB*) con lo stesso nome file radice, viene usato il nome completo del primo tipo definito nel file di origine per il nome del file manifesto.</span><span class="sxs-lookup"><span data-stu-id="1660b-115">If the resource file is colocated with a source file (*.cs* or *.vb*) of the same root file name, the full name of the first type that's defined in the source file is used for the manifest file name.</span></span> <span data-ttu-id="1660b-116">Se, ad esempio, `MyNamespace.Form1` è il primo tipo definito in *Form1.cs*e *Form1.cs* è colocato con *Form1. resx*, il nome del manifesto generato per il file di risorse è *MyNamespace. Form1. resources*.</span><span class="sxs-lookup"><span data-stu-id="1660b-116">For example, if `MyNamespace.Form1` is the first type defined in *Form1.cs*, and *Form1.cs* is colocated with *Form1.resx*, the generated manifest name for that resource file is *MyNamespace.Form1.resources*.</span></span>

## <a name="logicalname-metadata"></a><span data-ttu-id="1660b-117">LogicalName (metadati)</span><span class="sxs-lookup"><span data-stu-id="1660b-117">LogicalName metadata</span></span>

<span data-ttu-id="1660b-118">Se un file di risorse viene incluso in modo esplicito nel file di progetto come un `EmbeddedResource` elemento con `LogicalName` metadati, il `LogicalName` valore viene usato come nome del manifesto.</span><span class="sxs-lookup"><span data-stu-id="1660b-118">If a resource file is explicitly included in the project file as an `EmbeddedResource` item with `LogicalName` metadata, the `LogicalName` value is used as the manifest name.</span></span> <span data-ttu-id="1660b-119">`LogicalName`ha la precedenza su qualsiasi altra impostazione o metadati.</span><span class="sxs-lookup"><span data-stu-id="1660b-119">`LogicalName` takes precedence over any other metadata or setting.</span></span>

<span data-ttu-id="1660b-120">Il nome del manifesto per il file di risorse definito nel frammento di file di progetto seguente è ad esempio *somename. resources*.</span><span class="sxs-lookup"><span data-stu-id="1660b-120">For example, the manifest name for the resource file that's defined in the following project file snippet is *SomeName.resources*.</span></span>

```xml
<EmbeddedResource Include="X.resx" LogicalName="SomeName.resources" />
```

<span data-ttu-id="1660b-121">-oppure-</span><span class="sxs-lookup"><span data-stu-id="1660b-121">-or-</span></span>

```xml
<EmbeddedResource Include="X.fr-FR.resx" LogicalName="SomeName.resources" />
```

## <a name="manifestresourcename-metadata"></a><span data-ttu-id="1660b-122">Metadati ManifestResourceName</span><span class="sxs-lookup"><span data-stu-id="1660b-122">ManifestResourceName metadata</span></span>

<span data-ttu-id="1660b-123">Se un file di risorse viene incluso in modo esplicito nel file di progetto come un `EmbeddedResource` elemento con `ManifestResourceName` metadati (ed `LogicalName` è assente), il `ManifestResourceName` valore, combinato con l'estensione di file *. resources*, viene usato come nome del file manifesto.</span><span class="sxs-lookup"><span data-stu-id="1660b-123">If a resource file is explicitly included in the project file as an `EmbeddedResource` item with `ManifestResourceName` metadata (and `LogicalName` is absent), the `ManifestResourceName` value, combined with the file extension *.resources*, is used as the manifest file name.</span></span>

<span data-ttu-id="1660b-124">Il nome del manifesto per il file di risorse definito nel frammento di file di progetto seguente è ad esempio *somename. resources*.</span><span class="sxs-lookup"><span data-stu-id="1660b-124">For example, the manifest name for the resource file that's defined in the following project file snippet is *SomeName.resources*.</span></span>

```xml
<EmbeddedResource Include="X.resx" ManifestResourceName="SomeName" />
```

<span data-ttu-id="1660b-125">Il nome del manifesto per il file di risorse definito nel frammento di file di progetto seguente è *somename.fr-fr. resources*.</span><span class="sxs-lookup"><span data-stu-id="1660b-125">The manifest name for the resource file that's defined in the following project file snippet is *SomeName.fr-FR.resources*.</span></span>

```xml
<EmbeddedResource Include="X.fr-FR.resx" ManifestResourceName="SomeName.fr-FR" />
```

## <a name="dependentupon-metadata"></a><span data-ttu-id="1660b-126">Metadati DependentUpon</span><span class="sxs-lookup"><span data-stu-id="1660b-126">DependentUpon metadata</span></span>

<span data-ttu-id="1660b-127">Se un file di risorse viene incluso in modo esplicito nel file di progetto come un `EmbeddedResource` elemento con `DependentUpon` metadati (e `LogicalName` e non `ManifestResourceName` sono assenti), le informazioni del file di origine definito da vengono `DependentUpon` usate per il nome file del manifesto della risorsa.</span><span class="sxs-lookup"><span data-stu-id="1660b-127">If a resource file is explicitly included in the project file as an `EmbeddedResource` item with `DependentUpon` metadata (and `LogicalName` and `ManifestResourceName` are absent), information from the source file defined by `DependentUpon` is used for the resource manifest file name.</span></span> <span data-ttu-id="1660b-128">In particolare, il nome del primo tipo definito nel file di origine viene usato nel nome del manifesto come segue: *Namespace. NomeClasse \[ . Impostazioni cultura]. resources*.</span><span class="sxs-lookup"><span data-stu-id="1660b-128">Specifically, the name of the first type that's defined in the source file is used in the manifest name as follows: *Namespace.Classname\[.Culture].resources*.</span></span>

<span data-ttu-id="1660b-129">Ad esempio, il nome del manifesto per il file di risorse definito nel frammento di file di progetto seguente è *Namespace. nomeclasse. resources* , dove `Namespace.Classname` è la prima classe definita in *myTypes.cs*.</span><span class="sxs-lookup"><span data-stu-id="1660b-129">For example, the manifest name for the resource file that's defined in the following project file snippet is *Namespace.Classname.resources* (where `Namespace.Classname` is the first class that's defined in *MyTypes.cs*).</span></span>

```xml
<EmbeddedResource Include="X.resx" DependentUpon="MyTypes.cs">
```

<span data-ttu-id="1660b-130">Il nome del manifesto per il file di risorse definito nel frammento di file di progetto seguente è *Namespace.ClassName.fr-fr. resources* , dove `Namespace.Classname` è la prima classe definita in *myTypes.cs*.</span><span class="sxs-lookup"><span data-stu-id="1660b-130">The manifest name for the resource file that's defined in the following project file snippet is *Namespace.Classname.fr-FR.resources* (where `Namespace.Classname` is the first class that's defined in *MyTypes.cs*).</span></span>

```xml
<EmbeddedResource Include="X.fr-FR.resx" DependentUpon="MyTypes.cs">
```

## <a name="embeddedresourceusedependentuponconvention-property"></a><span data-ttu-id="1660b-131">Proprietà EmbeddedResourceUseDependentUponConvention</span><span class="sxs-lookup"><span data-stu-id="1660b-131">EmbeddedResourceUseDependentUponConvention property</span></span>

<span data-ttu-id="1660b-132">Se `EmbeddedResourceUseDependentUponConvention` è impostato su `false` nel file di progetto, ogni nome di file del manifesto della risorsa è basato sullo spazio dei nomi radice per il progetto e sul percorso relativo dalla radice del progetto al file con *estensione resx* .</span><span class="sxs-lookup"><span data-stu-id="1660b-132">If `EmbeddedResourceUseDependentUponConvention` is set to `false` in the project file, each resource manifest file name is based off the root namespace for the project and the relative path from the project root to the *.resx* file.</span></span> <span data-ttu-id="1660b-133">In particolare, il nome del file manifesto della risorsa generato è *RootNamespace. RelativePathWithDotsForSlashes. \[ Impostazioni cultura.] risorse*.</span><span class="sxs-lookup"><span data-stu-id="1660b-133">More specifically, the generated resource manifest file name is *RootNamespace.RelativePathWithDotsForSlashes.\[Culture.]resources*.</span></span> <span data-ttu-id="1660b-134">Si tratta anche della logica usata per generare i nomi di manifesto nelle versioni di .NET Core precedenti alla 3,0.</span><span class="sxs-lookup"><span data-stu-id="1660b-134">This is also the logic used to generate manifest names in .NET Core versions prior to 3.0.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="1660b-135">Se `RootNamespace` non è definito, per impostazione predefinita viene impostato il nome del progetto.</span><span class="sxs-lookup"><span data-stu-id="1660b-135">If `RootNamespace` is not defined, it defaults to the project name.</span></span>
> - <span data-ttu-id="1660b-136">Se `LogicalName` `ManifestResourceName` `DependentUpon` per un elemento del file di progetto si specificano i metadati, o `EmbeddedResource` , questa regola di denominazione non si applica al file di risorse.</span><span class="sxs-lookup"><span data-stu-id="1660b-136">If `LogicalName`, `ManifestResourceName`, or `DependentUpon` metadata is specified for an `EmbeddedResource` item in the project file, this naming rule does not apply to that resource file.</span></span>

## <a name="see-also"></a><span data-ttu-id="1660b-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1660b-137">See also</span></span>

- [<span data-ttu-id="1660b-138">Funzionamento della denominazione delle risorse del manifesto</span><span class="sxs-lookup"><span data-stu-id="1660b-138">How Manifest Resource Naming Works</span></span>](https://gist.github.com/BenVillalobos/041673b9a73bec60fdc3bf0f86fae62a)
- [<span data-ttu-id="1660b-139">Proprietà MSBuild per progetti .NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="1660b-139">MSBuild properties for .NET Core SDK projects</span></span>](../project-sdk/msbuild-props.md)
- [<span data-ttu-id="1660b-140">Modifiche di rilievo di MSBuild</span><span class="sxs-lookup"><span data-stu-id="1660b-140">MSBuild breaking changes</span></span>](../compatibility/msbuild.md)
