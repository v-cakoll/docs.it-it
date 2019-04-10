---
title: Documenti in WPF
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
ms.openlocfilehash: b4057f54934fb5c7c9bb3d4fb97fe8e197e324ad
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59313957"
---
# <a name="documents-in-wpf"></a>Documenti in WPF
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] offre un'ampia gamma di funzionalità di documenti che consentono la creazione di contenuti ad alta fedeltà che sono progettato per essere più facilmente accessibile e lettura rispetto alle generazioni precedenti di [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)]. Oltre a caratteristiche avanzate in termini di funzionalità e qualità, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] assicura servizi integrati per la visualizzazione, la creazione di pacchetti e la sicurezza dei documenti. Questo argomento costituisce un'introduzione ai tipi di documenti e alla creazione di pacchetti di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  

<a name="types_of_documents"></a>   
## <a name="types-of-documents"></a>Tipi di documenti  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] documenti viene diviso in due ampie categorie in base all'utilizzo previsto; Questi documenti sono suddivisi "documenti statici" e "i documenti dinamici."  
  
 I documenti statici sono destinati ad applicazioni che richiedono una presentazione [!INCLUDE[TLA#tla_wys](../../../../includes/tlasharptla-wys-md.md)] precisa, indipendentemente dall'hardware di visualizzazione o di stampa usato. Tra gli usi tipici dei documenti statici rientrano le attività di desktop publishing, elaborazione di testi e layout di form, in cui la corrispondenza alla progettazione della pagina originale è essenziale. Come parte del layout, in un documento statico viene mantenuta la disposizione precisa degli elementi di contenuto indipendentemente dal dispositivo di visualizzazione o di stampa in uso. Ad esempio, la pagina di un documento statico visualizzata con un'impostazione di 96 dpi non varia quando viene stampata con una stampante laser a 600 dpi o con un fotocompositore a 4800 dpi. Il layout di pagina rimane invariato in ogni caso, benché la qualità del documento dipenda dalle capacità del dispositivo usato.  
  
 D'altro canto, i documenti dinamici sono progettati per ottimizzare la visualizzazione e la leggibilità e sono particolarmente adatti quando la facilità di lettura è il principale requisito d'uso per il documento. Anziché essere impostati su un layout predefinito, questi documenti consentono di adattare e ridisporre il contenuto in modo dinamico in base alle variabili in fase di esecuzione, ad esempio, le dimensioni della finestra, la risoluzione del dispositivo e le preferenze facoltative dell'utente. Una pagina Web è un esempio semplice di documento dinamico in cui il contenuto della pagina viene formattato dinamicamente per adattarsi alla finestra corrente. I documenti dinamici ottimizzano l'esperienza di visualizzazione e di lettura per l'utente, in base all'ambiente di runtime. Ad esempio, lo stesso documento dinamico verrà riformattato in modo dinamico per una leggibilità ottimale sia su dispositivi di visualizzazione da 19 pollici ad alta risoluzione che su piccoli schermi PDA da 2x3 pollici. Inoltre, i documenti dinamici dispongono di numerose funzionalità incorporate tra cui ricerca, modalità di visualizzazione che ottimizzano la leggibilità e possibilità di modificare le dimensioni e l'aspetto dei tipi di carattere.  Vedere [Cenni preliminari sui documenti dinamici](flow-document-overview.md) per immagini, esempi e informazioni approfondite sui documenti dinamici.  
  
<a name="document_viewer"></a>   
## <a name="document-controls-and-text-layout"></a>Controlli dei documenti e layout del testo  
 .NET Framework fornisce un set di controlli precompilati che semplificano l'utilizzo di documenti statici, documenti dinamici e testo generico all'interno dell'applicazione.  La visualizzazione del contenuto del documento fisso è supportata tramite i <xref:System.Windows.Controls.DocumentViewer> controllo.  La visualizzazione del contenuto di documenti dinamici è supportata da tre diversi controlli: <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentPageViewer>, e <xref:System.Windows.Controls.FlowDocumentScrollViewer> che eseguono il mapping a scenari utente diverso (vedere la sezioni riportate di seguito).  Altri controlli di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] forniscono un layout semplificato per supportare l'uso di testo generico (vedere la sezione [Testo nell'interfaccia utente](#text_in_the_user_interface) più avanti).  
  
### <a name="fixed-document-control---documentviewer"></a>Controllo dei documenti statici: DocumentViewer  
 Il <xref:System.Windows.Controls.DocumentViewer> controllo è progettato per visualizzare <xref:System.Windows.Documents.FixedDocument> contenuto. Il <xref:System.Windows.Controls.DocumentViewer> controllo fornisce un'interfaccia utente intuitiva che fornisce il supporto incorporato per operazioni comuni, tra cui stampa dell'output, copiare negli Appunti, zoom e funzionalità di ricerca di testo. Il controllo consente di accedere a pagine di contenuto attraverso un meccanismo di scorrimento intuitivo. Analogamente a tutti i [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] controlli, <xref:System.Windows.Controls.DocumentViewer> supporta la modifica completa o parziale dello stile, che consente il controllo integrazione visiva praticamente in qualsiasi applicazione o ambiente.  
  
 <xref:System.Windows.Controls.DocumentViewer> è progettato per visualizzare il contenuto in una modalità di sola lettura; modifica o la modifica del contenuto non è disponibile e non è supportata.  
  
<a name="flow_document"></a>   
### <a name="flow-document-controls"></a>Controlli dei documenti dinamici  
 **Nota:** Per altre informazioni sulla funzionalità dei documenti dinamici e come crearli, vedere [Cenni preliminari sui documenti dinamici](flow-document-overview.md).  
  
 La visualizzazione del contenuto di documenti dinamici è supportata da tre controlli: <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentPageViewer>, e <xref:System.Windows.Controls.FlowDocumentScrollViewer>.  
  
#### <a name="flowdocumentreader"></a>FlowDocumentReader  
 <xref:System.Windows.Controls.FlowDocumentReader> include funzionalità che consentono all'utente di scegliere dinamicamente tra le varie modalità di visualizzazione, inclusa una modalità di visualizzazione a singola pagina (una pagina per volta), un due-pagina-in-a-time (formato lettura libro) visualizzazione modalità e una modalità di visualizzazione (infinito) scorrimento continuo.  Per altre informazioni sulle modalità di visualizzazione, vedere <xref:System.Windows.Controls.FlowDocumentReaderViewingMode>.  Se la possibilità di passare in modo dinamico tra diverse modalità di visualizzazione, non occorre <xref:System.Windows.Controls.FlowDocumentPageViewer> e <xref:System.Windows.Controls.FlowDocumentScrollViewer> forniscono flusso leggera visualizzatori di contenuto che sono stati risolti in una modalità di visualizzazione particolare.  
  
#### <a name="flowdocumentpageviewer-and-flowdocumentscrollviewer"></a>FlowDocumentPageViewer e FlowDocumentScrollViewer  
 <xref:System.Windows.Controls.FlowDocumentPageViewer> Visualizza il contenuto nella pagina alla volta la modalità di visualizzazione, mentre <xref:System.Windows.Controls.FlowDocumentScrollViewer> Visualizza il contenuto nella modalità a scorrimento continuo.  Entrambe <xref:System.Windows.Controls.FlowDocumentPageViewer> e <xref:System.Windows.Controls.FlowDocumentScrollViewer> rimangono fissi su una modalità di visualizzazione particolare. Confrontare con <xref:System.Windows.Controls.FlowDocumentReader>, che include funzionalità che consentono all'utente di scegliere dinamicamente tra le varie modalità di visualizzazione (fornito dal <xref:System.Windows.Controls.FlowDocumentReaderViewingMode> enumerazione), al costo da più risorse rispetto a <xref:System.Windows.Controls.FlowDocumentPageViewer> o <xref:System.Windows.Controls.FlowDocumentScrollViewer>.  
  
 Per impostazione predefinita, viene sempre visualizzata una barra di scorrimento verticale e in caso di necessità diventa visibile una barra di scorrimento orizzontale. Il valore predefinito [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] per <xref:System.Windows.Controls.FlowDocumentScrollViewer> non include una barra degli strumenti, ma il <xref:System.Windows.Controls.FlowDocumentScrollViewer.IsToolBarVisible%2A> proprietà può essere utilizzata per abilitare una barra degli strumenti incorporata.  
  
<a name="text_in_the_user_interface"></a>   
### <a name="text-in-the-user-interface"></a>Testo nell'interfaccia utente  
 Oltre all'aggiunta di testo ai documenti, è ovviamente possibile usare il testo nell'interfaccia utente delle applicazioni, ad esempio nei form. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] include più controlli per il disegno di testo sullo schermo. Ogni controllo è destinato a uno scenario diverso e dispone di un proprio elenco di funzionalità e limitazioni. In generale, il <xref:System.Windows.Controls.TextBlock> elemento deve essere usato quando è richiesto, ad esempio una breve frase in un supporto limitato del testo un [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]. <xref:System.Windows.Controls.Label> può essere utilizzato quando è necessario il supporto minimo del testo. Per altre informazioni, vedere [Cenni preliminari sul controllo TextBlock](../controls/textblock-overview.md).  
  
<a name="packaging"></a>   
## <a name="document-packaging"></a>Creazione di pacchetti di documenti  
 Il <xref:System.IO.Packaging> [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] costituiscono un mezzo efficace per organizzare i dati dell'applicazione, il contenuto del documento e le risorse correlate in un singolo contenitore che è accessibile e portabile e facile da distribuire. Un file ZIP è un esempio di un <xref:System.IO.Packaging.Package> tipo in grado di contenere più oggetti come una singola unità. La creazione di pacchetti [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] fornire una proprietà predefinita <xref:System.IO.Packaging.ZipPackage> implementazione progettata tramite uno standard Open Packaging Conventions con architettura del file XML e ZIP. Le [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] per la creazione di pacchetti di [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] semplificano la creazione di pacchetti, nonché l'archiviazione e l'accesso agli oggetti che contengono. Un oggetto archiviato in una <xref:System.IO.Packaging.Package> viene definito un <xref:System.IO.Packaging.PackagePart> ("parte"). I pacchetti possono anche includere certificati digitali firmati utilizzabili per identificare l'autore di una parte e per confermare che il contenuto di un pacchetto non è stato modificato.  I pacchetti includono inoltre un <xref:System.IO.Packaging.PackageRelationship> funzionalità che consente a informazioni aggiuntive da aggiungere a un pacchetto o associato a parti specifiche senza modificare il contenuto delle parti esistenti.  I servizi dei pacchetti supportano anche [!INCLUDE[TLA#tla_rm](../../../../includes/tlasharptla-rm-md.md)].  
  
 L'architettura dei pacchetti di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] costituisce la base per numerose tecnologie chiave:  
  
-   [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] i documenti conformi al [!INCLUDE[TLA#tla_xps](../../../../includes/tlasharptla-xps-md.md)].  
  
-   Documenti in formato XML aperto di Microsoft Office "12" (con estensione docx).  
  
-   Formati di archiviazione personalizzati per la progettazione delle applicazioni.  
  
 Basato su API di assemblaggio, un' <xref:System.Windows.Xps.Packaging.XpsDocument> è progettata specificamente per l'archiviazione [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] documenti statici. Un' <xref:System.Windows.Xps.Packaging.XpsDocument> è un documento autonomo che può essere aperto in un visualizzatore, visualizzato in un <xref:System.Windows.Controls.DocumentViewer> consentono di controllare, indirizzato a uno spool di stampa o stampato direttamente con un [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)]-della stampante compatibile.  
  
 Le sezioni seguenti forniscono informazioni aggiuntive sul <xref:System.IO.Packaging.Package> e <xref:System.Windows.Xps.Packaging.XpsDocument> [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] fornita con [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
<a name="packages"></a>   
### <a name="package-components"></a>Componenti dei pacchetti  
 Le API per la creazione di pacchetti di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] consentono l'organizzazione dei dati delle applicazioni e dei documenti in un'unica unità portabile. Uno dei tipi di pacchetti più comuni è il file ZIP, il tipo predefinito fornito con [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  <xref:System.IO.Packaging.Package> è una classe astratta dalla quale <xref:System.IO.Packaging.ZipPackage> viene implementato usando un'architettura di file XML e ZIP standard aperta.  Il <xref:System.IO.Packaging.Package.Open%2A> Usa metodo <xref:System.IO.Packaging.ZipPackage> per creare e usare file ZIP per impostazione predefinita. Un pacchetto può contenere tre tipi di elementi di base:  
  
|||  
|-|-|  
|<xref:System.IO.Packaging.PackagePart>|Contenuto delle applicazioni, dati, documenti e file di risorse.|  
|<xref:System.IO.Packaging.PackageDigitalSignature>|[Certificato x.509] per l'identificazione, l'autenticazione e la convalida.|  
|<xref:System.IO.Packaging.PackageRelationship>|Informazioni aggiunte relative al pacchetto o a una parte specifica.|  
  
<a name="PackageParts"></a>   
#### <a name="packageparts"></a>PackagePart  
 Oggetto <xref:System.IO.Packaging.PackagePart> ("parte") è una classe astratta che fa riferimento a un oggetto archiviato in un <xref:System.IO.Packaging.Package>. In un file ZIP le parti del pacchetto corrispondono ai singoli file archiviati nel file ZIP.  <xref:System.IO.Packaging.ZipPackagePart> fornisce l'implementazione predefinita per gli oggetti serializzabili archiviati in un <xref:System.IO.Packaging.ZipPackage>.  Analogamente a un file system, le parti contenute nel pacchetto vengono archiviate secondo un'organizzazione di directory o cartelle di tipo gerarchico.  Usando il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] pacchetto di API, le applicazioni possono scrivere, archiviare e leggere più <xref:System.IO.Packaging.PackagePart> di oggetti usando un singolo contenitore di file con estensione ZIP.  
  
<a name="PackageDigitalSignatures"></a>   
#### <a name="packagedigitalsignatures"></a>PackageDigitalSignature  
 Per la sicurezza, un <xref:System.IO.Packaging.PackageDigitalSignature> ("firma digitale") può essere associato alle parti di un pacchetto. Oggetto <xref:System.IO.Packaging.PackageDigitalSignature> incorpora un certificato [509] che fornisce due funzionalità:  
  
1. Identifica e autentica l'autore della parte.  
  
2. Conferma che la parte non è stata modificata.  
  
 La firma digitale non impedisce che una parte venga modificata, ma un controllo di convalida della firma digitale avrà esito negativo se la parte è stata in qualche modo modificata. L'applicazione potrà quindi intraprendere l'azione appropriata, ad esempio bloccare l'apertura della parte o notificare all'utente che la parte è stata modificata e non è sicura.  
  
<a name="PackageRelationships"></a>   
#### <a name="packagerelationships"></a>PackageRelationship  
 Oggetto <xref:System.IO.Packaging.PackageRelationship> ("relazione") fornisce un meccanismo per associare informazioni aggiuntive al pacchetto o una parte all'interno del pacchetto. Una relazione è una funzionalità a livello di pacchetto in grado di associare informazioni aggiuntive a una parte senza modificarne il contenuto effettivo. L'inserimento di nuovi dati direttamente nel contenuto in genere non è un'operazione pratica:  
  
-   Il tipo effettivo della parte e il relativo schema di contenuto non sono noti.  
  
-   Anche se è noto, lo schema di contenuto potrebbe non offrire un metodo per l'aggiunta di nuove informazioni.  
  
-   La parte potrebbe essere crittografata o firmata digitalmente, condizioni che impediscono qualsiasi modifica.  
  
 Le relazioni dei pacchetti offrono un metodo individuabile per aggiungere e associare altre informazioni a singole parti o all'intero pacchetto. Le relazioni dei pacchetti vengono usate per due funzioni principali:  
  
1. Definizione delle relazioni di dipendenza tra le parti.  
  
2. Definizione delle relazioni delle informazioni che aggiungono note o altri dati correlati alla parte.  
  
 Oggetto <xref:System.IO.Packaging.PackageRelationship> fornisce un modo rapido e individuabile per definire le dipendenze e aggiungere altre informazioni associate a una parte del pacchetto o il pacchetto nel suo complesso.  
  
<a name="Dependency_Relationships"></a>   
##### <a name="dependency-relationships"></a>Relazioni di dipendenza  
 Le relazioni di dipendenza vengono usate per descrivere le dipendenze tra le parti. Ad esempio, un pacchetto può contenere una parte HTML che include uno o più tag immagine \<img>. I tag immagine fanno riferimento a immagini posizionate come altre parti interne o esterne al pacchetto (ad esempio accessibili tramite Internet). Creazione di un <xref:System.IO.Packaging.PackageRelationship> associato al file HTML consente di individuare e accedere alle risorse dipendenti semplice e rapide. Un'applicazione browser o del visualizzatore può accedere direttamente alle relazioni tra le parti e avviare immediatamente l'assemblaggio delle risorse dipendenti senza conoscere lo schema, né analizzare il documento.  
  
<a name="Information_Relationships"></a>   
##### <a name="information-relationships"></a>Relazioni delle informazioni  
 Simile alla nota o annotazione, un <xref:System.IO.Packaging.PackageRelationship> può anche essere utilizzato per archiviare altri tipi di informazioni da associare a una parte senza dover effettivamente modificare il contenuto della parte.  
  
<a name="XPS_Documents"></a>   
## <a name="xps-documents"></a>Documenti XPS  
 [!INCLUDE[TLA#tla_xps](../../../../includes/tlasharptla-xps-md.md)] documento è un pacchetto che contiene uno o più documenti statici insieme a tutte le risorse e le informazioni necessarie per il rendering.  [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] è anche l'oggetto nativo [!INCLUDE[TLA#tla_winvista](../../../../includes/tlasharptla-winvista-md.md)] formato del file dello spool di stampa.  Un <xref:System.Windows.Xps.Packaging.XpsDocument> viene archiviato in un dataset ZIP standard e può includere una combinazione di componenti XML e binari, ad esempio i file di immagine e del tipo di carattere. Gli oggetti [PackageRelationship](#PackageRelationships) vengono usati per definire le dipendenze tra il contenuto e le risorse necessarie per eseguire il rendering completo del documento.  Il <xref:System.Windows.Xps.Packaging.XpsDocument> progettazione offre una soluzione documento singolo, ad alta fedeltà che supporta più utilizzi:  
  
-   Lettura, scrittura e archiviazione del contenuto di documenti statici e risorse come un file singolo, portabile e facile da distribuire.  
  
-   Visualizzazione di documenti con l'applicazione [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] Viewer.  
  
-   Produzione di documenti nel formato di output nativo dello spool di stampa di [!INCLUDE[TLA#tla_winvista](../../../../includes/tlasharptla-winvista-md.md)].  
  
-   Routing diretto dei documenti a una stampante compatibile con [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)].  
  
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
- [Cenni preliminari sulla stampa](printing-overview.md)
- [Serializzazione e archiviazione di documenti](document-serialization-and-storage.md)
