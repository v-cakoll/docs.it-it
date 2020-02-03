---
title: File di dati, di contenuto e di risorse dell'applicazione
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WPF application [WPF], files
- loose resources [WPF]
- content files [WPF]
- Site of Origin files [WPF]
- resource files [WPF]
- remote files [WPF]
- embedded resources [WPF]
- files [WPF]
- referencing application files [WPF]
- application development [WPF], files
- application management [WPF]
ms.assetid: 7ad2943b-3961-41d3-8fc6-1582d43f5d99
ms.openlocfilehash: ee636c49da64ad07ec5df2f11171b7f9aed713d1
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743358"
---
# <a name="wpf-application-resource-content-and-data-files"></a><span data-ttu-id="f54b7-102">File di dati e di risorse dell'applicazione WPF.</span><span class="sxs-lookup"><span data-stu-id="f54b7-102">WPF Application Resource, Content, and Data Files</span></span>
<span data-ttu-id="f54b7-103">Le applicazioni Microsoft Windows spesso dipendono da file che contengono dati non eseguibili, ad esempio [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], immagini, video e audio.</span><span class="sxs-lookup"><span data-stu-id="f54b7-103">Microsoft Windows applications often depend on files that contain non-executable data, such as [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], images, video, and audio.</span></span> <span data-ttu-id="f54b7-104">Windows Presentation Foundation (WPF) offre supporto speciale per la configurazione, l'identificazione e l'utilizzo di questi tipi di file di dati, chiamati file di dati dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="f54b7-104">Windows Presentation Foundation (WPF) offers special support for configuring, identifying, and using these types of data files, which are called application data files.</span></span> <span data-ttu-id="f54b7-105">Questo supporto si basa su un set specifico di tipi di file di dati dell'applicazione, che include:</span><span class="sxs-lookup"><span data-stu-id="f54b7-105">This support revolves around a specific set of application data file types, including:</span></span>  
  
- <span data-ttu-id="f54b7-106">**File di risorse**: file di dati compilati in un file eseguibile o in un assembly WPF di libreria.</span><span class="sxs-lookup"><span data-stu-id="f54b7-106">**Resource Files**: Data files that are compiled into either an executable or library WPF assembly.</span></span>  
  
- <span data-ttu-id="f54b7-107">**File di contenuto**: file di dati autonomi con un'associazione esplicita a un assembly WPF eseguibile.</span><span class="sxs-lookup"><span data-stu-id="f54b7-107">**Content Files**: Standalone data files that have an explicit association with an executable WPF assembly.</span></span>  
  
- <span data-ttu-id="f54b7-108">**File del sito di origine**: file di dati autonomi senza associazione a un assembly WPF eseguibile.</span><span class="sxs-lookup"><span data-stu-id="f54b7-108">**Site of Origin Files**: Standalone data files that have no association with an executable WPF assembly.</span></span>  
  
 <span data-ttu-id="f54b7-109">Un'importante distinzione da fare tra questi tre tipi di file riguarda il fatto che i file di risorse e i file di dati sono resi noti in fase di compilazione e pertanto sono conosciuti esplicitamente da un assembly.</span><span class="sxs-lookup"><span data-stu-id="f54b7-109">One important distinction to make between these three types of files is that resource files and content files are known at build time; an assembly has explicit knowledge of them.</span></span> <span data-ttu-id="f54b7-110">Per i file del sito di origine, tuttavia, un assembly può non conoscerli affatto o una conoscenza implicita tramite un riferimento URI (Uniform Resource Identifier) di Pack. in quest'ultimo caso, non vi è alcuna garanzia che il file del sito di origine a cui si fa riferimento esista effettivamente.</span><span class="sxs-lookup"><span data-stu-id="f54b7-110">For site of origin files, however, an assembly may have no knowledge of them at all, or implicit knowledge through a pack uniform resource identifier (URI) reference; the case of the latter, there is no guarantee that the referenced site of origin file actually exists.</span></span>  
  
 <span data-ttu-id="f54b7-111">Per fare riferimento ai file di dati dell'applicazione, Windows Presentation Foundation (WPF) usa lo schema URI (Uniform Resource Identifier) di Pack, descritto in dettaglio in [URI di Pack in WPF](pack-uris-in-wpf.md).</span><span class="sxs-lookup"><span data-stu-id="f54b7-111">To reference application data files, Windows Presentation Foundation (WPF) uses the Pack uniform resource identifier (URI) Scheme, which is described in detail in [Pack URIs in WPF](pack-uris-in-wpf.md)).</span></span>  
  
 <span data-ttu-id="f54b7-112">Questo argomento descrive come configurare e usare i file di dati dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="f54b7-112">This topic describes how to configure and use application data files.</span></span>  

<a name="Resource_Files"></a>   
## <a name="resource-files"></a><span data-ttu-id="f54b7-113">File di risorse</span><span class="sxs-lookup"><span data-stu-id="f54b7-113">Resource Files</span></span>  
 <span data-ttu-id="f54b7-114">Se un file di dati deve essere sempre disponibile per un'applicazione, l'unico modo per garantire la disponibilità è compilarlo nell'assembly eseguibile principale dell'applicazione o in uno degli assembly a cui si fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="f54b7-114">If an application data file must always be available to an application, the only way to guarantee availability is to compile it into an application's main executable assembly or one of its referenced assemblies.</span></span> <span data-ttu-id="f54b7-115">Questo tipo di file di dati dell'applicazione è noto come *file di risorse*.</span><span class="sxs-lookup"><span data-stu-id="f54b7-115">This type of application data file is known as a *resource file*.</span></span>  
  
 <span data-ttu-id="f54b7-116">I file di risorse devono essere utilizzati nei casi seguenti:</span><span class="sxs-lookup"><span data-stu-id="f54b7-116">You should use resource files when:</span></span>  
  
- <span data-ttu-id="f54b7-117">Non occorre aggiornare il contenuto del file di risorse dopo la relativa compilazione in un assembly.</span><span class="sxs-lookup"><span data-stu-id="f54b7-117">You don't need to update the resource file's content after it is compiled into an assembly.</span></span>  
  
- <span data-ttu-id="f54b7-118">Si desidera semplificare la complessità di distribuzione dell'applicazione riducendo il numero di dipendenze dei file.</span><span class="sxs-lookup"><span data-stu-id="f54b7-118">You want to simplify application distribution complexity by reducing the number of file dependencies.</span></span>  
  
- <span data-ttu-id="f54b7-119">Il file di dati dell'applicazione deve essere localizzabile. vedere [Cenni preliminari sulla globalizzazione e localizzazione WPF](../advanced/wpf-globalization-and-localization-overview.md).</span><span class="sxs-lookup"><span data-stu-id="f54b7-119">Your application data file needs to be localizable (see [WPF Globalization and Localization Overview](../advanced/wpf-globalization-and-localization-overview.md)).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f54b7-120">I file di risorse descritti in questa sezione sono diversi dai file di risorse descritti in [risorse XAML](../../../desktop-wpf/fundamentals/xaml-resources-define.md) e diversi dalle risorse incorporate o collegate descritte in [gestire le risorse dell'applicazione (.NET)](/visualstudio/ide/managing-application-resources-dotnet).</span><span class="sxs-lookup"><span data-stu-id="f54b7-120">The resource files described in this section are different than the resource files described in [XAML Resources](../../../desktop-wpf/fundamentals/xaml-resources-define.md) and different than the embedded or linked resources described in [Manage Application Resources (.NET)](/visualstudio/ide/managing-application-resources-dotnet).</span></span>  
  
### <a name="configuring-resource-files"></a><span data-ttu-id="f54b7-121">Configurazione dei file di risorse</span><span class="sxs-lookup"><span data-stu-id="f54b7-121">Configuring Resource Files</span></span>  
 <span data-ttu-id="f54b7-122">In WPF un file di risorse è un file incluso in un progetto di Microsoft Build Engine (MSBuild) come elemento `Resource`.</span><span class="sxs-lookup"><span data-stu-id="f54b7-122">In WPF, a resource file is a file that is included in an Microsoft build engine (MSBuild) project as a `Resource` item.</span></span>  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003" ... >  
  ...  
  <ItemGroup>  
    <Resource Include="ResourceFile.xaml" />  
  </ItemGroup>  
  ...  
</Project>  
```  
  
> [!NOTE]
> <span data-ttu-id="f54b7-123">In Visual Studio è possibile creare un file di risorse aggiungendo un file a un progetto e impostando il relativo `Build Action` su `Resource`.</span><span class="sxs-lookup"><span data-stu-id="f54b7-123">In Visual Studio, you create a resource file by adding a file to a project and setting its `Build Action` to `Resource`.</span></span>  
  
 <span data-ttu-id="f54b7-124">Quando il progetto viene compilato, MSBuild compila la risorsa nell'assembly.</span><span class="sxs-lookup"><span data-stu-id="f54b7-124">When the project is built, MSBuild compiles the resource into the assembly.</span></span>  
  
### <a name="using-resource-files"></a><span data-ttu-id="f54b7-125">Uso dei file di risorse</span><span class="sxs-lookup"><span data-stu-id="f54b7-125">Using Resource Files</span></span>  
 <span data-ttu-id="f54b7-126">Per caricare un file di risorse, è possibile chiamare il metodo <xref:System.Windows.Application.GetResourceStream%2A> della classe <xref:System.Windows.Application>, passando un URI di pacchetto che identifica il file di risorse desiderato.</span><span class="sxs-lookup"><span data-stu-id="f54b7-126">To load a resource file, you can call the <xref:System.Windows.Application.GetResourceStream%2A> method of the <xref:System.Windows.Application> class, passing a pack URI that identifies the desired resource file.</span></span> <span data-ttu-id="f54b7-127"><xref:System.Windows.Application.GetResourceStream%2A> restituisce un oggetto <xref:System.Windows.Resources.StreamResourceInfo>, che espone il file di risorse come <xref:System.IO.Stream> e ne descrive il tipo di contenuto.</span><span class="sxs-lookup"><span data-stu-id="f54b7-127"><xref:System.Windows.Application.GetResourceStream%2A> returns a <xref:System.Windows.Resources.StreamResourceInfo> object, which exposes the resource file as a <xref:System.IO.Stream> and describes its content type.</span></span>  
  
 <span data-ttu-id="f54b7-128">Come esempio, il codice seguente illustra come usare <xref:System.Windows.Application.GetResourceStream%2A> per caricare un file di risorse <xref:System.Windows.Controls.Page> e impostarlo come contenuto di un <xref:System.Windows.Controls.Frame> (`pageFrame`):</span><span class="sxs-lookup"><span data-stu-id="f54b7-128">As an example, the following code shows how to use <xref:System.Windows.Application.GetResourceStream%2A> to load a <xref:System.Windows.Controls.Page> resource file and set it as the content of a <xref:System.Windows.Controls.Frame> (`pageFrame`):</span></span>  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadAPageResourceFileManuallyCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.cs#loadapageresourcefilemanuallycode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadAPageResourceFileManuallyCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.vb#loadapageresourcefilemanuallycode)]  
  
 <span data-ttu-id="f54b7-129">Quando si chiama <xref:System.Windows.Application.GetResourceStream%2A> consente di accedere al <xref:System.IO.Stream>, è necessario eseguire l'operazione aggiuntiva di conversione nel tipo della proprietà che verrà impostata con.</span><span class="sxs-lookup"><span data-stu-id="f54b7-129">While calling <xref:System.Windows.Application.GetResourceStream%2A> gives you access to the <xref:System.IO.Stream>, you need to perform the additional work of converting it to the type of the property that you'll be setting it with.</span></span> <span data-ttu-id="f54b7-130">È invece possibile consentire a WPF di gestire l'apertura e la conversione del <xref:System.IO.Stream> caricando un file di risorse direttamente nella proprietà di un tipo usando il codice.</span><span class="sxs-lookup"><span data-stu-id="f54b7-130">Instead, you can let WPF take care of opening and converting the <xref:System.IO.Stream> by loading a resource file directly into the property of a type using code.</span></span>  
  
 <span data-ttu-id="f54b7-131">Nell'esempio seguente viene illustrato come caricare un <xref:System.Windows.Controls.Page> direttamente in una <xref:System.Windows.Controls.Frame> (`pageFrame`) utilizzando il codice.</span><span class="sxs-lookup"><span data-stu-id="f54b7-131">The following example shows how to load a <xref:System.Windows.Controls.Page> directly into a <xref:System.Windows.Controls.Frame> (`pageFrame`) using code.</span></span>  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadPageResourceFileFromCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.cs#loadpageresourcefilefromcode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadPageResourceFileFromCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.vb#loadpageresourcefilefromcode)]  
  
 <span data-ttu-id="f54b7-132">L'esempio seguente illustra il markup equivalente del precedente esempio.</span><span class="sxs-lookup"><span data-stu-id="f54b7-132">The following example is the markup equivalent of the preceding example.</span></span>  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#LoadPageResourceFileFromXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml#loadpageresourcefilefromxaml)]  
  
### <a name="application-code-files-as-resource-files"></a><span data-ttu-id="f54b7-133">File di codice dell'applicazione come file di risorse</span><span class="sxs-lookup"><span data-stu-id="f54b7-133">Application Code Files as Resource Files</span></span>  
 <span data-ttu-id="f54b7-134">È possibile fare riferimento A un set speciale di file di codice dell'applicazione WPF usando URI di pacchetto, tra cui finestre, pagine, documenti dinamici e dizionari risorse.</span><span class="sxs-lookup"><span data-stu-id="f54b7-134">A special set of WPF application code files can be referenced using pack URIs, including windows, pages, flow documents, and resource dictionaries.</span></span> <span data-ttu-id="f54b7-135">Ad esempio, è possibile impostare la proprietà <xref:System.Windows.Application.StartupUri%2A?displayProperty=nameWithType> con un URI di tipo pack che fa riferimento alla finestra o alla pagina che si desidera caricare all'avvio di un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="f54b7-135">For example, you can set the <xref:System.Windows.Application.StartupUri%2A?displayProperty=nameWithType> property with a pack URI that references the window or page that you would like to load when an application starts.</span></span>  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#SetApplicationStartupURI](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/App.xaml#setapplicationstartupuri)]  
  
 <span data-ttu-id="f54b7-136">Questa operazione può essere eseguita quando un file XAML viene incluso in un progetto MSBuild come elemento `Page`.</span><span class="sxs-lookup"><span data-stu-id="f54b7-136">You can do this when a XAML file is included in an MSBuild project as a `Page` item.</span></span>  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003" ... >  
  ...  
  <ItemGroup>  
    <Page Include="MainWindow.xaml" />  
  </ItemGroup>  
  ...  
</Project>  
```  
  
> [!NOTE]
> <span data-ttu-id="f54b7-137">In Visual Studio si aggiunge un nuovo <xref:System.Windows.Window>, <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Page>, <xref:System.Windows.Documents.FlowDocument>o <xref:System.Windows.ResourceDictionary> a un progetto, per impostazione predefinita il `Build Action` per il file di markup viene `Page`.</span><span class="sxs-lookup"><span data-stu-id="f54b7-137">In Visual Studio, you add a new <xref:System.Windows.Window>, <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Page>, <xref:System.Windows.Documents.FlowDocument>, or <xref:System.Windows.ResourceDictionary> to a project, the `Build Action` for the markup file will default to `Page`.</span></span>  
  
 <span data-ttu-id="f54b7-138">Quando viene compilato un progetto con `Page` elementi, gli elementi [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] vengono convertiti in formato binario e compilati nell'assembly associato.</span><span class="sxs-lookup"><span data-stu-id="f54b7-138">When a project with `Page` items is compiled, the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] items are converted to binary format and compiled into the associated assembly.</span></span> <span data-ttu-id="f54b7-139">Di conseguenza, questi file possono essere utilizzati allo stesso modo dei file di risorse tipici.</span><span class="sxs-lookup"><span data-stu-id="f54b7-139">Consequently, these files can be used in the same way as typical resource files.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f54b7-140">Se un file di [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] viene configurato come elemento `Resource` e non dispone di un file code-behind, la [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] non elaborata viene compilata in un assembly anziché in una versione binaria del [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]non elaborato.</span><span class="sxs-lookup"><span data-stu-id="f54b7-140">If a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file is configured as a `Resource` item, and does not have a code-behind file, the raw [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] is compiled into an assembly rather than a binary version of the raw [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span>  
  
<a name="Content_Files"></a>   
## <a name="content-files"></a><span data-ttu-id="f54b7-141">File di contenuto</span><span class="sxs-lookup"><span data-stu-id="f54b7-141">Content Files</span></span>  
 <span data-ttu-id="f54b7-142">Un *file di contenuto* viene distribuito come file separato insieme a un assembly eseguibile.</span><span class="sxs-lookup"><span data-stu-id="f54b7-142">A *content file* is distributed as a loose file alongside an executable assembly.</span></span> <span data-ttu-id="f54b7-143">Sebbene questi file non vengano compilati in un assembly, dal canto loro gli assembly vengono compilati con i metadati che stabiliscono un'associazione con ciascun file di dati.</span><span class="sxs-lookup"><span data-stu-id="f54b7-143">Although they are not compiled into an assembly, assemblies are compiled with metadata that establishes an association with each content file.</span></span>  
  
 <span data-ttu-id="f54b7-144">È necessario utilizzare i file di dati quando l'applicazione richiede un set specifico di file di dati che possono essere aggiornati senza dover ricompilare l'assembly che li utilizza.</span><span class="sxs-lookup"><span data-stu-id="f54b7-144">You should use content files when your application requires a specific set of application data files that you want to be able to update without recompiling the assembly that consumes them.</span></span>  
  
### <a name="configuring-content-files"></a><span data-ttu-id="f54b7-145">Configurazione dei file di dati</span><span class="sxs-lookup"><span data-stu-id="f54b7-145">Configuring Content Files</span></span>  
 <span data-ttu-id="f54b7-146">Per aggiungere un file di contenuto a un progetto, è necessario includere un file di dati dell'applicazione come elemento `Content`.</span><span class="sxs-lookup"><span data-stu-id="f54b7-146">To add a content file to a project, an application data file must be included as a `Content` item.</span></span> <span data-ttu-id="f54b7-147">Inoltre, poiché un file di contenuto non viene compilato direttamente nell'assembly, è necessario impostare l'elemento di metadati MSBuild `CopyToOutputDirectory` per specificare che il file di contenuto viene copiato in un percorso relativo all'assembly compilato.</span><span class="sxs-lookup"><span data-stu-id="f54b7-147">Furthermore, because a content file is not compiled directly into the assembly, you need to set the MSBuild `CopyToOutputDirectory` metadata element to specify that the content file is copied to a location that is relative to the built assembly.</span></span> <span data-ttu-id="f54b7-148">Se si desidera che la risorsa venga copiata nella cartella dell'output di compilazione ogni volta che viene compilato un progetto, impostare il `CopyToOutputDirectory` elemento dei metadati con il valore di `Always`.</span><span class="sxs-lookup"><span data-stu-id="f54b7-148">If you want the resource to be copied to the build output folder every time a project is built, you set the `CopyToOutputDirectory` metadata element with the `Always` value.</span></span> <span data-ttu-id="f54b7-149">In caso contrario, è possibile assicurarsi che solo la versione più recente della risorsa venga copiata nella cartella dell'output di compilazione usando il valore `PreserveNewest`.</span><span class="sxs-lookup"><span data-stu-id="f54b7-149">Otherwise, you can ensure that only the newest version of the resource is copied to the build output folder by using the `PreserveNewest` value.</span></span>  
  
 <span data-ttu-id="f54b7-150">Di seguito viene illustrato un file configurato come file di dati, che viene copiato nella cartella dell'output di compilazione solo quando una nuova versione della risorsa viene aggiunta al progetto.</span><span class="sxs-lookup"><span data-stu-id="f54b7-150">The following shows a file that is configured as a content file which is copied to the build output folder only when a new version of the resource is added to the project.</span></span>  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003" ... >  
  ...  
  <ItemGroup>  
    <Content Include="ContentFile.xaml">  
      <CopyToOutputDirectory>PreserveNewest</CopyToOutputDirectory>  
    </Content>  
  </ItemGroup>  
  ...  
</Project>  
```  
  
> [!NOTE]
> <span data-ttu-id="f54b7-151">In Visual Studio è possibile creare un file di contenuto aggiungendo un file a un progetto e impostando il relativo `Build Action` su `Content`, quindi impostare la relativa `Copy to Output Directory` su `Copy always` (uguale a `Always`) e `Copy if newer` (uguale a `PreserveNewest`).</span><span class="sxs-lookup"><span data-stu-id="f54b7-151">In Visual Studio, you create a content file by adding a file to a project and setting its `Build Action` to `Content`, and set its `Copy to Output Directory` to `Copy always` (same as `Always`) and `Copy if newer` (same as `PreserveNewest`).</span></span>  
  
 <span data-ttu-id="f54b7-152">Quando il progetto viene compilato, un attributo <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> viene compilato nei metadati dell'assembly per ogni file di contenuto.</span><span class="sxs-lookup"><span data-stu-id="f54b7-152">When the project is built, an <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> attribute is compiled into the metadata of the assembly for each content file.</span></span>  
  
 `[assembly: AssemblyAssociatedContentFile("ContentFile.xaml")]`  
  
 <span data-ttu-id="f54b7-153">Il valore della <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> implica il percorso del file di contenuto rispetto alla relativa posizione nel progetto.</span><span class="sxs-lookup"><span data-stu-id="f54b7-153">The value of the <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> implies the path to the content file relative to its position in the project.</span></span> <span data-ttu-id="f54b7-154">Se, ad esempio, un file di contenuto si trova in una sottocartella del progetto, le informazioni aggiuntive sul percorso verranno incorporate nel valore <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute>.</span><span class="sxs-lookup"><span data-stu-id="f54b7-154">For example, if a content file was located in a project subfolder, the additional path information would be incorporated into the <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> value.</span></span>  
  
 `[assembly: AssemblyAssociatedContentFile("Resources/ContentFile.xaml")]`  
  
 <span data-ttu-id="f54b7-155">Il valore <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> è anche il valore del percorso del file di contenuto nella cartella di output di compilazione.</span><span class="sxs-lookup"><span data-stu-id="f54b7-155">The <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> value is also the value of the path to the content file in the build output folder.</span></span>  
  
### <a name="using-content-files"></a><span data-ttu-id="f54b7-156">Uso dei file di contenuto</span><span class="sxs-lookup"><span data-stu-id="f54b7-156">Using Content Files</span></span>  
 <span data-ttu-id="f54b7-157">Per caricare un file di contenuto, è possibile chiamare il metodo <xref:System.Windows.Application.GetContentStream%2A> della classe <xref:System.Windows.Application>, passando un URI di pacchetto che identifica il file di contenuto desiderato.</span><span class="sxs-lookup"><span data-stu-id="f54b7-157">To load a content file, you can call the <xref:System.Windows.Application.GetContentStream%2A> method of the <xref:System.Windows.Application> class, passing a pack URI that identifies the desired content file.</span></span> <span data-ttu-id="f54b7-158"><xref:System.Windows.Application.GetContentStream%2A> restituisce un oggetto <xref:System.Windows.Resources.StreamResourceInfo>, che espone il file di contenuto come <xref:System.IO.Stream> e ne descrive il tipo di contenuto.</span><span class="sxs-lookup"><span data-stu-id="f54b7-158"><xref:System.Windows.Application.GetContentStream%2A> returns a <xref:System.Windows.Resources.StreamResourceInfo> object, which exposes the content file as a <xref:System.IO.Stream> and describes its content type.</span></span>  
  
 <span data-ttu-id="f54b7-159">Come esempio, il codice seguente illustra come usare <xref:System.Windows.Application.GetContentStream%2A> per caricare un file di contenuto <xref:System.Windows.Controls.Page> e impostarlo come contenuto di un <xref:System.Windows.Controls.Frame> (`pageFrame`).</span><span class="sxs-lookup"><span data-stu-id="f54b7-159">As an example, the following code shows how to use <xref:System.Windows.Application.GetContentStream%2A> to load a <xref:System.Windows.Controls.Page> content file and set it as the content of a <xref:System.Windows.Controls.Frame> (`pageFrame`).</span></span>  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadAPageContentFileManuallyCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.cs#loadapagecontentfilemanuallycode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadAPageContentFileManuallyCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.vb#loadapagecontentfilemanuallycode)]  
  
 <span data-ttu-id="f54b7-160">Quando si chiama <xref:System.Windows.Application.GetContentStream%2A> consente di accedere al <xref:System.IO.Stream>, è necessario eseguire l'operazione aggiuntiva di conversione nel tipo della proprietà che verrà impostata con.</span><span class="sxs-lookup"><span data-stu-id="f54b7-160">While calling <xref:System.Windows.Application.GetContentStream%2A> gives you access to the <xref:System.IO.Stream>, you need to perform the additional work of converting it to the type of the property that you'll be setting it with.</span></span> <span data-ttu-id="f54b7-161">È invece possibile consentire a WPF di gestire l'apertura e la conversione del <xref:System.IO.Stream> caricando un file di risorse direttamente nella proprietà di un tipo usando il codice.</span><span class="sxs-lookup"><span data-stu-id="f54b7-161">Instead, you can let WPF take care of opening and converting the <xref:System.IO.Stream> by loading a resource file directly into the property of a type using code.</span></span>  
  
 <span data-ttu-id="f54b7-162">Nell'esempio seguente viene illustrato come caricare un <xref:System.Windows.Controls.Page> direttamente in una <xref:System.Windows.Controls.Frame> (`pageFrame`) utilizzando il codice.</span><span class="sxs-lookup"><span data-stu-id="f54b7-162">The following example shows how to load a <xref:System.Windows.Controls.Page> directly into a <xref:System.Windows.Controls.Frame> (`pageFrame`) using code.</span></span>  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadPageContentFileFromCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.cs#loadpagecontentfilefromcode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadPageContentFileFromCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.vb#loadpagecontentfilefromcode)]  
  
 <span data-ttu-id="f54b7-163">L'esempio seguente illustra il markup equivalente del precedente esempio.</span><span class="sxs-lookup"><span data-stu-id="f54b7-163">The following example is the markup equivalent of the preceding example.</span></span>  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#LoadPageContentFileFromXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml#loadpagecontentfilefromxaml)]  
  
<a name="Site_of_Origin_Files"></a>   
## <a name="site-of-origin-files"></a><span data-ttu-id="f54b7-164">File del sito di origine</span><span class="sxs-lookup"><span data-stu-id="f54b7-164">Site of Origin Files</span></span>  
 <span data-ttu-id="f54b7-165">I file di risorse hanno una relazione esplicita con gli assembly distribuiti insieme, come definito dall'<xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute>.</span><span class="sxs-lookup"><span data-stu-id="f54b7-165">Resource files have an explicit relationship with the assemblies that they are distributed alongside, as defined by the <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute>.</span></span> <span data-ttu-id="f54b7-166">Talvolta, è tuttavia possibile che si debba stabilire una relazione implicita o inesistente tra un assembly e un file di dati dell'applicazione, come nei casi seguenti:</span><span class="sxs-lookup"><span data-stu-id="f54b7-166">But, there are times when you may want to establish either an implicit or non-existent relationship between an assembly and an application data file, including when:</span></span>  
  
- <span data-ttu-id="f54b7-167">Un file non esiste in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="f54b7-167">A file doesn't exist at compile time.</span></span>  
  
- <span data-ttu-id="f54b7-168">I file richiesti dall'assembly non saranno noti fino alla fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="f54b7-168">You don't know what files your assembly will require until run time.</span></span>  
  
- <span data-ttu-id="f54b7-169">Si desidera avere la possibilità di aggiornare i file senza ricompilare l'assembly al quale sono associati.</span><span class="sxs-lookup"><span data-stu-id="f54b7-169">You want to be able to update files without recompiling the assembly that they are associated with.</span></span>  
  
- <span data-ttu-id="f54b7-170">L'applicazione utilizza file di dati di grandi dimensioni, ad esempio audio e video, che devono essere scaricati dagli utenti unicamente su richiesta.</span><span class="sxs-lookup"><span data-stu-id="f54b7-170">Your application uses large data files, such as audio and video, and you only want users to download them if they choose to.</span></span>  
  
 <span data-ttu-id="f54b7-171">È possibile caricare questi tipi di file usando schemi URI tradizionali, ad esempio gli schemi file:///e http://.</span><span class="sxs-lookup"><span data-stu-id="f54b7-171">It is possible to load these types of files by using traditional URI schemes, such as the file:/// and http:// schemes.</span></span>  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#AbsolutePackUriFileHttpReferenceXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/AbsolutePackUriPage.xaml#absolutepackurifilehttpreferencexaml)]  
  
 <span data-ttu-id="f54b7-172">Tuttavia, gli schemi file:/// e http:// richiedono che l'applicazione abbia un livello di attendibilità totale.</span><span class="sxs-lookup"><span data-stu-id="f54b7-172">However, the file:/// and http:// schemes require your application to have full trust.</span></span> <span data-ttu-id="f54b7-173">Se l'applicazione è un'applicazione browser XAML (XBAP) avviata da Internet o Intranet e richiede solo il set di autorizzazioni consentite per le applicazioni avviate da tali percorsi, i file separati possono essere caricati solo dal sito di origine dell'applicazione (percorso di avvio).</span><span class="sxs-lookup"><span data-stu-id="f54b7-173">If your application is a XAML browser application (XBAP) that was launched from the Internet or intranet, and it requests only the set of permissions that are allowed for applications launched from those locations, loose files can only be loaded from the application's site of origin (launch location).</span></span> <span data-ttu-id="f54b7-174">Tali file sono noti come file *del sito di origine* .</span><span class="sxs-lookup"><span data-stu-id="f54b7-174">Such files are known as *site of origin* files.</span></span>  
  
 <span data-ttu-id="f54b7-175">I file del sito di origine rappresentano l'unica opzione per le applicazioni parzialmente attendibili, benché non siano limitati a questo tipo di applicazione.</span><span class="sxs-lookup"><span data-stu-id="f54b7-175">Site of origin files are the only option for partial trust applications, although are not limited to partial trust applications.</span></span> <span data-ttu-id="f54b7-176">È possibile che le applicazioni completamente attendibili debbano caricare file di dati dell'applicazione sconosciuti in fase di compilazione. Sebbene queste applicazioni possano utilizzare file:///, è probabile che i file di dati dell'applicazione vengano installati nella stessa cartella dell'assembly dell'applicazione o in una sottocartella di questo.</span><span class="sxs-lookup"><span data-stu-id="f54b7-176">Full trust applications may still need to load application data files that they do not know about at build time; while full trust applications could use file:///, it is likely that the application data files will be installed in the same folder as, or a subfolder of, the application assembly.</span></span> <span data-ttu-id="f54b7-177">In questo caso è più facile utilizzare un riferimento al sito di origine piuttosto che file:///, poiché l'utilizzo di file:/// richiede l'elaborazione del percorso completo del file.</span><span class="sxs-lookup"><span data-stu-id="f54b7-177">In this case, using site of origin referencing is easier than using file:///, because using file:/// requires you to work out the full path the file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f54b7-178">I file del sito di origine non vengono memorizzati nella cache con un'applicazione browser XAML (XBAP) in un computer client, mentre i file di contenuto sono.</span><span class="sxs-lookup"><span data-stu-id="f54b7-178">Site of origin files are not cached with an XAML browser application (XBAP) on a client machine, while content files are.</span></span> <span data-ttu-id="f54b7-179">Di conseguenza, vengono scaricati solo se esplicitamente richiesto.</span><span class="sxs-lookup"><span data-stu-id="f54b7-179">Consequently, they are only downloaded when specifically requested.</span></span> <span data-ttu-id="f54b7-180">Se un'applicazione browser XAML (XBAP) contiene file multimediali di grandi dimensioni, la configurazione come file del sito di origine indica che l'avvio iniziale dell'applicazione è molto più veloce e che i file vengono scaricati solo su richiesta.</span><span class="sxs-lookup"><span data-stu-id="f54b7-180">If an XAML browser application (XBAP) application has large media files, configuring them as site of origin files means the initial application launch is much faster, and the files are only downloaded on demand.</span></span>  
  
### <a name="configuring-site-of-origin-files"></a><span data-ttu-id="f54b7-181">Configurazione dei file del sito di origine</span><span class="sxs-lookup"><span data-stu-id="f54b7-181">Configuring Site of Origin Files</span></span>  
 <span data-ttu-id="f54b7-182">Se i file del sito di origine sono inesistenti o sconosciuti in fase di compilazione, è necessario usare i meccanismi di distribuzione tradizionali per garantire che i file necessari siano disponibili in fase di esecuzione, incluso l'uso del programma `XCopy` dalla riga di comando o del Microsoft Windows Installer.</span><span class="sxs-lookup"><span data-stu-id="f54b7-182">If your site of origin files are non-existent or unknown at compile time, you need to use traditional deployment mechanisms for ensuring the required files are available at run time, including using either the `XCopy` command-line program or the Microsoft Windows Installer.</span></span>  
  
 <span data-ttu-id="f54b7-183">Se si conosce in fase di compilazione i file che si desidera individuare nel sito di origine, ma si desidera comunque evitare una dipendenza esplicita, è possibile aggiungere tali file a un progetto MSBuild come `None` elemento.</span><span class="sxs-lookup"><span data-stu-id="f54b7-183">If you do know at compile time the files that you would like to be located at the site of origin, but still want to avoid an explicit dependency, you can add those files to an MSBuild project as `None` item.</span></span> <span data-ttu-id="f54b7-184">Come per i file di contenuto, è necessario impostare l'attributo `CopyToOutputDirectory` di MSBuild per specificare che il file del sito di origine viene copiato in un percorso relativo all'assembly compilato, specificando il valore di `Always` o il valore di `PreserveNewest`.</span><span class="sxs-lookup"><span data-stu-id="f54b7-184">As with content files, you need to set the MSBuild `CopyToOutputDirectory` attribute to specify that the site of origin file is copied to a location that is relative to the built assembly, by specifying either the `Always` value or the `PreserveNewest` value.</span></span>  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003" ... >  
  ...  
  <None Include="PageSiteOfOriginFile.xaml">  
    <CopyToOutputDirectory>Always</CopyToOutputDirectory>  
  </None>  
  ...  
</Project>  
```  
  
> [!NOTE]
> <span data-ttu-id="f54b7-185">In Visual Studio è possibile creare un file del sito di origine aggiungendo un file a un progetto e impostando il relativo `Build Action` su `None`.</span><span class="sxs-lookup"><span data-stu-id="f54b7-185">In Visual Studio, you create a site of origin file by adding a file to a project and setting its `Build Action` to `None`.</span></span>  
  
 <span data-ttu-id="f54b7-186">Quando il progetto viene compilato, MSBuild copia i file specificati nella cartella di output di compilazione.</span><span class="sxs-lookup"><span data-stu-id="f54b7-186">When the project is built, MSBuild copies the specified files to the build output folder.</span></span>  
  
### <a name="using-site-of-origin-files"></a><span data-ttu-id="f54b7-187">Uso dei file del sito di origine</span><span class="sxs-lookup"><span data-stu-id="f54b7-187">Using Site of Origin Files</span></span>  
 <span data-ttu-id="f54b7-188">Per caricare un file del sito di origine, è possibile chiamare il metodo <xref:System.Windows.Application.GetRemoteStream%2A> della classe <xref:System.Windows.Application>, passando un URI di pacchetto che identifica il file del sito di origine desiderato.</span><span class="sxs-lookup"><span data-stu-id="f54b7-188">To load a site of origin file, you can call the <xref:System.Windows.Application.GetRemoteStream%2A> method of the <xref:System.Windows.Application> class, passing a pack URI that identifies the desired site of origin file.</span></span> <span data-ttu-id="f54b7-189"><xref:System.Windows.Application.GetRemoteStream%2A> restituisce un oggetto <xref:System.Windows.Resources.StreamResourceInfo>, che espone il file del sito di origine come <xref:System.IO.Stream> e ne descrive il tipo di contenuto.</span><span class="sxs-lookup"><span data-stu-id="f54b7-189"><xref:System.Windows.Application.GetRemoteStream%2A> returns a <xref:System.Windows.Resources.StreamResourceInfo> object, which exposes the site of origin file as a <xref:System.IO.Stream> and describes its content type.</span></span>  
  
 <span data-ttu-id="f54b7-190">Come esempio, il codice seguente illustra come usare <xref:System.Windows.Application.GetRemoteStream%2A> per caricare un file del sito di origine <xref:System.Windows.Controls.Page> e impostarlo come contenuto di un <xref:System.Windows.Controls.Frame> (`pageFrame`).</span><span class="sxs-lookup"><span data-stu-id="f54b7-190">As an example, the following code shows how to use <xref:System.Windows.Application.GetRemoteStream%2A> to load a <xref:System.Windows.Controls.Page> site of origin file and set it as the content of a <xref:System.Windows.Controls.Frame> (`pageFrame`).</span></span>  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadAPageSOOFileManuallyCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/SOOPage.xaml.cs#loadapagesoofilemanuallycode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadAPageSOOFileManuallyCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/SOOPage.xaml.vb#loadapagesoofilemanuallycode)]  
  
 <span data-ttu-id="f54b7-191">Quando si chiama <xref:System.Windows.Application.GetRemoteStream%2A> consente di accedere al <xref:System.IO.Stream>, è necessario eseguire l'operazione aggiuntiva di conversione nel tipo della proprietà che verrà impostata con.</span><span class="sxs-lookup"><span data-stu-id="f54b7-191">While calling <xref:System.Windows.Application.GetRemoteStream%2A> gives you access to the <xref:System.IO.Stream>, you need to perform the additional work of converting it to the type of the property that you'll be setting it with.</span></span> <span data-ttu-id="f54b7-192">È invece possibile consentire a WPF di gestire l'apertura e la conversione del <xref:System.IO.Stream> caricando un file di risorse direttamente nella proprietà di un tipo usando il codice.</span><span class="sxs-lookup"><span data-stu-id="f54b7-192">Instead, you can let WPF take care of opening and converting the <xref:System.IO.Stream> by loading a resource file directly into the property of a type using code.</span></span>  
  
 <span data-ttu-id="f54b7-193">Nell'esempio seguente viene illustrato come caricare un <xref:System.Windows.Controls.Page> direttamente in una <xref:System.Windows.Controls.Frame> (`pageFrame`) utilizzando il codice.</span><span class="sxs-lookup"><span data-stu-id="f54b7-193">The following example shows how to load a <xref:System.Windows.Controls.Page> directly into a <xref:System.Windows.Controls.Frame> (`pageFrame`) using code.</span></span>  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadPageSOOFileFromCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/SOOPage.xaml.cs#loadpagesoofilefromcode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadPageSOOFileFromCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/SOOPage.xaml.vb#loadpagesoofilefromcode)]  
  
 <span data-ttu-id="f54b7-194">L'esempio seguente illustra il markup equivalente del precedente esempio.</span><span class="sxs-lookup"><span data-stu-id="f54b7-194">The following example is the markup equivalent of the preceding example.</span></span>  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#LoadPageSOOFileFromXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/SOOPage.xaml#loadpagesoofilefromxaml)]  
  
<a name="Rebuilding_after_Changing_Build_Type"></a>   
## <a name="rebuilding-after-changing-build-type"></a><span data-ttu-id="f54b7-195">Ricompilazione in seguito alla modifica del tipo di compilazione</span><span class="sxs-lookup"><span data-stu-id="f54b7-195">Rebuilding After Changing Build Type</span></span>  
 <span data-ttu-id="f54b7-196">Dopo avere modificato il tipo di compilazione di un file di dati dell'applicazione, è necessario ricompilare l'intera applicazione affinché le modifiche vengano applicate.</span><span class="sxs-lookup"><span data-stu-id="f54b7-196">After you change the build type of an application data file, you need to rebuild the entire application to ensure those changes are applied.</span></span> <span data-ttu-id="f54b7-197">Se ci si limita a compilare l'applicazione, le modifiche non vengono applicate.</span><span class="sxs-lookup"><span data-stu-id="f54b7-197">If you only build the application, the changes are not applied.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f54b7-198">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f54b7-198">See also</span></span>

- [<span data-ttu-id="f54b7-199">URI di tipo pack in WPF</span><span class="sxs-lookup"><span data-stu-id="f54b7-199">Pack URIs in WPF</span></span>](pack-uris-in-wpf.md)
