---
title: Sicurezza dell'attendibilità parzialePartial Trust Security
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- partial trust security [WPF]
- detecting permissions [WPF]
- security settings for Internet Explorer [WPF]
- partial trust applications [WPF], debugging
- permissions [WPF], managing
- debugging partial trust applications [WPF]
- permissions [WPF], detecting
- feature security requirements [WPF]
- managing permissions [WPF]
ms.assetid: ef2c0810-1dbf-4511-babd-1fab95b523b5
ms.openlocfilehash: 99c7d9cfae2b137053ca77d9e3d7055b4674ce5b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174576"
---
# <a name="wpf-partial-trust-security"></a>Sicurezza con attendibilità parziale in WPF
<a name="introduction"></a>I n generale, sarebbe opportuno limitare l'accesso diretto alle risorse critiche del sistema da parte delle applicazioni Internet in modo da impedire qualsiasi danno. Per impostazione predefinita, i linguaggi di script HTML e lato client non sono in grado di accedere alle risorse di sistema critiche. Poiché le applicazioni ospitate da browser Windows Presentation Foundation (WPF) possono essere avviate dal browser, devono essere conformi a un set di restrizioni simile. Per applicare queste restrizioni, WPFWPF si basa su sicurezza dall'accesso di codice (CAS) e ClickOnce (vedere [Strategia](wpf-security-strategy-platform-security.md)di sicurezza WPF - sicurezza della piattaforma ). Per impostazione predefinita, le applicazioni ospitate da browser richiedono il set di autorizzazioni CAS dell'area Internet, indipendentemente dal fatto che vengano avviate da Internet, dalla rete Intranet locale o dal computer locale. Le applicazioni in esecuzione con un set di autorizzazioni incompleto vengono definite applicazioni in esecuzione con attendibilità parziale.  
  
 WPFWPF fornisce un'ampia gamma di supporto per garantire che il maggior numero possibile di funzionalità possa essere utilizzato in modo sicuro in attendibilità parziale e, insieme a CAS, fornisce supporto aggiuntivo per la programmazione con attendibilità parziale.  
  
 In questo argomento sono incluse le sezioni seguenti:  
  
- [Supporto con attendibilità parziale della funzionalità WPF](#WPF_Feature_Partial_Trust_Support)  
  
- [Programmazione con attendibilità parziale](#Partial_Trust_Programming)  
  
- [Gestione delle autorizzazioni](#Managing_Permissions)  
  
<a name="WPF_Feature_Partial_Trust_Support"></a>
## <a name="wpf-feature-partial-trust-support"></a>Supporto con attendibilità parziale della funzionalità WPF  
 Nella tabella seguente sono elencate le funzionalità generali di Windows Presentation Foundation (WPF) che possono essere utilizzate in modo sicuro entro i limiti del set di autorizzazioni dell'area Internet.  
  
 Tabella 1: Funzionalità WPF sicure in attendibilità parziale  
  
|Area di funzionalità|Funzionalità|  
|------------------|-------------|  
|Generale|Finestra del browser<br /><br /> Accesso al sito di origine<br /><br /> IsolatedStorage (limite di 512 KB)<br /><br /> Provider UIAutomation<br /><br /> Esecuzione di comandi<br /><br /> Input Method Editor (IME)<br /><br /> Stilo e input penna da tablet<br /><br /> Trascinamento della selezione simulato mediante eventi di acquisizione e spostamento del mouse<br /><br /> OpenFileDialog<br /><br /> Deserializzazione XAML (tramite XamlReader.Load)|  
|Integrazione Web|Finestra di dialogo di download del browser<br /><br /> Navigazione di primo livello avviata dall'utente<br /><br /> Collegamenti mailto:<br /><br /> Parametri URI (Uniform Resource Identifier)<br /><br /> HTTPWebRequest<br /><br /> Contenuto WPF ospitato in IFRAME<br /><br /> Hosting di pagine HTML dello stesso sito usando Frame<br /><br /> Hosting di pagine HTML dello stesso sito usando WebBrowser<br /><br /> Servizi Web (ASMX)<br /><br /> Servizi Web (mediante Windows Communication Foundation)<br /><br /> Scripting<br /><br /> Document Object Model (DOM)|  
|Elementi visivi|2D e 3D<br /><br /> Animazione<br /><br /> Elementi multimediali (sito di origine e tra domini)<br /><br /> Immagini/Audio/Video|  
|Lettura|FlowDocument<br /><br /> Documenti XPS<br /><br /> Tipi di carattere incorporati e di sistema<br /><br /> Caratteri CFF e TrueType|  
|Modifica|Controllo ortografico<br /><br /> RichTextBox<br /><br /> Supporto Appunti per testo non crittografato e input penna<br /><br /> Operazione Incolla avviata dall'utente<br /><br /> Copia di contenuto selezionato|  
|Controlli|Controlli generali|  
  
 Questa tabella illustra le funzionalità WPFWPF a livello generale. Per informazioni più dettagliate, Windows SDK documenta le autorizzazioni richieste da ogni membro in WPFWPF. Inoltre, per le funzionalità seguenti sono disponibili informazioni più dettagliate sull'esecuzione in situazioni di attendibilità parziale, con alcune considerazioni speciali.  
  
- [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)](Vedere [Cenni preliminari su XAML (WPF)](../../desktop-wpf/fundamentals/xaml.md).  
  
- Popup (vedere <xref:System.Windows.Controls.Primitives.Popup?displayProperty=nameWithType>).  
  
- Trascinae (consultate [Panoramica del trascinamento](./advanced/drag-and-drop-overview.md)della selezione).  
  
- Appunti (vedere <xref:System.Windows.Clipboard?displayProperty=nameWithType>).  
  
- Imaging (vedere <xref:System.Windows.Controls.Image?displayProperty=nameWithType>).  
  
- Serializzazione <xref:System.Windows.Markup.XamlReader.Load%2A?displayProperty=nameWithType>(vedere , <xref:System.Windows.Markup.XamlWriter.Save%2A?displayProperty=nameWithType>).  
  
- Finestra di dialogo <xref:Microsoft.Win32.OpenFileDialog?displayProperty=nameWithType>Apri file (vedere ).  
  
 Nella tabella seguente vengono descritte le funzionalità WPFWPF che non sono sicure per l'esecuzione entro i limiti del set di autorizzazioni dell'area Internet.  
  
 Tabella 2: Funzionalità WPF non sicure in attendibilità parziale  
  
|Area di funzionalità|Funzionalità|  
|------------------|-------------|  
|Generale|Finestra (finestre e finestre di dialogo definite dall'applicazione)<br /><br /> SaveFileDialog<br /><br /> File system<br /><br /> Accesso al Registro di sistema<br /><br /> Trascinamento e rilascio<br /><br /> Serializzazione XAML (mediante XamlWriter.Save)<br /><br /> Client UIAutomation<br /><br /> Accesso alla finestra di origine (HwndHost)<br /><br /> Supporto vocale completo<br /><br /> Interoperabilità con Windows Form|  
|Elementi visivi|Effetti bitmap<br /><br /> Codifica delle immagini|  
|Modifica|Appunti RTF (Rich-Text Format)<br /><br /> Supporto XAML completo|  
  
<a name="Partial_Trust_Programming"></a>
## <a name="partial-trust-programming"></a>Programmazione con attendibilità parziale  
 Per le applicazioni XBAP, il codice che supera il set di autorizzazioni predefinito avrà un comportamento diverso a seconda dell'area di sicurezza. In alcuni casi, l'utente riceverà un avviso quando tenta di installare il codice. L'utente potrà scegliere se continuare o annullare l'installazione. La tabella seguente descrive il comportamento dell'applicazione per ogni area di sicurezza e le azioni necessarie relative all'applicazione per acquisire attendibilità totale.  
  
|Area di sicurezza|Comportamento|Ottenere l'attendibilità totale|  
|-------------------|--------------|------------------------|  
|Computer locale|Attendibilità totale automatica|Non è richiesto alcun intervento.|  
|Intranet e siti attendibili|Richiesta di attendibilità totale|Firma dell'applicazione XBAP con un certificato in modo che l'utente veda l'origine nel prompt.|  
|Internet|Esito negativo con "Attendibilità non concessa"|Firma dell'applicazione XBAP con un certificato.|  
  
> [!NOTE]
> Il comportamento descritto nella tabella precedente è relativo alle applicazioni XBAP con attendibilità totale che non seguono il modello di distribuzione attendibile di ClickOnce.  
  
 In genere, è probabile che il codice che richiede autorizzazioni ulteriori rispetto a quelle consentite sia codice comune condiviso dalle applicazioni autonome e da quelle ospitate dal browser. CAS e WPFWPF offrono diverse tecniche per la gestione di questo scenario.  
  
<a name="Detecting_Permissions_using_CAS"></a>
### <a name="detecting-permissions-using-cas"></a>Rilevamento delle autorizzazioni tramite CAS  
 In alcune situazioni, è possibile che il codice condiviso negli assembly di libreria venga utilizzato sia dalle applicazioni autonome che dalle applicazioni XBAP. In questi casi, è possibile che il codice esegua funzionalità che potrebbero richiedere un numero di autorizzazioni maggiore rispetto al set assegnato all'applicazione. L'applicazione può rilevare se dispone o meno di una determinata autorizzazione utilizzando la sicurezza di Microsoft .NET Framework. In particolare, è possibile verificare se <xref:System.Security.CodeAccessPermission.Demand%2A> dispone di un'autorizzazione specifica chiamando il metodo sull'istanza dell'autorizzazione desiderata. Questa procedura è illustrata nell'esempio seguente, in cui il codice esegue una query per verificare la disponibilità dell'autorizzazione per salvare un file sul disco locale:  
  
 [!code-csharp[PartialTrustSecurityOverviewSnippets#DetectPermsCODE1](~/samples/snippets/csharp/VS_Snippets_Wpf/PartialTrustSecurityOverviewSnippets/CSharp/FileHandling.cs#detectpermscode1)]
 [!code-vb[PartialTrustSecurityOverviewSnippets#DetectPermsCODE1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PartialTrustSecurityOverviewSnippets/VisualBasic/FileHandling.vb#detectpermscode1)]  
[!code-csharp[PartialTrustSecurityOverviewSnippets#DetectPermsCODE2](~/samples/snippets/csharp/VS_Snippets_Wpf/PartialTrustSecurityOverviewSnippets/CSharp/FileHandling.cs#detectpermscode2)]
[!code-vb[PartialTrustSecurityOverviewSnippets#DetectPermsCODE2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PartialTrustSecurityOverviewSnippets/VisualBasic/FileHandling.vb#detectpermscode2)]  
  
 Se un'applicazione non dispone dell'autorizzazione <xref:System.Security.CodeAccessPermission.Demand%2A> desiderata, la chiamata a genererà un'eccezione di sicurezza. In caso contrario, l'autorizzazione è disponibile. `IsPermissionGranted`incapsula questo comportamento `true` `false` e restituisce o come appropriato.  
  
<a name="Graceful_Degradation_of_Functionality"></a>
### <a name="graceful-degradation-of-functionality"></a>Riduzione normale delle prestazioni della funzionalità  
 La capacità del codice di rilevare le autorizzazioni disponibili risulta particolarmente interessante quando il codice può essere eseguito da aree diverse. Sebbene il rilevamento dell'area sia importante, è meglio fornire un'alternativa all'utente, se possibile. Ad esempio, di solito un'applicazione con attendibilità totale consente agli utenti di creare file in qualsiasi posizione, mentre un'applicazione con attendibilità parziale consente di creare file unicamente in uno spazio di archiviazione isolato. Se il codice per la creazione di un file è contenuto in un assembly condiviso da applicazioni con attendibilità totale (autonome) e applicazioni con attendibilità parziale (ospitate dal browser) e si vuole che entrambi i tipi di applicazioni consentano la creazione di file, il codice condiviso dovrà rilevare se viene eseguito in attendibilità parziale o totale prima di creare un file nel percorso appropriato. I due casi sono illustrati nel codice seguente.  
  
 [!code-csharp[PartialTrustSecurityOverviewSnippets#DetectPermsGracefulCODE1](~/samples/snippets/csharp/VS_Snippets_Wpf/PartialTrustSecurityOverviewSnippets/CSharp/FileHandlingGraceful.cs#detectpermsgracefulcode1)]
 [!code-vb[PartialTrustSecurityOverviewSnippets#DetectPermsGracefulCODE1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PartialTrustSecurityOverviewSnippets/VisualBasic/FileHandlingGraceful.vb#detectpermsgracefulcode1)]  
[!code-csharp[PartialTrustSecurityOverviewSnippets#DetectPermsGracefulCODE2](~/samples/snippets/csharp/VS_Snippets_Wpf/PartialTrustSecurityOverviewSnippets/CSharp/FileHandlingGraceful.cs#detectpermsgracefulcode2)]
[!code-vb[PartialTrustSecurityOverviewSnippets#DetectPermsGracefulCODE2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PartialTrustSecurityOverviewSnippets/VisualBasic/FileHandlingGraceful.vb#detectpermsgracefulcode2)]  
  
 In molte situazioni è possibile trovare un'alternativa all'attendibilità parziale.  
  
 In un ambiente controllato, ad esempio una rete Intranet, i framework gestiti personalizzati possono essere installati attraverso la base client nella Global Assembly Cache (GAC). Queste librerie possono eseguire codice che richiede attendibilità totale e farvi <xref:System.Security.AllowPartiallyTrustedCallersAttribute> riferimento solo da applicazioni a cui è consentito l'attendibilità parziale tramite (per ulteriori informazioni, vedere [Security](security-wpf.md) and [WPF Security Strategy - Platform Security](wpf-security-strategy-platform-security.md)).  
  
<a name="Browser_Host_Detection"></a>
### <a name="browser-host-detection"></a>Rilevamento host del browser  
 L'utilizzo di CAS per verificare le autorizzazioni è una tecnica adatta quando è necessario controllare in base alle autorizzazioni. Tuttavia, tale tecnica dipende dal rilevamento di eccezioni durante la normale elaborazione, operazione che in genere non è consigliata e che può causare problemi di prestazioni. Al contrario, se l'applicazione browser XAML (XBAP) viene <xref:System.Windows.Interop.BrowserInteropHelper.IsBrowserHosted%2A?displayProperty=nameWithType> eseguita solo all'interno della sandbox dell'area Internet, è possibile utilizzare la proprietà , che restituisce true per le applicazioni browser XAML (XBAP).  
  
> [!NOTE]
> <xref:System.Windows.Interop.BrowserInteropHelper.IsBrowserHosted%2A>distingue solo se un'applicazione è in esecuzione in un browser, non il set di autorizzazioni con cui viene eseguita un'applicazione.  
  
<a name="Managing_Permissions"></a>
## <a name="managing-permissions"></a>Gestione delle autorizzazioni  
 Per impostazione predefinita, le applicazioni XBAP vengono eseguite con attendibilità parziale (set di autorizzazioni dell'area Internet predefinito). Tuttavia, a seconda dei requisiti dell'applicazione, questo set predefinito può essere modificato. Ad esempio, se un'applicazione XBAP viene avviata da una rete Intranet locale, può sfruttare un set di autorizzazioni maggiore, illustrato nella tabella seguente.  
  
 Tabella 3: Autorizzazioni LocalIntranet e Internet  
  
|Autorizzazione|Attributo|LocalIntranet|Internet|  
|----------------|---------------|-------------------|--------------|  
|DNS|Accesso ai server DNS|Sì|No|  
|Variabili di ambiente|Lettura|Sì|No|  
|Finestre di dialogo file|Apri|Sì|Sì|  
|Finestre di dialogo file|Senza restrizioni|Sì|No|  
|Spazio di memorizzazione isolato|Isolamento assembly in base all'utente|Sì|No|  
|Spazio di memorizzazione isolato|Isolamento sconosciuto|Sì|Sì|  
|Spazio di memorizzazione isolato|Quota utenti illimitata|Sì|No|  
|Contenuti multimediali|Audio, video e immagini sicuri|Sì|Sì|  
|Stampa|Stampa predefinita|Sì|No|  
|Stampa|Stampa sicura|Sì|Sì|  
|Reflection|Emissione|Sì|No|  
|Security|Esecuzione del codice gestito|Sì|Sì|  
|Security|Asserzione autorizzazioni concesse|Sì|No|  
|Interfaccia utente|Senza restrizioni|Sì|No|  
|Interfaccia utente|Finestre di primo livello sicure|Sì|Sì|  
|Interfaccia utente|Appunti personali|Sì|Sì|  
|Web browser|Navigazione sicura dei frame in HTML|Sì|Sì|  
  
> [!NOTE]
> L'operazione di taglia e incolla, se avviata dall'utente, è consentita solo con l'attendibilità parziale.  
  
 Per aumentare il numero di autorizzazioni, è necessario modificare le impostazioni del progetto e il manifesto dell'applicazione ClickOnce. Per altre informazioni, vedere [Panoramica delle applicazioni browser XAML di WPF](./app-development/wpf-xaml-browser-applications-overview.md). Anche i seguenti documenti possono rivelarsi utili.  
  
- [Mage.exe (strumento di generazione e modifica di manifesti)](../tools/mage-exe-manifest-generation-and-editing-tool.md).  
  
- [MageUI.exe (strumento di generazione e modifica di manifesti, client grafico)](../tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client.md).  
  
- [Protezione delle applicazioni ClickOnce](/visualstudio/deployment/securing-clickonce-applications).  
  
 Se l'applicazione XBAP richiede l'attendibilità totale, è possibile utilizzare gli stessi strumenti per aumentare le autorizzazioni richieste. Anche se un'applicazione XBAP riceverà l'attendibilità totale solo se è installata e avviata dal computer locale, dalla rete Intranet o da un URL elencato nei siti attendibili o consentiti del browser. Se l'applicazione viene installata dalla Intranet o da un sito attendibile, verrà visualizzato all'utente il prompt standard di ClickOnce con la notifica relativa alle autorizzazioni elevate. L'utente potrà scegliere se continuare o annullare l'installazione.  
  
 In alternativa, è possibile usare il modello di distribuzione attendibile di ClickOnce per una distribuzione con attendibilità totale da qualsiasi area di sicurezza. Per ulteriori informazioni, vedere [Cenni preliminari](/visualstudio/deployment/trusted-application-deployment-overview) sulla distribuzione di applicazioni attendibili e [Sicurezza](security-wpf.md).  
  
## <a name="see-also"></a>Vedere anche

- [Sicurezza](security-wpf.md)
- [Strategia di sicurezza di WPF - Sicurezza della piattaforma](wpf-security-strategy-platform-security.md)
- [Strategia di sicurezza WPF - Progettazione della sicurezza](wpf-security-strategy-security-engineering.md)
