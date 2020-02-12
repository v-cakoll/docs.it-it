---
title: URI di pacchetto
ms.date: 03/30/2017
helpviewer_keywords:
- pack URI scheme [WPF]
- loading embedded resources [WPF]
- URIs (Uniform Resource Identifiers)
- Uniform Resource Identifiers (URIs)
- loading non-resource files
- application management [WPF]
ms.assetid: 43adb517-21a7-4df3-98e8-09e9cdf764c4
ms.openlocfilehash: a98c97a4aa95fb956a2ca6d417e009a281a938b6
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/11/2020
ms.locfileid: "77124481"
---
# <a name="pack-uris-in-wpf"></a>URI di tipo pack in WPF

In Windows Presentation Foundation (WPF), gli URI (Uniform Resource Identifier) vengono usati per identificare e caricare i file in molti modi, inclusi i seguenti:

- Specifica del [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] da visualizzare all'avvio di un'applicazione.

- Caricando immagini.

- Spostandosi sulle pagine.

- Caricando file di dati non eseguibili.

Gli URI possono inoltre essere utilizzati per identificare e caricare file da diverse posizioni, incluse le seguenti:

- L'assembly corrente.

- Un assembly a cui si fa riferimento.

- Un percorso relativo a un assembly.

- L'applicazione del sito di origine.

Per fornire un meccanismo coerente per l'identificazione e il caricamento di questi tipi di file da questi percorsi, WPF sfrutta l'estensibilità dello *schema URI*di tipo pack. In questo argomento viene fornita una panoramica dello schema, viene illustrato come costruire URI di pacchetto per diversi scenari, vengono illustrati gli URI assoluti e relativi e la risoluzione degli URI, prima di illustrare come utilizzare gli URI di Pack da markup e codice.

<a name="The_Pack_URI_Scheme"></a>

## <a name="the-pack-uri-scheme"></a>Schema URI di tipo pack

Lo schema URI di tipo pack viene usato dalla specifica [Open Packaging Conventions](https://www.ecma-international.org/publications/standards/Ecma-376.htm) (OPC), che descrive un modello per organizzare e identificare il contenuto. Gli elementi chiave di questo modello sono i pacchetti e le parti, dove un *pacchetto* è un contenitore logico per una o più *parti*logiche. La figura seguente illustra questo concetto.

![Diagramma di package e parti](./media/pack-uris-in-wpf/wpf-package-parts-diagram.png)

Per identificare le parti, la specifica OPC sfrutta l'estendibilità di RFC 2396 (Uniform Resource Identifier (URI): sintassi generica) per definire lo schema URI di Pack.

Lo schema specificato da un URI viene definito dal relativo prefisso. http, FTP e file sono esempi noti. Lo schema URI di Pack utilizza "Pack" come schema e contiene due componenti: Authority e Path. Di seguito è riportato il formato per un URI di pacchetto.

*percorso*/dell'*autorità* Pack://

L' *autorità* specifica il tipo di pacchetto in cui è contenuta una parte, mentre il *percorso* specifica la posizione di una parte all'interno di un pacchetto.

Questo concetto è illustrato nella figura seguente:

![Relazione tra package, autorità e percorso](./media/pack-uris-in-wpf/wpf-relationship-diagram.png)

Pacchetti e parti sono analoghi ad applicazioni e file, dove un'applicazione (pacchetto) può includere uno o più file (parti), tra cui:

- File di risorse compilati nell'assembly locale.

- File di risorse compilati in un assembly a cui si fa riferimento.

- File di risorse compilati in un assembly contenente un riferimento.

- File di contenuto.

- File del sito di origine.

Per accedere a questi tipi di file, WPF supporta due autorità: application:///e siteoforigin:///. L'autorità application:/// identifica i file di dati dell'applicazione noti al momento della compilazione, inclusi file di risorse e di contenuto. L'autorità siteoforigin:/// identifica i file del sito di origine. La figura seguente illustra l'ambito di ciascuna autorità.

![Diagramma dell'URI di tipo pack](./media/pack-uris-in-wpf/wpf-pack-uri-scheme.png)

> [!NOTE]
> Il componente Authority di un URI di pacchetto è un URI incorporato che punta a un pacchetto e deve essere conforme allo standard RFC 2396. Inoltre, il carattere "/" deve essere sostituito con il carattere "," e i caratteri riservati quali "%" e "?" devono essere preceduti da un carattere di escape. Per informazioni dettagliate, vedere la specifica OPC.

Le sezioni seguenti illustrano come costruire gli URI di pacchetto usando queste due autorità insieme ai percorsi appropriati per l'identificazione dei file di risorse, di contenuto e del sito di origine.

<a name="Resource_File_Pack_URIs___Local_Assembly"></a>

## <a name="resource-file-pack-uris"></a>URI di tipo pack di file di risorse

I file di risorse sono configurati come MSBuild `Resource` gli elementi e vengono compilati in assembly. WPF supporta la costruzione di URI di tipo pack che possono essere utilizzati per identificare i file di risorse compilati nell'assembly locale o compilati in un assembly a cui viene fatto riferimento dall'assembly locale.

<a name="Local_Assembly_Resource_File"></a>

### <a name="local-assembly-resource-file"></a>File di risorse dell'assembly locale

L'URI di Pack per un file di risorse compilato nell'assembly locale usa l'autorità e il percorso seguenti:

- **Autorità**: application:///.

- **Percorso**: nome del file di risorse che include il percorso relativo alla radice della cartella del progetto dell'assembly locale.

Nell'esempio seguente viene illustrato l'URI di pacchetto per un file di risorse [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] che si trova nella radice della cartella del progetto dell'assembly locale.

`pack://application:,,,/ResourceFile.xaml`

Nell'esempio seguente viene illustrato l'URI di pacchetto per un file di risorse [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] che si trova in una sottocartella della cartella del progetto dell'assembly locale.

`pack://application:,,,/Subfolder/ResourceFile.xaml`

<a name="Resource_File_Pack_URIs___Referenced_Assembly"></a>

### <a name="referenced-assembly-resource-file"></a>File di risorse dell'assembly a cui si fa riferimento

L'URI di Pack per un file di risorse compilato in un assembly a cui si fa riferimento usa l'autorità e il percorso seguenti:

- **Autorità**: application:///.

- **Percorso**: nome di un file di risorse compilato in un assembly a cui si fa riferimento. Il percorso deve essere conforme al formato seguente:

  *NomeBreveAssembly*{ *; Versione*] { *; PublicKey*]; componente/*percorso*

  - **NomeBreveAssembly**: nome breve dell'assembly a cui si fa riferimento.

  - **;Versione** [facoltativo]: versione dell'assembly a cui si fa riferimento che contiene il file di risorse. Viene usato quando vengono caricati due o più assembly a cui si fa riferimento con lo stesso nome breve.

  - **;ChiavePubblica** [facoltativo]: chiave pubblica usata per firmare l'assembly a cui si fa riferimento. Viene usato quando vengono caricati due o più assembly a cui si fa riferimento con lo stesso nome breve.

  - **;component**: specifica che il riferimento all'assembly avviene dall'assembly locale.

  - **/Percorso**: nome del file di risorse, contenente il percorso relativo alla radice della cartella del progetto dell'assembly a cui si fa riferimento.

Nell'esempio seguente viene illustrato l'URI di pacchetto per un file di risorse [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] che si trova nella radice della cartella del progetto dell'assembly a cui si fa riferimento.

`pack://application:,,,/ReferencedAssembly;component/ResourceFile.xaml`

Nell'esempio seguente viene illustrato l'URI di pacchetto per un file di risorse [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] che si trova in una sottocartella della cartella del progetto dell'assembly a cui si fa riferimento.

`pack://application:,,,/ReferencedAssembly;component/Subfolder/ResourceFile.xaml`

Nell'esempio seguente viene illustrato l'URI di pacchetto per un file di risorse [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] che si trova nella cartella radice di una cartella di progetto di un assembly specifico della versione a cui si fa riferimento.

`pack://application:,,,/ReferencedAssembly;v1.0.0.1;component/ResourceFile.xaml`

Si noti che la sintassi dell'URI di Pack per i file di risorse dell'assembly a cui si fa riferimento può essere usata solo con l'autorità application:///. Il codice seguente, ad esempio, non è supportato in WPF.

`pack://siteoforigin:,,,/SomeAssembly;component/ResourceFile.xaml`

<a name="Content_File_Pack_URIs"></a>

## <a name="content-file-pack-uris"></a>URI di tipo pack di file di contenuto

L'URI di Pack per un file di contenuto usa l'autorità e il percorso seguenti:

- **Autorità**: application:///.

- **Percorso**: nome del file di contenuto contenente il percorso relativo alla posizione del file system del principale assembly eseguibile dell'applicazione.

Nell'esempio seguente viene illustrato l'URI di pacchetto per un file di contenuto [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], che si trova nella stessa cartella dell'assembly eseguibile.

`pack://application:,,,/ContentFile.xaml`

Nell'esempio seguente viene illustrato l'URI di pacchetto per un file di contenuto [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], che si trova in una sottocartella relativa all'assembly eseguibile dell'applicazione.

`pack://application:,,,/Subfolder/ContentFile.xaml`

> [!NOTE]
> Non è possibile passare a file di contenuto HTML. Lo schema URI supporta solo la navigazione a file HTML che si trovano nel sito di origine.

<a name="The_siteoforigin_____Authority"></a>

## <a name="site-of-origin-pack-uris"></a>URI di tipo pack del sito di origine

L'URI di Pack per un file del sito di origine usa l'autorità e il percorso seguenti:

- **Autorità**: siteoforigin:///.

- **Percorso**: nome del file del sito di origine contenente il percorso relativo alla posizione da cui è stato avviato l'assembly eseguibile.

Nell'esempio seguente viene illustrato l'URI di pacchetto per un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file del sito di origine, archiviato nel percorso da cui viene avviato l'assembly eseguibile.

`pack://siteoforigin:,,,/SiteOfOriginFile.xaml`

Nell'esempio seguente viene illustrato l'URI di pacchetto per un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file del sito di origine, archiviato nella sottocartella relativa al percorso da cui viene avviato l'assembly eseguibile dell'applicazione.

`pack://siteoforigin:,,,/Subfolder/SiteOfOriginFile.xaml`

<a name="Page_Files"></a>

## <a name="page-files"></a>File di paging

I file XAML configurati come MSBuild `Page` gli elementi vengono compilati in assembly nello stesso modo dei file di risorse. Di conseguenza, è possibile identificare gli elementi di MSBuild `Page` usando gli URI di pacchetto per i file di risorse.

I tipi di file di [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] comunemente configurati come MSBuild`Page` elementi hanno uno dei seguenti elementi come elemento radice:

- <xref:System.Windows.Window?displayProperty=nameWithType>

- <xref:System.Windows.Controls.Page?displayProperty=nameWithType>

- <xref:System.Windows.Navigation.PageFunction%601?displayProperty=nameWithType>

- <xref:System.Windows.ResourceDictionary?displayProperty=nameWithType>

- <xref:System.Windows.Documents.FlowDocument?displayProperty=nameWithType>

- <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType>

<a name="Absolute_vs_Relative_Pack_URIs"></a>

## <a name="absolute-vs-relative-pack-uris"></a>URI di pacchetto assoluto rispetto a

Un URI di pacchetto completo include lo schema, l'autorità e il percorso ed è considerato un URI di pacchetto assoluto. Per semplificare gli sviluppatori, [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] elementi consentono in genere di impostare attributi appropriati con un URI di pacchetto relativo, che include solo il percorso.

Si consideri, ad esempio, l'URI di pacchetto assoluto seguente per un file di risorse nell'assembly locale.

`pack://application:,,,/ResourceFile.xaml`

L'URI di pacchetto relativo che fa riferimento a questo file di risorse è il seguente.

`/ResourceFile.xaml`

> [!NOTE]
> Poiché i file del sito di origine non sono associati ad assembly, è possibile farvi riferimento solo con URI di pacchetto assoluti.

Per impostazione predefinita, un URI di pacchetto relativo viene considerato relativo alla posizione del markup o del codice che contiene il riferimento. Se viene utilizzata una barra rovesciata principale, tuttavia, il riferimento all'URI di pacchetto relativo viene quindi considerato relativo alla radice dell'applicazione. Si consideri ad esempio la struttura di progetto seguente.

`App.xaml`

`Page2.xaml`

`\SubFolder`

`+ Page1.xaml`

`+ Page2.xaml`

Se Pagina1. XAML contiene un URI che fa riferimento alla *radice*\SubFolder\Page2.XAML, il riferimento può usare l'URI di pacchetto relativo seguente.

`Page2.xaml`

Se Pagina1. XAML contiene un URI che fa riferimento alla *radice*\Page2.XAML, il riferimento può usare l'URI di pacchetto relativo seguente.

`/Page2.xaml`

<a name="Pack_URI_Resolution"></a>

## <a name="pack-uri-resolution"></a>Risoluzione degli URI di tipo pack

Il formato degli URI di tipo pack rende possibile l'aspetto degli URI di tipo pack per diversi tipi di file. Si consideri, ad esempio, l'URI di pacchetto assoluto seguente.

`pack://application:,,,/ResourceOrContentFile.xaml`

Questo URI di tipo pack assoluto può fare riferimento a un file di risorse nell'assembly locale o in un file di contenuto. Lo stesso vale per l'URI relativo seguente.

`/ResourceOrContentFile.xaml`

Per determinare il tipo di file a cui fa riferimento un URI di tipo pack, WPF risolve gli URI per i file di risorse in assembly locali e file di contenuto usando l'euristica seguente:

1. Esegue il probe dei metadati dell'assembly per un attributo <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> corrispondente all'URI del pacchetto.

2. Se viene trovato l'attributo <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute>, il percorso dell'URI del pacchetto fa riferimento a un file di contenuto.

3. Se l'attributo <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> non viene trovato, verificare i file di risorse impostati compilati nell'assembly locale.

4. Se viene trovato un file di risorse che corrisponde al percorso dell'URI del pacchetto, il percorso dell'URI del pacchetto fa riferimento a un file di risorse.

5. Se la risorsa non viene trovata, il <xref:System.Uri> creato internamente non è valido.

La risoluzione dell'URI non è valida per gli URI che fanno riferimento agli elementi seguenti:

- File di contenuto in assembly a cui si fa riferimento: questi tipi di file non sono supportati da WPF.

- File incorporati negli assembly a cui si fa riferimento: gli URI che li identificano sono univoci in quanto includono sia il nome dell'assembly a cui si fa riferimento sia il suffisso `;component`.

- File del sito di origine: gli URI che li identificano sono univoci perché sono gli unici file che possono essere identificati da URI di pacchetto che contengono l'autorità siteoforigin:///.

Una semplificazione che la risoluzione URI di Pack consente è che il codice sia indipendente dalle posizioni dei file di risorse e di contenuto. Se, ad esempio, si dispone di un file di risorse nell'assembly locale riconfigurato come file di contenuto, l'URI di pacchetto per la risorsa rimane invariato, così come il codice che usa l'URI di Pack.

<a name="Programming_with_Pack_URIs"></a>

## <a name="programming-with-pack-uris"></a>Programmazione con URI di tipo pack

Molte classi WPF implementano proprietà che possono essere impostate con URI di pacchetto, tra cui:

- <xref:System.Windows.Application.StartupUri%2A?displayProperty=nameWithType>

- <xref:System.Windows.Controls.Frame.Source%2A?displayProperty=nameWithType>

- <xref:System.Windows.Navigation.NavigationWindow.Source%2A?displayProperty=nameWithType>

- <xref:System.Windows.Documents.Hyperlink.NavigateUri%2A?displayProperty=nameWithType>

- <xref:System.Windows.Window.Icon%2A?displayProperty=nameWithType>

- <xref:System.Windows.Controls.Image.Source%2A?displayProperty=nameWithType>

Queste proprietà possono essere impostate da markup e codice. Questa sezione illustra le costruzioni di base per entrambi e quindi riporta esempi di scenari comuni.

<a name="Using_Pack_URIs_in_Markup"></a>

### <a name="using-pack-uris-in-markup"></a>Uso di URI di tipo pack nel markup

Un URI di pacchetto viene specificato nel markup impostando l'elemento di un attributo con l'URI del pacchetto. Ad esempio:

`<element attribute="pack://application:,,,/File.xaml" />`

Nella tabella 1 sono illustrati i vari URI di pacchetto assoluti che è possibile specificare nel markup.

Tabella 1: URI di tipo pack assoluti nel markup

|File|URI pack assoluto|
|----------|-------------------------------------------------------------------------------------------------------------------------|
|File di risorse - assembly locale|`"pack://application:,,,/ResourceFile.xaml"`|
|File di risorse in una sottocartella - assembly locale|`"pack://application:,,,/Subfolder/ResourceFile.xaml"`|
|File di risorse - assembly a cui si fa riferimento|`"pack://application:,,,/ReferencedAssembly;component/ResourceFile.xaml"`|
|File di risorse in una sottocartella dell'assembly a cui si fa riferimento|`"pack://application:,,,/ReferencedAssembly;component/Subfolder/ResourceFile.xaml"`|
|File di risorse in un assembly a cui si fa riferimento con versione|`"pack://application:,,,/ReferencedAssembly;v1.0.0.0;component/ResourceFile.xaml"`|
|File di contenuto|`"pack://application:,,,/ContentFile.xaml"`|
|File di contenuto in una sottocartella|`"pack://application:,,,/Subfolder/ContentFile.xaml"`|
|File del sito di origine|`"pack://siteoforigin:,,,/SOOFile.xaml"`|
|File del sito di origine in una sottocartella|`"pack://siteoforigin:,,,/Subfolder/SOOFile.xaml"`|

Nella tabella 2 sono illustrati i vari URI di pacchetto relativi che è possibile specificare nel markup.

Tabella 2: URI di tipo pack relativi nel markup

|File|URI di pacchetto relativo|
|----------|-------------------------------------------------------------------------------------------------------------------------|
|File di risorse nell'assembly locale|`"/ResourceFile.xaml"`|
|File di risorse in una sottocartella dell'assembly locale|`"/Subfolder/ResourceFile.xaml"`|
|File di risorse nell'assembly a cui si fa riferimento|`"/ReferencedAssembly;component/ResourceFile.xaml"`|
|File di risorse in una sottocartella dell'assembly a cui si fa riferimento|`"/ReferencedAssembly;component/Subfolder/ResourceFile.xaml"`|
|File di contenuto|`"/ContentFile.xaml"`|
|File di contenuto in una sottocartella|`"/Subfolder/ContentFile.xaml"`|

<a name="Using_Pack_URIs_in_Code"></a>

### <a name="using-pack-uris-in-code"></a>Uso di URI di tipo pack nel codice

È possibile specificare un URI di pacchetto nel codice creando un'istanza della classe <xref:System.Uri> e passando l'URI del pacchetto come parametro al costruttore. Questo approccio è illustrato nell'esempio seguente.

```csharp
Uri uri = new Uri("pack://application:,,,/File.xaml");
```

Per impostazione predefinita, la classe <xref:System.Uri> considera gli URI di pacchetto come assoluti. Di conseguenza, viene generata un'eccezione quando un'istanza della classe <xref:System.Uri> viene creata con un URI di pacchetto relativo.

```csharp
Uri uri = new Uri("/File.xaml");
```

Fortunatamente, l'overload <xref:System.Uri.%23ctor%28System.String%2CSystem.UriKind%29> del costruttore della classe <xref:System.Uri> accetta un parametro di tipo <xref:System.UriKind> per consentire di specificare se un URI di tipo pack è assoluto o relativo.

```csharp
// Absolute URI (default)
Uri absoluteUri = new Uri("pack://application:,,,/File.xaml", UriKind.Absolute);
// Relative URI
Uri relativeUri = new Uri("/File.xaml",
                        UriKind.Relative);
```

È necessario specificare solo <xref:System.UriKind.Absolute> o <xref:System.UriKind.Relative> quando si è certi che l'URI di pacchetto fornito sia uno o l'altro. Se non si conosce il tipo di URI di tipo pack usato, ad esempio quando un utente immette un URI di tipo pack in fase di esecuzione, usare invece <xref:System.UriKind.RelativeOrAbsolute>.

```csharp
// Relative or Absolute URI provided by user via a text box
TextBox userProvidedUriTextBox = new TextBox();
Uri uri = new Uri(userProvidedUriTextBox.Text, UriKind.RelativeOrAbsolute);
```

Nella tabella 3 vengono illustrati i vari URI di pacchetto relativi che è possibile specificare nel codice utilizzando <xref:System.Uri?displayProperty=nameWithType>.

Tabella 3: URI di tipo pack assoluti nel codice

|File|URI pack assoluto|
|----------|-------------------------------------------------------------------------------------------------------------------------|
|File di risorse - assembly locale|`Uri uri = new Uri("pack://application:,,,/ResourceFile.xaml", UriKind.Absolute);`|
|File di risorse in una sottocartella - assembly locale|`Uri uri = new Uri("pack://application:,,,/Subfolder/ResourceFile.xaml", UriKind.Absolute);`|
|File di risorse - assembly a cui si fa riferimento|`Uri uri = new Uri("pack://application:,,,/ReferencedAssembly;component/ResourceFile.xaml", UriKind.Absolute);`|
|File di risorse in una sottocartella dell'assembly a cui si fa riferimento|`Uri uri = new Uri("pack://application:,,,/ReferencedAssembly;component/Subfolder/ResourceFile.xaml", UriKind.Absolute);`|
|File di risorse in un assembly a cui si fa riferimento con versione|`Uri uri = new Uri("pack://application:,,,/ReferencedAssembly;v1.0.0.0;component/ResourceFile.xaml", UriKind.Absolute);`|
|File di contenuto|`Uri uri = new Uri("pack://application:,,,/ContentFile.xaml", UriKind.Absolute);`|
|File di contenuto in una sottocartella|`Uri uri = new Uri("pack://application:,,,/Subfolder/ContentFile.xaml", UriKind.Absolute);`|
|File del sito di origine|`Uri uri = new Uri("pack://siteoforigin:,,,/SOOFile.xaml", UriKind.Absolute);`|
|File del sito di origine in una sottocartella|`Uri uri = new Uri("pack://siteoforigin:,,,/Subfolder/SOOFile.xaml", UriKind.Absolute);`|

Nella tabella 4 sono illustrati i vari URI di pacchetto relativi che è possibile specificare nel codice utilizzando <xref:System.Uri?displayProperty=nameWithType>.

Tabella 4: URI di tipo pack relativi nel codice

|File|URI di pacchetto relativo|
|----------|-------------------------------------------------------------------------------------------------------------------------|
|File di risorse - assembly locale|`Uri uri = new Uri("/ResourceFile.xaml", UriKind.Relative);`|
|File di risorse in una sottocartella - assembly locale|`Uri uri = new Uri("/Subfolder/ResourceFile.xaml", UriKind.Relative);`|
|File di risorse - assembly a cui si fa riferimento|`Uri uri = new Uri("/ReferencedAssembly;component/ResourceFile.xaml", UriKind.Relative);`|
|File di risorse in una sottocartella - assembly a cui si fa riferimento|`Uri uri = new Uri("/ReferencedAssembly;component/Subfolder/ResourceFile.xaml", UriKind.Relative);`|
|File di contenuto|`Uri uri = new Uri("/ContentFile.xaml", UriKind.Relative);`|
|File di contenuto in una sottocartella|`Uri uri = new Uri("/Subfolder/ContentFile.xaml", UriKind.Relative);`|

<a name="Common_Pack_URI_Scenarios"></a>

### <a name="common-pack-uri-scenarios"></a>Scenari comuni di URI Pack

Nelle sezioni precedenti è stato illustrato come costruire URI di pacchetto per identificare i file di risorse, di contenuto e del sito di origine. In WPF queste costruzioni vengono usate in diversi modi e nelle sezioni seguenti vengono illustrati alcuni utilizzi comuni.

<a name="Specifying_the_UI_to_Show_when_an_Application_Starts"></a>

#### <a name="specifying-the-ui-to-show-when-an-application-starts"></a>Specifica dell'interfaccia utente da visualizzare all'avvio di un'applicazione

<xref:System.Windows.Application.StartupUri%2A> specifica il primo [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] da visualizzare quando viene avviata un'applicazione WPF. Per le applicazioni autonome, il [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] può essere una finestra, come illustrato nell'esempio seguente.

[!code-xaml[PackURIOverviewSnippets#StartupUriWindow](~/samples/snippets/csharp/VS_Snippets_Wpf/PackURIOverviewSnippets/CS/Copy of App.xaml#startupuriwindow)]

Le applicazioni autonome e le applicazioni browser XAML (XBAPs) possono inoltre specificare una pagina come interfaccia utente iniziale, come illustrato nell'esempio seguente.

[!code-xaml[PackURIOverviewSnippets#StartupUriPage](~/samples/snippets/csharp/VS_Snippets_Wpf/PackURIOverviewSnippets/CS/App.xaml#startupuripage)]

Se l'applicazione è un'applicazione autonoma e viene specificata una pagina con <xref:System.Windows.Application.StartupUri%2A>, WPF apre un <xref:System.Windows.Navigation.NavigationWindow> per ospitare la pagina. Per le applicazioni XBAPs, la pagina viene visualizzata nel browser host.

<a name="Navigating_to_a_Page"></a>

#### <a name="navigating-to-a-page"></a>Spostamento su una pagina

L'esempio seguente illustra come spostarsi su una pagina.

[!code-xaml[NavigationOverviewSnippets#HyperlinkXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml1)]
[!code-xaml[NavigationOverviewSnippets#HyperlinkXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml2)]
[!code-xaml[NavigationOverviewSnippets#HyperlinkXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml3)]

Per ulteriori informazioni sui vari modi per spostarsi in WPF, vedere [Cenni preliminari sulla navigazione](navigation-overview.md).

<a name="Specifying_a_Window_Icon"></a>

#### <a name="specifying-a-window-icon"></a>Specifica dell'icona di una finestra

L'esempio seguente illustra come usare un URI per specificare l'icona di una finestra.

[!code-xaml[WindowIconSnippets#WindowIconSetXAML](~/samples/snippets/xaml/VS_Snippets_Wpf/WindowIconSnippets/XAML/MainWindow.xaml#windowiconsetxaml)]

Per altre informazioni, vedere <xref:System.Windows.Window.Icon%2A>.

<a name="Loading_Image__Audio__and_Video_Files"></a>

#### <a name="loading-image-audio-and-video-files"></a>Caricamento di file di immagine, audio e video

WPF consente alle applicazioni di usare un'ampia gamma di tipi di supporti, che possono essere identificati e caricati con URI di tipo pack, come illustrato negli esempi seguenti.

[!code-xaml[MediaPlayerVideoSample#VideoPackURIAtSOO](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaPlayerVideoSample/CS/HomePage.xaml#videopackuriatsoo)]

[!code-xaml[MediaPlayerAudioSample#AudioPackURIAtSOO](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaPlayerAudioSample/CS/HomePage.xaml#audiopackuriatsoo)]

[!code-xaml[ImageSample#ImagePackURIContent](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageSample/CS/HomePage.xaml#imagepackuricontent)]

Per ulteriori informazioni sull'utilizzo del contenuto multimediale, vedere [grafica e multimedia](../graphics-multimedia/index.md).

<a name="Loading_a_Resource_Dictionary_from_the_Site_of_Origin"></a>

#### <a name="loading-a-resource-dictionary-from-the-site-of-origin"></a>Caricamento di un dizionario risorse dal sito di origine

È possibile usare i dizionari risorse (<xref:System.Windows.ResourceDictionary>) per supportare i temi dell'applicazione. Un modo per creare e gestire i temi consiste nel creare più temi come dizionari risorse che si trovano nel sito di origine di un'applicazione. In questo modo è possibile aggiungere e aggiornare i temi senza ricompilare e ridistribuire un'applicazione. Questi dizionari risorse possono essere identificati e caricati usando gli URI di pacchetto, come illustrato nell'esempio seguente.

[!code-xaml[ResourceDictionarySnippets#ResourceDictionaryPackURI](~/samples/snippets/csharp/VS_Snippets_Wpf/ResourceDictionarySnippets/CS/App.xaml#resourcedictionarypackuri)]

Per una panoramica dei temi in WPF, vedere applicazione di [stili e modelli](../../../desktop-wpf/fundamentals/styles-templates-overview.md).

## <a name="see-also"></a>Vedere anche

- [File di dati e di risorse dell'applicazione WPF](wpf-application-resource-content-and-data-files.md)
