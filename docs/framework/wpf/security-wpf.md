---
title: Security
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
ms.openlocfilehash: e0a56dcbf8d151fcb0d4f6271ecba15c0ff955a4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174615"
---
# <a name="security-wpf"></a>Sicurezza (WPF)
<a name="introduction"></a>Quando si sviluppano applicazioni autonome e ospitate da browser di Windows Presentation Foundation (WPF), è necessario considerare il modello di sicurezza. WpfWPF le applicazioni autonome vengono eseguite con autorizzazioni senza restrizioni (set di autorizzazioni**CAS FullTrust),** sia che vengano distribuite tramite Windows Installer (MSI), XCopy o ClickOnce.WPF standalone applications execute with unrestricted permissions ( CAS FullTrust permission set), whether deployed using Windows Installer (.msi), XCopy, or ClickOnce. Non è supportata la distribuzione di applicazioni WPF autonome e parzialmente attendibili con ClickOnce. Tuttavia, un'applicazione host con attendibilità <xref:System.AppDomain> totale può creare un'attendibilità parziale utilizzando il modello di componente aggiuntivo .NET Framework. Per ulteriori informazioni, vedere [Cenni preliminari sui componenti aggiuntivi WPF](./app-development/wpf-add-ins-overview.md).  
  
 Le applicazioni WPF ospitate da browser sono ospitate da Windows Internet Explorer o Firefox [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] e possono essere applicazioni browser XAML (XBAP) o documenti persi per ulteriori informazioni, vedere [Cenni preliminari](./app-development/wpf-xaml-browser-applications-overview.md)sulle applicazioni browser XAML WPF .  
  
 Le applicazioni WPF ospitate da browser vengono eseguite all'interno di una sandbox di sicurezza con attendibilità parziale, per impostazione predefinita, limitata al set di autorizzazioni dell'area**Internet** CAS predefinito. In questo modo si isolano in modo efficace le applicazioni ospitate da browser WPF dal computer client nello stesso modo in cui ci si aspetta che le applicazioni Web tipiche siano isolate. Un'applicazione XBAP può elevare il livello di privilegi fino ad Attendibilità totale a seconda dell'area di sicurezza dell'URL di distribuzione e della configurazione di sicurezza del client. Per altre informazioni, vedere [Sicurezza con attendibilità parziale in WPF](wpf-partial-trust-security.md).  
  
 In questo argomento viene illustrato il modello di sicurezza per le applicazioni autonome e ospitate da browser di Windows Presentation Foundation (WPF).  
  
 In questo argomento sono incluse le sezioni seguenti:  
  
- [Navigazione sicura](#SafeTopLevelNavigation)  
  
- [Impostazioni di sicurezza del software per l'esplorazione Web](#InternetExplorerSecuritySettings)  
  
- [Controllo WebBrowser e controlli della funzionalità](#webbrowser_control_and_feature_controls)  
  
- [Disabilitazione degli assembly APTCA per le applicazioni client parzialmente attendibili](#APTCA)  
  
- [Comportamento della sandbox per i file XAML separati](#LooseContentSandboxing)  
  
- [Risorse per lo sviluppo di applicazioni WPF che garantiscano la sicurezza](#BestPractices)  
  
<a name="SafeTopLevelNavigation"></a>
## <a name="safe-navigation"></a>Navigazione sicura  
 Per le applicazioni XBAP, WPFWPF distingue due tipi di navigazione: applicazione e browser.  
  
 La *navigazione tramite applicazione* consiste nel passaggio tra elementi di contenuto all'interno di un'applicazione ospitata da un browser. La *navigazione tramite browser* implica la modifica del contenuto e dell'URL del percorso del browser stesso. La relazione tra la navigazione dell'applicazione (in genere XAML) e lo spostamento nel browser (in genere HTML) è illustrata nella figura seguente:The relationship between application navigation (typically XAML) and browser navigation (typically HTML) is shown in the following illustration:
  
 ![Relazione tra l'esplorazione dell'applicazione e la navigazione nel browser.](./media/security-wpf/application-browser-navigation-relationship.png)  
  
 Il tipo di contenuto considerato sicuro per un'applicazione XBAP è determinato principalmente dall'utilizzo della navigazione dell'applicazione o del browser.  
  
<a name="Application_Navigation_Security"></a>
### <a name="application-navigation-security"></a>Sicurezza della navigazione tramite applicazione  
 L'esplorazione dell'applicazione è considerata sicura se può essere identificata con un URI di tipo pack, che supporta quattro tipi di contenuto:Application navigation is considered safe if it can be identified with a pack URI, which supports four types of content:  
  
|Content Type|Descrizione|Esempio di URI|  
|------------------|-----------------|-----------------|  
|Risorsa|File aggiunti a un progetto con un tipo di **compilazione Risorsa**.|`pack://application:,,,/MyResourceFile.xaml`|  
|Contenuto|File aggiunti a un progetto con un tipo di **compilazione Contenuto**.|`pack://application:,,,/MyContentFile.xaml`|  
|Sito di origine|File aggiunti a un progetto con un tipo di **compilazione None**.|`pack://siteoforigin:,,,/MySiteOfOriginFile.xaml`|  
|Codice dell'applicazione|Risorse XAML che dispongono di code-behind compilato.<br /><br /> -oppure-<br /><br /> File XAML aggiunti a un progetto con un tipo di **compilazione Page**.|`pack://application:,,,/MyResourceFile` `.xaml`|  
  
> [!NOTE]
> Per altre informazioni sui file di dati dell'applicazione e sugli URI di tipo pack, vedere File di [dati, contenuto e risorse dell'applicazione WPF.](./app-development/wpf-application-resource-content-and-data-files.md)  
  
 La navigazione dei file di questi tipi di contenuto è possibile sia da parte dell'utente che a livello di codice:  
  
- **Navigazione dell'utente**. L'utente si sposta <xref:System.Windows.Documents.Hyperlink> facendo clic su un elemento.  
  
- **Navigazione a livello di codice**. L'applicazione si sposta senza coinvolgere l'utente, ad esempio impostando la <xref:System.Windows.Navigation.NavigationWindow.Source%2A?displayProperty=nameWithType> proprietà .  
  
<a name="Browser_Navigation_Security"></a>
### <a name="browser-navigation-security"></a>Sicurezza della navigazione tramite browser  
 La navigazione tramite browser è considerata sicura solo nelle condizioni seguenti:  
  
- **Navigazione dell'utente**. L'utente si sposta <xref:System.Windows.Documents.Hyperlink> facendo clic su <xref:System.Windows.Navigation.NavigationWindow>un elemento <xref:System.Windows.Controls.Frame>che si trova all'interno del principale , non in un oggetto nidificato.  
  
- **Zona**. Il contenuto per la navigazione si trova nell'area Internet o Intranet locale.  
  
- **Protocollo**. Il protocollo utilizzato è **http**, **https**, **file**o **mailto**.  
  
 Se un'applicazione XBAP tenta di passare al contenuto in <xref:System.Security.SecurityException> modo non conforme a queste condizioni, viene generata un'eccezione .  
  
<a name="InternetExplorerSecuritySettings"></a>
## <a name="web-browsing-software-security-settings"></a>Impostazioni di sicurezza del software per l'esplorazione Web  
 Le impostazioni di sicurezza nel computer in uso determinano l'accesso garantito a qualsiasi software per l'esplorazione Web. Il software di esplorazione del Web include qualsiasi applicazione o componente che utilizza le API [WinINet](/windows/win32/wininet/portal) o [UrlMon,](https://docs.microsoft.com/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa767916(v=vs.85)) inclusi Internet Explorer e PresentationHost.exe.  
  
 Internet Explorer fornisce un meccanismo mediante il quale è possibile configurare la funzionalità che può essere eseguita da o da Internet Explorer, inclusi i seguenti:  
  
- Componenti basati su .NET Framework  
  
- Controlli e plug-in ActiveX  
  
- Download  
  
- Scripting  
  
- Autenticazione dell'utente  
  
 L'insieme di funzionalità che possono essere protette in questo modo viene configurato in base all'area per le aree **Internet**, **Intranet**, **Siti attendibili**e Siti **con restrizioni.** La procedura seguente descrive come configurare le impostazioni di sicurezza:  
  
1. Aprire il **Pannello di controllo**.  
  
2. Fare clic su **Rete e Internet** e quindi su Opzioni **Internet**.  
  
     Viene visualizzata la finestra di dialogo Opzioni Internet.  
  
3. Nella scheda **Sicurezza** selezionare l'area per cui configurare le impostazioni di sicurezza.  
  
4. Fare clic sul pulsante **Livello personalizzato.**  
  
     Viene visualizzata la finestra di dialogo Impostazioni di **protezione** ed è possibile configurare le impostazioni di sicurezza per l'area selezionata.  
  
     ![Screenshot che mostra la finestra di dialogo Impostazioni di sicurezza.](./media/security-wpf/windows-presentation-foundation-security-settings.png)  
  
> [!NOTE]
> È anche possibile passare alla finestra di dialogo Opzioni Internet tramite Internet Explorer. Fare clic su **Strumenti** e quindi su **Opzioni Internet**.  
  
 A partire da Windows Internet Explorer 7, sono incluse le seguenti impostazioni di protezione specifiche per .NET Framework:  
  
- **XAML libero**. Controlla se Internet Explorer può [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] individuare e liberare i file. (opzioni Abilita, Disabilita e Chiedi conferma).  
  
- **Applicazioni browser XAML**. Controlla se Internet Explorer può individuare ed eseguire applicazioni XBAP. (opzioni Abilita, Disabilita e Chiedi conferma).  
  
 Per impostazione predefinita, queste impostazioni sono tutte abilitate per le aree **Internet**, **Intranet locale**e **Siti attendibili** e disabilitate per l'area Siti **con restrizioni.**  
  
<a name="Security_Settings_for_IE6_and_Below"></a>
### <a name="security-related-wpf-registry-settings"></a>Impostazioni del Registro di sistema WPF correlate alla sicurezza  
 Oltre alle impostazioni di sicurezza disponibili tramite Opzioni Internet, sono disponibili i seguenti valori del Registro di sistema per bloccare in modo selettivo alcune funzionalità WPF relative alla sicurezza. I valori sono definiti nella chiave seguente:  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\Windows Presentation Foundation\Features`  
  
 La tabella seguente elenca i valori che è possibile impostare.  
  
|Nome del valore|Tipo di valore|Dati valore|  
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
 Il <xref:System.Windows.Controls.WebBrowser> controllo WPFWPF può essere utilizzato per ospitare contenuto Web. Il <xref:System.Windows.Controls.WebBrowser> controllo WPFwpf esegue il wrapping del controllo ActiveX WebBrowser sottostante. WPFWPF fornisce un supporto per la protezione <xref:System.Windows.Controls.WebBrowser> dell'applicazione quando si utilizza il controllo WPFWPF per ospitare contenuto Web non attendibile. Tuttavia, alcune funzionalità di sicurezza devono <xref:System.Windows.Controls.WebBrowser> essere applicate direttamente dalle applicazioni che utilizzano il controllo. Per ulteriori informazioni sul controllo ActiveX WebBrowser, vedere [Cenni preliminari ed esercitazioni](https://docs.microsoft.com/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752041(v=vs.85))sul controllo WebBrowser .  
  
> [!NOTE]
> Questa sezione si <xref:System.Windows.Controls.Frame> applica anche al <xref:System.Windows.Controls.WebBrowser> controllo poiché utilizza l'oggetto per passare al contenuto HTML.  
  
 Se il <xref:System.Windows.Controls.WebBrowser> controllo WPFWPF viene utilizzato per ospitare contenuto Web <xref:System.AppDomain> non attendibile, l'applicazione deve usare un'attendibilità parziale per isolare il codice dell'applicazione da codice di script HTML potenzialmente dannoso. Ciò è particolarmente vero se l'applicazione interagisce <xref:System.Windows.Controls.WebBrowser.InvokeScript%2A> con lo <xref:System.Windows.Controls.WebBrowser.ObjectForScripting%2A> script ospitato utilizzando il metodo e la proprietà . Per ulteriori informazioni, vedere [Cenni preliminari sui componenti aggiuntivi WPF](./app-development/wpf-add-ins-overview.md).  
  
 Se l'applicazione <xref:System.Windows.Controls.WebBrowser> usa il controllo WPFWPF, un altro modo per aumentare la sicurezza e ridurre gli attacchi consiste nell'abilitare i controlli delle funzionalità di Internet Explorer.If your application uses the WPFWPF control, another way to increase security and mitigate attacks is to enable Internet Explorer feature controls. I controlli delle funzionalità sono aggiunte a Internet Explorer che consentono agli amministratori e agli sviluppatori <xref:System.Windows.Controls.WebBrowser> di configurare le funzionalità di Internet Explorer e le applicazioni che ospitano il controllo ActiveX WebBrowser, di cui il controllo WPF esegue il wrapping. I controlli funzionalità possono essere configurati utilizzando la funzione [CoInternetSetFeatureEnabled](https://docs.microsoft.com/previous-versions/windows/internet-explorer/ie-developer/platform-apis/ms537168(v=vs.85)) o modificando i valori nel Registro di sistema. Per ulteriori informazioni sui controlli delle entità geografiche, vedere Introduzione ai controlli [delle entità geografiche](https://docs.microsoft.com/previous-versions/windows/internet-explorer/ie-developer/platform-apis/ms537184(v=vs.85)) e [Ai controlli delle funzionalità Internet](https://docs.microsoft.com/previous-versions/windows/internet-explorer/ie-developer/general-info/ee330720(v=vs.85)).  
  
 Se si sviluppa un'applicazione WPF autonoma che usa il controllo WPFWPF, <xref:System.Windows.Controls.WebBrowser> WPFWPF abilita automaticamente i controlli funzionalità seguenti per l'applicazione.  
  
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
  
 I controlli delle funzionalità vengono applicati dal processo che crea un'istanza dell'oggetto ActiveX WebBrowser. Pertanto, se si crea un'applicazione autonoma in grado di passare a contenuto non attendibile, è assolutamente opportuno abilitare controlli della funzionalità aggiuntivi.  
  
> [!NOTE]
> Questa indicazione è basata sui suggerimenti generali per la sicurezza host MSHTML e SHDOCVW. Per ulteriori informazioni, vedere le domande frequenti su [MSHTML Host Security: Parte I di II](https://msrc-blog.microsoft.com/2009/04/02/the-mshtml-host-security-faq-part-i-of-ii/) e [Domande frequenti sulla protezione host MSHTML: parte II di II](https://msrc-blog.microsoft.com/2009/04/03/the-mshtml-host-security-faq-part-ii-of-ii/).  
  
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
  
 Se si esegue un'applicazione browser XAML con attendibilità <xref:System.Windows.Controls.WebBrowser> parziale (XBAP) che include un controllo WPF in Windows Internet Explorer, WPF ospita il controllo ActiveX WebBrowser nello spazio degli indirizzi del processo di Internet Explorer. Poiché il controllo ActiveX WebBrowser è ospitato nel processo di Internet Explorer, tutti i controlli funzionalità per Internet Explorer sono abilitati anche per il controllo ActiveX WebBrowser.  
  
 Le applicazioni XBAP in esecuzione in Internet Explorer ottengono anche un livello di sicurezza aggiuntivo rispetto alle applicazioni autonome normali. Questa protezione aggiuntiva è perché Internet Explorer, e quindi il controllo ActiveX WebBrowser, viene eseguito in modalità protetta per impostazione predefinita in Windows Vista e Windows 7. Per ulteriori informazioni sulla modalità protetta, vedere [Informazioni e utilizzo della modalità protetta](https://docs.microsoft.com/previous-versions/windows/internet-explorer/ie-developer/)di Internet Explorer .  
  
> [!NOTE]
> Se si tenta di eseguire un'applicazione <xref:System.Windows.Controls.WebBrowser> XBAP che include un <xref:System.Security.SecurityException> controllo WPF in Firefox, mentre nell'area Internet verrà generata un'eccezione. Tale eccezione è determinata dai criteri di sicurezza WPF.  
  
<a name="APTCA"></a>
## <a name="disabling-aptca-assemblies-for-partially-trusted-client-applications"></a>Disabilitazione degli assembly APTCA per le applicazioni client parzialmente attendibili  
 Quando gli assembly gestiti vengono installati nella Global Assembly Cache (GAC), diventano completamente attendibili perché l'utente deve fornire l'autorizzazione esplicita per installarli. Dal momento che sono completamente attendibili, possono essere usati solo dalle applicazioni client gestite completamente attendibili. Per consentire alle applicazioni parzialmente attendibili di <xref:System.Security.AllowPartiallyTrustedCallersAttribute> utilizzarle, è necessario contrassegnarle con (APTCA). Solo gli assembly per cui il test di sicurezza per l'esecuzione ha dato come esito un'attendibilità parziale possono essere contrassegnati con questo attributo.  
  
 Tuttavia, è possibile che un assembly APTCA presenti un difetto di sicurezza dopo l'installazione nel GAC. Quando viene individuato un difetto nel sistema di sicurezza, gli editori dell'assembly possono creare un aggiornamento della sicurezza per risolvere il problema nelle installazioni esistenti e per proteggere le installazioni eseguite dopo l'individuazione del problema. Un'opzione per l'aggiornamento è la disinstallazione dell'assembly, anche se in questo modo può essere compromessa la funzionalità di altre applicazioni client completamente attendibili che usano l'assembly.  
  
 WPFWPF fornisce un meccanismo mediante il quale un assembly APTCA può essere disabilitato per XBAP parzialmente attendibili senza disinstallare l'assembly APTCA.  
  
 Per disabilitare un assembly APTCA, è necessario creare una chiave speciale del Registro di sistema:  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\policy\APTCA\<AssemblyFullName>, FileVersion=<AssemblyFileVersion>`  
  
 Di seguito viene riportato un esempio:  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\policy\APTCA\aptcagac, Version=1.0.0.0, Culture=neutral, PublicKeyToken=215e3ac809a0fea7, FileVersion=1.0.0.0`  
  
 Questa chiave definisce una voce per l'assembly APTCA. È anche necessario creare un valore di questa chiave che abiliti o disabiliti l'assembly. Di seguito sono riportati i dettagli del valore:  
  
- Nome valore: **APTCA_FLAG**.  
  
- Tipo di valore: **REG_DWORD**.  
  
- Dati valore: **1** per disabilitare; **0** per abilitare.  
  
 Se è necessario disabilitare un assembly per applicazioni client parzialmente attendibili, è possibile scrivere un aggiornamento per creare la chiave del Registro di sistema e il valore.  
  
> [!NOTE]
> Gli assembly .NET Framework di base non sono interessati dalla loro disabilitazione in questo modo perché sono necessari per l'esecuzione delle applicazioni gestite. Il supporto per la disabilitazione degli assembly APTCA è destinato principalmente alle applicazioni di terze parti.  
  
<a name="LooseContentSandboxing"></a>
## <a name="sandbox-behavior-for-loose-xaml-files"></a>Comportamento della sandbox per i file XAML separati  
 I [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] file sciolti sono file XAML di solo markup che non dipendono da alcun assembly code-behind, gestore eventi o assembly specifico dell'applicazione. Quando [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] i file sciolti vengono spostati direttamente dal browser, vengono caricati in una sandbox di sicurezza in base al set di autorizzazioni dell'area Internet predefinito.  
  
 Tuttavia, il comportamento di [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] sicurezza è diverso quando <xref:System.Windows.Navigation.NavigationWindow> <xref:System.Windows.Controls.Frame> i file separati vengono spostati da un o in un'applicazione autonoma.  
  
 In entrambi i [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] casi, il file loose che si sposta per ereditare le autorizzazioni dell'applicazione host. Tuttavia, questo comportamento potrebbe essere indesiderato dal [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] punto di vista della sicurezza, in particolare se un file non è stato prodotto da un'entità non attendibile o sconosciuta. Questo tipo di contenuto è noto <xref:System.Windows.Controls.Frame> <xref:System.Windows.Navigation.NavigationWindow> come *contenuto esterno*ed entrambi e può essere configurato per isolarlo quando ci si sposta. L'isolamento viene ottenuto impostando la proprietà **SandboxExternalContent** su <xref:System.Windows.Controls.Frame> <xref:System.Windows.Navigation.NavigationWindow>true, come illustrato negli esempi seguenti per e :  
  
 [!code-xaml[SecurityOverviewSnippets#FrameMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/SecurityOverviewSnippets/CS/Window2.xaml#framemarkup)]  
  
 [!code-xaml[SecurityOverviewSnippets#NavigationWindowMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/SecurityOverviewSnippets/CS/Window1.xaml#navigationwindowmarkup)]  
  
 Con questa impostazione, il contenuto esterno verrà caricato in un processo separato da quello in cui è ospitata l'applicazione. Questo processo è limitato al set di autorizzazioni predefinito dell'area Internet e in questo modo l'area viene isolata efficacemente dall'applicazione host e dal computer client.  
  
> [!NOTE]
> Anche se la [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] navigazione a <xref:System.Windows.Navigation.NavigationWindow> <xref:System.Windows.Controls.Frame> file persi da un'applicazione autonoma o in un'applicazione autonoma viene implementata in base all'infrastruttura di hosting del browser WPF, che coinvolge il processo PresentationHost, il livello di sicurezza è leggermente inferiore a quando il contenuto viene caricato direttamente in Internet Explorer in Windows Vista e Windows 7 (che sarebbe ancora tramite PresentationHost). Ciò si verifica in quanto un'applicazione WPF autonoma che usa un Web browser non fornisce la funzionalità di sicurezza di modalità protetta aggiuntiva di Internet Explorer.  
  
<a name="BestPractices"></a>
## <a name="resources-for-developing-wpf-applications-that-promote-security"></a>Risorse per lo sviluppo di applicazioni WPF che garantiscano la sicurezza  
 Di seguito sono riportate alcune risorse aggiuntive per sviluppare applicazioni WPFWPF che promuovono la sicurezza:The following are some additional resources to help develop WPF applications that promote security:  
  
|Area|Risorsa|  
|----------|--------------|  
|Codice gestito|[Patterns and Practices Security Guidance for Applications (Modelli e indicazioni sulla sicurezza per applicazioni)](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10))|  
|CAS|[Sicurezza dall'accesso di codiceCode Access Security](../misc/code-access-security.md)|  
|ClickOnce|[Sicurezza e distribuzione ClickOnceClickOnce Security and Deployment](/visualstudio/deployment/clickonce-security-and-deployment)|  
|WPF|[Sicurezza dell'attendibilità parziale WPFWPF Partial Trust Security](wpf-partial-trust-security.md)|  
  
## <a name="see-also"></a>Vedere anche

- [Sicurezza dell'attendibilità parziale WPFWPF Partial Trust Security](wpf-partial-trust-security.md)
- [Strategia di sicurezza di WPF - Sicurezza della piattaforma](wpf-security-strategy-platform-security.md)
- [Strategia di sicurezza WPF - Progettazione della sicurezza](wpf-security-strategy-security-engineering.md)
- [Patterns and Practices Security Guidance for Applications (Modelli e indicazioni sulla sicurezza per applicazioni)](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10))
- [Sicurezza dall'accesso di codiceCode Access Security](../misc/code-access-security.md)
- [Sicurezza e distribuzione ClickOnceClickOnce Security and Deployment](/visualstudio/deployment/clickonce-security-and-deployment)
- [Panoramica di XAML (WPF)](../../desktop-wpf/fundamentals/xaml.md)
