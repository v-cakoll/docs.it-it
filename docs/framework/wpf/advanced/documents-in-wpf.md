---
title: Documenti
ms.date: 03/30/2017
helpviewer_keywords:
- documents [WPF], packaging
- documents [WPF], text layout
- documents [WPF], XPS
- 'XPS documents [WPF], , '
- documents [WPF], controls
- documents [WPF], types of
- documents [WPF], browser-viewable
ms.assetid: 6e8db7bc-050a-4070-aa72-bb8c46e87ff8
ms.openlocfilehash: eccb333b8e9a71ea30454f8bdf9fd2bf6dc90b9b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76737964"
---
# <a name="documents-in-wpf"></a>Documenti in WPF
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] offre un'ampia gamma di funzionalità dei documenti che consentono la creazione di contenuto ad alta fedeltà progettato per essere più facilmente accessibile e leggibile rispetto alle generazioni precedenti di Windows. Oltre a caratteristiche avanzate in termini di funzionalità e qualità, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] assicura servizi integrati per la visualizzazione, la creazione di pacchetti e la sicurezza dei documenti. Questo argomento costituisce un'introduzione ai tipi di documenti e alla creazione di pacchetti di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  

<a name="types_of_documents"></a>   
## <a name="types-of-documents"></a>Tipi di documenti  
 In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] i documenti sono suddivisi in due categorie generali in base all'uso previsto: documenti statici e documenti dinamici.  
  
 I documenti corretti sono destinati ad applicazioni che richiedono una presentazione "What You See is what you get" (WYSIWYG), indipendentemente dall'hardware di visualizzazione o della stampante usato. Tra gli usi tipici dei documenti statici rientrano le attività di desktop publishing, elaborazione di testi e layout di form, in cui la corrispondenza alla progettazione della pagina originale è essenziale. Come parte del layout, in un documento statico viene mantenuta la disposizione precisa degli elementi di contenuto indipendentemente dal dispositivo di visualizzazione o di stampa in uso. Ad esempio, la pagina di un documento statico visualizzata con un'impostazione di 96 dpi non varia quando viene stampata con una stampante laser a 600 dpi o con un fotocompositore a 4800 dpi. Il layout di pagina rimane invariato in ogni caso, benché la qualità del documento dipenda dalle capacità del dispositivo usato.  
  
 D'altro canto, i documenti dinamici sono progettati per ottimizzare la visualizzazione e la leggibilità e sono particolarmente adatti quando la facilità di lettura è il principale requisito d'uso per il documento. Anziché essere impostati su un layout predefinito, questi documenti consentono di adattare e ridisporre il contenuto in modo dinamico in base alle variabili in fase di esecuzione, ad esempio, le dimensioni della finestra, la risoluzione del dispositivo e le preferenze facoltative dell'utente. Una pagina Web è un esempio semplice di documento dinamico in cui il contenuto della pagina viene formattato dinamicamente per adattarsi alla finestra corrente. I documenti dinamici ottimizzano l'esperienza di visualizzazione e di lettura per l'utente, in base all'ambiente di runtime. Ad esempio, lo stesso documento dinamico verrà riformattato in modo dinamico per una leggibilità ottimale sia su dispositivi di visualizzazione da 19 pollici ad alta risoluzione che su piccoli schermi PDA da 2x3 pollici. Inoltre, i documenti dinamici dispongono di numerose funzionalità incorporate tra cui ricerca, modalità di visualizzazione che ottimizzano la leggibilità e possibilità di modificare le dimensioni e l'aspetto dei tipi di carattere.  Vedere [Cenni preliminari sui documenti dinamici](flow-document-overview.md) per immagini, esempi e informazioni approfondite sui documenti dinamici.  
  
<a name="document_viewer"></a>   
## <a name="document-controls-and-text-layout"></a>Controlli dei documenti e layout del testo  
 Il .NET Framework fornisce un set di controlli predefiniti che semplificano l'uso di documenti fissi, documenti dinamici e testo generale all'interno dell'applicazione.  La visualizzazione del contenuto del documento fisso è supportata tramite il controllo <xref:System.Windows.Controls.DocumentViewer>.  La visualizzazione del contenuto dei documenti dinamici è supportata da tre controlli diversi: <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentPageViewer>e <xref:System.Windows.Controls.FlowDocumentScrollViewer> che vengono mappati a diversi scenari utente (vedere le sezioni seguenti).  Altri controlli di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] forniscono un layout semplificato per supportare l'uso di testo generico (vedere la sezione [Testo nell'interfaccia utente](#text_in_the_user_interface) più avanti).  
  
### <a name="fixed-document-control---documentviewer"></a>Controllo dei documenti statici: DocumentViewer  
 Il controllo <xref:System.Windows.Controls.DocumentViewer> è progettato per visualizzare <xref:System.Windows.Documents.FixedDocument> contenuto. Il controllo <xref:System.Windows.Controls.DocumentViewer> fornisce un'interfaccia utente intuitiva che offre supporto incorporato per operazioni comuni, tra cui l'output di stampa, la copia negli Appunti, lo zoom e le funzionalità di ricerca del testo. Il controllo consente di accedere a pagine di contenuto attraverso un meccanismo di scorrimento intuitivo. Come tutti i controlli [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], <xref:System.Windows.Controls.DocumentViewer> supporta il restyling completo o parziale, che consente di integrare visivamente il controllo in qualsiasi applicazione o ambiente.  
  
 <xref:System.Windows.Controls.DocumentViewer> è progettato per visualizzare il contenuto in modalità di sola lettura. la modifica o la modifica del contenuto non è disponibile e non è supportata.  
  
<a name="flow_document"></a>   
### <a name="flow-document-controls"></a>Controlli dei documenti dinamici  

> [!NOTE]
> Per informazioni più dettagliate sulle funzionalità dei documenti dinamici e su come crearle, vedere [Cenni preliminari sui documenti dinamici](flow-document-overview.md).  
  
 La visualizzazione del contenuto dei documenti dinamici è supportata da tre controlli: <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentPageViewer>e <xref:System.Windows.Controls.FlowDocumentScrollViewer>.  
  
#### <a name="flowdocumentreader"></a>FlowDocumentReader  
 <xref:System.Windows.Controls.FlowDocumentReader> include funzionalità che consentono all'utente di scegliere in modo dinamico tra le varie modalità di visualizzazione, inclusa una modalità di visualizzazione a pagina singola (pagina alla volta), una modalità di visualizzazione a due pagine alla volta (formato lettura libro) e una modalità di visualizzazione a scorrimento continuo (senza fine).  Per ulteriori informazioni su queste modalità di visualizzazione, vedere <xref:System.Windows.Controls.FlowDocumentReaderViewingMode>.  Se non è necessario passare dinamicamente da una modalità di visualizzazione all'altra, <xref:System.Windows.Controls.FlowDocumentPageViewer> e <xref:System.Windows.Controls.FlowDocumentScrollViewer> forniscono visualizzatori di contenuto del flusso più semplici che sono corretti in una particolare modalità di visualizzazione.  
  
#### <a name="flowdocumentpageviewer-and-flowdocumentscrollviewer"></a>FlowDocumentPageViewer e FlowDocumentScrollViewer  
 <xref:System.Windows.Controls.FlowDocumentPageViewer> Visualizza il contenuto nella modalità di visualizzazione pagina alla volta, mentre <xref:System.Windows.Controls.FlowDocumentScrollViewer> Visualizza il contenuto in modalità di scorrimento continuo.  Sia <xref:System.Windows.Controls.FlowDocumentPageViewer> che <xref:System.Windows.Controls.FlowDocumentScrollViewer> sono corretti a una particolare modalità di visualizzazione. Confrontare con <xref:System.Windows.Controls.FlowDocumentReader>, che include funzionalità che consentono all'utente di scegliere dinamicamente tra le varie modalità di visualizzazione (fornite dall'enumerazione <xref:System.Windows.Controls.FlowDocumentReaderViewingMode>), al costo di un maggior utilizzo di risorse rispetto a <xref:System.Windows.Controls.FlowDocumentPageViewer> o <xref:System.Windows.Controls.FlowDocumentScrollViewer>.  
  
 Per impostazione predefinita, viene sempre visualizzata una barra di scorrimento verticale e in caso di necessità diventa visibile una barra di scorrimento orizzontale. Il [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] predefinito per <xref:System.Windows.Controls.FlowDocumentScrollViewer> non include una barra degli strumenti; Tuttavia, la proprietà <xref:System.Windows.Controls.FlowDocumentScrollViewer.IsToolBarVisible%2A> può essere utilizzata per abilitare una barra degli strumenti incorporata.  
  
<a name="text_in_the_user_interface"></a>   
### <a name="text-in-the-user-interface"></a>Testo nell'interfaccia utente  
 Oltre all'aggiunta di testo ai documenti, è ovviamente possibile usare il testo nell'interfaccia utente delle applicazioni, ad esempio nei form. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] include più controlli per la creazione di testo sullo schermo. Ogni controllo è destinato a uno scenario diverso e dispone di un proprio elenco di funzionalità e limitazioni. In generale, l'elemento <xref:System.Windows.Controls.TextBlock> deve essere utilizzato quando è necessario il supporto di testo limitato, ad esempio una breve frase in una [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]. <xref:System.Windows.Controls.Label> può essere utilizzato quando è richiesto un supporto di testo minimo. Per altre informazioni, vedere [Cenni preliminari sul controllo TextBlock](../controls/textblock-overview.md).  
  
<a name="packaging"></a>   
## <a name="document-packaging"></a>Creazione di pacchetti di documenti  
 Le API <xref:System.IO.Packaging> offrono un modo efficiente per organizzare i dati delle applicazioni, il contenuto dei documenti e le risorse correlate in un unico contenitore semplice da accedere, portatile e facile da distribuire. Un file ZIP è un esempio di <xref:System.IO.Packaging.Package> tipo in grado di contenere più oggetti come singola unità. Le API per la creazione di pacchetti forniscono un'implementazione di <xref:System.IO.Packaging.ZipPackage> predefinita progettata usando uno standard Open Packaging Conventions con l'architettura di file XML e ZIP. Le API [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Packaging semplificano la creazione di pacchetti e l'archiviazione e l'accesso agli oggetti in essi contenuti. Un oggetto archiviato in un <xref:System.IO.Packaging.Package> viene definito come <xref:System.IO.Packaging.PackagePart> ("parte"). I pacchetti possono anche includere certificati digitali firmati utilizzabili per identificare l'autore di una parte e per confermare che il contenuto di un pacchetto non è stato modificato.  I pacchetti includono inoltre una funzionalità <xref:System.IO.Packaging.PackageRelationship> che consente di aggiungere informazioni aggiuntive a un pacchetto o associate a parti specifiche senza modificare effettivamente il contenuto delle parti esistenti.  I servizi pacchetti supportano anche Microsoft Windows Rights Management (RM).  
  
 L'architettura dei pacchetti di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] costituisce la base per numerose tecnologie chiave:  
  
- Documenti XPS conformi a XPS (XML Paper Specification).  
  
- Documenti in formato XML aperto di Microsoft Office "12" (con estensione docx).  
  
- Formati di archiviazione personalizzati per la progettazione delle applicazioni.  
  
 In base alle API per la creazione di pacchetti, un <xref:System.Windows.Xps.Packaging.XpsDocument> è progettato appositamente per archiviare [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] documenti di contenuto fissi. Un <xref:System.Windows.Xps.Packaging.XpsDocument> è un documento autonomo che può essere aperto in un visualizzatore, visualizzato in un controllo <xref:System.Windows.Controls.DocumentViewer>, instradato a uno spool di stampa o inviato direttamente a una stampante compatibile con XPS.  
  
 Le sezioni seguenti forniscono informazioni aggiuntive sulle API <xref:System.IO.Packaging.Package> e <xref:System.Windows.Xps.Packaging.XpsDocument> fornite con [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
<a name="packages"></a>   
### <a name="package-components"></a>Componenti dei pacchetti  
 Le API per la creazione di pacchetti di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] consentono l'organizzazione dei dati delle applicazioni e dei documenti in un'unica unità portabile. Uno dei tipi di pacchetti più comuni è il file ZIP, il tipo predefinito fornito con [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  <xref:System.IO.Packaging.Package> è una classe astratta da cui viene implementato <xref:System.IO.Packaging.ZipPackage> mediante un'architettura di file XML e ZIP standard aperta.  Il metodo <xref:System.IO.Packaging.Package.Open%2A> utilizza <xref:System.IO.Packaging.ZipPackage> per creare e utilizzare file ZIP per impostazione predefinita. Un pacchetto può contenere tre tipi di elementi di base:  
  
|||  
|-|-|  
|<xref:System.IO.Packaging.PackagePart>|Contenuto delle applicazioni, dati, documenti e file di risorse.|  
|<xref:System.IO.Packaging.PackageDigitalSignature>|[Certificato x.509] per l'identificazione, l'autenticazione e la convalida.|  
|<xref:System.IO.Packaging.PackageRelationship>|Informazioni aggiunte relative al pacchetto o a una parte specifica.|  
  
<a name="PackageParts"></a>   
#### <a name="packageparts"></a>PackagePart  
 Un <xref:System.IO.Packaging.PackagePart> ("parte") è una classe astratta che fa riferimento a un oggetto archiviato in un <xref:System.IO.Packaging.Package>. In un file ZIP le parti del pacchetto corrispondono ai singoli file archiviati nel file ZIP.  <xref:System.IO.Packaging.ZipPackagePart> fornisce l'implementazione predefinita per gli oggetti serializzabili archiviati in un <xref:System.IO.Packaging.ZipPackage>.  Analogamente a un file system, le parti contenute nel pacchetto vengono archiviate secondo un'organizzazione di directory o cartelle di tipo gerarchico.  Utilizzando le API [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Packaging, le applicazioni possono scrivere, archiviare e leggere più oggetti <xref:System.IO.Packaging.PackagePart> utilizzando un singolo contenitore di file ZIP.  
  
<a name="PackageDigitalSignatures"></a>   
#### <a name="packagedigitalsignatures"></a>PackageDigitalSignature  
 Per la sicurezza, un <xref:System.IO.Packaging.PackageDigitalSignature> ("firma digitale") può essere associato a parti all'interno di un pacchetto. Un <xref:System.IO.Packaging.PackageDigitalSignature> incorpora un [509] che fornisce due funzionalità:  
  
1. Identifica e autentica l'autore della parte.  
  
2. Conferma che la parte non è stata modificata.  
  
 La firma digitale non impedisce che una parte venga modificata, ma un controllo di convalida della firma digitale avrà esito negativo se la parte è stata in qualche modo modificata. L'applicazione potrà quindi intraprendere l'azione appropriata, ad esempio bloccare l'apertura della parte o notificare all'utente che la parte è stata modificata e non è sicura.  
  
<a name="PackageRelationships"></a>   
#### <a name="packagerelationships"></a>PackageRelationship  
 Un <xref:System.IO.Packaging.PackageRelationship> ("Relationship") fornisce un meccanismo per associare informazioni aggiuntive al pacchetto o a una parte all'interno del pacchetto. Una relazione è una funzionalità a livello di pacchetto in grado di associare informazioni aggiuntive a una parte senza modificarne il contenuto effettivo. L'inserimento di nuovi dati direttamente nel contenuto in genere non è un'operazione pratica:  
  
- Il tipo effettivo della parte e il relativo schema di contenuto non sono noti.  
  
- Anche se è noto, lo schema di contenuto potrebbe non offrire un metodo per l'aggiunta di nuove informazioni.  
  
- La parte potrebbe essere crittografata o firmata digitalmente, condizioni che impediscono qualsiasi modifica.  
  
 Le relazioni dei pacchetti offrono un metodo individuabile per aggiungere e associare altre informazioni a singole parti o all'intero pacchetto. Le relazioni dei pacchetti vengono usate per due funzioni principali:  
  
1. Definizione delle relazioni di dipendenza tra le parti.  
  
2. Definizione delle relazioni delle informazioni che aggiungono note o altri dati correlati alla parte.  
  
 Un <xref:System.IO.Packaging.PackageRelationship> fornisce un metodo rapido e individuabile per definire le dipendenze e aggiungere altre informazioni associate a una parte del pacchetto o al pacchetto nel suo complesso.  
  
<a name="Dependency_Relationships"></a>   
##### <a name="dependency-relationships"></a>Relazioni di dipendenza  
 Le relazioni di dipendenza vengono usate per descrivere le dipendenze tra le parti. Ad esempio, un pacchetto può contenere una parte HTML che include uno o più tag immagine \<img>. I tag immagine fanno riferimento a immagini posizionate come altre parti interne o esterne al pacchetto (ad esempio accessibili tramite Internet). La creazione di un <xref:System.IO.Packaging.PackageRelationship> associato al file HTML rende l'individuazione e l'accesso alle risorse dipendenti in modo rapido e semplice. Un'applicazione browser o del visualizzatore può accedere direttamente alle relazioni tra le parti e avviare immediatamente l'assemblaggio delle risorse dipendenti senza conoscere lo schema, né analizzare il documento.  
  
<a name="Information_Relationships"></a>   
##### <a name="information-relationships"></a>Relazioni delle informazioni  
 Analogamente a una nota o a un'annotazione, un <xref:System.IO.Packaging.PackageRelationship> può essere utilizzato anche per archiviare altri tipi di informazioni da associare a una parte senza dover modificare effettivamente il contenuto della parte.  
  
<a name="XPS_Documents"></a>   
## <a name="xps-documents"></a>Documenti XPS  
 Il documento XPS (XML Paper Specification) è un pacchetto che contiene uno o più documenti fissi insieme a tutte le risorse e le informazioni necessarie per il rendering.  XPS è anche il formato nativo di file spooler di stampa di Windows Vista.  Un <xref:System.Windows.Xps.Packaging.XpsDocument> viene archiviato nel set di dati ZIP standard e può includere una combinazione di componenti XML e binari, ad esempio file di immagine e di tipi di carattere. Gli oggetti [PackageRelationship](#PackageRelationships) vengono usati per definire le dipendenze tra il contenuto e le risorse necessarie per eseguire il rendering completo del documento.  La progettazione di <xref:System.Windows.Xps.Packaging.XpsDocument> offre un'unica soluzione di documento ad alta fedeltà che supporta più utilizzi:  
  
- Lettura, scrittura e archiviazione del contenuto di documenti statici e risorse come un file singolo, portabile e facile da distribuire.  
  
- Visualizzazione di documenti con l'applicazione XPS Viewer.  
  
- Output dei documenti nel formato di output dello spooler di stampa nativo di Windows Vista.  
  
- Routing di documenti direttamente a una stampante compatibile con XPS.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Documents.FixedDocument>
- <xref:System.Windows.Documents.FlowDocument>
- <xref:System.Windows.Xps.Packaging.XpsDocument>
- <xref:System.IO.Packaging.ZipPackage>
- <xref:System.IO.Packaging.ZipPackagePart>
- <xref:System.IO.Packaging.PackageRelationship>
- <xref:System.Windows.Controls.DocumentViewer>
- [Testo](optimizing-performance-text.md)
- [Cenni preliminari sui documenti dinamici](flow-document-overview.md)
- [Panoramica della stampa](printing-overview.md)
- [Serializzazione e archiviazione di documenti](document-serialization-and-storage.md)
