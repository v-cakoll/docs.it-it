---
title: File di dati e di risorse dell'applicazione WPF.
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
ms.openlocfilehash: 57eae5067a72777db2c19331029b6df679a9fdce
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69956184"
---
# <a name="wpf-application-resource-content-and-data-files"></a>File di dati e di risorse dell'applicazione WPF.
[!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)]le applicazioni spesso dipendono da file che contengono dati non eseguibili, [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]ad esempio immagini, video e audio. Windows Presentation Foundation (WPF) offre supporto speciale per la configurazione, l'identificazione e l'utilizzo di questi tipi di file di dati, chiamati file di dati dell'applicazione. Questo supporto si basa su un set specifico di tipi di file di dati dell'applicazione, che include:  
  
- **File di risorse**: File di dati compilati in un assembly eseguibile [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] o libreria.  
  
- **File di contenuto**: File di dati autonomi con un'associazione esplicita a [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] un assembly eseguibile.  
  
- **File del sito di origine**: File di dati autonomi senza associazione a un assembly [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] eseguibile.  
  
 Un'importante distinzione da fare tra questi tre tipi di file riguarda il fatto che i file di risorse e i file di dati sono resi noti in fase di compilazione e pertanto sono conosciuti esplicitamente da un assembly. Per i file del sito di origine, tuttavia, un assembly può non conoscerli affatto o una conoscenza implicita tramite un riferimento [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] a un pacchetto; il caso del secondo, non esiste alcuna garanzia che il file del sito di origine a cui si fa riferimento esista effettivamente.  
  
 Per fare riferimento ai file di dati dell'applicazione, Windows Presentation Foundation (WPF [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] ) utilizza lo schema di pacchetto, descritto in dettaglio in [URI di Pack in WPF](pack-uris-in-wpf.md).  
  
 Questo argomento descrive come configurare e usare i file di dati dell'applicazione.  

<a name="Resource_Files"></a>   
## <a name="resource-files"></a>File di risorse  
 Se un file di dati deve essere sempre disponibile per un'applicazione, l'unico modo per garantire la disponibilità è compilarlo nell'assembly eseguibile principale dell'applicazione o in uno degli assembly a cui si fa riferimento. Questo tipo di file di dati dell'applicazione è noto come *file di risorse*.  
  
 I file di risorse devono essere utilizzati nei casi seguenti:  
  
- Non occorre aggiornare il contenuto del file di risorse dopo la relativa compilazione in un assembly.  
  
- Si desidera semplificare la complessità di distribuzione dell'applicazione riducendo il numero di dipendenze dei file.  
  
- Il file di dati dell'applicazione deve essere localizzabile. vedere [Cenni preliminari sulla globalizzazione e localizzazione WPF](../advanced/wpf-globalization-and-localization-overview.md).  
  
> [!NOTE]
> I file di risorse descritti in questa sezione sono diversi dai file di risorse descritti in [risorse XAML](../advanced/xaml-resources.md) e diversi dalle risorse incorporate o collegate descritte in [gestire le risorse dell'applicazione (.NET)](/visualstudio/ide/managing-application-resources-dotnet).  
  
### <a name="configuring-resource-files"></a>Configurazione dei file di risorse  
 In [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], un file di risorse è un file incluso in un progetto di Microsoft Build Engine (MSBuild) `Resource` come elemento.  
  
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
> In [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)]è possibile creare un file di risorse aggiungendo un file a un progetto e `Build Action` impostando su `Resource`.  
  
 Quando il progetto viene compilato, MSBuild compila la risorsa nell'assembly.  
  
### <a name="using-resource-files"></a>Uso dei file di risorse  
 Per caricare un file <xref:System.Windows.Application.GetResourceStream%2A> <xref:System.Windows.Application> di risorse, è possibile chiamare il metodo della classe, passando un pacchetto [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] che identifica il file di risorse desiderato. <xref:System.Windows.Application.GetResourceStream%2A>Restituisce un <xref:System.Windows.Resources.StreamResourceInfo> oggetto che espone il file <xref:System.IO.Stream> di risorse come e ne descrive il tipo di contenuto.  
  
 Come esempio, il codice <xref:System.Windows.Application.GetResourceStream%2A> seguente illustra come usare per caricare un <xref:System.Windows.Controls.Page> file di risorse e impostarlo come contenuto di un <xref:System.Windows.Controls.Frame> (`pageFrame`):  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadAPageResourceFileManuallyCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.cs#loadapageresourcefilemanuallycode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadAPageResourceFileManuallyCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.vb#loadapageresourcefilemanuallycode)]  
  
 Quando la <xref:System.Windows.Application.GetResourceStream%2A> <xref:System.IO.Stream>chiamata a consente di accedere a, è necessario eseguire le operazioni aggiuntive di conversione nel tipo della proprietà con cui verrà impostata. In alternativa, è possibile [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] fare in maniera che l'apertura e <xref:System.IO.Stream> la conversione di ricarichino un file di risorse direttamente nella proprietà di un tipo usando il codice.  
  
 Nell'esempio seguente viene illustrato come caricare un <xref:System.Windows.Controls.Page> oggetto direttamente in <xref:System.Windows.Controls.Frame> un`pageFrame`oggetto () utilizzando il codice.  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadPageResourceFileFromCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.cs#loadpageresourcefilefromcode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadPageResourceFileFromCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.vb#loadpageresourcefilefromcode)]  
  
 L'esempio seguente illustra il markup equivalente del precedente esempio.  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#LoadPageResourceFileFromXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml#loadpageresourcefilefromxaml)]  
  
### <a name="application-code-files-as-resource-files"></a>File di codice dell'applicazione come file di risorse  
 È possibile fare riferimento [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] A un set speciale di file di codice dell' [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)]applicazione usando Pack, tra cui finestre, pagine, documenti dinamici e dizionari risorse. Ad esempio, è possibile impostare la <xref:System.Windows.Application.StartupUri%2A?displayProperty=nameWithType> proprietà con un pacchetto [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] che fa riferimento alla finestra o alla pagina che si desidera caricare all'avvio di un'applicazione.  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#SetApplicationStartupURI](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/App.xaml#setapplicationstartupuri)]  
  
 Questa operazione può essere eseguita quando un file XAML viene incluso in un progetto MSBuild come `Page` elemento.  
  
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
> In [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)]è possibile aggiungere un nuovo <xref:System.Windows.Window>oggetto <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Page> <xref:System.Windows.ResourceDictionary> `Build Action` ,, o a un progetto, per il file di markup viene impostato come `Page`predefinito. <xref:System.Windows.Documents.FlowDocument>  
  
 Quando viene compilato un `Page` progetto con elementi, gli [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] elementi vengono convertiti in formato binario e compilati nell'assembly associato. Di conseguenza, questi file possono essere utilizzati allo stesso modo dei file di risorse tipici.  
  
> [!NOTE]
> Se un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file è configurato `Resource` come elemento e non dispone di un file code-behind, il file RAW [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] viene compilato in un assembly anziché in una versione binaria di RAW [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
<a name="Content_Files"></a>   
## <a name="content-files"></a>File di dati  
 Un *file di contenuto* viene distribuito come file separato insieme a un assembly eseguibile. Sebbene questi file non vengano compilati in un assembly, dal canto loro gli assembly vengono compilati con i metadati che stabiliscono un'associazione con ciascun file di dati.  
  
 È necessario utilizzare i file di dati quando l'applicazione richiede un set specifico di file di dati che possono essere aggiornati senza dover ricompilare l'assembly che li utilizza.  
  
### <a name="configuring-content-files"></a>Configurazione dei file di dati  
 Per aggiungere un file di contenuto a un progetto, è necessario includere un file di dati dell' `Content` applicazione come elemento. Inoltre, poiché un file di contenuto non viene compilato direttamente nell'assembly, è necessario impostare l'elemento dei `CopyToOutputDirectory` metadati MSBuild per specificare che il file di contenuto viene copiato in un percorso relativo all'assembly compilato. Se si desidera che la risorsa venga copiata nella cartella dell'output di compilazione ogni volta che viene compilato un progetto, `CopyToOutputDirectory` impostare l'elemento dei `Always` metadati con il valore. In caso contrario, è possibile assicurarsi che solo la versione più recente della risorsa venga copiata nella cartella dell'output di `PreserveNewest` compilazione usando il valore.  
  
 Di seguito viene illustrato un file configurato come file di dati, che viene copiato nella cartella dell'output di compilazione solo quando una nuova versione della risorsa viene aggiunta al progetto.  
  
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
> In [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)]è possibile creare un file di contenuto aggiungendo un file a un progetto e `Build Action` impostando `Copy if newer` `Content` `Always` `Copy to Output Directory` `Copy always` su e impostando la proprietà su (uguale a) e (uguale `PreserveNewest`a).  
  
 Quando il progetto viene compilato, viene <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> compilato un attributo nei metadati dell'assembly per ogni file di contenuto.  
  
 `[assembly: AssemblyAssociatedContentFile("ContentFile.xaml")]`  
  
 Il valore di <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> implica il percorso del file di contenuto rispetto alla relativa posizione nel progetto. Se, ad esempio, un file di contenuto si trova in una sottocartella del progetto, le informazioni aggiuntive sul percorso verranno <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> incorporate nel valore.  
  
 `[assembly: AssemblyAssociatedContentFile("Resources/ContentFile.xaml")]`  
  
 Il <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> valore è anche il valore del percorso del file di contenuto nella cartella di output di compilazione.  
  
### <a name="using-content-files"></a>Uso dei file di contenuto  
 Per caricare un file <xref:System.Windows.Application.GetContentStream%2A> <xref:System.Windows.Application> di contenuto, è possibile chiamare il metodo della classe, passando un pacchetto [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] che identifica il file di contenuto desiderato. <xref:System.Windows.Application.GetContentStream%2A>Restituisce un <xref:System.Windows.Resources.StreamResourceInfo> oggetto che espone il file <xref:System.IO.Stream> di contenuto come e ne descrive il tipo di contenuto.  
  
 Come esempio, il codice <xref:System.Windows.Application.GetContentStream%2A> seguente illustra come usare per caricare un <xref:System.Windows.Controls.Page> file di contenuto e impostarlo come contenuto di un oggetto <xref:System.Windows.Controls.Frame> (`pageFrame`).  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadAPageContentFileManuallyCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.cs#loadapagecontentfilemanuallycode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadAPageContentFileManuallyCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.vb#loadapagecontentfilemanuallycode)]  
  
 Quando la <xref:System.Windows.Application.GetContentStream%2A> <xref:System.IO.Stream>chiamata a consente di accedere a, è necessario eseguire le operazioni aggiuntive di conversione nel tipo della proprietà con cui verrà impostata. In alternativa, è possibile [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] fare in maniera che l'apertura e <xref:System.IO.Stream> la conversione di ricarichino un file di risorse direttamente nella proprietà di un tipo usando il codice.  
  
 Nell'esempio seguente viene illustrato come caricare un <xref:System.Windows.Controls.Page> oggetto direttamente in <xref:System.Windows.Controls.Frame> un`pageFrame`oggetto () utilizzando il codice.  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadPageContentFileFromCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.cs#loadpagecontentfilefromcode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadPageContentFileFromCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.vb#loadpagecontentfilefromcode)]  
  
 L'esempio seguente illustra il markup equivalente del precedente esempio.  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#LoadPageContentFileFromXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml#loadpagecontentfilefromxaml)]  
  
<a name="Site_of_Origin_Files"></a>   
## <a name="site-of-origin-files"></a>File del sito di origine  
 I file di risorse hanno una relazione esplicita con gli assembly distribuiti insieme, come definito da <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute>. Talvolta, è tuttavia possibile che si debba stabilire una relazione implicita o inesistente tra un assembly e un file di dati dell'applicazione, come nei casi seguenti:  
  
- Un file non esiste in fase di compilazione.  
  
- I file richiesti dall'assembly non saranno noti fino alla fase di esecuzione.  
  
- Si desidera avere la possibilità di aggiornare i file senza ricompilare l'assembly al quale sono associati.  
  
- L'applicazione utilizza file di dati di grandi dimensioni, ad esempio audio e video, che devono essere scaricati dagli utenti unicamente su richiesta.  
  
 È possibile caricare questi tipi di file utilizzando schemi tradizionali [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] , ad esempio gli schemi file:///e http://.  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#AbsolutePackUriFileHttpReferenceXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/AbsolutePackUriPage.xaml#absolutepackurifilehttpreferencexaml)]  
  
 Tuttavia, gli schemi file:/// e http:// richiedono che l'applicazione abbia un livello di attendibilità totale. Se l'applicazione è una [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] che è stata avviata da Internet o Intranet e richiede solo il set di autorizzazioni consentite per le applicazioni avviate da tali percorsi, i file separati possono essere caricati solo dal sito di origine dell'applicazione ( percorso di avvio). Tali file sono noti come file *del sito di origine* .  
  
 I file del sito di origine rappresentano l'unica opzione per le applicazioni parzialmente attendibili, benché non siano limitati a questo tipo di applicazione. È possibile che le applicazioni completamente attendibili debbano caricare file di dati dell'applicazione sconosciuti in fase di compilazione. Sebbene queste applicazioni possano utilizzare file:///, è probabile che i file di dati dell'applicazione vengano installati nella stessa cartella dell'assembly dell'applicazione o in una sottocartella di questo. In questo caso è più facile utilizzare un riferimento al sito di origine piuttosto che file:///, poiché l'utilizzo di file:/// richiede l'elaborazione del percorso completo del file.  
  
> [!NOTE]
> I file del sito di origine non vengono memorizzati [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] nella cache con un computer client, mentre i file di contenuto sono. Di conseguenza, vengono scaricati solo se esplicitamente richiesto. Se un' [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] applicazione dispone di file multimediali di grandi dimensioni, configurarli come file del sito di origine significa che l'avvio iniziale dell'applicazione è molto più veloce e che i file vengono scaricati solo su richiesta.  
  
### <a name="configuring-site-of-origin-files"></a>Configurazione dei file del sito di origine  
 Se i file del sito di origine sono inesistenti o sconosciuti in fase di compilazione, è necessario utilizzare i meccanismi di distribuzione tradizionali per garantire che i file necessari siano disponibili in fase di esecuzione `XCopy` , incluso l'utilizzo del programma da riga di comando o [!INCLUDE[TLA#tla_wininstall](../../../../includes/tlasharptla-wininstall-md.md)].  
  
 Se si conosce in fase di compilazione i file che si desidera individuare nel sito di origine, ma si desidera comunque evitare una dipendenza esplicita, è possibile aggiungere tali file a un progetto MSBuild come `None` elemento. Come per i file di contenuto, è necessario impostare l' `CopyToOutputDirectory` attributo MSBuild per specificare che il file del sito di origine viene copiato in un percorso relativo all'assembly compilato, specificando il `Always` valore o `PreserveNewest` il valore.  
  
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
> In [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)]è possibile creare un file del sito di origine aggiungendo un file a un progetto e `Build Action` impostando su `None`.  
  
 Quando il progetto viene compilato, MSBuild copia i file specificati nella cartella di output di compilazione.  
  
### <a name="using-site-of-origin-files"></a>Uso dei file del sito di origine  
 Per caricare un file del sito di origine, è possibile chiamare <xref:System.Windows.Application.GetRemoteStream%2A> il metodo <xref:System.Windows.Application> della classe, passando un pacchetto [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] che identifica il file del sito di origine desiderato. <xref:System.Windows.Application.GetRemoteStream%2A>Restituisce un <xref:System.Windows.Resources.StreamResourceInfo> oggetto che espone il file del sito di origine <xref:System.IO.Stream> come e ne descrive il tipo di contenuto.  
  
 Come esempio, il codice <xref:System.Windows.Application.GetRemoteStream%2A> seguente illustra come usare per caricare un <xref:System.Windows.Controls.Page> file del sito di origine e impostarlo come contenuto di un oggetto <xref:System.Windows.Controls.Frame> (`pageFrame`).  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadAPageSOOFileManuallyCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/SOOPage.xaml.cs#loadapagesoofilemanuallycode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadAPageSOOFileManuallyCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/SOOPage.xaml.vb#loadapagesoofilemanuallycode)]  
  
 Quando la <xref:System.Windows.Application.GetRemoteStream%2A> <xref:System.IO.Stream>chiamata a consente di accedere a, è necessario eseguire le operazioni aggiuntive di conversione nel tipo della proprietà con cui verrà impostata. In alternativa, è possibile [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] fare in maniera che l'apertura e <xref:System.IO.Stream> la conversione di ricarichino un file di risorse direttamente nella proprietà di un tipo usando il codice.  
  
 Nell'esempio seguente viene illustrato come caricare un <xref:System.Windows.Controls.Page> oggetto direttamente in <xref:System.Windows.Controls.Frame> un`pageFrame`oggetto () utilizzando il codice.  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadPageSOOFileFromCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/SOOPage.xaml.cs#loadpagesoofilefromcode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadPageSOOFileFromCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/SOOPage.xaml.vb#loadpagesoofilefromcode)]  
  
 L'esempio seguente illustra il markup equivalente del precedente esempio.  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#LoadPageSOOFileFromXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/SOOPage.xaml#loadpagesoofilefromxaml)]  
  
<a name="Rebuilding_after_Changing_Build_Type"></a>   
## <a name="rebuilding-after-changing-build-type"></a>Ricompilazione in seguito alla modifica del tipo di compilazione  
 Dopo avere modificato il tipo di compilazione di un file di dati dell'applicazione, è necessario ricompilare l'intera applicazione affinché le modifiche vengano applicate. Se ci si limita a compilare l'applicazione, le modifiche non vengono applicate.  
  
## <a name="see-also"></a>Vedere anche

- [URI di tipo pack in WPF](pack-uris-in-wpf.md)
