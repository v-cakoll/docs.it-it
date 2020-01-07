---
title: File di dati e di risorse dell'applicazione WPF
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
ms.openlocfilehash: d966116db09c2baef7deabf5d01138e8445098be
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/03/2020
ms.locfileid: "75636263"
---
# <a name="wpf-application-resource-content-and-data-files"></a>File di dati e di risorse dell'applicazione WPF
Le applicazioni Microsoft Windows spesso dipendono da file che contengono dati non eseguibili, ad esempio [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], immagini, video e audio. Windows Presentation Foundation (WPF) offre supporto speciale per la configurazione, l'identificazione e l'utilizzo di questi tipi di file di dati, chiamati file di dati dell'applicazione. Questo supporto si basa su un set specifico di tipi di file di dati dell'applicazione, che include:  
  
- **File di risorse**: file di dati compilati in un file eseguibile o in un assembly WPF di libreria.  
  
- **File di contenuto**: file di dati autonomi con un'associazione esplicita a un assembly WPF eseguibile.  
  
- **File del sito di origine**: file di dati autonomi senza associazione a un assembly WPF eseguibile.  
  
 Un'importante distinzione da fare tra questi tre tipi di file riguarda il fatto che i file di risorse e i file di dati sono resi noti in fase di compilazione e pertanto sono conosciuti esplicitamente da un assembly. Per i file del sito di origine, tuttavia, un assembly può non conoscerli affatto o una conoscenza implicita tramite un riferimento URI (Uniform Resource Identifier) di Pack. in quest'ultimo caso, non vi è alcuna garanzia che il file del sito di origine a cui si fa riferimento esista effettivamente.  
  
 Per fare riferimento ai file di dati dell'applicazione, Windows Presentation Foundation (WPF) usa lo schema URI (Uniform Resource Identifier) di Pack, descritto in dettaglio in [URI di Pack in WPF](pack-uris-in-wpf.md).  
  
 Questo argomento descrive come configurare e usare i file di dati dell'applicazione.  

<a name="Resource_Files"></a>   
## <a name="resource-files"></a>File di risorse  
 Se un file di dati deve essere sempre disponibile per un'applicazione, l'unico modo per garantire la disponibilità è compilarlo nell'assembly eseguibile principale dell'applicazione o in uno degli assembly a cui si fa riferimento. Questo tipo di file di dati dell'applicazione è noto come *file di risorse*.  
  
 I file di risorse devono essere utilizzati nei casi seguenti:  
  
- Non occorre aggiornare il contenuto del file di risorse dopo la relativa compilazione in un assembly.  
  
- Si desidera semplificare la complessità di distribuzione dell'applicazione riducendo il numero di dipendenze dei file.  
  
- Il file di dati dell'applicazione deve essere localizzabile. vedere [Cenni preliminari sulla globalizzazione e localizzazione WPF](../advanced/wpf-globalization-and-localization-overview.md).  
  
> [!NOTE]
> I file di risorse descritti in questa sezione sono diversi dai file di risorse descritti in [risorse XAML](../../../desktop-wpf/fundamentals/xaml-resources-define.md) e diversi dalle risorse incorporate o collegate descritte in [gestire le risorse dell'applicazione (.NET)](/visualstudio/ide/managing-application-resources-dotnet).  
  
### <a name="configuring-resource-files"></a>Configurazione dei file di risorse  
 In WPF un file di risorse è un file incluso in un progetto di Microsoft Build Engine (MSBuild) come elemento `Resource`.  
  
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
> In Visual Studio è possibile creare un file di risorse aggiungendo un file a un progetto e impostando il relativo `Build Action` su `Resource`.  
  
 Quando il progetto viene compilato, MSBuild compila la risorsa nell'assembly.  
  
### <a name="using-resource-files"></a>Uso dei file di risorse  
 Per caricare un file di risorse, è possibile chiamare il metodo <xref:System.Windows.Application.GetResourceStream%2A> della classe <xref:System.Windows.Application>, passando un URI di pacchetto che identifica il file di risorse desiderato. <xref:System.Windows.Application.GetResourceStream%2A> restituisce un oggetto <xref:System.Windows.Resources.StreamResourceInfo>, che espone il file di risorse come <xref:System.IO.Stream> e ne descrive il tipo di contenuto.  
  
 Come esempio, il codice seguente illustra come usare <xref:System.Windows.Application.GetResourceStream%2A> per caricare un file di risorse <xref:System.Windows.Controls.Page> e impostarlo come contenuto di un <xref:System.Windows.Controls.Frame> (`pageFrame`):  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadAPageResourceFileManuallyCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.cs#loadapageresourcefilemanuallycode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadAPageResourceFileManuallyCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.vb#loadapageresourcefilemanuallycode)]  
  
 Quando si chiama <xref:System.Windows.Application.GetResourceStream%2A> consente di accedere al <xref:System.IO.Stream>, è necessario eseguire l'operazione aggiuntiva di conversione nel tipo della proprietà che verrà impostata con. È invece possibile consentire a WPF di gestire l'apertura e la conversione del <xref:System.IO.Stream> caricando un file di risorse direttamente nella proprietà di un tipo usando il codice.  
  
 Nell'esempio seguente viene illustrato come caricare un <xref:System.Windows.Controls.Page> direttamente in una <xref:System.Windows.Controls.Frame> (`pageFrame`) utilizzando il codice.  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadPageResourceFileFromCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.cs#loadpageresourcefilefromcode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadPageResourceFileFromCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.vb#loadpageresourcefilefromcode)]  
  
 L'esempio seguente illustra il markup equivalente del precedente esempio.  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#LoadPageResourceFileFromXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml#loadpageresourcefilefromxaml)]  
  
### <a name="application-code-files-as-resource-files"></a>File di codice dell'applicazione come file di risorse  
 È possibile fare riferimento A un set speciale di file di codice dell'applicazione WPF usando URI di pacchetto, tra cui finestre, pagine, documenti dinamici e dizionari risorse. Ad esempio, è possibile impostare la proprietà <xref:System.Windows.Application.StartupUri%2A?displayProperty=nameWithType> con un URI di tipo pack che fa riferimento alla finestra o alla pagina che si desidera caricare all'avvio di un'applicazione.  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#SetApplicationStartupURI](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/App.xaml#setapplicationstartupuri)]  
  
 Questa operazione può essere eseguita quando un file XAML viene incluso in un progetto MSBuild come elemento `Page`.  
  
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
> In Visual Studio si aggiunge un nuovo <xref:System.Windows.Window>, <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Page>, <xref:System.Windows.Documents.FlowDocument>o <xref:System.Windows.ResourceDictionary> a un progetto, per impostazione predefinita il `Build Action` per il file di markup viene `Page`.  
  
 Quando viene compilato un progetto con `Page` elementi, gli elementi [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] vengono convertiti in formato binario e compilati nell'assembly associato. Di conseguenza, questi file possono essere utilizzati allo stesso modo dei file di risorse tipici.  
  
> [!NOTE]
> Se un file di [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] viene configurato come elemento `Resource` e non dispone di un file code-behind, la [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] non elaborata viene compilata in un assembly anziché in una versione binaria del [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]non elaborato.  
  
<a name="Content_Files"></a>   
## <a name="content-files"></a>File di contenuto  
 Un *file di contenuto* viene distribuito come file separato insieme a un assembly eseguibile. Sebbene questi file non vengano compilati in un assembly, dal canto loro gli assembly vengono compilati con i metadati che stabiliscono un'associazione con ciascun file di dati.  
  
 È necessario utilizzare i file di dati quando l'applicazione richiede un set specifico di file di dati che possono essere aggiornati senza dover ricompilare l'assembly che li utilizza.  
  
### <a name="configuring-content-files"></a>Configurazione dei file di dati  
 Per aggiungere un file di contenuto a un progetto, è necessario includere un file di dati dell'applicazione come elemento `Content`. Inoltre, poiché un file di contenuto non viene compilato direttamente nell'assembly, è necessario impostare l'elemento di metadati MSBuild `CopyToOutputDirectory` per specificare che il file di contenuto viene copiato in un percorso relativo all'assembly compilato. Se si desidera che la risorsa venga copiata nella cartella dell'output di compilazione ogni volta che viene compilato un progetto, impostare il `CopyToOutputDirectory` elemento dei metadati con il valore di `Always`. In caso contrario, è possibile assicurarsi che solo la versione più recente della risorsa venga copiata nella cartella dell'output di compilazione usando il valore `PreserveNewest`.  
  
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
> In Visual Studio è possibile creare un file di contenuto aggiungendo un file a un progetto e impostando il relativo `Build Action` su `Content`, quindi impostare la relativa `Copy to Output Directory` su `Copy always` (uguale a `Always`) e `Copy if newer` (uguale a `PreserveNewest`).  
  
 Quando il progetto viene compilato, un attributo <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> viene compilato nei metadati dell'assembly per ogni file di contenuto.  
  
 `[assembly: AssemblyAssociatedContentFile("ContentFile.xaml")]`  
  
 Il valore della <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> implica il percorso del file di contenuto rispetto alla relativa posizione nel progetto. Se, ad esempio, un file di contenuto si trova in una sottocartella del progetto, le informazioni aggiuntive sul percorso verranno incorporate nel valore <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute>.  
  
 `[assembly: AssemblyAssociatedContentFile("Resources/ContentFile.xaml")]`  
  
 Il valore <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> è anche il valore del percorso del file di contenuto nella cartella di output di compilazione.  
  
### <a name="using-content-files"></a>Uso dei file di contenuto  
 Per caricare un file di contenuto, è possibile chiamare il metodo <xref:System.Windows.Application.GetContentStream%2A> della classe <xref:System.Windows.Application>, passando un URI di pacchetto che identifica il file di contenuto desiderato. <xref:System.Windows.Application.GetContentStream%2A> restituisce un oggetto <xref:System.Windows.Resources.StreamResourceInfo>, che espone il file di contenuto come <xref:System.IO.Stream> e ne descrive il tipo di contenuto.  
  
 Come esempio, il codice seguente illustra come usare <xref:System.Windows.Application.GetContentStream%2A> per caricare un file di contenuto <xref:System.Windows.Controls.Page> e impostarlo come contenuto di un <xref:System.Windows.Controls.Frame> (`pageFrame`).  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadAPageContentFileManuallyCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.cs#loadapagecontentfilemanuallycode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadAPageContentFileManuallyCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.vb#loadapagecontentfilemanuallycode)]  
  
 Quando si chiama <xref:System.Windows.Application.GetContentStream%2A> consente di accedere al <xref:System.IO.Stream>, è necessario eseguire l'operazione aggiuntiva di conversione nel tipo della proprietà che verrà impostata con. È invece possibile consentire a WPF di gestire l'apertura e la conversione del <xref:System.IO.Stream> caricando un file di risorse direttamente nella proprietà di un tipo usando il codice.  
  
 Nell'esempio seguente viene illustrato come caricare un <xref:System.Windows.Controls.Page> direttamente in una <xref:System.Windows.Controls.Frame> (`pageFrame`) utilizzando il codice.  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadPageContentFileFromCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.cs#loadpagecontentfilefromcode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadPageContentFileFromCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.vb#loadpagecontentfilefromcode)]  
  
 L'esempio seguente illustra il markup equivalente del precedente esempio.  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#LoadPageContentFileFromXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml#loadpagecontentfilefromxaml)]  
  
<a name="Site_of_Origin_Files"></a>   
## <a name="site-of-origin-files"></a>File del sito di origine  
 I file di risorse hanno una relazione esplicita con gli assembly distribuiti insieme, come definito dall'<xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute>. Talvolta, è tuttavia possibile che si debba stabilire una relazione implicita o inesistente tra un assembly e un file di dati dell'applicazione, come nei casi seguenti:  
  
- Un file non esiste in fase di compilazione.  
  
- I file richiesti dall'assembly non saranno noti fino alla fase di esecuzione.  
  
- Si desidera avere la possibilità di aggiornare i file senza ricompilare l'assembly al quale sono associati.  
  
- L'applicazione utilizza file di dati di grandi dimensioni, ad esempio audio e video, che devono essere scaricati dagli utenti unicamente su richiesta.  
  
 È possibile caricare questi tipi di file usando schemi URI tradizionali, ad esempio gli schemi file:///e http://.  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#AbsolutePackUriFileHttpReferenceXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/AbsolutePackUriPage.xaml#absolutepackurifilehttpreferencexaml)]  
  
 Tuttavia, gli schemi file:/// e http:// richiedono che l'applicazione abbia un livello di attendibilità totale. Se l'applicazione è un'applicazione browser XAML (XBAP) avviata da Internet o Intranet e richiede solo il set di autorizzazioni consentite per le applicazioni avviate da tali percorsi, i file separati possono essere caricati solo dal sito di origine dell'applicazione (percorso di avvio). Tali file sono noti come file *del sito di origine* .  
  
 I file del sito di origine rappresentano l'unica opzione per le applicazioni parzialmente attendibili, benché non siano limitati a questo tipo di applicazione. È possibile che le applicazioni completamente attendibili debbano caricare file di dati dell'applicazione sconosciuti in fase di compilazione. Sebbene queste applicazioni possano utilizzare file:///, è probabile che i file di dati dell'applicazione vengano installati nella stessa cartella dell'assembly dell'applicazione o in una sottocartella di questo. In questo caso è più facile utilizzare un riferimento al sito di origine piuttosto che file:///, poiché l'utilizzo di file:/// richiede l'elaborazione del percorso completo del file.  
  
> [!NOTE]
> I file del sito di origine non vengono memorizzati nella cache con un'applicazione browser XAML (XBAP) in un computer client, mentre i file di contenuto sono. Di conseguenza, vengono scaricati solo se esplicitamente richiesto. Se un'applicazione browser XAML (XBAP) contiene file multimediali di grandi dimensioni, la configurazione come file del sito di origine indica che l'avvio iniziale dell'applicazione è molto più veloce e che i file vengono scaricati solo su richiesta.  
  
### <a name="configuring-site-of-origin-files"></a>Configurazione dei file del sito di origine  
 Se i file del sito di origine sono inesistenti o sconosciuti in fase di compilazione, è necessario usare i meccanismi di distribuzione tradizionali per garantire che i file necessari siano disponibili in fase di esecuzione, incluso l'uso del programma `XCopy` dalla riga di comando o del Microsoft Windows Installer.  
  
 Se si conosce in fase di compilazione i file che si desidera individuare nel sito di origine, ma si desidera comunque evitare una dipendenza esplicita, è possibile aggiungere tali file a un progetto MSBuild come `None` elemento. Come per i file di contenuto, è necessario impostare l'attributo `CopyToOutputDirectory` di MSBuild per specificare che il file del sito di origine viene copiato in un percorso relativo all'assembly compilato, specificando il valore di `Always` o il valore di `PreserveNewest`.  
  
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
> In Visual Studio è possibile creare un file del sito di origine aggiungendo un file a un progetto e impostando il relativo `Build Action` su `None`.  
  
 Quando il progetto viene compilato, MSBuild copia i file specificati nella cartella di output di compilazione.  
  
### <a name="using-site-of-origin-files"></a>Uso dei file del sito di origine  
 Per caricare un file del sito di origine, è possibile chiamare il metodo <xref:System.Windows.Application.GetRemoteStream%2A> della classe <xref:System.Windows.Application>, passando un URI di pacchetto che identifica il file del sito di origine desiderato. <xref:System.Windows.Application.GetRemoteStream%2A> restituisce un oggetto <xref:System.Windows.Resources.StreamResourceInfo>, che espone il file del sito di origine come <xref:System.IO.Stream> e ne descrive il tipo di contenuto.  
  
 Come esempio, il codice seguente illustra come usare <xref:System.Windows.Application.GetRemoteStream%2A> per caricare un file del sito di origine <xref:System.Windows.Controls.Page> e impostarlo come contenuto di un <xref:System.Windows.Controls.Frame> (`pageFrame`).  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadAPageSOOFileManuallyCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/SOOPage.xaml.cs#loadapagesoofilemanuallycode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadAPageSOOFileManuallyCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/SOOPage.xaml.vb#loadapagesoofilemanuallycode)]  
  
 Quando si chiama <xref:System.Windows.Application.GetRemoteStream%2A> consente di accedere al <xref:System.IO.Stream>, è necessario eseguire l'operazione aggiuntiva di conversione nel tipo della proprietà che verrà impostata con. È invece possibile consentire a WPF di gestire l'apertura e la conversione del <xref:System.IO.Stream> caricando un file di risorse direttamente nella proprietà di un tipo usando il codice.  
  
 Nell'esempio seguente viene illustrato come caricare un <xref:System.Windows.Controls.Page> direttamente in una <xref:System.Windows.Controls.Frame> (`pageFrame`) utilizzando il codice.  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadPageSOOFileFromCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/SOOPage.xaml.cs#loadpagesoofilefromcode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadPageSOOFileFromCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/SOOPage.xaml.vb#loadpagesoofilefromcode)]  
  
 L'esempio seguente illustra il markup equivalente del precedente esempio.  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#LoadPageSOOFileFromXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/SOOPage.xaml#loadpagesoofilefromxaml)]  
  
<a name="Rebuilding_after_Changing_Build_Type"></a>   
## <a name="rebuilding-after-changing-build-type"></a>Ricompilazione in seguito alla modifica del tipo di compilazione  
 Dopo avere modificato il tipo di compilazione di un file di dati dell'applicazione, è necessario ricompilare l'intera applicazione affinché le modifiche vengano applicate. Se ci si limita a compilare l'applicazione, le modifiche non vengono applicate.  
  
## <a name="see-also"></a>Vedere anche

- [URI di tipo pack in WPF](pack-uris-in-wpf.md)
