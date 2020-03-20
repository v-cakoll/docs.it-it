---
title: File di risorse, contenuto e dati dell'applicazioneApplication Resource, Content, and Data Files
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
ms.openlocfilehash: f17898972eeef66447060db32bae5fae377b710e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186194"
---
# <a name="wpf-application-resource-content-and-data-files"></a>File di dati e di risorse dell'applicazione WPF
Le applicazioni Microsoft Windows spesso dipendono da file [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]che contengono dati non eseguibili, ad esempio immagini, video e audio. Windows Presentation Foundation (WPF)Windows Presentation Foundation (WPF)Windows Presentation Foundation (WPF) offre un supporto speciale per la configurazione, l'identificazione e l'utilizzo di questi tipi di file di dati, denominati file di dati dell'applicazione. Questo supporto si basa su un set specifico di tipi di file di dati dell'applicazione, che include:  
  
- **File di risorse:** file di dati compilati in un assembly WPF eseguibile o di libreria.  
  
- **File di contenuto:** file di dati autonomi con un'associazione esplicita con un assembly WPF eseguibile.  
  
- **Site of Origin Files**: File di dati autonomi senza associazione con un assembly WPF eseguibile.  
  
 Un'importante distinzione da fare tra questi tre tipi di file riguarda il fatto che i file di risorse e i file di dati sono resi noti in fase di compilazione e pertanto sono conosciuti esplicitamente da un assembly. Per i file del sito di origine, tuttavia, un assembly potrebbe non esserne a conoscenza o informazioni implicite tramite un riferimento URI (Uniform Resource Identifier) di tipo pack; nel caso di quest'ultimo, non vi è alcuna garanzia che il sito di origine di riferimento esista effettivamente.  
  
 Per fare riferimento ai file di dati dell'applicazione, Windows Presentation Foundation (WPF) usa lo schema URI (Uniform Resource Identifier) del pacchetto, descritto in dettaglio [negli URI di tipo pack in WPFWPF](pack-uris-in-wpf.md).  
  
 Questo argomento descrive come configurare e usare i file di dati dell'applicazione.  

<a name="Resource_Files"></a>
## <a name="resource-files"></a>File di risorse  
 Se un file di dati deve essere sempre disponibile per un'applicazione, l'unico modo per garantire la disponibilità è compilarlo nell'assembly eseguibile principale dell'applicazione o in uno degli assembly a cui si fa riferimento. Questo tipo di file di dati dell'applicazione è noto come file di *risorse.*  
  
 I file di risorse devono essere utilizzati nei casi seguenti:  
  
- Non occorre aggiornare il contenuto del file di risorse dopo la relativa compilazione in un assembly.  
  
- Si desidera semplificare la complessità di distribuzione dell'applicazione riducendo il numero di dipendenze dei file.  
  
- Il file di dati dell'applicazione deve essere localizzabile (vedere [Cenni preliminari sulla globalizzazione e la localizzazione WPF](../advanced/wpf-globalization-and-localization-overview.md)).  
  
> [!NOTE]
> I file di risorse descritti in questa sezione sono diversi dai file di risorse descritti in [Risorse XAML](../../../desktop-wpf/fundamentals/xaml-resources-define.md) e diversi dalle risorse incorporate o collegate descritte in Gestire le [risorse dell'applicazione (.NET).](/visualstudio/ide/managing-application-resources-dotnet)  
  
### <a name="configuring-resource-files"></a>Configurazione dei file di risorse  
 In WPFWPF, un file di risorse è un file incluso in `Resource` un progetto di motore di compilazione Microsoft (MSBuild) come elemento.  
  
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
> In Visual Studio è possibile creare un file di risorse `Build Action` `Resource`aggiungendo un file a un progetto e impostandone l'impostazione su .  
  
 Quando il progetto viene compilato, MSBuild compila la risorsa nell'assembly.  
  
### <a name="using-resource-files"></a>Uso dei file di risorse  
 Per caricare un file di <xref:System.Windows.Application.GetResourceStream%2A> risorse, <xref:System.Windows.Application> è possibile chiamare il metodo della classe, passando un URI di tipo pack che identifica il file di risorse desiderato. <xref:System.Windows.Application.GetResourceStream%2A>restituisce <xref:System.Windows.Resources.StreamResourceInfo> un oggetto, che espone <xref:System.IO.Stream> il file di risorse come un e ne descrive il tipo di contenuto.  
  
 Ad esempio, il codice seguente <xref:System.Windows.Application.GetResourceStream%2A> mostra come <xref:System.Windows.Controls.Page> utilizzare per caricare un file <xref:System.Windows.Controls.Frame> `pageFrame`di risorse e impostarlo come contenuto di un ( ):  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadAPageResourceFileManuallyCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.cs#loadapageresourcefilemanuallycode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadAPageResourceFileManuallyCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.vb#loadapageresourcefilemanuallycode)]  
  
 Durante <xref:System.Windows.Application.GetResourceStream%2A> la chiamata consente <xref:System.IO.Stream>di accedere a , è necessario eseguire l'ulteriore lavoro di conversione nel tipo della proprietà con cui verrà impostata. Al contrario, è possibile consentire WPFWPF <xref:System.IO.Stream> di aprire e convertire il caricando un file di risorse direttamente nella proprietà di un tipo utilizzando il codice.  
  
 Nell'esempio seguente viene <xref:System.Windows.Controls.Page> illustrato come <xref:System.Windows.Controls.Frame> `pageFrame`caricare direttamente un in a ( ) utilizzando il codice.  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadPageResourceFileFromCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.cs#loadpageresourcefilefromcode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadPageResourceFileFromCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.vb#loadpageresourcefilefromcode)]  
  
 L'esempio seguente illustra il markup equivalente del precedente esempio.  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#LoadPageResourceFileFromXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml#loadpageresourcefilefromxaml)]  
  
### <a name="application-code-files-as-resource-files"></a>File di codice dell'applicazione come file di risorse  
 È possibile fare riferimento a un set speciale di file di codice dell'applicazione WPFWPF usando URI di tipo pack, tra cui finestre, pagine, documenti dinamici e dizionari risorse. Ad esempio, è <xref:System.Windows.Application.StartupUri%2A?displayProperty=nameWithType> possibile impostare la proprietà con un URI di tipo pack che fa riferimento alla finestra o alla pagina che si desidera caricare all'avvio di un'applicazione.  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#SetApplicationStartupURI](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/App.xaml#setapplicationstartupuri)]  
  
 È possibile eseguire questa operazione quando un file XAML `Page` è incluso in un progetto MSBuild come elemento.  
  
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
> In Visual Studio si <xref:System.Windows.Window>aggiunge <xref:System.Windows.Navigation.NavigationWindow> <xref:System.Windows.Controls.Page>un <xref:System.Windows.Documents.FlowDocument>nuovo <xref:System.Windows.ResourceDictionary> , , `Build Action` , , o a `Page`un progetto, per il file di markup verrà impostato su .  
  
 Quando viene `Page` compilato un progetto [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] con elementi, gli elementi vengono convertiti in formato binario e compilati nell'assembly associato. Di conseguenza, questi file possono essere utilizzati allo stesso modo dei file di risorse tipici.  
  
> [!NOTE]
> Se [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] un file è `Resource` configurato come elemento e non dispone di [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] un file code-behind, il file [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]non elaborato viene compilato in un assembly anziché in una versione binaria dell'oggetto raw .  
  
<a name="Content_Files"></a>
## <a name="content-files"></a>File di dati  
 Un file di *contenuto* viene distribuito come file loose insieme a un assembly eseguibile. Sebbene questi file non vengano compilati in un assembly, dal canto loro gli assembly vengono compilati con i metadati che stabiliscono un'associazione con ciascun file di dati.  
  
 È necessario utilizzare i file di dati quando l'applicazione richiede un set specifico di file di dati che possono essere aggiornati senza dover ricompilare l'assembly che li utilizza.  
  
### <a name="configuring-content-files"></a>Configurazione dei file di dati  
 Per aggiungere un file di contenuto a un progetto, `Content` un file di dati dell'applicazione deve essere incluso come elemento. Inoltre, poiché un file di contenuto non viene compilato direttamente `CopyToOutputDirectory` nell'assembly, è necessario impostare l'elemento di metadati MSBuild per specificare che il file di contenuto viene copiato in un percorso relativo all'assembly compilato. Se si desidera che la risorsa venga copiata nella cartella dell'output di compilazione ogni volta che viene compilato un progetto, impostare l'elemento `CopyToOutputDirectory` di metadati con il `Always` valore. In caso contrario, è possibile assicurarsi che solo la versione `PreserveNewest` più recente della risorsa venga copiata nella cartella dell'output di compilazione utilizzando il valore .  
  
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
> In Visual Studio è possibile creare un file di contenuto `Build Action` `Content`aggiungendo un `Copy to Output Directory` file `Copy always` a `Always`un progetto e impostandone un'impostazione su , e impostarne l'impostazione su ( e `Copy if newer` (uguale a `PreserveNewest`).  
  
 Quando il progetto viene <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> compilato, un attributo viene compilato nei metadati dell'assembly per ogni file di contenuto.  
  
 `[assembly: AssemblyAssociatedContentFile("ContentFile.xaml")]`  
  
 Il valore <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> dell'oggetto implica il percorso del file di contenuto rispetto alla sua posizione nel progetto. Ad esempio, se un file di contenuto si trova in una sottocartella del progetto, le informazioni aggiuntive sul percorso verranno incorporate nel <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> valore.  
  
 `[assembly: AssemblyAssociatedContentFile("Resources/ContentFile.xaml")]`  
  
 Il <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> valore è anche il valore del percorso del file di contenuto nella cartella dell'output di compilazione.  
  
### <a name="using-content-files"></a>Uso dei file di contenuto  
 Per caricare un file di <xref:System.Windows.Application.GetContentStream%2A> contenuto, <xref:System.Windows.Application> è possibile chiamare il metodo della classe, passando un URI di tipo pack che identifica il file di contenuto desiderato. <xref:System.Windows.Application.GetContentStream%2A>restituisce <xref:System.Windows.Resources.StreamResourceInfo> un oggetto, che espone <xref:System.IO.Stream> il file di contenuto come un e ne descrive il tipo di contenuto.  
  
 Ad esempio, nel codice seguente <xref:System.Windows.Application.GetContentStream%2A> viene illustrato <xref:System.Windows.Controls.Page> come utilizzare per caricare un <xref:System.Windows.Controls.Frame> `pageFrame`file di contenuto e impostarlo come contenuto di un oggetto ( ).  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadAPageContentFileManuallyCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.cs#loadapagecontentfilemanuallycode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadAPageContentFileManuallyCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.vb#loadapagecontentfilemanuallycode)]  
  
 Durante <xref:System.Windows.Application.GetContentStream%2A> la chiamata consente <xref:System.IO.Stream>di accedere a , è necessario eseguire l'ulteriore lavoro di conversione nel tipo della proprietà con cui verrà impostata. Al contrario, è possibile consentire WPFWPF <xref:System.IO.Stream> di aprire e convertire il caricando un file di risorse direttamente nella proprietà di un tipo utilizzando il codice.  
  
 Nell'esempio seguente viene <xref:System.Windows.Controls.Page> illustrato come <xref:System.Windows.Controls.Frame> `pageFrame`caricare direttamente un in a ( ) utilizzando il codice.  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadPageContentFileFromCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.cs#loadpagecontentfilefromcode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadPageContentFileFromCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.vb#loadpagecontentfilefromcode)]  
  
 L'esempio seguente illustra il markup equivalente del precedente esempio.  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#LoadPageContentFileFromXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml#loadpagecontentfilefromxaml)]  
  
<a name="Site_of_Origin_Files"></a>
## <a name="site-of-origin-files"></a>File del sito di origine  
 I file di risorse hanno una relazione esplicita con <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute>gli assembly a cui vengono distribuiti, come definito dall'oggetto . Talvolta, è tuttavia possibile che si debba stabilire una relazione implicita o inesistente tra un assembly e un file di dati dell'applicazione, come nei casi seguenti:  
  
- Un file non esiste in fase di compilazione.  
  
- I file richiesti dall'assembly non saranno noti fino alla fase di esecuzione.  
  
- Si desidera avere la possibilità di aggiornare i file senza ricompilare l'assembly al quale sono associati.  
  
- L'applicazione utilizza file di dati di grandi dimensioni, ad esempio audio e video, che devono essere scaricati dagli utenti unicamente su richiesta.  
  
 È possibile caricare questi tipi di file utilizzando schemi URI tradizionali, ad esempio gli schemi file:/// e http://.  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#AbsolutePackUriFileHttpReferenceXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/AbsolutePackUriPage.xaml#absolutepackurifilehttpreferencexaml)]  
  
 Tuttavia, gli schemi file:/// e http:// richiedono che l'applicazione abbia un livello di attendibilità totale. Se l'applicazione è un'applicazione browser XAML (XBAP) avviata da Internet o da una rete Intranet e richiede solo il set di autorizzazioni consentite per le applicazioni avviate da tali posizioni, i file persiemi possono essere caricati solo dal menu sito di origine dell'applicazione (posizione di avvio). Tali file sono noti come sito di file *di origine.*  
  
 I file del sito di origine rappresentano l'unica opzione per le applicazioni parzialmente attendibili, benché non siano limitati a questo tipo di applicazione. È possibile che le applicazioni completamente attendibili debbano caricare file di dati dell'applicazione sconosciuti in fase di compilazione. Sebbene queste applicazioni possano utilizzare file:///, è probabile che i file di dati dell'applicazione vengano installati nella stessa cartella dell'assembly dell'applicazione o in una sottocartella di questo. In questo caso è più facile utilizzare un riferimento al sito di origine piuttosto che file:///, poiché l'utilizzo di file:/// richiede l'elaborazione del percorso completo del file.  
  
> [!NOTE]
> I file del sito di origine non vengono memorizzati nella cache con un'applicazione browser XAML (XBAP) in un computer client, mentre i file di contenuto lo sono. Di conseguenza, vengono scaricati solo se esplicitamente richiesto. Se un'applicazione browser XAML (XBAP) dispone di file multimediali di grandi dimensioni, configurarli come file del sito di origine significa che l'avvio iniziale dell'applicazione è molto più veloce e i file vengono scaricati solo su richiesta.  
  
### <a name="configuring-site-of-origin-files"></a>Configurazione dei file del sito di origine  
 Se i file di origine del sito sono inesistenti o sconosciuti in fase di compilazione, è necessario utilizzare `XCopy` i meccanismi di distribuzione tradizionali per garantire che i file necessari siano disponibili in fase di esecuzione, incluso l'utilizzo del programma della riga di comando o di Microsoft Windows Installer.  
  
 Se si conoscono in fase di compilazione i file che si desidera si trovano nel sito di origine, ma si `None` desidera comunque evitare una dipendenza esplicita, è possibile aggiungere tali file a un progetto MSBuild come elemento. Come per i file di contenuto, `CopyToOutputDirectory` è necessario impostare l'attributo MSBuild per specificare che il file `Always` del sito `PreserveNewest` di origine viene copiato in un percorso relativo all'assembly compilato, specificando il valore o il valore.  
  
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
> In Visual Studio è possibile creare un file del sito di `Build Action` `None`origine aggiungendo un file a un progetto e impostandone l'impostazione su .  
  
 Quando il progetto viene compilato, MSBuild copia i file specificati nella cartella dell'output di compilazione.  
  
### <a name="using-site-of-origin-files"></a>Uso dei file del sito di origine  
 Per caricare un file del sito <xref:System.Windows.Application.GetRemoteStream%2A> di origine, è possibile chiamare il metodo della <xref:System.Windows.Application> classe, passando un URI di tipo pack che identifica il file di origine del sito desiderato. <xref:System.Windows.Application.GetRemoteStream%2A>restituisce <xref:System.Windows.Resources.StreamResourceInfo> un oggetto, che espone il <xref:System.IO.Stream> file del sito di origine come un e ne descrive il tipo di contenuto.  
  
 Ad esempio, nel codice seguente <xref:System.Windows.Application.GetRemoteStream%2A> viene illustrato <xref:System.Windows.Controls.Page> come utilizzare per caricare un file <xref:System.Windows.Controls.Frame> `pageFrame`del sito di origine e impostarlo come contenuto di a ( ).  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadAPageSOOFileManuallyCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/SOOPage.xaml.cs#loadapagesoofilemanuallycode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadAPageSOOFileManuallyCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/SOOPage.xaml.vb#loadapagesoofilemanuallycode)]  
  
 Durante <xref:System.Windows.Application.GetRemoteStream%2A> la chiamata consente <xref:System.IO.Stream>di accedere a , è necessario eseguire l'ulteriore lavoro di conversione nel tipo della proprietà con cui verrà impostata. Al contrario, è possibile consentire WPFWPF <xref:System.IO.Stream> di aprire e convertire il caricando un file di risorse direttamente nella proprietà di un tipo utilizzando il codice.  
  
 Nell'esempio seguente viene <xref:System.Windows.Controls.Page> illustrato come <xref:System.Windows.Controls.Frame> `pageFrame`caricare direttamente un in a ( ) utilizzando il codice.  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadPageSOOFileFromCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/SOOPage.xaml.cs#loadpagesoofilefromcode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadPageSOOFileFromCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/SOOPage.xaml.vb#loadpagesoofilefromcode)]  
  
 L'esempio seguente illustra il markup equivalente del precedente esempio.  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#LoadPageSOOFileFromXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/SOOPage.xaml#loadpagesoofilefromxaml)]  
  
<a name="Rebuilding_after_Changing_Build_Type"></a>
## <a name="rebuilding-after-changing-build-type"></a>Ricompilazione in seguito alla modifica del tipo di compilazione  
 Dopo avere modificato il tipo di compilazione di un file di dati dell'applicazione, è necessario ricompilare l'intera applicazione affinché le modifiche vengano applicate. Se ci si limita a compilare l'applicazione, le modifiche non vengono applicate.  
  
## <a name="see-also"></a>Vedere anche

- [URI di tipo pack in WPF](pack-uris-in-wpf.md)
