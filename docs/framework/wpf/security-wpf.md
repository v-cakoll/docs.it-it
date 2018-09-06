---
title: Sicurezza (WPF)
ms.date: 03/30/2017
helpviewer_keywords:
- XAML files [WPF], sandbox behavior
- browser-hosted application security [WPF]
- application security [WPF]
- navigation security [WPF]
- loose XAML files [WPF], sandbox behavior
- WPF security [WPF]
- WebBrowser control [WPF], security
- feature controls [WPF], security
- XBAP security [WPF]
- Internet Explorer security settings [WPF]
ms.assetid: ee1baea0-3611-4e36-9ad6-fcd5205376fb
ms.openlocfilehash: 970fd0483d7e0126b258afd5ac5c3607cbc6aa0a
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2018
ms.locfileid: "43891876"
---
# <a name="security-wpf"></a>Sicurezza (WPF)
<a name="introduction"></a> Durante lo sviluppo di Windows Presentation Foundation (WPF) applicazioni autonome e ospitate da browser, è necessario considerare il modello di sicurezza. [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] applicazioni autonome vengono eseguite con autorizzazioni senza restrizioni ( [!INCLUDE[TLA2#tla_cas](../../../includes/tla2sharptla-cas-md.md)] **FullTrust** set di autorizzazioni), se distribuite mediante Windows Installer (MSI), XCopy, o [!INCLUDE[TLA2#tla_clickonce](../../../includes/tla2sharptla-clickonce-md.md)]. Non è supportata la distribuzione di applicazioni WPF autonome e parzialmente attendibili con ClickOnce. Tuttavia, un'applicazione host di attendibilità totale può creare una relazione di trust parziale <xref:System.AppDomain> usando il modello di componente aggiuntivo di .NET Framework. Per altre informazioni, vedere [Cenni preliminari sui componenti aggiuntivi di WPF](../../../docs/framework/wpf/app-development/wpf-add-ins-overview.md).  
  
 [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] sono ospitate applicazioni ospitate da browser [!INCLUDE[TLA#tla_iegeneric](../../../includes/tlasharptla-iegeneric-md.md)] o Firefox, e può essere rappresentata [!INCLUDE[TLA#tla_xbap#plural](../../../includes/tlasharptla-xbapsharpplural-md.md)] o loose [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] documenti per altre informazioni, vedere [panoramica delle applicazioni Browser XAML di WPF](../../../docs/framework/wpf/app-development/wpf-xaml-browser-applications-overview.md).  
  
 [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] applicazioni ospitate da browser eseguono all'interno di una sandbox di sicurezza parzialmente attendibile, per impostazione predefinita, che è limitato per impostazione predefinita [!INCLUDE[TLA2#tla_cas](../../../includes/tla2sharptla-cas-md.md)] **Internet** zona set di autorizzazioni. Questo isola [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] applicazioni ospitate da browser dal computer client allo stesso modo si aspetta che le applicazioni Web tipiche siano isolati. Un'applicazione XBAP può elevare il livello di privilegi fino ad Attendibilità totale a seconda dell'area di sicurezza dell'URL di distribuzione e della configurazione di sicurezza del client. Per altre informazioni, vedere [Sicurezza con attendibilità parziale in WPF](../../../docs/framework/wpf/wpf-partial-trust-security.md).  
  
 Questo argomento illustra il modello di sicurezza per Windows Presentation Foundation (WPF) applicazioni autonome e ospitate da browser.  
  
 Di seguito sono elencate le diverse sezioni di questo argomento:  
  
-   [Navigazione sicura](#SafeTopLevelNavigation)  
  
-   [Impostazioni di sicurezza del software per l'esplorazione Web](#InternetExplorerSecuritySettings)  
  
-   [Controllo WebBrowser e controlli della funzionalità](#webbrowser_control_and_feature_controls)  
  
-   [Disabilitazione degli assembly APTCA per le applicazioni client parzialmente attendibili](#APTCA)  
  
-   [Comportamento della sandbox per i file XAML separati](#LooseContentSandboxing)  
  
-   [Risorse per lo sviluppo di applicazioni WPF che garantiscano la sicurezza](#BestPractices)  
  
<a name="SafeTopLevelNavigation"></a>   
## <a name="safe-navigation"></a>Navigazione sicura  
 Per la [!INCLUDE[TLA2#tla_xbap#plural](../../../includes/tla2sharptla-xbapsharpplural-md.md)], [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] distingue due tipi di navigazione: applicazioni e del browser.  
  
 La *navigazione tramite applicazione* consiste nel passaggio tra elementi di contenuto all'interno di un'applicazione ospitata da un browser. La *navigazione tramite browser* implica la modifica del contenuto e dell'URL del percorso del browser stesso. La relazione tra la navigazione tramite applicazione (in genere XAML) e la navigazione tramite browser (in genere HTML) è illustrata nella figura seguente:
  
 ![Diagramma della navigazione](../../../docs/framework/wpf/media/safetoplevelnavigationfigure.png "SafeTopLevelNavigationFigure")  
  
 Il tipo di contenuto considerato sicuro per un [!INCLUDE[TLA2#tla_xbap](../../../includes/tla2sharptla-xbap-md.md)] per passare alla è principalmente determinato dal fatto che viene utilizzata la navigazione tramite applicazione o la navigazione tramite browser.  
  
<a name="Application_Navigation_Security"></a>   
### <a name="application-navigation-security"></a>Sicurezza della navigazione tramite applicazione  
 Navigazione tramite applicazione è considerata sicura se può essere identificata con un pack [!INCLUDE[TLA2#tla_uri](../../../includes/tla2sharptla-uri-md.md)], che supporta quattro tipi di contenuto:  
  
|Tipo di contenuto|Descrizione|Esempio di URI|  
|------------------|-----------------|-----------------|  
|Risorsa|I file che vengono aggiunti a un progetto con un tipo di compilazione **risorsa**.|`pack://application:,,,/MyResourceFile.xaml`|  
|Content|I file che vengono aggiunti a un progetto con un tipo di compilazione **contenuto**.|`pack://application:,,,/MyContentFile.xaml`|  
|Sito di origine|I file che vengono aggiunti a un progetto con un tipo di compilazione **None**.|`pack://siteoforigin:,,,/MySiteOfOriginFile.xaml`|  
|Codice dell'applicazione|Risorse XAML che dispongono di code-behind compilato.<br /><br /> oppure<br /><br /> File XAML aggiunti a un progetto con un tipo di compilazione **pagina**.|`pack://application:,,,/MyResourceFile` `.xaml`|  
  
> [!NOTE]
>  Per altre informazioni sui file di dati dell'applicazione e pack [!INCLUDE[TLA2#tla_uri#plural](../../../includes/tla2sharptla-urisharpplural-md.md)], vedere [WPF Application Resource, contenuto e i file di dati](../../../docs/framework/wpf/app-development/wpf-application-resource-content-and-data-files.md).  
  
 La navigazione dei file di questi tipi di contenuto è possibile sia da parte dell'utente che a livello di codice:  
  
-   **Navigazione dell'utente**. L'utente esegue la navigazione facendo un <xref:System.Windows.Documents.Hyperlink> elemento.  
  
-   **Navigazione a livello di codice**. L'applicazione passa senza intervento dell'utente, ad esempio, impostando il <xref:System.Windows.Navigation.NavigationWindow.Source%2A?displayProperty=nameWithType> proprietà.  
  
<a name="Browser_Navigation_Security"></a>   
### <a name="browser-navigation-security"></a>Sicurezza della navigazione tramite browser  
 La navigazione tramite browser è considerata sicura solo nelle condizioni seguenti:  
  
-   **Navigazione dell'utente**. L'utente esegue la navigazione facendo una <xref:System.Windows.Documents.Hyperlink> dell'elemento corrispondente nel terminale <xref:System.Windows.Navigation.NavigationWindow>, non in nidificato <xref:System.Windows.Controls.Frame>.  
  
-   **Area**. Il contenuto per la navigazione si trova nell'area Internet o Intranet locale.  
  
-   **Protocollo**. È il protocollo usato **http**, **https**, **file**, oppure **mailto**.  
  
 Se un' [!INCLUDE[TLA2#tla_xbap](../../../includes/tla2sharptla-xbap-md.md)] prova a esplorare il contenuto in modo che non è conforme a queste condizioni, un <xref:System.Security.SecurityException> viene generata un'eccezione.  
  
<a name="InternetExplorerSecuritySettings"></a>   
## <a name="web-browsing-software-security-settings"></a>Impostazioni di sicurezza del software per l'esplorazione Web  
 Le impostazioni di sicurezza nel computer in uso determinano l'accesso garantito a qualsiasi software per l'esplorazione Web. Software per l'esplorazione Web include qualsiasi applicazione o componente che utilizza il [WinINet](https://go.microsoft.com/fwlink/?LinkId=179379) oppure [UrlMon](https://go.microsoft.com/fwlink/?LinkId=179383) API, inclusi Internet Explorer e PresentationHost.exe.  
  
 [!INCLUDE[TLA2#tla_iegeneric](../../../includes/tla2sharptla-iegeneric-md.md)] fornisce un meccanismo mediante il quale è possibile configurare la funzionalità che può essere eseguita da o in [!INCLUDE[TLA2#tla_iegeneric](../../../includes/tla2sharptla-iegeneric-md.md)], inclusi i seguenti:  
  
-   Componenti basati su framework .NET  
  
-   Controlli e plug-in ActiveX  
  
-   Download  
  
-   Scripting  
  
-   Autenticazione utente  
  
 La raccolta delle funzionalità che possono essere protette in questo modo viene configurata su una base per ogni area per il **Internet**, **Intranet**, **dei siti attendibili**, e  **Siti con restrizioni** zone. La procedura seguente descrive come configurare le impostazioni di sicurezza:  
  
1.  Aprire il **Pannello di controllo**.  
  
2.  Fare clic su **rete e Internet** e quindi fare clic su **Opzioni Internet**.  
  
     Viene visualizzata la finestra di dialogo Opzioni Internet.  
  
3.  Nel **sicurezza** scheda, selezionare l'area per configurare le impostazioni di sicurezza.  
  
4.  Scegliere il **livello personalizzato** pulsante.  
  
     Il **impostazioni di sicurezza** verrà visualizzata la finestra di dialogo ed è possibile configurare le impostazioni di sicurezza per l'area selezionata.  
  
     ![Finestra di dialogo Impostazioni di sicurezza](../../../docs/framework/wpf/media/wpfsecurityfigure1.PNG "WPFSecurityFigure1")  
  
> [!NOTE]
>  È anche possibile passare alla finestra di dialogo Opzioni Internet tramite Internet Explorer. Fare clic su **degli strumenti** e quindi fare clic su **Opzioni Internet**.  
  
 A partire da [!INCLUDE[TLA#tla_ie7](../../../includes/tlasharptla-ie7-md.md)], le seguenti impostazioni di sicurezza in modo specifico per .NET Framework sono incluse:  
  
-   **XAML libero**. Controlli se [!INCLUDE[TLA2#tla_iegeneric](../../../includes/tla2sharptla-iegeneric-md.md)] possibile esplorazione e separare [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] file. (opzioni Abilita, Disabilita e Chiedi conferma).  
  
-   **Applicazioni browser XAML**. Controlli se [!INCLUDE[TLA2#tla_iegeneric](../../../includes/tla2sharptla-iegeneric-md.md)] possono passare a ed eseguire [!INCLUDE[TLA2#tla_xbap#plural](../../../includes/tla2sharptla-xbapsharpplural-md.md)]. (opzioni Abilita, Disabilita e Chiedi conferma).  
  
 Per impostazione predefinita, queste impostazioni sono tutte abilitate per il **Internet**, **intranet locale**, e **siti attendibili** zone e disabilitato per il **siti con restrizioni**  zona.  
  
<a name="Security_Settings_for_IE6_and_Below"></a>   
### <a name="security-related-wpf-registry-settings"></a>Impostazioni del Registro di sistema WPF correlate alla sicurezza  
 Oltre alle impostazioni di sicurezza disponibili tramite Opzioni Internet, sono disponibili i seguenti valori del Registro di sistema per bloccare in modo selettivo alcune funzionalità WPF relative alla sicurezza. I valori sono definiti nella chiave seguente:  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\Windows Presentation Foundation\Features`  
  
 La tabella seguente elenca i valori che è possibile impostare.  
  
|Nome valore|Tipo di valore|Dati valore|  
|----------------|----------------|----------------|  
|XBAPDisallow|REG_DWORD|1 per non consentire; 0 per consentire.|  
|LooseXamlDisallow|REG_DWORD|1 per non consentire; 0 per consentire.|  
|WebBrowserDisallow|REG_DWORD|1 per non consentire; 0 per consentire.|  
|MediaAudioDisallow|REG_DWORD|1 per non consentire; 0 per consentire.|  
|MediaImageDisallow|REG_DWORD|1 per non consentire; 0 per consentire.|  
|MediaVideoDisallow|REG_DWORD|1 per non consentire; 0 per consentire.|  
|ScriptInteropDisallow|REG_DWORD|1 per non consentire; 0 per consentire.|  
  
<a name="webbrowser_control_and_feature_controls"></a>   
## <a name="webbrowser-control-and-feature-controls"></a>Controllo WebBrowser e controlli della funzionalità  
 WPF <xref:System.Windows.Controls.WebBrowser> controllo può essere usato per ospitare contenuto Web. WPF <xref:System.Windows.Controls.WebBrowser> controllo esegue il wrapping del controllo WebBrowser ActiveX sottostante. WPF fornisce supporto per la protezione dell'applicazione quando si usa l'applicazione WPF <xref:System.Windows.Controls.WebBrowser> controllo da ospitare contenuto Web non attendibile. Tuttavia, alcune funzionalità di sicurezza deve essere applicato direttamente dalle applicazioni tramite il <xref:System.Windows.Controls.WebBrowser> controllo. Per altre informazioni sul controllo WebBrowser ActiveX, vedere [WebBrowser controllo panoramiche ed esercitazioni](https://go.microsoft.com/fwlink/?LinkId=179388).  
  
> [!NOTE]
>  In questa sezione si applica anche per il <xref:System.Windows.Controls.Frame> controllare perché Usa il <xref:System.Windows.Controls.WebBrowser> di esplorare il contenuto HTML.  
  
 Se l'applicazione WPF <xref:System.Windows.Controls.WebBrowser> controllo viene usato per ospitare contenuto Web non attendibile, l'applicazione deve usare una relazione di trust parziale <xref:System.AppDomain> per essere utile per isolare il codice dell'applicazione dal codice di script HTML potenzialmente dannoso. Ciò è particolarmente vero se l'applicazione interagisca con lo script ospitato tramite il <xref:System.Windows.Controls.WebBrowser.InvokeScript%2A> metodo e <xref:System.Windows.Controls.WebBrowser.ObjectForScripting%2A> proprietà. Per altre informazioni, vedere [Cenni preliminari sui componenti aggiuntivi di WPF](../../../docs/framework/wpf/app-development/wpf-add-ins-overview.md).  
  
 Se l'applicazione usa l'applicazione WPF <xref:System.Windows.Controls.WebBrowser> controllo, è un altro modo per aumentare la sicurezza e ridurre gli attacchi per abilitare i controlli di funzionalità di Internet Explorer. Controlli della funzionalità vengono aggiunte a Internet Explorer che consentono ad amministratori e sviluppatori di configurare le funzionalità di Internet Explorer e le applicazioni che ospitano il controllo WebBrowser ActiveX, quale l'applicazione WPF <xref:System.Windows.Controls.WebBrowser> controllo esegue il wrapping. Controlli della funzionalità possono essere configurati tramite il [CoInternetSetFeatureEnabled](https://go.microsoft.com/fwlink/?LinkId=179394) funzione oppure modificando i valori del Registro di sistema. Per altre informazioni sui controlli della funzionalità, vedere [Introduction to Feature Controls](https://go.microsoft.com/fwlink/?LinkId=179390) e [controlli della funzionalità Internet](https://go.microsoft.com/fwlink/?LinkId=179392).  
  
 Se si sviluppa un'applicazione WPF autonoma che usa l'applicazione WPF <xref:System.Windows.Controls.WebBrowser> (controllo), WPF abilita automaticamente i seguenti controlli della funzionalità per l'applicazione.  
  
|Controllo della funzionalità|  
|---------------------|  
|FEATURE_MIME_HANDLING|  
|FEATURE_MIME_SNIFFING|  
|FEATURE_OBJECT_CACHING|  
|FEATURE_SAFE_BINDTOOBJECT|  
|FEATURE_WINDOW_RESTRICTIONS|  
|FEATURE_ZONE_ELEVATION|  
|FEATURE_RESTRICT_FILEDOWNLOAD|  
|FEATURE_RESTRICT_ACTIVEXINSTALL|  
|FEATURE_ADDON_MANAGEMENT|  
|FEATURE_HTTP_USERNAME_PASSWORD_DISABLE|  
|FEATURE_SECURITYBAND|  
|FEATURE_UNC_SAVEDFILECHECK|  
|FEATURE_VALIDATE_NAVIGATE_URL|  
|FEATURE_DISABLE_TELNET_PROTOCOL|  
|FEATURE_WEBOC_POPUPMANAGEMENT|  
|FEATURE_DISABLE_LEGACY_COMPRESSION|  
|FEATURE_SSLUX|  
  
 Poiché questi controlli della funzionalità vengono abilitati incondizionatamente, potrebbero danneggiare un'applicazione con attendibilità totale. In questo caso, se non sono presenti rischi per la sicurezza relativi all'applicazione specifica e al contenuto che ospita, è possibile disabilitare il controllo della funzionalità corrispondente.  
  
 Controlli della funzionalità vengono applicati dal processo di creazione di un'istanza dell'oggetto WebBrowser ActiveX. Pertanto, se si crea un'applicazione autonoma in grado di passare a contenuto non attendibile, è assolutamente opportuno abilitare controlli della funzionalità aggiuntivi.  
  
> [!NOTE]
>  Questa indicazione è basata sui suggerimenti generali per la sicurezza host MSHTML e SHDOCVW. Per altre informazioni, vedere [The MSHTML Host Security FAQ: parte I di II](https://go.microsoft.com/fwlink/?LinkId=179396) e [The MSHTML Host Security FAQ: Part II of II](https://go.microsoft.com/fwlink/?LinkId=179415).  
  
 Per il file eseguibile, abilitare i controlli della funzionalità riportati di seguito impostando il valore del Registro di sistema su 1.  
  
|Controllo della funzionalità|  
|---------------------|  
|FEATURE_ACTIVEX_REPURPOSEDETECTION|  
|FEATURE_BLOCK_LMZ_IMG|  
|FEATURE_BLOCK_LMZ_OBJECT|  
|FEATURE_BLOCK_LMZ_SCRIPT|  
|FEATURE_RESTRICT_RES_TO_LMZ|  
|FEATURE_RESTRICT_ABOUT_PROTOCOL_IE7|  
|FEATURE_SHOW_APP_PROTOCOL_WARN_DIALOG|  
|FEATURE_LOCALMACHINE_LOCKDOWN|  
|FEATURE_FORCE_ADDR_AND_STATUS|  
|FEATURE_RESTRICTED_ZONE_WHEN_FILE_NOT_FOUND|  
  
 Per il file eseguibile, disabilitare il controllo della funzionalità riportato di seguito impostando il valore del Registro di sistema su 0.  
  
|Controllo della funzionalità|  
|---------------------|  
|FEATURE_ENABLE_SCRIPT_PASTE_URLACTION_IF_PROMPT|  
  
 Se si esegue una relazione di trust parziale [!INCLUDE[TLA#tla_xbap](../../../includes/tlasharptla-xbap-md.md)] che include un WPF <xref:System.Windows.Controls.WebBrowser> controllare in [!INCLUDE[TLA#tla_iegeneric](../../../includes/tlasharptla-iegeneric-md.md)], WPF ospita il controllo WebBrowser ActiveX nello spazio degli indirizzi del processo di Internet Explorer. Poiché il controllo WebBrowser ActiveX è ospitato nel [!INCLUDE[TLA2#tla_iegeneric](../../../includes/tla2sharptla-iegeneric-md.md)] processo, anche tutti i controlli della funzionalità per Internet Explorer vengono abilitati per il controllo WebBrowser ActiveX.  
  
 Le applicazioni XBAP in esecuzione in Internet Explorer ottengono anche un livello di sicurezza aggiuntivo rispetto alle applicazioni autonome normali. Questa protezione aggiuntiva è Internet Explorer e pertanto il controllo WebBrowser ActiveX, viene eseguita in protetto per impostazione predefinita in modalità [!INCLUDE[TLA#tla_winvista](../../../includes/tlasharptla-winvista-md.md)] e [!INCLUDE[win7](../../../includes/win7-md.md)]. Per altre informazioni sulla modalità protetta, vedere [comprensione e l'utilizzo della modalità protetta di Internet Explorer](https://go.microsoft.com/fwlink/?LinkId=179393).  
  
> [!NOTE]
>  Se si prova a eseguire un'applicazione XBAP che include un controllo WPF <xref:System.Windows.Controls.WebBrowser> controllo in Firefox, mentre nell'area Internet, un <xref:System.Security.SecurityException> verrà generata. Tale eccezione è determinata dai criteri di sicurezza WPF.  
  
<a name="APTCA"></a>   
## <a name="disabling-aptca-assemblies-for-partially-trusted-client-applications"></a>Disabilitazione degli assembly APTCA per le applicazioni client parzialmente attendibili  
 Se sono installati gli assembly gestiti nel [!INCLUDE[TLA#tla_gac](../../../includes/tlasharptla-gac-md.md)], diventano completamente attendibili perché l'utente deve fornire un'autorizzazione esplicita per installarli. Dal momento che sono completamente attendibili, possono essere usati solo dalle applicazioni client gestite completamente attendibili. Per consentire alle applicazioni parzialmente attendibili di usarli, devono essere contrassegnati con il <xref:System.Security.AllowPartiallyTrustedCallersAttribute> (APTCA). Solo gli assembly per cui il test di sicurezza per l'esecuzione ha dato come esito un'attendibilità parziale possono essere contrassegnati con questo attributo.  
  
 Tuttavia, è possibile che un assembly APTCA può presentare un difetto di protezione dopo l'installazione nel [!INCLUDE[TLA2#tla_gac](../../../includes/tla2sharptla-gac-md.md)]. Quando viene individuato un difetto nel sistema di sicurezza, gli editori dell'assembly possono creare un aggiornamento della sicurezza per risolvere il problema nelle installazioni esistenti e per proteggere le installazioni eseguite dopo l'individuazione del problema. Un'opzione per l'aggiornamento è la disinstallazione dell'assembly, anche se in questo modo può essere compromessa la funzionalità di altre applicazioni client completamente attendibili che usano l'assembly.  
  
 [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] fornisce un meccanismo mediante il quale un assembly APTCA può essere disabilitato per parzialmente attendibile [!INCLUDE[TLA2#tla_xbap#plural](../../../includes/tla2sharptla-xbapsharpplural-md.md)] senza disinstallare l'assembly APTCA.  
  
 Per disabilitare un assembly APTCA, è necessario creare una chiave speciale del Registro di sistema:  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\policy\APTCA\<AssemblyFullName>, FileVersion=<AssemblyFileVersion>`  
  
 Di seguito viene riportato un esempio:  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\policy\APTCA\aptcagac, Version=1.0.0.0, Culture=neutral, PublicKeyToken=215e3ac809a0fea7, FileVersion=1.0.0.0`  
  
 Questa chiave definisce una voce per l'assembly APTCA. È anche necessario creare un valore di questa chiave che abiliti o disabiliti l'assembly. Di seguito sono riportati i dettagli del valore:  
  
-   Nome valore: **APTCA_FLAG**.  
  
-   Tipo di valore: **REG_DWORD**.  
  
-   Dati valore: **1** disabilitare; **0** abilitare.  
  
 Se è necessario disabilitare un assembly per applicazioni client parzialmente attendibili, è possibile scrivere un aggiornamento per creare la chiave del Registro di sistema e il valore.  
  
> [!NOTE]
>  Assembly di .NET Framework principali non sono interessate dalla disabilitazione in questo modo perché sono necessari per eseguire le applicazioni gestite. Il supporto per la disabilitazione degli assembly APTCA è destinato principalmente alle applicazioni di terze parti.  
  
<a name="LooseContentSandboxing"></a>   
## <a name="sandbox-behavior-for-loose-xaml-files"></a>Comportamento della sandbox per i file XAML separati  
 Loose [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] i file sono file XAML di soli markup che non dipendono da alcun code-behind, gestore eventi o assembly specifici dell'applicazione. Quando regime [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] si passa a file direttamente dal browser, vengono caricati in una sandbox di sicurezza basata su set di autorizzazioni area Internet predefinito.  
  
 Tuttavia, il comportamento di sicurezza è diverso quando loose [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] si passa a file da una un' <xref:System.Windows.Navigation.NavigationWindow> o <xref:System.Windows.Controls.Frame> in un'applicazione autonoma.  
  
 In entrambi i casi, il regime [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] file di destinazione della navigazione eredita le autorizzazioni dell'applicazione host. Tuttavia, questo comportamento può essere inaccettabile dal punto di vista della sicurezza, in particolare se loose [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] file è stato prodotto da un'entità, ovvero non affidabile o sconosciuta. Questo tipo di contenuto è noto come *contenuti esterni*ed entrambe <xref:System.Windows.Controls.Frame> e <xref:System.Windows.Navigation.NavigationWindow> può essere configurato per isolarlo durante l'esplorazione. Isolamento viene ottenuto impostando il **SandboxExternalContent** la proprietà su true, come illustrato negli esempi seguenti per <xref:System.Windows.Controls.Frame> e <xref:System.Windows.Navigation.NavigationWindow>:  
  
 [!code-xaml[SecurityOverviewSnippets#FrameMARKUP](../../../samples/snippets/csharp/VS_Snippets_Wpf/SecurityOverviewSnippets/CS/Window2.xaml#framemarkup)]  
  
 [!code-xaml[SecurityOverviewSnippets#NavigationWindowMARKUP](../../../samples/snippets/csharp/VS_Snippets_Wpf/SecurityOverviewSnippets/CS/Window1.xaml#navigationwindowmarkup)]  
  
 Con questa impostazione, il contenuto esterno verrà caricato in un processo separato da quello in cui è ospitata l'applicazione. Questo processo è limitato al set di autorizzazioni predefinito dell'area Internet e in questo modo l'area viene isolata efficacemente dall'applicazione host e dal computer client.  
  
> [!NOTE]
>  Anche se navigazione loose [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] file provenienti da una un' <xref:System.Windows.Navigation.NavigationWindow> o <xref:System.Windows.Controls.Frame> nella versione autonoma di un'applicazione viene implementata basate sul browser WPF coinvolgendo il processo PresentationHost, infrastruttura che ospita il livello di sicurezza è leggermente inferiore rispetto a quando il contenuto viene caricato direttamente in Internet Explorer sul [!INCLUDE[wiprlhext](../../../includes/wiprlhext-md.md)] e [!INCLUDE[win7](../../../includes/win7-md.md)] (che potrebbe essere ancora tramite PresentationHost). Ciò si verifica in quanto un'applicazione WPF autonoma che usa un Web browser non fornisce la funzionalità di sicurezza di modalità protetta aggiuntiva di Internet Explorer.  
  
<a name="BestPractices"></a>   
## <a name="resources-for-developing-wpf-applications-that-promote-security"></a>Risorse per lo sviluppo di applicazioni WPF che garantiscano la sicurezza  
 Di seguito sono segnalate altre risorse utili per sviluppare [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] le applicazioni che garantiscano la sicurezza:  
  
|Area|Risorsa|  
|----------|--------------|  
|Codice gestito|[Patterns and Practices Security Guidance for Applications](https://go.microsoft.com/fwlink/?LinkId=117426) (Modelli e indicazioni sulla sicurezza per applicazioni)|  
|[!INCLUDE[TLA2#tla_cas](../../../includes/tla2sharptla-cas-md.md)]|[Sicurezza dall'accesso di codice](../../../docs/framework/misc/code-access-security.md)|  
|[!INCLUDE[TLA2#tla_clickonce](../../../includes/tla2sharptla-clickonce-md.md)]|[Sicurezza e distribuzione di ClickOnce](/visualstudio/deployment/clickonce-security-and-deployment)|  
|[!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)]|[Sicurezza con attendibilità parziale in WPF](../../../docs/framework/wpf/wpf-partial-trust-security.md)|  
  
## <a name="see-also"></a>Vedere anche  
 [Sicurezza con attendibilità parziale in WPF](../../../docs/framework/wpf/wpf-partial-trust-security.md)  
 [Strategia di sicurezza di WPF - Sicurezza della piattaforma](../../../docs/framework/wpf/wpf-security-strategy-platform-security.md)  
 [Strategia di sicurezza WPF - Progettazione della sicurezza](../../../docs/framework/wpf/wpf-security-strategy-security-engineering.md)  
 [Patterns and Practices Security Guidance for Applications](https://go.microsoft.com/fwlink/?LinkId=117426) (Modelli e indicazioni sulla sicurezza per applicazioni)  
 [Sicurezza dall'accesso di codice](../../../docs/framework/misc/code-access-security.md)  
 [Sicurezza e distribuzione di ClickOnce](/visualstudio/deployment/clickonce-security-and-deployment)  
 [Cenni preliminari su XAML (WPF)](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)
