---
title: Includere i tipi di carattere nel pacchetto delle applicazioni
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- applications [WPF], packaging fonts with
- fonts [WPF], packaging with applications
- typography [WPF], packaging fonts with applications
- packaging fonts with applications [WPF]
ms.assetid: db15ee48-4d24-49f5-8b9d-a64460865286
ms.openlocfilehash: 7bdf3b11557d94ab39c93a21ac53b917e3a1767d
ms.sourcegitcommit: 839777281a281684a7e2906dccb3acd7f6a32023
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/24/2020
ms.locfileid: "82141125"
---
# <a name="packaging-fonts-with-applications"></a><span data-ttu-id="b1c18-102">Includere i tipi di carattere nel pacchetto delle applicazioni</span><span class="sxs-lookup"><span data-stu-id="b1c18-102">Packaging Fonts with Applications</span></span>
<span data-ttu-id="b1c18-103">In questo argomento viene fornita una panoramica su come creare un pacchetto [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] di tipi di carattere con l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b1c18-103">This topic provides an overview of how to package fonts with your [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] application.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b1c18-104">Come con la maggior parte delle applicazioni software, i file dei tipi di carattere vengono concessi in licenza e non venduti.</span><span class="sxs-lookup"><span data-stu-id="b1c18-104">As with most types of software, font files are licensed, rather than sold.</span></span> <span data-ttu-id="b1c18-105">Le licenze che regolano l'utilizzo dei tipi di carattere variano a seconda del fornitore, ma in generale la maggior parte delle licenze, incluse quelle relative ai tipi di carattere forniti da Microsoft con le applicazioni e Windows, non consentono di incorporare i tipi di carattere all'interno delle applicazioni o di ridistribuirli.</span><span class="sxs-lookup"><span data-stu-id="b1c18-105">Licenses that govern the use of fonts vary from vendor to vendor but in general most licenses, including those covering the fonts Microsoft supplies with applications and Windows, do not allow the fonts to be embedded within applications or otherwise redistributed.</span></span> <span data-ttu-id="b1c18-106">Per questo motivo, gli sviluppatori sono tenuti ad assicurarsi che l'utente abbia i diritti di licenza separati per qualsiasi tipo di carattere incorporato in un'applicazione o ridistribuito in altro modo.</span><span class="sxs-lookup"><span data-stu-id="b1c18-106">Therefore, as a developer it is your responsibility to ensure that you have the required license rights for any font you embed within an application or otherwise redistribute.</span></span>  

<a name="introduction_to_packaging_fonts"></a>
## <a name="introduction-to-packaging-fonts"></a><span data-ttu-id="b1c18-107">Introduzione all'inclusione dei tipi di carattere nel pacchetto</span><span class="sxs-lookup"><span data-stu-id="b1c18-107">Introduction to Packaging Fonts</span></span>  
 <span data-ttu-id="b1c18-108">È possibile creare facilmente pacchetti di tipi di carattere [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] come risorse all'interno delle applicazioni per visualizzare il testo dell'interfaccia utente e altri tipi di contenuto basato su testo.</span><span class="sxs-lookup"><span data-stu-id="b1c18-108">You can easily package fonts as resources within your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications to display user interface text and other types of text based content.</span></span> <span data-ttu-id="b1c18-109">I tipi di carattere possono essere separati o incorporati nei file di assembly dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b1c18-109">The fonts can be separate from or embedded within the application's assembly files.</span></span> <span data-ttu-id="b1c18-110">È anche possibile creare una libreria di tipi di carattere di sole risorse, a cui l'applicazione può fare riferimento.</span><span class="sxs-lookup"><span data-stu-id="b1c18-110">You can also create a resource-only font library, which your application can reference.</span></span>  
  
 <span data-ttu-id="b1c18-111">I tipi di carattere OpenType e TrueType® contengono un flag di tipo, fsType, che indica i diritti di licenza per l'incorporamento del tipo di carattere.</span><span class="sxs-lookup"><span data-stu-id="b1c18-111">OpenType and TrueType® fonts contain a type flag, fsType, that indicates font embedding licensing rights for the font.</span></span> <span data-ttu-id="b1c18-112">Questo flag di tipo, tuttavia, fa riferimento solo ai tipi di carattere incorporati archiviati in un documento e non ai tipi di carattere incorporati in un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b1c18-112">However, this type flag only refers to embedded fonts stored in a document–it does not refer to fonts embedded in an application.</span></span> <span data-ttu-id="b1c18-113">È possibile recuperare i diritti di incorporamento del tipo di carattere per un <xref:System.Windows.Media.GlyphTypeface> tipo di carattere creando <xref:System.Windows.Media.GlyphTypeface.EmbeddingRights%2A> un oggetto e facendo riferimento alla relativa proprietà.</span><span class="sxs-lookup"><span data-stu-id="b1c18-113">You can retrieve the font embedding rights for a font by creating a <xref:System.Windows.Media.GlyphTypeface> object and referencing its <xref:System.Windows.Media.GlyphTypeface.EmbeddingRights%2A> property.</span></span> <span data-ttu-id="b1c18-114">Per ulteriori informazioni sul flag fsType, vedere la sezione "metriche del sistema operativo/2 e Windows" della [specifica OpenType](https://www.microsoft.com/typography/otspec/os2.htm) .</span><span class="sxs-lookup"><span data-stu-id="b1c18-114">Refer to the "OS/2 and Windows Metrics" section of the [OpenType Specification](https://www.microsoft.com/typography/otspec/os2.htm) for more information on the fsType flag.</span></span>  
  
 <span data-ttu-id="b1c18-115">Il sito Web [Microsoft Typography](https://docs.microsoft.com/typography/) include informazioni di contatto che consentono di individuare un particolare fornitore di tipi di carattere o trovare un fornitore di tipi di carattere per il lavoro personalizzato.</span><span class="sxs-lookup"><span data-stu-id="b1c18-115">The [Microsoft Typography](https://docs.microsoft.com/typography/) Web site includes contact information that can help you locate a particular font vendor or find a font vendor for custom work.</span></span>  
  
<a name="adding_fonts_as_content_items"></a>
## <a name="adding-fonts-as-content-items"></a><span data-ttu-id="b1c18-116">Aggiunta di tipi di carattere come elementi di contenuto</span><span class="sxs-lookup"><span data-stu-id="b1c18-116">Adding Fonts as Content Items</span></span>  
 <span data-ttu-id="b1c18-117">È possibile aggiungere tipi di carattere all'applicazione come elementi di contenuto del progetto separati dai file di assembly dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b1c18-117">You can add fonts to your application as project content items that are separate from the application's assembly files.</span></span> <span data-ttu-id="b1c18-118">Gli elementi di contenuto non vengono quindi incorporati come risorse in un assembly.</span><span class="sxs-lookup"><span data-stu-id="b1c18-118">This means that content items are not embedded as resources within an assembly.</span></span> <span data-ttu-id="b1c18-119">L'esempio di file di progetto seguente illustra come definire gli elementi di contenuto.</span><span class="sxs-lookup"><span data-stu-id="b1c18-119">The following project file example shows how to define content items.</span></span>  
  
```xml  
<Project DefaultTargets="Build"  
                xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  <!-- Other project build settings ... -->  
  
  <ItemGroup>  
    <Content Include="Peric.ttf" />  
    <Content Include="Pericl.ttf" />  
  </ItemGroup>  
</Project>  
```  
  
 <span data-ttu-id="b1c18-120">Per assicurarsi che l'applicazione possa usare i tipi di carattere in fase di esecuzione, i tipi di carattere devono essere accessibili nella directory di distribuzione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b1c18-120">In order to ensure that the application can use the fonts at run time, the fonts must be accessible in the application's deployment directory.</span></span> <span data-ttu-id="b1c18-121">L' `<CopyToOutputDirectory>` elemento nel file di progetto dell'applicazione consente di copiare automaticamente i tipi di carattere nella directory di distribuzione dell'applicazione durante il processo di compilazione.</span><span class="sxs-lookup"><span data-stu-id="b1c18-121">The `<CopyToOutputDirectory>` element in the application's project file allows you to automatically copy the fonts to the application deployment directory during the build process.</span></span> <span data-ttu-id="b1c18-122">L'esempio di file di progetto seguente illustra come copiare i tipi di carattere nella directory di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="b1c18-122">The following project file example shows how to copy fonts to the deployment directory.</span></span>  
  
```xml  
<ItemGroup>  
  <Content Include="Peric.ttf">  
    <CopyToOutputDirectory>PreserveNewest</CopyToOutputDirectory>  
  </Content>  
  <Content Include="Pericl.ttf">  
    <CopyToOutputDirectory>PreserveNewest</CopyToOutputDirectory>  
  </Content>  
</ItemGroup>  
```  
  
 <span data-ttu-id="b1c18-123">L'esempio di codice seguente illustra come fare riferimento al tipo di carattere dell'applicazione come elemento di contenuto. L'elemento di contenuto a cui si fa riferimento deve essere nella stessa directory dei file di assembly dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b1c18-123">The following code example shows how to reference the application's font as a content item—the referenced content item must be in the same directory as the application's assembly files.</span></span>  
  
 [!code-xaml[FontSnippets#FontPackageSnippet8](~/samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/FontPackageSnippets.xaml#fontpackagesnippet8)]  
  
<a name="adding_fonts_as_resource_items"></a>
## <a name="adding-fonts-as-resource-items"></a><span data-ttu-id="b1c18-124">Aggiunta di tipi di carattere come elementi risorsa</span><span class="sxs-lookup"><span data-stu-id="b1c18-124">Adding Fonts as Resource Items</span></span>  
 <span data-ttu-id="b1c18-125">È possibile aggiungere tipi di carattere all'applicazione come elementi risorsa del progetto incorporati nei file di assembly dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b1c18-125">You can add fonts to your application as project resource items that are embedded within the application's assembly files.</span></span> <span data-ttu-id="b1c18-126">L'uso di una sottodirectory separata per le risorse consente di organizzare i file di progetto dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b1c18-126">Using a separate subdirectory for resources helps to organize the application's project files.</span></span> <span data-ttu-id="b1c18-127">L'esempio di file di progetto seguente illustra come definire i tipi di carattere come elementi risorsa in una sottodirectory separata.</span><span class="sxs-lookup"><span data-stu-id="b1c18-127">The following project file example shows how to define fonts as resource items in a separate subdirectory.</span></span>  
  
```xml  
<Project DefaultTargets="Build"  
                xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  <!-- Other project build settings ... -->  
  
  <ItemGroup>  
    <Resource Include="resources\Peric.ttf" />  
    <Resource Include="resources\Pericl.ttf" />  
  </ItemGroup>  
</Project>  
```  
  
> [!NOTE]
> <span data-ttu-id="b1c18-128">Quando si aggiungono tipi di carattere come risorse all'applicazione, assicurarsi di impostare l' `<Resource>` elemento e non l' `<EmbeddedResource>` elemento nel file di progetto dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b1c18-128">When you add fonts as resources to your application, make sure you are setting the `<Resource>` element, and not the `<EmbeddedResource>` element in your application's project file.</span></span> <span data-ttu-id="b1c18-129">L' `<EmbeddedResource>` elemento per l'azione di compilazione non è supportato.</span><span class="sxs-lookup"><span data-stu-id="b1c18-129">The `<EmbeddedResource>` element for the build action is not supported.</span></span>  
  
 <span data-ttu-id="b1c18-130">L'esempio di markup seguente illustra come fare riferimento alle risorse dei tipi di carattere dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b1c18-130">The following markup example shows how to reference the application's font resources.</span></span>  
  
 [!code-xaml[FontSnippets#FontPackageSnippet1](~/samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/FontPackageSnippets.xaml#fontpackagesnippet1)]  
  
### <a name="referencing-font-resource-items-from-code"></a><span data-ttu-id="b1c18-131">Riferimento agli elementi risorsa dei tipi di carattere dal codice</span><span class="sxs-lookup"><span data-stu-id="b1c18-131">Referencing Font Resource Items from Code</span></span>  
 <span data-ttu-id="b1c18-132">Per fare riferimento agli elementi delle risorse del tipo di carattere dal codice, è necessario fornire un riferimento a una risorsa del tipo di carattere in due parti: URI (Uniform Resource Identifier) di base. e il riferimento al percorso del tipo di carattere.</span><span class="sxs-lookup"><span data-stu-id="b1c18-132">In order to reference font resource items from code, you must supply a two-part font resource reference: the base uniform resource identifier (URI); and the font location reference.</span></span> <span data-ttu-id="b1c18-133">Questi valori vengono usati come parametri per il <xref:System.Windows.Media.FontFamily.%23ctor%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="b1c18-133">These values are used as the parameters for the <xref:System.Windows.Media.FontFamily.%23ctor%2A> method.</span></span> <span data-ttu-id="b1c18-134">Nell'esempio di codice seguente viene illustrato come fare riferimento alle risorse dei tipi di carattere dell'applicazione nella `resources`sottodirectory del progetto denominata.</span><span class="sxs-lookup"><span data-stu-id="b1c18-134">The following code example shows how to reference the application's font resources in the project subdirectory called `resources`.</span></span>  
  
 [!code-csharp[FontSnippets#FontPackageSnippet2](~/samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/FontPackageSnippets.xaml.cs#fontpackagesnippet2)]
 [!code-vb[FontSnippets#FontPackageSnippet2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FontSnippets/visualbasic/fontpackagesnippets.xaml.vb#fontpackagesnippet2)]  
  
 <span data-ttu-id="b1c18-135">L'URI (Uniform Resource Identifier) di base può includere la sottodirectory dell'applicazione in cui risiede la risorsa del tipo di carattere.</span><span class="sxs-lookup"><span data-stu-id="b1c18-135">The base uniform resource identifier (URI) can include the application subdirectory where the font resource resides.</span></span> <span data-ttu-id="b1c18-136">In questo caso, non è necessario specificare una directory per il riferimento al percorso dei tipi di carattere, ma è necessario includere`./`un carattere "" che indica che la risorsa del tipo di carattere si trova nella stessa directory specificata dall'URI (Uniform Resource Identifier) di base.</span><span class="sxs-lookup"><span data-stu-id="b1c18-136">In this case, the font location reference would not need to specify a directory, but would have to include a leading "`./`", which indicates the font resource is in the same directory specified by the base uniform resource identifier (URI).</span></span> <span data-ttu-id="b1c18-137">L'esempio di codice seguente illustra un modo alternativo per fare riferimento all'elemento risorsa dei tipi di carattere, che equivale all'esempio di codice precedente.</span><span class="sxs-lookup"><span data-stu-id="b1c18-137">The following code example shows an alternate way of referencing the font resource item—it is equivalent to the previous code example.</span></span>  
  
 [!code-csharp[FontSnippets#FontPackageSnippet5](~/samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/FontPackageSnippets.xaml.cs#fontpackagesnippet5)]
 [!code-vb[FontSnippets#FontPackageSnippet5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FontSnippets/visualbasic/fontpackagesnippets.xaml.vb#fontpackagesnippet5)]  
  
### <a name="referencing-fonts-from-the-same-application-subdirectory"></a><span data-ttu-id="b1c18-138">Riferimento ai tipi di carattere dalla stessa sottodirectory dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="b1c18-138">Referencing Fonts from the Same Application Subdirectory</span></span>  
 <span data-ttu-id="b1c18-139">È possibile inserire sia il contenuto dell'applicazione che i file di risorse nella stessa sottodirectory definita dall'utente del progetto dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b1c18-139">You can place both application content and resource files within the same user-defined subdirectory of your application project.</span></span> <span data-ttu-id="b1c18-140">L'esempio di file di progetto seguente illustra una pagina contenuto e le risorse dei tipi di carattere definite nella stessa sottodirectory.</span><span class="sxs-lookup"><span data-stu-id="b1c18-140">The following project file example shows a content page and font resources defined in the same subdirectory.</span></span>  
  
```xml  
<ItemGroup>  
  <Page Include="pages\HomePage.xaml" />  
</ItemGroup>  
<ItemGroup>  
  <Resource Include="pages\Peric.ttf" />  
  <Resource Include="pages\Pericl.ttf" />  
</ItemGroup>  
```  
  
 <span data-ttu-id="b1c18-141">Poiché il tipo di carattere e il contenuto dell'applicazione sono nella stessa sottodirectory, il riferimento al tipo di carattere è relativo al contenuto dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b1c18-141">Since the application content and font are in the same subdirectory, the font reference is relative to the application content.</span></span> <span data-ttu-id="b1c18-142">Gli esempi seguenti illustrano come fare riferimento alla risorsa del tipo di carattere dell'applicazione quando il tipo di carattere è nella stessa directory dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b1c18-142">The following examples show how to reference the application's font resource when the font is in the same directory as the application.</span></span>  
  
 [!code-xaml[FontSnippets#FontPackageSnippet3](~/samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/pages/HomePage.xaml#fontpackagesnippet3)]  
  
 [!code-csharp[FontSnippets#FontPackageSnippet4](~/samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/pages/HomePage.xaml.cs#fontpackagesnippet4)]
 [!code-vb[FontSnippets#FontPackageSnippet4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FontSnippets/visualbasic/pages/homepage.xaml.vb#fontpackagesnippet4)]  
  
### <a name="enumerating-fonts-in-an-application"></a><span data-ttu-id="b1c18-143">Enumerazione di tipi di carattere in un'applicazione</span><span class="sxs-lookup"><span data-stu-id="b1c18-143">Enumerating Fonts in an Application</span></span>  
 <span data-ttu-id="b1c18-144">Per enumerare i tipi di carattere come elementi di risorsa nell'applicazione <xref:System.Windows.Media.Fonts.GetFontFamilies%2A> , <xref:System.Windows.Media.Fonts.GetTypefaces%2A> usare il metodo o.</span><span class="sxs-lookup"><span data-stu-id="b1c18-144">To enumerate fonts as resource items in your application, use either the <xref:System.Windows.Media.Fonts.GetFontFamilies%2A> or <xref:System.Windows.Media.Fonts.GetTypefaces%2A> method.</span></span> <span data-ttu-id="b1c18-145">Nell'esempio seguente viene illustrato come utilizzare il <xref:System.Windows.Media.Fonts.GetFontFamilies%2A> metodo per restituire la raccolta di <xref:System.Windows.Media.FontFamily> oggetti dal percorso dei tipi di carattere dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b1c18-145">The following example shows how to use the <xref:System.Windows.Media.Fonts.GetFontFamilies%2A> method to return the collection of <xref:System.Windows.Media.FontFamily> objects from the application font location.</span></span> <span data-ttu-id="b1c18-146">In questo caso, l'applicazione contiene una sottodirectory denominata "resources".</span><span class="sxs-lookup"><span data-stu-id="b1c18-146">In this case, the application contains a subdirectory named "resources".</span></span>  
  
 [!code-csharp[FontSnippets#FontsSnippet3](~/samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/FontFamilySnippets.xaml.cs#fontssnippet3)]
 [!code-vb[FontSnippets#FontsSnippet3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FontSnippets/visualbasic/fontfamilysnippets.xaml.vb#fontssnippet3)]  
  
 <span data-ttu-id="b1c18-147">Nell'esempio seguente viene illustrato come utilizzare il <xref:System.Windows.Media.Fonts.GetTypefaces%2A> metodo per restituire la raccolta di <xref:System.Windows.Media.Typeface> oggetti dal percorso dei tipi di carattere dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b1c18-147">The following example shows how to use the <xref:System.Windows.Media.Fonts.GetTypefaces%2A> method to return the collection of <xref:System.Windows.Media.Typeface> objects from the application font location.</span></span> <span data-ttu-id="b1c18-148">In questo caso, l'applicazione contiene una sottodirectory denominata "resources".</span><span class="sxs-lookup"><span data-stu-id="b1c18-148">In this case, the application contains a subdirectory named "resources".</span></span>  
  
 [!code-csharp[FontSnippets#FontsSnippet7](~/samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/FontFamilySnippets.xaml.cs#fontssnippet7)]
 [!code-vb[FontSnippets#FontsSnippet7](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FontSnippets/visualbasic/fontfamilysnippets.xaml.vb#fontssnippet7)]  
  
<a name="creating_a_font_resource_library"></a>
## <a name="creating-a-font-resource-library"></a><span data-ttu-id="b1c18-149">Creazione di una libreria di risorse tipo di carattere</span><span class="sxs-lookup"><span data-stu-id="b1c18-149">Creating a Font Resource Library</span></span>  
 <span data-ttu-id="b1c18-150">È possibile creare una libreria di sole risorse contenente solo tipi di carattere. Nessun codice fa parte di questo tipo di progetto libreria.</span><span class="sxs-lookup"><span data-stu-id="b1c18-150">You can create a resource-only library that contains only fonts—no code is part of this type of library project.</span></span> <span data-ttu-id="b1c18-151">La creazione di una libreria di sole risorse è una tecnica comune per disaccoppiare le risorse dal codice dell'applicazione che le usa</span><span class="sxs-lookup"><span data-stu-id="b1c18-151">Creating a resource-only library is a common technique for decoupling resources from the application code that uses them.</span></span> <span data-ttu-id="b1c18-152">e consente anche di includere l'assembly di librerie in più progetti di applicazione.</span><span class="sxs-lookup"><span data-stu-id="b1c18-152">This also allows the library assembly to be included with multiple application projects.</span></span> <span data-ttu-id="b1c18-153">L'esempio di file di progetto seguente illustra le parti chiave di un progetto di libreria di sole risorse.</span><span class="sxs-lookup"><span data-stu-id="b1c18-153">The following project file example shows the key portions of a resource-only library project.</span></span>  
  
```xml  
<PropertyGroup>  
  <AssemblyName>FontLibrary</AssemblyName>  
  <OutputType>library</OutputType>  
  ...  
</PropertyGroup>  
...
<ItemGroup>  
  <Resource Include="Kooten.ttf" />  
  <Resource Include="Pesca.ttf" />  
</ItemGroup  
```  
  
### <a name="referencing-a-font-in-a-resource-library"></a><span data-ttu-id="b1c18-154">Riferimento a un tipo di carattere in una libreria di risorse</span><span class="sxs-lookup"><span data-stu-id="b1c18-154">Referencing a Font in a Resource Library</span></span>  
 <span data-ttu-id="b1c18-155">Per fare riferimento a un tipo di carattere in una libreria di risorse dall'applicazione, è necessario far precedere il riferimento al tipo di carattere dal nome dell'assembly di librerie.</span><span class="sxs-lookup"><span data-stu-id="b1c18-155">To reference a font in a resource library from your application, you must prefix the font reference with the name of the library assembly.</span></span> <span data-ttu-id="b1c18-156">In questo caso, l'assembly di risorse del tipo di carattere è "FontLibrary".</span><span class="sxs-lookup"><span data-stu-id="b1c18-156">In this case, the font resource assembly is "FontLibrary".</span></span> <span data-ttu-id="b1c18-157">Per separare il nome dell'assembly dal riferimento nell'assembly, usare un carattere ";".</span><span class="sxs-lookup"><span data-stu-id="b1c18-157">To separate the assembly name from the reference within the assembly, use a ';' character.</span></span> <span data-ttu-id="b1c18-158">Aggiungendo la parola chiave "Component" seguita dal riferimento al nome del tipo di carattere, si completa l'intero riferimento alla risorsa della libreria di tipi di carattere.</span><span class="sxs-lookup"><span data-stu-id="b1c18-158">Adding the "Component" keyword followed by the reference to the font name completes the full reference to the font library's resource.</span></span> <span data-ttu-id="b1c18-159">L'esempio di codice seguente illustra come fare riferimento a un tipo di carattere in un assembly di librerie di risorse.</span><span class="sxs-lookup"><span data-stu-id="b1c18-159">The following code example shows how to reference a font in a resource library assembly.</span></span>  
  
 [!code-xaml[OpenTypeFontsSample#OpenTypeFontsSample1](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontsSample/CS/Kootenay.xaml#opentypefontssample1)]  
  
> [!NOTE]
> <span data-ttu-id="b1c18-160">Questo SDK contiene un set di tipi di carattere OpenType di esempio che è [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] possibile usare con le applicazioni.</span><span class="sxs-lookup"><span data-stu-id="b1c18-160">This SDK contains a set of sample OpenType fonts that you can use with [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications.</span></span> <span data-ttu-id="b1c18-161">I tipi di carattere sono definiti in una libreria di sole risorse.</span><span class="sxs-lookup"><span data-stu-id="b1c18-161">The fonts are defined in a resource-only library.</span></span> <span data-ttu-id="b1c18-162">Per ulteriori informazioni, vedere [Sample OpenType Font Pack](sample-opentype-font-pack.md).</span><span class="sxs-lookup"><span data-stu-id="b1c18-162">For more information, see [Sample OpenType Font Pack](sample-opentype-font-pack.md).</span></span>  
  
<a name="limitations_on_font_usage"></a>
## <a name="limitations-on-font-usage"></a><span data-ttu-id="b1c18-163">Limitazioni all'utilizzo dei tipi di carattere</span><span class="sxs-lookup"><span data-stu-id="b1c18-163">Limitations on Font Usage</span></span>  
 <span data-ttu-id="b1c18-164">L'elenco seguente descrive diverse limitazioni relative alla creazione di pacchetti e all'uso [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] di tipi di carattere nelle applicazioni:</span><span class="sxs-lookup"><span data-stu-id="b1c18-164">The following list describes several limitations on the packaging and use of fonts in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications:</span></span>  
  
- <span data-ttu-id="b1c18-165">**Bit autorizzazione per l'incorporamento tipi di carattere:** [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] le applicazioni non controllano né applicano bit di autorizzazione per l'incorporamento tipi di carattere.</span><span class="sxs-lookup"><span data-stu-id="b1c18-165">**Font embedding permission bits:** [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications do not check or enforce any font embedding permission bits.</span></span> <span data-ttu-id="b1c18-166">Per ulteriori informazioni, vedere la sezione relativa ai [tipi di carattere Introduction_to_Packing](#introduction_to_packaging_fonts) .</span><span class="sxs-lookup"><span data-stu-id="b1c18-166">See the [Introduction_to_Packing Fonts](#introduction_to_packaging_fonts) section for more information.</span></span>  
  
- <span data-ttu-id="b1c18-167">**Tipi di carattere del sito di origine:** [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] le applicazioni non consentono un riferimento a un tipo di carattere a un URI (Uniform Resource Identifier) http o FTP.</span><span class="sxs-lookup"><span data-stu-id="b1c18-167">**Site of origin fonts:** [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications do not allow a font reference to an http or ftp uniform resource identifier (URI).</span></span>  
  
- <span data-ttu-id="b1c18-168">**URI assoluto con la notazione Pack:** [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] le applicazioni non consentono di creare un <xref:System.Windows.Media.FontFamily> oggetto a livello di codice usando "Pack:" come parte del riferimento URI (Uniform Resource Identifier) assoluto a un tipo di carattere.</span><span class="sxs-lookup"><span data-stu-id="b1c18-168">**Absolute URI using the pack: notation:** [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications do not allow you to create a <xref:System.Windows.Media.FontFamily> object programmatically using "pack:" as part of the absolute uniform resource identifier (URI) reference to a font.</span></span> <span data-ttu-id="b1c18-169">Ad esempio, `"pack://application:,,,/resources/#Pericles Light"` è un riferimento al tipo di carattere non valido.</span><span class="sxs-lookup"><span data-stu-id="b1c18-169">For example, `"pack://application:,,,/resources/#Pericles Light"` is an invalid font reference.</span></span>  
  
- <span data-ttu-id="b1c18-170">**Incorporamento tipi di carattere automatico:** durante la fase di progettazione, non è disponibile il supporto per cercare l'uso dei tipi di carattere di un'applicazione e incorporare automaticamente i tipi di carattere nelle risorse dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b1c18-170">**Automatic font embedding:** During design time, there is no support for searching an application's use of fonts and automatically embedding the fonts in the application's resources.</span></span>  
  
- <span data-ttu-id="b1c18-171">\*\*Subset di tipi di carattere: le applicazioni \*\* [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] non supportano la creazione di subset di tipi di carattere per documenti non statici.</span><span class="sxs-lookup"><span data-stu-id="b1c18-171">**Font subsets:** [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications do not support the creation of font subsets for non-fixed documents.</span></span>  
  
- <span data-ttu-id="b1c18-172">Se è presente un riferimento non corretto, l'applicazione torna a usare un tipo di carattere disponibile.</span><span class="sxs-lookup"><span data-stu-id="b1c18-172">In cases where there is an incorrect reference, the application falls back to using an available font.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1c18-173">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="b1c18-173">See also</span></span>

- <xref:System.Windows.Documents.Typography>
- <xref:System.Windows.Media.FontFamily>
- <span data-ttu-id="b1c18-174">[Microsoft Typography: Links, News, and Contacts](https://docs.microsoft.com/typography/) (Microsoft Typography: collegamenti, novità e contatti)</span><span class="sxs-lookup"><span data-stu-id="b1c18-174">[Microsoft Typography: Links, News, and Contacts](https://docs.microsoft.com/typography/)</span></span>
- [<span data-ttu-id="b1c18-175">Specifica OpenType</span><span class="sxs-lookup"><span data-stu-id="b1c18-175">OpenType Specification</span></span>](https://www.microsoft.com/typography/otspec/)
- [<span data-ttu-id="b1c18-176">Funzionalità dei tipi di carattere OpenType</span><span class="sxs-lookup"><span data-stu-id="b1c18-176">OpenType Font Features</span></span>](opentype-font-features.md)
- [<span data-ttu-id="b1c18-177">Esempio di pacchetto di tipi di carattere OpenType</span><span class="sxs-lookup"><span data-stu-id="b1c18-177">Sample OpenType Font Pack</span></span>](sample-opentype-font-pack.md)
