---
title: URI di tipo pack in WPF
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pack URI scheme [WPF]
- loading embedded resources [WPF]
- URIs (Uniform Resource Identifiers)
- Uniform Resource Identifiers (URIs)
- loading non-resource files
- application management [WPF]
ms.assetid: 43adb517-21a7-4df3-98e8-09e9cdf764c4
caps.latest.revision: 35
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d90345f6c6e44bfdd98d2a1313a36372cdfe8b06
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/30/2018
---
# <a name="pack-uris-in-wpf"></a>URI di tipo pack in WPF
In Windows Presentation Foundation (WPF), [!INCLUDE[TLA#tla_uri#plural](../../../../includes/tlasharptla-urisharpplural-md.md)] vengono utilizzati per identificare e caricare i file in molti modi, inclusi i seguenti:  
  
-   Specifica il [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] da visualizzare al primo avvio di un'applicazione.  
  
-   Caricando immagini.  
  
-   Spostandosi sulle pagine.  
  
-   Caricando file di dati non eseguibili.  
  
 Inoltre, [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] può essere utilizzato per identificare e caricare i file da varie posizioni, tra cui le operazioni seguenti:  
  
-   L'assembly corrente.  
  
-   Un assembly a cui si fa riferimento.  
  
-   Un percorso relativo a un assembly.  
  
-   L'applicazione del sito di origine.  
  
 Per fornire un meccanismo uniforme per l'identificazione e il caricamento di questi tipi di file da questi percorsi, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] sfrutta l'estensibilità del *schema URI di tipo pack*. In questo argomento viene fornita una panoramica dello schema, viene illustrato come costruire pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] per un'ampia gamma di scenari, illustra absolute e relative [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] e [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] risoluzione, prima che illustra come utilizzare pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] da entrambi markup e il codice.  
  
  
<a name="The_Pack_URI_Scheme"></a>   
## <a name="the-pack-uri-scheme"></a>Schema URI di tipo pack  
 Il pacchetto di [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] lo schema viene utilizzato il [Open Packaging Conventions](http://go.microsoft.com/fwlink/?LinkID=71255) specifica (OPC), che descrive un modello per l'organizzazione e l'identificazione del contenuto. Gli elementi principali di questo modello sono pacchetti e le parti, in cui un *pacchetto* è un contenitore logico per uno o più logica *parti*. La figura seguente illustra questo concetto.  
  
 ![Diagramma di pacchetti e parti](../../../../docs/framework/wpf/app-development/media/wpfpackurischemefigure1.PNG "WPFPackURISchemeFigure1")  
  
 Per identificare le parti, la specifica OPC sfrutta l'estensibilità dello standard RFC 2396 (Uniform Resource Identifiers (URI): sintassi generica) per definire il pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] schema.  
  
 Lo schema specificato da un [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] è definito dal prefisso; http, ftp e file sono esempi noti. Il pacchetto [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] schema utilizza "pack" come schema e contiene due componenti: autorità e percorso. Di seguito è riportato il formato per un pacchetto [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].  
  
 Service Pack: / /*autorità*/*percorso*
  
 Il *autorità* specifica il tipo di pacchetto che è contenuta una parte, mentre il *percorso* specifica il percorso di una parte all'interno di un pacchetto.  
  
 Questo concetto è illustrato nella figura seguente:  
  
 ![Relazioni tra pacchetto, autorità e percorso](../../../../docs/framework/wpf/app-development/media/wpfpackurischemefigure2.PNG "WPFPackURISchemeFigure2")  
  
 Pacchetti e parti sono analoghi ad applicazioni e file, dove un'applicazione (pacchetto) può includere uno o più file (parti), tra cui:  
  
-   File di risorse compilati nell'assembly locale.  
  
-   File di risorse compilati in un assembly a cui si fa riferimento.  
  
-   File di risorse compilati in un assembly contenente un riferimento.  
  
-   File di contenuto.  
  
-   File del sito di origine.  
  
 Per accedere a questi tipi di file, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] supporta due autorità: application: / / / e siteoforigin: / / /. L'autorità application:/// identifica i file di dati dell'applicazione noti al momento della compilazione, inclusi file di risorse e di contenuto. L'autorità siteoforigin:/// identifica i file del sito di origine. La figura seguente illustra l'ambito di ciascuna autorità.  
  
 ![Diagramma dell'URI di tipo pack](../../../../docs/framework/wpf/app-development/media/wpfpackurischemefigure4.png "WPFPackURISchemeFigure4")  
  
> [!NOTE]
>  Il componente autorità di un pacchetto di [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] è incorporato [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] che punta a un pacchetto e deve essere conforme allo standard RFC 2396. Inoltre, il carattere "/" deve essere sostituito con il carattere "," e i caratteri riservati quali "%" e "?" devono essere preceduti da un carattere di escape. Per informazioni dettagliate, vedere la specifica OPC.  
  
 Le sezioni seguenti illustrano come costruire pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] utilizzando queste due autorità in combinazione con i percorsi appropriati per l'identificazione delle risorse e il contenuto del sito di origine.  
  
<a name="Resource_File_Pack_URIs___Local_Assembly"></a>   
## <a name="resource-file-pack-uris"></a>URI di tipo pack di file di risorse  
 File di risorse sono configurati come [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] `Resource` gli elementi e vengono compilati in assembly. [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] supporta la costruzione di pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] che può essere utilizzato per identificare i file di risorse che vengono compilati nell'assembly locale o in un assembly cui viene fatto riferimento dall'assembly locale.  
  
<a name="Local_Assembly_Resource_File"></a>   
### <a name="local-assembly-resource-file"></a>File di risorse dell'assembly locale  
 Il pacchetto di [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] per una risorsa file compilato nell'assembly locale utilizza autorità e il percorso seguente:  
  
-   **Autorità**: application:///.  
  
-   **Percorso**: nome del file di risorse che include il percorso relativo alla radice della cartella del progetto dell'assembly locale.  
  
 Nell'esempio seguente viene illustrato il pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] per un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file di risorse che si trova nella radice della cartella di progetto dell'assembly locale.  
  
 `pack://application:,,,/ResourceFile.xaml`  
  
 Nell'esempio seguente viene illustrato il pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] per un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file di risorse che si trova in una sottocartella della cartella del progetto dell'assembly locale.  
  
 `pack://application:,,,/Subfolder/ResourceFile.xaml`  
  
<a name="Resource_File_Pack_URIs___Referenced_Assembly"></a>   
### <a name="referenced-assembly-resource-file"></a>File di risorse dell'assembly a cui si fa riferimento  
 Il pacchetto di [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] per una risorsa file che viene compilato in un assembly di riferimento utilizza autorità e il percorso seguente:  
  
-   **Autorità**: application:///.  
  
-   **Percorso**: nome di un file di risorse compilato in un assembly a cui si fa riferimento. Il percorso deve essere conforme al formato seguente:  
  
     *AssemblyShortName*{*; Versione*] {*; PublicKey*]; component /*percorso*  
  
    -   **NomeBreveAssembly**: nome breve dell'assembly a cui si fa riferimento.  
  
    -   **;Versione** [facoltativo]: versione dell'assembly a cui si fa riferimento che contiene il file di risorse. Viene usato quando vengono caricati due o più assembly a cui si fa riferimento con lo stesso nome breve.  
  
    -   **;ChiavePubblica** [facoltativo]: chiave pubblica usata per firmare l'assembly a cui si fa riferimento. Viene usato quando vengono caricati due o più assembly a cui si fa riferimento con lo stesso nome breve.  
  
    -   **;component**: specifica che il riferimento all'assembly avviene dall'assembly locale.  
  
    -   **/Percorso**: nome del file di risorse, contenente il percorso relativo alla radice della cartella del progetto dell'assembly a cui si fa riferimento.  
  
 Nell'esempio seguente viene illustrato il pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] per un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file di risorse che si trova nella radice della cartella di progetto dell'assembly di riferimento.  
  
 `pack://application:,,,/ReferencedAssembly;component/ResourceFile.xaml`  
  
 Nell'esempio seguente viene illustrato il pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] per un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file di risorse che si trova in una sottocartella della cartella del progetto dell'assembly di riferimento.  
  
 `pack://application:,,,/ReferencedAssembly;component/Subfolder/ResourceFile.xaml`  
  
 Nell'esempio seguente viene illustrato il pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] per un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file di risorse che si trova nella cartella radice della cartella di progetto un riferimento, specifici della versione dell'assembly.  
  
 `pack://application:,,,/ReferencedAssembly;v1.0.0.1;component/ResourceFile.xaml`  
  
 Si noti che il pacchetto [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] sintassi per i file di risorse di assembly di riferimento può essere utilizzata solo con l'applicazione: / / / autorità. Ad esempio, le operazioni seguenti non sono supportata [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].  
  
 `pack://siteoforigin:,,,/SomeAssembly;component/ResourceFile.xaml`  
  
<a name="Content_File_Pack_URIs"></a>   
## <a name="content-file-pack-uris"></a>URI di tipo pack di file di contenuto  
 Il pacchetto di [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] per un file di contenuto Usa autorità e il percorso seguente:  
  
-   **Autorità**: application:///.  
  
-   **Percorso**: nome del file di contenuto contenente il percorso relativo alla posizione del file system del principale assembly eseguibile dell'applicazione.  
  
 Nell'esempio seguente viene illustrato il pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] per un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file di contenuto, si trova nella stessa cartella dell'assembly eseguibile.  
  
 `pack://application:,,,/ContentFile.xaml`  
  
 Nell'esempio seguente viene illustrato il pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] per un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file di contenuto, si trova in una sottocartella relativo all'assembly eseguibile dell'applicazione.  
  
 `pack://application:,,,/Subfolder/ContentFile.xaml`  
  
> [!NOTE]
>  Non è possibile spostarsi su file di contenuto [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)]. Il [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] schema supporta solo lo spostamento di [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)] file che si trovano nel sito di origine.  
  
<a name="The_siteoforigin_____Authority"></a>   
## <a name="site-of-origin-pack-uris"></a>URI di tipo pack del sito di origine  
 Il pacchetto di [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] per un sito di origine file utilizza autorità e il percorso seguente:  
  
-   **Autorità**: siteoforigin:///.  
  
-   **Percorso**: nome del file del sito di origine contenente il percorso relativo alla posizione da cui è stato avviato l'assembly eseguibile.  
  
 Nell'esempio seguente viene illustrato il pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] per un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file sito di origine, archiviato nella posizione da cui viene avviato l'assembly eseguibile.  
  
 `pack://siteoforigin:,,,/SiteOfOriginFile.xaml`  
  
 Nell'esempio seguente viene illustrato il pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] per un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file sito di origine, archiviato in una sottocartella, è relativo al percorso da cui viene avviato l'assembly eseguibile dell'applicazione.  
  
 `pack://siteoforigin:,,,/Subfolder/SiteOfOriginFile.xaml`  
  
<a name="Page_Files"></a>   
## <a name="page-files"></a>File di paging  
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] i file che sono configurati come [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] `Page` gli elementi vengono compilati in assembly nello stesso modo come file di risorse. Di conseguenza, [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] `Page` elementi possono essere identificati utilizzando pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] per i file di risorse.  
  
 I tipi di [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file che sono in genere configurati come [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] `Page` gli elementi hanno uno dei seguenti elementi radice:  
  
-   <xref:System.Windows.Window?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Controls.Page?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Navigation.PageFunction%601?displayProperty=nameWithType>  
  
-   <xref:System.Windows.ResourceDictionary?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Documents.FlowDocument?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType>  
  
<a name="Absolute_vs_Relative_Pack_URIs"></a>   
## <a name="absolute-vs-relative-pack-uris"></a>URI di tipo pack assoluti e relativi  
 Un pacchetto completo [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] include lo schema, l'autorità e percorso, e viene considerato un pack assoluto [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]. Per semplificare il lavoro per gli sviluppatori, [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] elementi consentono di impostare gli attributi appropriati con un relativo pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)], che include solo il percorso.  
  
 Ad esempio, si consideri il seguente pack assoluto [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] per un file di risorse nell'assembly locale.  
  
 `pack://application:,,,/ResourceFile.xaml`  
  
 Il relativo pacchetto [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] che fa riferimento a questa risorsa file potrebbe essere la seguente.  
  
 `/ResourceFile.xaml`  
  
> [!NOTE]
>  Poiché il file di origine del sito non sono associati agli assembly, è possibile solo possibile farvi riferimento assoluto Pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)].  
  
 Per impostazione predefinita, un Service pack relativo [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] viene considerato relativo alla posizione del markup o del codice che contiene il riferimento. Se viene utilizzata una barra rovesciata iniziale, tuttavia, il relativo pacchetto [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] riferimento viene quindi considerato relativo alla radice dell'applicazione. Si consideri ad esempio la struttura di progetto seguente.  
  
 `App.xaml`  
  
 `Page2.xaml`  
  
 `\SubFolder`  
  
 `+ Page1.xaml`  
  
 `+ Page2.xaml`  
  
 Se Page1 contiene un [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] che fa riferimento *radice*\SubFolder\Page2.xaml, il riferimento può utilizzare il seguente pack relativo [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].  
  
 `Page2.xaml`  
  
 Se Page1 contiene un [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] che fa riferimento *radice*\Page2.xaml, il riferimento può utilizzare il seguente pack relativo [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].  
  
 `/Page2.xaml`  
  
<a name="Pack_URI_Resolution"></a>   
## <a name="pack-uri-resolution"></a>Risoluzione degli URI di tipo pack  
 Il formato del pacchetto [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] rende possibile per pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] per diversi tipi di file abbia lo stesso aspetto. Ad esempio, si consideri il seguente pack assoluto [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].  
  
 `pack://application:,,,/ResourceOrContentFile.xaml`  
  
 Questo pacchetto assoluto [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] potrebbe fare riferimento a un file di risorse nell'assembly locale o un file di contenuto. Lo stesso vale per il seguente relativo [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].  
  
 `/ResourceOrContentFile.xaml`  
  
 Per determinare il tipo di file di un pacchetto di [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] fa riferimento, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] risolve [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] per i file di risorse negli assembly locali e i file di contenuto utilizzando la seguente euristica:  
  
1.  I metadati dell'assembly per verificare la presenza di un <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> attributo che corrisponda al pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].  
  
2.  Se il <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> attributo viene trovato, il percorso del pacchetto di [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] fa riferimento a un file di contenuto.  
  
3.  Se il <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> attributo non viene trovato, esaminare i file di set di risorse che vengono compilati in assembly locale.  
  
4.  Se un file di risorse che corrisponde al percorso del pacchetto di [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] viene trovato, il percorso del pacchetto di [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] fa riferimento a un file di risorse.  
  
5.  Se la risorsa non viene trovato, internamente creato <xref:System.Uri> non è valido.  
  
 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] la risoluzione non è applicabile per [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] che fanno riferimento al seguente:  
  
-   File di dati negli assembly di riferimento: questi tipi di file non supportati da [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].  
  
-   File incorporati negli assembly di riferimento: [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] che li identificano sono univoci, perché includono sia il nome dell'assembly di riferimento e `;component` suffisso.  
  
-   Sito di origine: [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] che li identificano sono univoci in quanto sono i soli file che possono essere identificati da pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] che contengono il siteoforigin: / / / autorità.  
  
 Una semplificazione di tipo pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] risoluzione consente al codice di essere indipendente dai percorsi dei file di risorse e dei file. Ad esempio, se si dispone di un file di risorse nell'assembly locale che viene riconfigurato in modo da un file di contenuto, il pacchetto di [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] per la risorsa rimane lo stesso, anche il codice che utilizza tale [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].  
  
<a name="Programming_with_Pack_URIs"></a>   
## <a name="programming-with-pack-uris"></a>Programmazione con URI di tipo pack  
 Molti [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] classi implementano proprietà che possono essere impostate con Service pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)], tra cui:  
  
-   <xref:System.Windows.Application.StartupUri%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Controls.Frame.Source%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Navigation.NavigationWindow.Source%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Documents.Hyperlink.NavigateUri%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Window.Icon%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Controls.Image.Source%2A?displayProperty=nameWithType>  
  
 Queste proprietà possono essere impostate da markup e codice. Questa sezione illustra le costruzioni di base per entrambi e quindi riporta esempi di scenari comuni.  
  
<a name="Using_Pack_URIs_in_Markup"></a>   
### <a name="using-pack-uris-in-markup"></a>Uso di URI di tipo pack nel markup  
 Un pacchetto di [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] viene specificato nel markup impostando l'elemento di un attributo con il pacchetto [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]. Ad esempio:  
  
 `<element attribute="pack://application:,,,/File.xaml" />`  
  
 Tabella 1 sono illustrati i vari pack assoluto [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] che è possibile specificare nel markup.  
  
 Tabella 1: URI di tipo pack assoluti nel markup  
  
|File|Pack assoluto [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]|  
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
  
 Tabella 2 sono illustrati i vari pack relativi [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] che è possibile specificare nel markup.  
  
 Tabella 2: URI di tipo pack relativi nel markup  
  
|File|Pack relativo [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]|  
|----------|-------------------------------------------------------------------------------------------------------------------------|  
|File di risorse nell'assembly locale|`"/ResourceFile.xaml"`|  
|File di risorse in una sottocartella dell'assembly locale|`"/Subfolder/ResourceFile.xaml"`|  
|File di risorse nell'assembly a cui si fa riferimento|`"/ReferencedAssembly;component/ResourceFile.xaml"`|  
|File di risorse in una sottocartella dell'assembly a cui si fa riferimento|`"/ReferencedAssembly;component/Subfolder/ResourceFile.xaml"`|  
|File di contenuto|`"/ContentFile.xaml"`|  
|File di contenuto in una sottocartella|`"/Subfolder/ContentFile.xaml"`|  
  
<a name="Using_Pack_URIs_in_Code"></a>   
### <a name="using-pack-uris-in-code"></a>Uso di URI di tipo pack nel codice  
 Specificare un pacchetto di [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] nel codice creando il <xref:System.Uri> classe e passare il [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] come parametro al costruttore. come illustrato nell'esempio seguente.  
  
```csharp  
Uri uri = new Uri("pack://application:,,,/File.xaml");  
```  
  
 Per impostazione predefinita, il <xref:System.Uri> classe considera pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] come assoluti. Di conseguenza, viene generata un'eccezione quando un'istanza di <xref:System.Uri> classe viene creata con un relativo pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].  
  
```csharp  
Uri uri = new Uri("/File.xaml");  
```  
  
 Fortunatamente, la <xref:System.Uri.%23ctor%28System.String%2CSystem.UriKind%29> overload di <xref:System.Uri> costruttore della classe accetta un parametro di tipo <xref:System.UriKind> consente di specificare se un pacchetto di [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] è assoluto o relativo.  
  
```csharp  
// Absolute URI (default)  
Uri absoluteUri = new Uri("pack://application:,,,/File.xaml", UriKind.Absolute);  
// Relative URI  
Uri relativeUri = new Uri("/File.xaml",   
                        UriKind.Relative);  
```  
  
 È necessario specificare solo <xref:System.UriKind.Absolute> o <xref:System.UriKind.Relative> quando si è certi che il pacchetto fornito [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] è uno o l'altro. Se non si conosce il tipo di pacchetto [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] utilizzato, ad esempio quando un utente immette un pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] in fase di esecuzione, utilizzare <xref:System.UriKind.RelativeOrAbsolute> invece.  
  
```csharp  
// Relative or Absolute URI provided by user via a text box  
TextBox userProvidedUriTextBox = new TextBox();  
Uri uri = new Uri(userProvidedUriTextBox.Text, UriKind.RelativeOrAbsolute);  
```  
  
 Tabella 3 sono illustrati i vari pack relativi [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] che è possibile specificare nel codice utilizzando <xref:System.Uri?displayProperty=nameWithType>.  
  
 Tabella 3: URI di tipo pack assoluti nel codice  
  
|File|Pack assoluto [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]|  
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
  
 Tabella 4 sono illustrati i vari pack relativi [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] che è possibile specificare nel codice utilizzando <xref:System.Uri?displayProperty=nameWithType>.  
  
 Tabella 4: URI di tipo pack relativi nel codice  
  
|File|Pack relativo [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]|  
|----------|-------------------------------------------------------------------------------------------------------------------------|  
|File di risorse - assembly locale|`Uri uri = new Uri("/ResourceFile.xaml", UriKind.Relative);`|  
|File di risorse in una sottocartella - assembly locale|`Uri uri = new Uri("/Subfolder/ResourceFile.xaml", UriKind.Relative);`|  
|File di risorse - assembly a cui si fa riferimento|`Uri uri = new Uri("/ReferencedAssembly;component/ResourceFile.xaml", UriKind.Relative);`|  
|File di risorse in una sottocartella - assembly a cui si fa riferimento|`Uri uri = new Uri("/ReferencedAssembly;component/Subfolder/ResourceFile.xaml", UriKind.Relative);`|  
|File di contenuto|`Uri uri = new Uri("/ContentFile.xaml", UriKind.Relative);`|  
|File di contenuto in una sottocartella|`Uri uri = new Uri("/Subfolder/ContentFile.xaml", UriKind.Relative);`|  
  
<a name="Common_Pack_URI_Scenarios"></a>   
### <a name="common-pack-uri-scenarios"></a>Scenari comuni di URI Pack  
 Nelle sezioni precedenti hanno illustrato come costruire pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] per identificare risorse e sito di origine. In [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], queste costruzioni vengono utilizzate in diversi modi e le sezioni seguenti illustrano alcuni utilizzi comuni.  
  
<a name="Specifying_the_UI_to_Show_when_an_Application_Starts"></a>   
#### <a name="specifying-the-ui-to-show-when-an-application-starts"></a>Specifica dell'interfaccia utente da visualizzare all'avvio di un'applicazione  
 <xref:System.Windows.Application.StartupUri%2A> Specifica il primo [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] da visualizzare quando un [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] viene avviata l'applicazione. Per le applicazioni autonome di [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] può essere una finestra, come illustrato nell'esempio seguente.  
  
 [!code-xaml[PackURIOverviewSnippets#StartupUriWindow](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PackURIOverviewSnippets/CS/Copy of App.xaml#startupuriwindow)]  
  
 Applicazioni autonome e [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] può specificare anche una pagina come l'interfaccia utente iniziale, come illustrato nell'esempio seguente.  
  
 [!code-xaml[PackURIOverviewSnippets#StartupUriPage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PackURIOverviewSnippets/CS/App.xaml#startupuripage)]  
  
 Se l'applicazione è un'applicazione autonoma e una pagina viene specificata con <xref:System.Windows.Application.StartupUri%2A>, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] apre un <xref:System.Windows.Navigation.NavigationWindow> per ospitare la pagina. Per [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)], la pagina viene visualizzata nel browser host.  
  
<a name="Navigating_to_a_Page"></a>   
#### <a name="navigating-to-a-page"></a>Spostamento su una pagina  
 L'esempio seguente illustra come spostarsi su una pagina.  
  
 [!code-xaml[NavigationOverviewSnippets#HyperlinkXAML1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml1)]  
[!code-xaml[NavigationOverviewSnippets#HyperlinkXAML2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml2)]  
[!code-xaml[NavigationOverviewSnippets#HyperlinkXAML3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml3)]  
  
 Per ulteriori informazioni sulle diverse modalità per spostarsi in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], vedere [Navigation Overview](../../../../docs/framework/wpf/app-development/navigation-overview.md).  
  
<a name="Specifying_a_Window_Icon"></a>   
#### <a name="specifying-a-window-icon"></a>Specifica dell'icona di una finestra  
 L'esempio seguente illustra come usare un URI per specificare l'icona di una finestra.  
  
 [!code-xaml[WindowIconSnippets#WindowIconSetXAML](../../../../samples/snippets/xaml/VS_Snippets_Wpf/WindowIconSnippets/XAML/MainWindow.xaml#windowiconsetxaml)]  
  
 Per altre informazioni, vedere <xref:System.Windows.Window.Icon%2A>.  
  
<a name="Loading_Image__Audio__and_Video_Files"></a>   
#### <a name="loading-image-audio-and-video-files"></a>Caricamento di file di immagine, audio e video  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] consente alle applicazioni di utilizzare un'ampia gamma di tipi di supporti, ognuno dei quali possono essere identificati e caricato con Service pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)], come illustrato negli esempi seguenti.  
  
 [!code-xaml[MediaPlayerVideoSample#VideoPackURIAtSOO](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MediaPlayerVideoSample/CS/HomePage.xaml#videopackuriatsoo)]  
  
 [!code-xaml[MediaPlayerAudioSample#AudioPackURIAtSOO](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MediaPlayerAudioSample/CS/HomePage.xaml#audiopackuriatsoo)]  
  
 [!code-xaml[ImageSample#ImagePackURIContent](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageSample/CS/HomePage.xaml#imagepackuricontent)]  
  
 Per ulteriori informazioni sull'utilizzo di contenuti multimediali, vedere [grafica e contenuti multimediali](../../../../docs/framework/wpf/graphics-multimedia/index.md).  
  
<a name="Loading_a_Resource_Dictionary_from_the_Site_of_Origin"></a>   
#### <a name="loading-a-resource-dictionary-from-the-site-of-origin"></a>Caricamento di un dizionario risorse dal sito di origine  
 I dizionari risorse (<xref:System.Windows.ResourceDictionary>) può essere utilizzata per supportare i temi dell'applicazione. Un modo per creare e gestire i temi consiste nel creare più temi come dizionari risorse che si trovano nel sito di origine di un'applicazione. In questo modo è possibile aggiungere e aggiornare i temi senza ricompilare e ridistribuire un'applicazione. Questi dizionari risorse possono essere identificati e caricati utilizzando pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)], mostrato nell'esempio seguente.  
  
 [!code-xaml[ResourceDictionarySnippets#ResourceDictionaryPackURI](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ResourceDictionarySnippets/CS/App.xaml#resourcedictionarypackuri)]  
  
 Per una panoramica dei temi in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], vedere [stili e modelli](../../../../docs/framework/wpf/controls/styling-and-templating.md).  
  
## <a name="see-also"></a>Vedere anche  
 [File di dati e di risorse dell'applicazione WPF](../../../../docs/framework/wpf/app-development/wpf-application-resource-content-and-data-files.md)
