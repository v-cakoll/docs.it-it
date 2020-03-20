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
ms.openlocfilehash: cef2ae26ec4fccd25ca193ba7d441969f36b25a8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187085"
---
# <a name="packaging-fonts-with-applications"></a>Includere i tipi di carattere nel pacchetto delle applicazioni
In questo argomento viene fornita una [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] panoramica su come creare un pacchetto di tipi di carattere con l'applicazione.  
  
> [!NOTE]
> Come con la maggior parte delle applicazioni software, i file dei tipi di carattere vengono concessi in licenza e non venduti. Le licenze che regolano l'uso dei tipi di carattere variano da fornitore a fornitore, ma in generale la maggior parte delle licenze, incluse quelle che coprono i tipi di carattere forniti da Microsoft con applicazioni e Windows, non consentono l'incorporamento dei tipi di carattere nelle applicazioni o ridistribuiti in altro modo. Per questo motivo, gli sviluppatori sono tenuti ad assicurarsi che l'utente abbia i diritti di licenza separati per qualsiasi tipo di carattere incorporato in un'applicazione o ridistribuito in altro modo.  

<a name="introduction_to_packaging_fonts"></a>
## <a name="introduction-to-packaging-fonts"></a>Introduzione all'inclusione dei tipi di carattere nel pacchetto  
 È possibile creare facilmente pacchetti [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] di tipi di carattere come risorse all'interno delle applicazioni per visualizzare il testo dell'interfaccia utente e altri tipi di contenuto basato su testo. I tipi di carattere possono essere separati o incorporati nei file di assembly dell'applicazione. È anche possibile creare una libreria di tipi di carattere di sole risorse, a cui l'applicazione può fare riferimento.  
  
 I tipi di carattere OpenType e TrueType® contengono un flag di tipo, fsType, che indica i diritti di licenza per l'incorporamento dei tipi di carattere per il tipo di carattere. Questo flag di tipo, tuttavia, fa riferimento solo ai tipi di carattere incorporati archiviati in un documento e non ai tipi di carattere incorporati in un'applicazione. È possibile recuperare i diritti di incorporamento <xref:System.Windows.Media.GlyphTypeface> dei tipi di <xref:System.Windows.Media.GlyphTypeface.EmbeddingRights%2A> carattere per un tipo di carattere creando un oggetto e facendo riferimento alla relativa proprietà. Fare riferimento alla sezione "OS/2 and Windows Metrics" della [specifica OpenType](https://www.microsoft.com/typography/otspec/os2.htm) per ulteriori informazioni sul flag fsType.  
  
 Il sito Web [Microsoft Typography](https://docs.microsoft.com/typography/) include informazioni di contatto che consentono di individuare un particolare fornitore di tipi di carattere o di trovare un fornitore di tipi di carattere per il lavoro personalizzato.  
  
<a name="adding_fonts_as_content_items"></a>
## <a name="adding-fonts-as-content-items"></a>Aggiunta di tipi di carattere come elementi di contenuto  
 È possibile aggiungere tipi di carattere all'applicazione come elementi di contenuto del progetto separati dai file di assembly dell'applicazione. Gli elementi di contenuto non vengono quindi incorporati come risorse in un assembly. L'esempio di file di progetto seguente illustra come definire gli elementi di contenuto.  
  
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
  
 Per assicurarsi che l'applicazione possa usare i tipi di carattere in fase di esecuzione, i tipi di carattere devono essere accessibili nella directory di distribuzione dell'applicazione. L'elemento `<CopyToOutputDirectory>` nel file di progetto dell'applicazione consente di copiare automaticamente i tipi di carattere nella directory di distribuzione dell'applicazione durante il processo di compilazione. L'esempio di file di progetto seguente illustra come copiare i tipi di carattere nella directory di distribuzione.  
  
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
  
 L'esempio di codice seguente illustra come fare riferimento al tipo di carattere dell'applicazione come elemento di contenuto. L'elemento di contenuto a cui si fa riferimento deve essere nella stessa directory dei file di assembly dell'applicazione.  
  
 [!code-xaml[FontSnippets#FontPackageSnippet8](~/samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/FontPackageSnippets.xaml#fontpackagesnippet8)]  
  
<a name="adding_fonts_as_resource_items"></a>
## <a name="adding-fonts-as-resource-items"></a>Aggiunta di tipi di carattere come elementi risorsa  
 È possibile aggiungere tipi di carattere all'applicazione come elementi risorsa del progetto incorporati nei file di assembly dell'applicazione. L'uso di una sottodirectory separata per le risorse consente di organizzare i file di progetto dell'applicazione. L'esempio di file di progetto seguente illustra come definire i tipi di carattere come elementi risorsa in una sottodirectory separata.  
  
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
> Quando si aggiungono tipi di carattere come risorse `<Resource>` all'applicazione, `<EmbeddedResource>` assicurarsi di impostare l'elemento e non l'elemento nel file di progetto dell'applicazione. L'elemento `<EmbeddedResource>` per l'azione di compilazione non è supportato.  
  
 L'esempio di markup seguente illustra come fare riferimento alle risorse dei tipi di carattere dell'applicazione.  
  
 [!code-xaml[FontSnippets#FontPackageSnippet1](~/samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/FontPackageSnippets.xaml#fontpackagesnippet1)]  
  
### <a name="referencing-font-resource-items-from-code"></a>Riferimento agli elementi risorsa dei tipi di carattere dal codice  
 Per fare riferimento agli elementi di risorsa del tipo di carattere dal codice, è necessario fornire un riferimento di risorsa del tipo di carattere in due parti: l'URI (Uniform Resource Identifier) di base. e il riferimento alla posizione del carattere. Questi valori vengono utilizzati <xref:System.Windows.Media.FontFamily.%23ctor%2A> come parametri per il metodo. Nell'esempio di codice riportato di seguito viene illustrato come `resources`fare riferimento alle risorse dei tipi di carattere dell'applicazione nella sottodirectory del progetto denominata .  
  
 [!code-csharp[FontSnippets#FontPackageSnippet2](~/samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/FontPackageSnippets.xaml.cs#fontpackagesnippet2)]
 [!code-vb[FontSnippets#FontPackageSnippet2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FontSnippets/visualbasic/fontpackagesnippets.xaml.vb#fontpackagesnippet2)]  
  
 L'URI (Uniform Resource Identifier) di base può includere la sottodirectory dell'applicazione in cui risiede la risorsa del tipo di carattere. In questo caso, il riferimento alla posizione del tipo di carattere`./`non deve specificare una directory, ma deve includere un carattere iniziale " ", che indica che la risorsa del tipo di carattere si trova nella stessa directory specificata dall'URI (Uniform Resource Identifier) di base. L'esempio di codice seguente illustra un modo alternativo per fare riferimento all'elemento risorsa dei tipi di carattere, che equivale all'esempio di codice precedente.  
  
 [!code-csharp[FontSnippets#FontPackageSnippet5](~/samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/FontPackageSnippets.xaml.cs#fontpackagesnippet5)]
 [!code-vb[FontSnippets#FontPackageSnippet5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FontSnippets/visualbasic/fontpackagesnippets.xaml.vb#fontpackagesnippet5)]  
  
### <a name="referencing-fonts-from-the-same-application-subdirectory"></a>Riferimento ai tipi di carattere dalla stessa sottodirectory dell'applicazione  
 È possibile inserire sia il contenuto dell'applicazione che i file di risorse nella stessa sottodirectory definita dall'utente del progetto dell'applicazione. L'esempio di file di progetto seguente illustra una pagina contenuto e le risorse dei tipi di carattere definite nella stessa sottodirectory.  
  
```xml  
<ItemGroup>  
  <Page Include="pages\HomePage.xaml" />  
</ItemGroup>  
<ItemGroup>  
  <Resource Include="pages\Peric.ttf" />  
  <Resource Include="pages\Pericl.ttf" />  
</ItemGroup>  
```  
  
 Poiché il tipo di carattere e il contenuto dell'applicazione sono nella stessa sottodirectory, il riferimento al tipo di carattere è relativo al contenuto dell'applicazione. Gli esempi seguenti illustrano come fare riferimento alla risorsa del tipo di carattere dell'applicazione quando il tipo di carattere è nella stessa directory dell'applicazione.  
  
 [!code-xaml[FontSnippets#FontPackageSnippet3](~/samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/pages/HomePage.xaml#fontpackagesnippet3)]  
  
 [!code-csharp[FontSnippets#FontPackageSnippet4](~/samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/pages/HomePage.xaml.cs#fontpackagesnippet4)]
 [!code-vb[FontSnippets#FontPackageSnippet4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FontSnippets/visualbasic/pages/homepage.xaml.vb#fontpackagesnippet4)]  
  
### <a name="enumerating-fonts-in-an-application"></a>Enumerazione di tipi di carattere in un'applicazione  
 Per enumerare i tipi di carattere <xref:System.Windows.Media.Fonts.GetFontFamilies%2A> <xref:System.Windows.Media.Fonts.GetTypefaces%2A> come elementi di risorsa nell'applicazione, utilizzare il metodo o . Nell'esempio seguente viene <xref:System.Windows.Media.Fonts.GetFontFamilies%2A> illustrato come utilizzare <xref:System.Windows.Media.FontFamily> il metodo per restituire la raccolta di oggetti dalla posizione del tipo di carattere dell'applicazione. In questo caso, l'applicazione contiene una sottodirectory denominata "resources".  
  
 [!code-csharp[FontSnippets#FontsSnippet3](~/samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/FontFamilySnippets.xaml.cs#fontssnippet3)]
 [!code-vb[FontSnippets#FontsSnippet3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FontSnippets/visualbasic/fontfamilysnippets.xaml.vb#fontssnippet3)]  
  
 Nell'esempio seguente viene <xref:System.Windows.Media.Fonts.GetTypefaces%2A> illustrato come utilizzare <xref:System.Windows.Media.Typeface> il metodo per restituire la raccolta di oggetti dalla posizione del tipo di carattere dell'applicazione. In questo caso, l'applicazione contiene una sottodirectory denominata "resources".  
  
 [!code-csharp[FontSnippets#FontsSnippet7](~/samples/snippets/csharp/VS_Snippets_Wpf/FontSnippets/CSharp/FontFamilySnippets.xaml.cs#fontssnippet7)]
 [!code-vb[FontSnippets#FontsSnippet7](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FontSnippets/visualbasic/fontfamilysnippets.xaml.vb#fontssnippet7)]  
  
<a name="creating_a_font_resource_library"></a>
## <a name="creating-a-font-resource-library"></a>Creazione di una libreria di risorse tipo di carattere  
 È possibile creare una libreria di sole risorse contenente solo tipi di carattere. Nessun codice fa parte di questo tipo di progetto libreria. La creazione di una libreria di sole risorse è una tecnica comune per disaccoppiare le risorse dal codice dell'applicazione che le usa e consente anche di includere l'assembly di librerie in più progetti di applicazione. L'esempio di file di progetto seguente illustra le parti chiave di un progetto di libreria di sole risorse.  
  
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
  
### <a name="referencing-a-font-in-a-resource-library"></a>Riferimento a un tipo di carattere in una libreria di risorse  
 Per fare riferimento a un tipo di carattere in una libreria di risorse dall'applicazione, è necessario far precedere il riferimento al tipo di carattere dal nome dell'assembly di librerie. In questo caso, l'assembly di risorse del tipo di carattere è "FontLibrary". Per separare il nome dell'assembly dal riferimento nell'assembly, usare un carattere ";". Aggiungendo la parola chiave "Component" seguita dal riferimento al nome del tipo di carattere, si completa l'intero riferimento alla risorsa della libreria di tipi di carattere. L'esempio di codice seguente illustra come fare riferimento a un tipo di carattere in un assembly di librerie di risorse.  
  
 [!code-xaml[OpenTypeFontsSample#OpenTypeFontsSample1](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontsSample/CS/Kootenay.xaml#opentypefontssample1)]  
  
> [!NOTE]
> Questo SDK contiene un set di tipi di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] carattere OpenType di esempio che è possibile utilizzare con le applicazioni. I tipi di carattere sono definiti in una libreria di sole risorse. Per ulteriori informazioni, consultate Esempio di pacchetto di [caratteri OpenType](sample-opentype-font-pack.md).  
  
<a name="limitations_on_font_usage"></a>
## <a name="limitations-on-font-usage"></a>Limitazioni all'utilizzo dei tipi di carattere  
 Nell'elenco seguente vengono descritte diverse limitazioni [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] relative alla creazione di pacchetti e all'utilizzo dei tipi di carattere nelle applicazioni:  
  
- **Bit autorizzazione per l'incorporamento tipi di carattere:** [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] le applicazioni non controllano né applicano bit di autorizzazione per l'incorporamento tipi di carattere. Per ulteriori informazioni, vedere la sezione [Tipi di carattere Introduction_to_Packing.](#introduction_to_packaging_fonts)  
  
- **Tipi di carattere del sito di origine:** [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] le applicazioni non consentono un riferimento al tipo di carattere a un URI (Uniform Resource Identifier) http o ftp.  
  
- **URI assoluto utilizzando il pacchetto: notazione:** [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] le <xref:System.Windows.Media.FontFamily> applicazioni non consentono di creare un oggetto a livello di codice utilizzando "pack:" come parte del riferimento URI (Uniform Resource Identifier) assoluto a un tipo di carattere. Ad esempio, `"pack://application:,,,/resources/#Pericles Light"` è un riferimento al tipo di carattere non valido.  
  
- **Incorporamento tipi di carattere automatico:** durante la fase di progettazione, non è disponibile il supporto per cercare l'uso dei tipi di carattere di un'applicazione e incorporare automaticamente i tipi di carattere nelle risorse dell'applicazione.  
  
- **Subset di tipi di carattere: le applicazioni ** [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] non supportano la creazione di subset di tipi di carattere per documenti non statici.  
  
- Se è presente un riferimento non corretto, l'applicazione torna a usare un tipo di carattere disponibile.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Documents.Typography>
- <xref:System.Windows.Media.FontFamily>
- [Microsoft Typography: Links, News, and Contacts](https://docs.microsoft.com/typography/) (Microsoft Typography: collegamenti, novità e contatti)
- [Specifica OpenType](https://www.microsoft.com/typography/otspec/)
- [Funzionalità dei tipi di carattere OpenType](opentype-font-features.md)
- [Esempio di pacchetto di tipi di carattere OpenType](sample-opentype-font-pack.md)
