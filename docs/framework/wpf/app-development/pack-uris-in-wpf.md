---
title: URI di tipo pack in WPF
ms.date: 03/30/2017
helpviewer_keywords:
- pack URI scheme [WPF]
- loading embedded resources [WPF]
- URIs (Uniform Resource Identifiers)
- Uniform Resource Identifiers (URIs)
- loading non-resource files
- application management [WPF]
ms.assetid: 43adb517-21a7-4df3-98e8-09e9cdf764c4
ms.openlocfilehash: f9ea4acfc7ba86d3424bb11af0de685651f99c61
ms.sourcegitcommit: bbfcc913c275885381820be28f61efcf8e83eecc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2019
ms.locfileid: "68796749"
---
# <a name="pack-uris-in-wpf"></a>URI di tipo pack in WPF

In Windows Presentation Foundation (WPF) [!INCLUDE[TLA#tla_uri#plural](../../../../includes/tlasharptla-urisharpplural-md.md)] vengono usati per identificare e caricare i file in molti modi, inclusi i seguenti:

- Che specifica [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] l'oggetto da visualizzare all'avvio iniziale di un'applicazione.

- Caricando immagini.

- Spostandosi sulle pagine.

- Caricando file di dati non eseguibili.

Inoltre, [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] può essere utilizzato per identificare e caricare i file da diverse posizioni, tra cui:

- L'assembly corrente.

- Un assembly a cui si fa riferimento.

- Un percorso relativo a un assembly.

- L'applicazione del sito di origine.

Per fornire un meccanismo coerente per l'identificazione e il caricamento di questi tipi di file da [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] questi percorsi, sfrutta l'estendibilità dello *schema URI*di tipo pack. In questo argomento viene fornita una panoramica dello schema, viene illustrato come creare [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] un pacchetto per un'ampia gamma di scenari, viene [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] illustrata l'assoluta e la [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] relativa risoluzione, [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] prima di illustrare l'utilizzo di Pack da entrambi i markup e codice.

<a name="The_Pack_URI_Scheme"></a>

## <a name="the-pack-uri-scheme"></a>Schema URI di tipo pack

Lo schema [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] di tipo pack viene usato dalla specifica [Open Packaging Conventions](https://go.microsoft.com/fwlink/?LinkID=71255) (OPC), che descrive un modello per organizzare e identificare il contenuto. Gli elementi chiave di questo modello sono i pacchetti e le parti, dove un *pacchetto* è un contenitore logico per una o più *parti*logiche. La figura seguente illustra questo concetto.

![Diagramma di package e parti](./media/pack-uris-in-wpf/wpf-package-parts-diagram.png)

Per identificare le parti, la specifica OPC sfrutta l'estendibilità di RFC 2396 (Uniform Resource Identifier (URI): Sintassi generica) per definire lo [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] schema di pacchetto.

Lo schema specificato da un oggetto [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] viene definito dal relativo prefisso. http, FTP e file sono esempi noti. Lo schema [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] di pacchetto utilizza "Pack" come schema e contiene due componenti: Authority e Path. Di seguito è riportato il formato di un [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]pacchetto.

*percorso* dell'*autorità*/Pack://

L' *autorità* specifica il tipo di pacchetto in cui è contenuta una parte, mentre il *percorso* specifica la posizione di una parte all'interno di un pacchetto.

Questo concetto è illustrato nella figura seguente:

![Relazione tra package, autorità e percorso](./media/pack-uris-in-wpf/wpf-relationship-diagram.png)

Pacchetti e parti sono analoghi ad applicazioni e file, dove un'applicazione (pacchetto) può includere uno o più file (parti), tra cui:

- File di risorse compilati nell'assembly locale.

- File di risorse compilati in un assembly a cui si fa riferimento.

- File di risorse compilati in un assembly contenente un riferimento.

- File di contenuto.

- File del sito di origine.

Per accedere a questi tipi di file [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] , supporta due autorità: Application:///e siteoforigin:///. L'autorità application:/// identifica i file di dati dell'applicazione noti al momento della compilazione, inclusi file di risorse e di contenuto. L'autorità siteoforigin:/// identifica i file del sito di origine. La figura seguente illustra l'ambito di ciascuna autorità.

![Diagramma dell'URI di tipo pack](./media/pack-uris-in-wpf/wpf-pack-uri-scheme.png)

> [!NOTE]
> Il componente Authority di un pacchetto [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] è un incorporato [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] che punta a un pacchetto e deve essere conforme allo standard RFC 2396. Inoltre, il carattere "/" deve essere sostituito con il carattere "," e i caratteri riservati quali "%" e "?" devono essere preceduti da un carattere di escape. Per informazioni dettagliate, vedere la specifica OPC.

Le sezioni seguenti illustrano come creare un [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] pacchetto usando queste due autorità insieme ai percorsi appropriati per identificare i file di risorse, di contenuto e del sito di origine.

<a name="Resource_File_Pack_URIs___Local_Assembly"></a>

## <a name="resource-file-pack-uris"></a>URI di tipo pack di file di risorse

I file di risorse sono [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] configurati come `Resource` elementi e vengono compilati in assembly. [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]supporta la costruzione di pacchetti [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] che possono essere utilizzati per identificare i file di risorse compilati nell'assembly locale o compilati in un assembly a cui viene fatto riferimento dall'assembly locale.

<a name="Local_Assembly_Resource_File"></a>

### <a name="local-assembly-resource-file"></a>File di risorse dell'assembly locale

Il pacchetto [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] per un file di risorse compilato nell'assembly locale usa l'autorità e il percorso seguenti:

- **Autorità**: application:///.

- **Percorso**: Nome del file di risorse, incluso il relativo percorso, relativo alla radice della cartella del progetto dell'assembly locale.

Nell'esempio seguente viene illustrato l' [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] oggetto Pack [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] per un file di risorse che si trova nella radice della cartella del progetto dell'assembly locale.

`pack://application:,,,/ResourceFile.xaml`

Nell'esempio seguente viene illustrato l' [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] oggetto Pack [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] per un file di risorse che si trova in una sottocartella della cartella del progetto dell'assembly locale.

`pack://application:,,,/Subfolder/ResourceFile.xaml`

<a name="Resource_File_Pack_URIs___Referenced_Assembly"></a>

### <a name="referenced-assembly-resource-file"></a>File di risorse dell'assembly a cui si fa riferimento

Il pacchetto [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] per un file di risorse compilato in un assembly a cui si fa riferimento usa l'autorità e il percorso seguenti:

- **Autorità**: application:///.

- **Percorso**: Nome di un file di risorse compilato in un assembly a cui si fa riferimento. Il percorso deve essere conforme al formato seguente:

  *NomeBreveAssembly* { *; Versione*] { *; PublicKey*]; componente/*percorso*

  - **NomeBreveAssembly**: nome breve dell'assembly a cui si fa riferimento.

  - **;Versione** [facoltativo]: versione dell'assembly a cui si fa riferimento che contiene il file di risorse. Viene usato quando vengono caricati due o più assembly a cui si fa riferimento con lo stesso nome breve.

  - **;ChiavePubblica** [facoltativo]: chiave pubblica usata per firmare l'assembly a cui si fa riferimento. Viene usato quando vengono caricati due o più assembly a cui si fa riferimento con lo stesso nome breve.

  - **;component**: specifica che il riferimento all'assembly avviene dall'assembly locale.

  - **/Percorso**: nome del file di risorse, contenente il percorso relativo alla radice della cartella del progetto dell'assembly a cui si fa riferimento.

Nell'esempio seguente viene illustrato l' [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] oggetto Pack [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] per un file di risorse che si trova nella radice della cartella del progetto dell'assembly a cui si fa riferimento.

`pack://application:,,,/ReferencedAssembly;component/ResourceFile.xaml`

Nell'esempio seguente viene illustrato l' [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] oggetto Pack [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] per un file di risorse che si trova in una sottocartella della cartella del progetto dell'assembly a cui si fa riferimento.

`pack://application:,,,/ReferencedAssembly;component/Subfolder/ResourceFile.xaml`

Nell'esempio seguente viene illustrato l' [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] oggetto Pack [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] per un file di risorse che si trova nella cartella radice di una cartella di progetto di un assembly specifico della versione a cui si fa riferimento.

`pack://application:,,,/ReferencedAssembly;v1.0.0.1;component/ResourceFile.xaml`

Si noti che la [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] sintassi Pack per i file di risorse dell'assembly a cui si fa riferimento può essere usata solo con l'autorità Application:///. Il codice seguente, ad esempio, non è [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]supportato in.

`pack://siteoforigin:,,,/SomeAssembly;component/ResourceFile.xaml`

<a name="Content_File_Pack_URIs"></a>

## <a name="content-file-pack-uris"></a>URI di tipo pack di file di contenuto

Il pacchetto [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] per un file di contenuto usa l'autorità e il percorso seguenti:

- **Autorità**: application:///.

- **Percorso**: Nome del file di contenuto, incluso il percorso relativo alla posizione file system dell'assembly eseguibile principale dell'applicazione.

Nell'esempio seguente viene illustrato l' [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] oggetto Pack [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] per un file di contenuto che si trova nella stessa cartella dell'assembly eseguibile.

`pack://application:,,,/ContentFile.xaml`

Nell'esempio seguente viene illustrato l' [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] oggetto Pack [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] per un file di contenuto, situato in una sottocartella relativa all'assembly eseguibile dell'applicazione.

`pack://application:,,,/Subfolder/ContentFile.xaml`

> [!NOTE]
> Non è possibile passare a file di contenuto HTML. Lo [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] schema supporta solo la navigazione a file HTML che si trovano nel sito di origine.

<a name="The_siteoforigin_____Authority"></a>

## <a name="site-of-origin-pack-uris"></a>URI di tipo pack del sito di origine

Il pacchetto [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] per un file del sito di origine usa l'autorità e il percorso seguenti:

- **Autorità**: siteoforigin:///.

- **Percorso**: Nome del file del sito di origine, incluso il percorso relativo alla posizione da cui è stato avviato l'assembly eseguibile.

Nell'esempio seguente viene illustrato l' [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] oggetto Pack [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] per un file del sito di origine, archiviato nella posizione da cui viene avviato l'assembly eseguibile.

`pack://siteoforigin:,,,/SiteOfOriginFile.xaml`

Nell'esempio seguente viene illustrato l' [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] oggetto Pack [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] per un file del sito di origine, archiviato nella sottocartella relativa al percorso da cui viene avviato l'assembly eseguibile dell'applicazione.

`pack://siteoforigin:,,,/Subfolder/SiteOfOriginFile.xaml`

<a name="Page_Files"></a>

## <a name="page-files"></a>File di paging

[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]i file configurati [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] come `Page` elementi vengono compilati in assembly nello stesso modo dei file di risorse. Di conseguenza [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] , `Page` gli elementi possono essere identificati usando Pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] per i file di risorse.

I tipi di [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file comunemente configurati come [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] `Page` elementi hanno uno dei seguenti elementi come elemento radice:

- <xref:System.Windows.Window?displayProperty=nameWithType>

- <xref:System.Windows.Controls.Page?displayProperty=nameWithType>

- <xref:System.Windows.Navigation.PageFunction%601?displayProperty=nameWithType>

- <xref:System.Windows.ResourceDictionary?displayProperty=nameWithType>

- <xref:System.Windows.Documents.FlowDocument?displayProperty=nameWithType>

- <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType>

<a name="Absolute_vs_Relative_Pack_URIs"></a>

## <a name="absolute-vs-relative-pack-uris"></a>URI di tipo pack assoluti e relativi

Un pacchetto [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] completo include lo schema, l'autorità e il percorso ed è considerato un pacchetto [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]assoluto. Per semplificare gli sviluppatori, [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] gli elementi consentono in genere di impostare attributi appropriati con un pacchetto [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]relativo, che include solo il percorso.

Si consideri, ad esempio, [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] il pacchetto assoluto seguente per un file di risorse nell'assembly locale.

`pack://application:,,,/ResourceFile.xaml`

Il pacchetto [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] relativo che fa riferimento a questo file di risorse è il seguente.

`/ResourceFile.xaml`

> [!NOTE]
> Poiché i file del sito di origine non sono associati ad assembly, è possibile farvi riferimento solo con il [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)]pacchetto Absolute.

Per impostazione predefinita, un pacchetto [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] relativo viene considerato relativo alla posizione del markup o del codice che contiene il riferimento. Se viene utilizzata una barra rovesciata principale, tuttavia, il [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] riferimento di pacchetto relativo viene considerato relativo alla radice dell'applicazione. Si consideri ad esempio la struttura di progetto seguente.

`App.xaml`

`Page2.xaml`

`\SubFolder`

`+ Page1.xaml`

`+ Page2.xaml`

Se Pagina1. XAML contiene un [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] che fa riferimento alla *radice*\SubFolder\Page2.XAML, il riferimento può usare il seguente [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]pacchetto relativo.

`Page2.xaml`

Se Pagina1. XAML contiene un [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] che fa riferimento alla *radice*\Page2.XAML, il riferimento può usare il seguente [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]pacchetto relativo.

`/Page2.xaml`

<a name="Pack_URI_Resolution"></a>

## <a name="pack-uri-resolution"></a>Risoluzione degli URI di tipo pack

Il formato di Pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] consente a Pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] per i diversi tipi di file di essere identici. Si consideri, ad esempio, [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]il pacchetto assoluto seguente.

`pack://application:,,,/ResourceOrContentFile.xaml`

Questo pacchetto [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] assoluto può fare riferimento a un file di risorse nell'assembly locale o in un file di contenuto. Lo stesso vale per l'oggetto relativo [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]seguente.

`/ResourceOrContentFile.xaml`

Per determinare il tipo di file a cui fa riferimento un [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] pacchetto, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] risolve [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] i file di risorse in assembly locali e file di contenuto usando l'euristica seguente:

1. Esegue il probe dei metadati <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> dell'assembly per un attributo [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]che corrisponde al pacchetto.

2. Se l' <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> attributo viene trovato, il percorso del pacchetto [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] fa riferimento a un file di contenuto.

3. Se l' <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> attributo non viene trovato, verificare i file di risorse set compilati nell'assembly locale.

4. Se viene trovato un file di risorse che corrisponde al percorso [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] del pacchetto, il percorso del pacchetto [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] fa riferimento a un file di risorse.

5. Se la risorsa non viene trovata, l'oggetto creato <xref:System.Uri> internamente non è valido.

[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]la risoluzione non si applica [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] a che fanno riferimento agli elementi seguenti:

- File di contenuto in assembly a cui si fa riferimento: questi tipi di [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]file non sono supportati da.

- File incorporati negli assembly a cui [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] si fa riferimento: che li identificano sono univoci perché includono sia il nome dell'assembly `;component` a cui si fa riferimento sia il suffisso.

- File del sito di origine [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] : che li identificano sono univoci perché sono gli unici file che possono essere identificati da Pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] che contengono l'autorità siteoforigin:///.

Una semplificazione consentita dalla risoluzione di Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] è che il codice sia indipendente dalle posizioni dei file di risorse e di contenuto. Se, ad esempio, si dispone di un file di risorse nell'assembly locale riconfigurato come file di contenuto, il pacchetto [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] per la risorsa rimane invariato, così come il codice che utilizza il pacchetto. [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]

<a name="Programming_with_Pack_URIs"></a>

## <a name="programming-with-pack-uris"></a>Programmazione con URI di tipo pack

Molte [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] classi implementano proprietà che possono essere impostate con [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)]Pack, tra cui:

- <xref:System.Windows.Application.StartupUri%2A?displayProperty=nameWithType>

- <xref:System.Windows.Controls.Frame.Source%2A?displayProperty=nameWithType>

- <xref:System.Windows.Navigation.NavigationWindow.Source%2A?displayProperty=nameWithType>

- <xref:System.Windows.Documents.Hyperlink.NavigateUri%2A?displayProperty=nameWithType>

- <xref:System.Windows.Window.Icon%2A?displayProperty=nameWithType>

- <xref:System.Windows.Controls.Image.Source%2A?displayProperty=nameWithType>

Queste proprietà possono essere impostate da markup e codice. Questa sezione illustra le costruzioni di base per entrambi e quindi riporta esempi di scenari comuni.

<a name="Using_Pack_URIs_in_Markup"></a>

### <a name="using-pack-uris-in-markup"></a>Uso di URI di tipo pack nel markup

Un pacchetto [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] viene specificato nel markup impostando l'elemento di un attributo con il pacchetto [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]. Ad esempio:

`<element attribute="pack://application:,,,/File.xaml" />`

Nella tabella 1 sono illustrati i diversi [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] pacchetti assoluti che è possibile specificare nel markup.

Tabella 1: URI di pacchetto assoluti nel markup

|File|Pack assoluto[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]|
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

Nella tabella 2 sono illustrati i vari [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] pacchetti relativi che è possibile specificare nel markup.

Tabella 2: URI di pacchetto relativi nel markup

|File|Pacchetto relativo[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]|
|----------|-------------------------------------------------------------------------------------------------------------------------|
|File di risorse nell'assembly locale|`"/ResourceFile.xaml"`|
|File di risorse in una sottocartella dell'assembly locale|`"/Subfolder/ResourceFile.xaml"`|
|File di risorse nell'assembly a cui si fa riferimento|`"/ReferencedAssembly;component/ResourceFile.xaml"`|
|File di risorse in una sottocartella dell'assembly a cui si fa riferimento|`"/ReferencedAssembly;component/Subfolder/ResourceFile.xaml"`|
|File di contenuto|`"/ContentFile.xaml"`|
|File di contenuto in una sottocartella|`"/Subfolder/ContentFile.xaml"`|

<a name="Using_Pack_URIs_in_Code"></a>

### <a name="using-pack-uris-in-code"></a>Uso di URI di tipo pack nel codice

Per specificare un pacchetto [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] nel codice, creare un'istanza <xref:System.Uri> della classe e passare il [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] pacchetto come parametro al costruttore. come illustrato nell'esempio seguente.

```csharp
Uri uri = new Uri("pack://application:,,,/File.xaml");
```

Per impostazione predefinita, <xref:System.Uri> la classe considera [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] il pacchetto come assoluto. Di conseguenza, viene generata un'eccezione quando viene creata un' <xref:System.Uri> istanza della classe con un pacchetto [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]relativo.

```csharp
Uri uri = new Uri("/File.xaml");
```

Fortunatamente, l' <xref:System.Uri.%23ctor%28System.String%2CSystem.UriKind%29> overload <xref:System.Uri> del costruttore della classe accetta un parametro di tipo <xref:System.UriKind> per consentire di specificare se un pacchetto [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] è assoluto o relativo.

```csharp
// Absolute URI (default)
Uri absoluteUri = new Uri("pack://application:,,,/File.xaml", UriKind.Absolute);
// Relative URI
Uri relativeUri = new Uri("/File.xaml",
                        UriKind.Relative);
```

È necessario specificare solo <xref:System.UriKind.Absolute> o <xref:System.UriKind.Relative> quando si è certi che il pacchetto [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] fornito sia uno o l'altro. Se non si conosce il tipo di pacchetto [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] usato, ad esempio quando un utente immette un pacchetto [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] in fase di esecuzione, usare <xref:System.UriKind.RelativeOrAbsolute> invece.

```csharp
// Relative or Absolute URI provided by user via a text box
TextBox userProvidedUriTextBox = new TextBox();
Uri uri = new Uri(userProvidedUriTextBox.Text, UriKind.RelativeOrAbsolute);
```

Nella tabella 3 vengono illustrati i vari [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] pacchetti relativi che è possibile specificare nel codice <xref:System.Uri?displayProperty=nameWithType>tramite.

Tabella 3: URI di pacchetto assoluti nel codice

|File|Pack assoluto[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]|
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

Nella tabella 4 sono illustrati i diversi [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] pacchetti relativi che è possibile specificare nel <xref:System.Uri?displayProperty=nameWithType>codice utilizzando.

Tabella 4: URI di pacchetto relativi nel codice

|File|Pacchetto relativo[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]|
|----------|-------------------------------------------------------------------------------------------------------------------------|
|File di risorse - assembly locale|`Uri uri = new Uri("/ResourceFile.xaml", UriKind.Relative);`|
|File di risorse in una sottocartella - assembly locale|`Uri uri = new Uri("/Subfolder/ResourceFile.xaml", UriKind.Relative);`|
|File di risorse - assembly a cui si fa riferimento|`Uri uri = new Uri("/ReferencedAssembly;component/ResourceFile.xaml", UriKind.Relative);`|
|File di risorse in una sottocartella - assembly a cui si fa riferimento|`Uri uri = new Uri("/ReferencedAssembly;component/Subfolder/ResourceFile.xaml", UriKind.Relative);`|
|File di contenuto|`Uri uri = new Uri("/ContentFile.xaml", UriKind.Relative);`|
|File di contenuto in una sottocartella|`Uri uri = new Uri("/Subfolder/ContentFile.xaml", UriKind.Relative);`|

<a name="Common_Pack_URI_Scenarios"></a>

### <a name="common-pack-uri-scenarios"></a>Scenari comuni di URI Pack

Nelle sezioni precedenti è stato illustrato come creare un [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] pacchetto per identificare i file di risorse, contenuti e siti di origine. In [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]queste costruzioni vengono usate in diversi modi e nelle sezioni seguenti vengono illustrati alcuni utilizzi comuni.

<a name="Specifying_the_UI_to_Show_when_an_Application_Starts"></a>

#### <a name="specifying-the-ui-to-show-when-an-application-starts"></a>Specifica dell'interfaccia utente da visualizzare all'avvio di un'applicazione

<xref:System.Windows.Application.StartupUri%2A>Specifica il primo [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] da visualizzare quando viene [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] avviata un'applicazione. Per le applicazioni autonome [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] , può essere una finestra, come illustrato nell'esempio seguente.

[!code-xaml[PackURIOverviewSnippets#StartupUriWindow](~/samples/snippets/csharp/VS_Snippets_Wpf/PackURIOverviewSnippets/CS/Copy of App.xaml#startupuriwindow)]

Le applicazioni autonome e [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] possono inoltre specificare una pagina come interfaccia utente iniziale, come illustrato nell'esempio seguente.

[!code-xaml[PackURIOverviewSnippets#StartupUriPage](~/samples/snippets/csharp/VS_Snippets_Wpf/PackURIOverviewSnippets/CS/App.xaml#startupuripage)]

Se l'applicazione è un'applicazione autonoma e viene specificata una pagina <xref:System.Windows.Application.StartupUri%2A>con [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] , apre <xref:System.Windows.Navigation.NavigationWindow> per ospitare la pagina. Per [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)], la pagina viene visualizzata nel browser host.

<a name="Navigating_to_a_Page"></a>

#### <a name="navigating-to-a-page"></a>Spostamento su una pagina

L'esempio seguente illustra come spostarsi su una pagina.

[!code-xaml[NavigationOverviewSnippets#HyperlinkXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml1)]
[!code-xaml[NavigationOverviewSnippets#HyperlinkXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml2)]
[!code-xaml[NavigationOverviewSnippets#HyperlinkXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml3)]

Per ulteriori informazioni sui vari modi per spostarsi in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], vedere [Cenni preliminari sulla navigazione](navigation-overview.md).

<a name="Specifying_a_Window_Icon"></a>

#### <a name="specifying-a-window-icon"></a>Specifica dell'icona di una finestra

L'esempio seguente illustra come usare un URI per specificare l'icona di una finestra.

[!code-xaml[WindowIconSnippets#WindowIconSetXAML](~/samples/snippets/xaml/VS_Snippets_Wpf/WindowIconSnippets/XAML/MainWindow.xaml#windowiconsetxaml)]

Per altre informazioni, vedere <xref:System.Windows.Window.Icon%2A>.

<a name="Loading_Image__Audio__and_Video_Files"></a>

#### <a name="loading-image-audio-and-video-files"></a>Caricamento di file di immagine, audio e video

[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]consente alle applicazioni di usare un'ampia gamma di tipi di supporti, che possono essere identificati e caricati con [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)]il pacchetto, come illustrato negli esempi seguenti.

[!code-xaml[MediaPlayerVideoSample#VideoPackURIAtSOO](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaPlayerVideoSample/CS/HomePage.xaml#videopackuriatsoo)]

[!code-xaml[MediaPlayerAudioSample#AudioPackURIAtSOO](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaPlayerAudioSample/CS/HomePage.xaml#audiopackuriatsoo)]

[!code-xaml[ImageSample#ImagePackURIContent](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageSample/CS/HomePage.xaml#imagepackuricontent)]

Per ulteriori informazioni sull'utilizzo del contenuto multimediale, vedere [grafica e multimedia](../graphics-multimedia/index.md).

<a name="Loading_a_Resource_Dictionary_from_the_Site_of_Origin"></a>

#### <a name="loading-a-resource-dictionary-from-the-site-of-origin"></a>Caricamento di un dizionario risorse dal sito di origine

È possibile usare<xref:System.Windows.ResourceDictionary>i dizionari risorse () per supportare i temi dell'applicazione. Un modo per creare e gestire i temi consiste nel creare più temi come dizionari risorse che si trovano nel sito di origine di un'applicazione. In questo modo è possibile aggiungere e aggiornare i temi senza ricompilare e ridistribuire un'applicazione. Questi dizionari risorse possono essere identificati e caricati usando [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)]Pack, illustrato nell'esempio seguente.

[!code-xaml[ResourceDictionarySnippets#ResourceDictionaryPackURI](~/samples/snippets/csharp/VS_Snippets_Wpf/ResourceDictionarySnippets/CS/App.xaml#resourcedictionarypackuri)]

Per una panoramica dei temi in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], vedere applicazione di [stili e modelli](../controls/styling-and-templating.md).

## <a name="see-also"></a>Vedere anche

- [File di dati e di risorse dell'applicazione WPF](wpf-application-resource-content-and-data-files.md)
