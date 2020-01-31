---
title: Sicurezza -
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
ms.openlocfilehash: a49634fd955b0dc1f4cac5c785d49c24d16bbc60
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868044"
---
# <a name="security-wpf"></a>Sicurezza (WPF)
<a name="introduction"></a>Quando si sviluppano applicazioni autonome e ospitate nel browser di Windows Presentation Foundation (WPF), è necessario prendere in considerazione il modello di sicurezza. Le applicazioni WPF autonome vengono eseguite con autorizzazioni senza restrizioni (set di autorizzazioni CAS**FullTrust** ), se distribuite mediante Windows Installer (MSI), XCOPY o ClickOnce. Non è supportata la distribuzione di applicazioni WPF autonome e parzialmente attendibili con ClickOnce. Tuttavia, un'applicazione host con attendibilità totale può creare una <xref:System.AppDomain> parzialmente attendibile usando il modello del componente aggiuntivo .NET Framework. Per altre informazioni, vedere [Cenni preliminari sui componenti](./app-development/wpf-add-ins-overview.md)aggiuntivi di WPF.  
  
 Le applicazioni WPF ospitate da browser sono ospitate da Windows Internet Explorer o Firefox e possono essere applicazioni browser XAML (XBAP) o documenti separati [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] per altre informazioni, vedere [Cenni preliminari sulle applicazioni browser XAML di WPF](./app-development/wpf-xaml-browser-applications-overview.md).  
  
 Per impostazione predefinita, le applicazioni WPF ospitate da browser vengono eseguite in una sandbox di sicurezza con attendibilità parziale, che è limitata al set di autorizzazioni predefinito dell'area**Internet** CAS. Questo consente di isolare in modo efficace le applicazioni ospitate da browser WPF dal computer client nello stesso modo in cui si prevede che le applicazioni Web tipiche siano isolate. Un'applicazione XBAP può elevare il livello di privilegi fino ad Attendibilità totale a seconda dell'area di sicurezza dell'URL di distribuzione e della configurazione di sicurezza del client. Per altre informazioni, vedere [Sicurezza con attendibilità parziale in WPF](wpf-partial-trust-security.md).  
  
 In questo argomento viene illustrato il modello di sicurezza per le applicazioni autonome Windows Presentation Foundation (WPF) e ospitate da browser.  
  
 Di seguito sono elencate le diverse sezioni di questo argomento:  
  
- [Navigazione sicura](#SafeTopLevelNavigation)  
  
- [Impostazioni di sicurezza del software per l'esplorazione Web](#InternetExplorerSecuritySettings)  
  
- [Controllo WebBrowser e controlli della funzionalità](#webbrowser_control_and_feature_controls)  
  
- [Disabilitazione degli assembly APTCA per le applicazioni client parzialmente attendibili](#APTCA)  
  
- [Comportamento della sandbox per i file XAML separati](#LooseContentSandboxing)  
  
- [Risorse per lo sviluppo di applicazioni WPF che garantiscano la sicurezza](#BestPractices)  
  
<a name="SafeTopLevelNavigation"></a>   
## <a name="safe-navigation"></a>Navigazione sicura  
 Per le applicazioni XBAP, WPF distingue due tipi di navigazione: applicazione e browser.  
  
 La *navigazione tramite applicazione* consiste nel passaggio tra elementi di contenuto all'interno di un'applicazione ospitata da un browser. La *navigazione tramite browser* implica la modifica del contenuto e dell'URL del percorso del browser stesso. Nella figura seguente è illustrata la relazione tra l'esplorazione dell'applicazione (in genere XAML) e la navigazione del browser (in genere HTML):
  
 ![Relazione tra esplorazione dell'applicazione e navigazione del browser.](./media/security-wpf/application-browser-navigation-relationship.png)  
  
 Il tipo di contenuto considerato sicuro per l'esplorazione di un'applicazione XBAP è determinato principalmente dal fatto che venga utilizzata la navigazione dell'applicazione o la navigazione del browser.  
  
<a name="Application_Navigation_Security"></a>   
### <a name="application-navigation-security"></a>Sicurezza della navigazione tramite applicazione  
 La navigazione dell'applicazione è considerata sicura se può essere identificata con un URI di tipo pack, che supporta quattro tipi di contenuto:  
  
|Tipo di contenuto|Descrizione|Esempio di URI|  
|------------------|-----------------|-----------------|  
|Risorsa|File aggiunti a un progetto con un tipo di compilazione **risorsa**.|`pack://application:,,,/MyResourceFile.xaml`|  
|Contenuto|File aggiunti a un progetto con un tipo di compilazione di **contenuto**.|`pack://application:,,,/MyContentFile.xaml`|  
|Sito di origine|File aggiunti a un progetto con un tipo di compilazione **None**.|`pack://siteoforigin:,,,/MySiteOfOriginFile.xaml`|  
|Codice dell'applicazione|Risorse XAML che dispongono di code-behind compilato.<br /><br /> oppure<br /><br /> File XAML aggiunti a un progetto con un tipo di compilazione **Page**.|`pack://application:,,,/MyResourceFile` `.xaml`|  
  
> [!NOTE]
> Per ulteriori informazioni sui file di dati dell'applicazione e sugli URI di pacchetto, vedere file di dati e di [risorse dell'applicazione WPF](./app-development/wpf-application-resource-content-and-data-files.md).  
  
 La navigazione dei file di questi tipi di contenuto è possibile sia da parte dell'utente che a livello di codice:  
  
- **Navigazione dell'utente**. L'utente si sposta facendo clic su un elemento <xref:System.Windows.Documents.Hyperlink>.  
  
- **Navigazione a livello di codice**. L'applicazione si sposta senza coinvolgere l'utente, ad esempio impostando la proprietà <xref:System.Windows.Navigation.NavigationWindow.Source%2A?displayProperty=nameWithType>.  
  
<a name="Browser_Navigation_Security"></a>   
### <a name="browser-navigation-security"></a>Sicurezza della navigazione tramite browser  
 La navigazione tramite browser è considerata sicura solo nelle condizioni seguenti:  
  
- **Navigazione dell'utente**. L'utente si sposta facendo clic su un elemento <xref:System.Windows.Documents.Hyperlink> che si trova all'interno del <xref:System.Windows.Navigation.NavigationWindow>principale, non in un <xref:System.Windows.Controls.Frame>annidato.  
  
- **Area**. Il contenuto per la navigazione si trova nell'area Internet o Intranet locale.  
  
- **Protocollo**. Il protocollo utilizzato è **http**, **https**, **file**o **mailto**.  
  
 Se un'applicazione XBAP tenta di passare al contenuto in modo non conforme a tali condizioni, viene generata un'<xref:System.Security.SecurityException>.  
  
<a name="InternetExplorerSecuritySettings"></a>   
## <a name="web-browsing-software-security-settings"></a>Impostazioni di sicurezza del software per l'esplorazione Web  
 Le impostazioni di sicurezza nel computer in uso determinano l'accesso garantito a qualsiasi software per l'esplorazione Web. Il software di esplorazione Web include qualsiasi applicazione o componente che utilizza le API [WinInet](/windows/win32/wininet/portal) o [Urlmon](https://docs.microsoft.com/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa767916(v=vs.85)) , inclusi Internet Explorer e PresentationHost. exe.  
  
 Internet Explorer fornisce un meccanismo mediante il quale è possibile configurare la funzionalità che può essere eseguita da o da Internet Explorer, incluse le seguenti:  
  
- Componenti .NET Framework-Reliant  
  
- Controlli e plug-in ActiveX  
  
- Download  
  
- Scripting  
  
- Autenticazione utente  
  
 La raccolta di funzionalità che è possibile proteggere in questo modo viene configurata in base alla zona per le zone **Internet**, **Intranet**, **siti attendibili**e **siti con restrizioni** . La procedura seguente descrive come configurare le impostazioni di sicurezza:  
  
1. Aprire il **Pannello di controllo**.  
  
2. Fare clic su **rete e Internet** e quindi su **Opzioni Internet**.  
  
     Viene visualizzata la finestra di dialogo Opzioni Internet.  
  
3. Nella scheda **sicurezza** selezionare la zona per cui configurare le impostazioni di sicurezza.  
  
4. Fare clic sul pulsante **livello personalizzato** .  
  
     Verrà visualizzata la finestra di dialogo **impostazioni di sicurezza** in cui è possibile configurare le impostazioni di sicurezza per la zona selezionata.  
  
     ![Screenshot che mostra la finestra di dialogo Impostazioni di sicurezza.](./media/security-wpf/windows-presentation-foundation-security-settings.png)  
  
> [!NOTE]
> È anche possibile passare alla finestra di dialogo Opzioni Internet tramite Internet Explorer. Fare clic su **strumenti** e quindi su **Opzioni Internet**.  
  
 A partire da Windows Internet Explorer 7, sono incluse le seguenti impostazioni di sicurezza specifiche per .NET Framework:  
  
- **XAML libero**. Controlla se Internet Explorer è in grado di accedere ai file [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] e perderli. (opzioni Abilita, Disabilita e Chiedi conferma).  
  
- **Applicazioni browser XAML**. Controlla se Internet Explorer può accedere ed eseguire le applicazioni XBAP. (opzioni Abilita, Disabilita e Chiedi conferma).  
  
 Per impostazione predefinita, queste impostazioni sono tutte abilitate per le zone **Internet**, **Intranet locale**e **siti attendibili** e disabilitate per l'area **siti con restrizioni** .  
  
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
 Il controllo <xref:System.Windows.Controls.WebBrowser> WPF può essere utilizzato per ospitare contenuto Web. Il controllo <xref:System.Windows.Controls.WebBrowser> WPF esegue il wrapping del controllo ActiveX WebBrowser sottostante. WPF fornisce supporto per la protezione dell'applicazione quando si usa il controllo WPF <xref:System.Windows.Controls.WebBrowser> per ospitare contenuto Web non attendibile. Tuttavia, alcune funzionalità di sicurezza devono essere applicate direttamente dalle applicazioni utilizzando il controllo <xref:System.Windows.Controls.WebBrowser>. Per ulteriori informazioni sul controllo ActiveX WebBrowser, vedere [Panoramica del controllo WebBrowser ed esercitazioni](https://docs.microsoft.com/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752041(v=vs.85)).  
  
> [!NOTE]
> Questa sezione si applica anche al controllo <xref:System.Windows.Controls.Frame> perché usa il <xref:System.Windows.Controls.WebBrowser> per passare al contenuto HTML.  
  
 Se il controllo WPF <xref:System.Windows.Controls.WebBrowser> viene utilizzato per ospitare contenuto Web non attendibile, l'applicazione deve utilizzare un <xref:System.AppDomain> parzialmente attendibile per isolare il codice dell'applicazione da codice script HTML potenzialmente dannoso. Ciò è particolarmente vero se l'applicazione sta interagendo con lo script ospitato usando il metodo <xref:System.Windows.Controls.WebBrowser.InvokeScript%2A> e la proprietà <xref:System.Windows.Controls.WebBrowser.ObjectForScripting%2A>. Per altre informazioni, vedere [Cenni preliminari sui componenti](./app-development/wpf-add-ins-overview.md)aggiuntivi di WPF.  
  
 Se l'applicazione usa il controllo WPF <xref:System.Windows.Controls.WebBrowser>, un altro modo per aumentare la sicurezza e mitigare gli attacchi consiste nell'abilitare i controlli delle funzionalità di Internet Explorer. I controlli delle funzionalità sono aggiunte a Internet Explorer che consentono agli amministratori e agli sviluppatori di configurare le funzionalità di Internet Explorer e delle applicazioni che ospitano il controllo ActiveX WebBrowser, a cui viene eseguito il wrapping del controllo WPF <xref:System.Windows.Controls.WebBrowser>. I controlli funzionalità possono essere configurati tramite la funzione [CoInternetSetFeatureEnabled](https://docs.microsoft.com/previous-versions/windows/internet-explorer/ie-developer/platform-apis/ms537168(v=vs.85)) o modificando i valori nel registro di sistema. Per altre informazioni sui controlli delle funzionalità, vedere [Introduzione ai controlli delle funzionalità e ai](https://docs.microsoft.com/previous-versions/windows/internet-explorer/ie-developer/platform-apis/ms537184(v=vs.85)) controlli delle [funzionalità Internet](https://docs.microsoft.com/previous-versions/windows/internet-explorer/ie-developer/general-info/ee330720(v=vs.85)).  
  
 Se si sviluppa un'applicazione WPF autonoma che usa il controllo WPF <xref:System.Windows.Controls.WebBrowser>, WPF abilita automaticamente i controlli di funzionalità seguenti per l'applicazione.  
  
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
> Questa indicazione è basata sui suggerimenti generali per la sicurezza host MSHTML e SHDOCVW. Per ulteriori informazioni, vedere [le domande frequenti sulla sicurezza dell'host MSHTML: parte i di II](https://msrc-blog.microsoft.com/2009/04/02/the-mshtml-host-security-faq-part-i-of-ii/) e [domande frequenti sulla sicurezza dell'host MSHTML: parte II di II](https://msrc-blog.microsoft.com/2009/04/03/the-mshtml-host-security-faq-part-ii-of-ii/).  
  
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
  
 Se si esegue un'applicazione browser XAML (XBAP) parzialmente attendibile che include un controllo WPF <xref:System.Windows.Controls.WebBrowser> in Windows Internet Explorer, WPF ospita il controllo ActiveX WebBrowser nello spazio degli indirizzi del processo di Internet Explorer. Poiché il controllo ActiveX WebBrowser è ospitato nel processo di Internet Explorer, tutti i controlli delle funzionalità per Internet Explorer sono abilitati anche per il controllo ActiveX WebBrowser.  
  
 Le applicazioni XBAP in esecuzione in Internet Explorer ottengono anche un livello di sicurezza aggiuntivo rispetto alle applicazioni autonome normali. Questa protezione aggiuntiva è dovuta al fatto che Internet Explorer, e pertanto il controllo ActiveX WebBrowser, viene eseguito in modalità protetta per impostazione predefinita in Windows Vista e Windows 7. Per ulteriori informazioni sulla modalità protetta, vedere [Understanding and working in Protected Mode Internet Explorer](https://docs.microsoft.com/previous-versions/windows/internet-explorer/ie-developer/).  
  
> [!NOTE]
> Se si tenta di eseguire un'applicazione XBAP che include un controllo WPF <xref:System.Windows.Controls.WebBrowser> in Firefox, mentre nell'area Internet verrà generata una <xref:System.Security.SecurityException>. Tale eccezione è determinata dai criteri di sicurezza WPF.  
  
<a name="APTCA"></a>   
## <a name="disabling-aptca-assemblies-for-partially-trusted-client-applications"></a>Disabilitazione degli assembly APTCA per le applicazioni client parzialmente attendibili  
 Quando gli assembly gestiti vengono installati nel Global Assembly Cache (GAC), diventano completamente attendibili perché l'utente deve fornire autorizzazioni esplicite per installarli. Dal momento che sono completamente attendibili, possono essere usati solo dalle applicazioni client gestite completamente attendibili. Per consentire l'uso di applicazioni parzialmente attendibili, è necessario contrassegnarle con il <xref:System.Security.AllowPartiallyTrustedCallersAttribute> (APTCA). Solo gli assembly per cui il test di sicurezza per l'esecuzione ha dato come esito un'attendibilità parziale possono essere contrassegnati con questo attributo.  
  
 Tuttavia, un assembly APTCA può presentare un difetto di sicurezza dopo l'installazione nella GAC. Quando viene individuato un difetto nel sistema di sicurezza, gli editori dell'assembly possono creare un aggiornamento della sicurezza per risolvere il problema nelle installazioni esistenti e per proteggere le installazioni eseguite dopo l'individuazione del problema. Un'opzione per l'aggiornamento è la disinstallazione dell'assembly, anche se in questo modo può essere compromessa la funzionalità di altre applicazioni client completamente attendibili che usano l'assembly.  
  
 WPF fornisce un meccanismo mediante il quale è possibile disabilitare un assembly APTCA per le applicazioni XBAP parzialmente attendibili senza disinstallare l'assembly APTCA.  
  
 Per disabilitare un assembly APTCA, è necessario creare una chiave speciale del Registro di sistema:  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\policy\APTCA\<AssemblyFullName>, FileVersion=<AssemblyFileVersion>`  
  
 Di seguito viene riportato un esempio:  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\policy\APTCA\aptcagac, Version=1.0.0.0, Culture=neutral, PublicKeyToken=215e3ac809a0fea7, FileVersion=1.0.0.0`  
  
 Questa chiave definisce una voce per l'assembly APTCA. È anche necessario creare un valore di questa chiave che abiliti o disabiliti l'assembly. Di seguito sono riportati i dettagli del valore:  
  
- Nome valore: **APTCA_FLAG**.  
  
- Tipo di valore: **REG_DWORD**.  
  
- Dati valore: **1** da disabilitare; **0** per abilitare.  
  
 Se è necessario disabilitare un assembly per applicazioni client parzialmente attendibili, è possibile scrivere un aggiornamento per creare la chiave del Registro di sistema e il valore.  
  
> [!NOTE]
> Gli assembly di base .NET Framework non sono interessati dalla disabilitazione in questo modo perché sono necessari per l'esecuzione delle applicazioni gestite. Il supporto per la disabilitazione degli assembly APTCA è destinato principalmente alle applicazioni di terze parti.  
  
<a name="LooseContentSandboxing"></a>   
## <a name="sandbox-behavior-for-loose-xaml-files"></a>Comportamento della sandbox per i file XAML separati  
 I file [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] separati sono file XAML di solo markup che non dipendono da alcun code-behind, da un gestore eventi o da un assembly specifico dell'applicazione. Quando si passa da un file [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] all'altra direttamente dal browser, questi vengono caricati in una sandbox di sicurezza in base al set di autorizzazioni predefinito dell'area Internet.  
  
 Tuttavia, il comportamento di sicurezza è diverso [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] quando si passa da un <xref:System.Windows.Navigation.NavigationWindow> o <xref:System.Windows.Controls.Frame> in un'applicazione autonoma.  
  
 In entrambi i casi, il file di [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] separato che è stato spostato per ereditare le autorizzazioni della relativa applicazione host. Questo comportamento, tuttavia, può essere indesiderato dal punto di vista della sicurezza, in particolare se un file di [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] separato è stato prodotto da un'entità non attendibile o sconosciuta. Questo tipo di contenuto è noto come *contenuto esterno*ed è possibile configurare sia <xref:System.Windows.Controls.Frame> che <xref:System.Windows.Navigation.NavigationWindow> per isolarlo quando ci si sposta. Per ottenere l'isolamento, impostare la proprietà **SandboxExternalContent** su true, come illustrato negli esempi seguenti per <xref:System.Windows.Controls.Frame> e <xref:System.Windows.Navigation.NavigationWindow>:  
  
 [!code-xaml[SecurityOverviewSnippets#FrameMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/SecurityOverviewSnippets/CS/Window2.xaml#framemarkup)]  
  
 [!code-xaml[SecurityOverviewSnippets#NavigationWindowMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/SecurityOverviewSnippets/CS/Window1.xaml#navigationwindowmarkup)]  
  
 Con questa impostazione, il contenuto esterno verrà caricato in un processo separato da quello in cui è ospitata l'applicazione. Questo processo è limitato al set di autorizzazioni predefinito dell'area Internet e in questo modo l'area viene isolata efficacemente dall'applicazione host e dal computer client.  
  
> [!NOTE]
> Anche se la navigazione per [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] file separati da un <xref:System.Windows.Navigation.NavigationWindow> o <xref:System.Windows.Controls.Frame> in un'applicazione autonoma viene implementata in base all'infrastruttura di hosting del browser WPF, che implica il processo PresentationHost, il livello di sicurezza è leggermente inferiore rispetto a quando il contenuto viene caricato direttamente in Internet Explorer in Windows Vista e Windows 7 (che rimane comunque tramite PresentationHost). Ciò si verifica in quanto un'applicazione WPF autonoma che usa un Web browser non fornisce la funzionalità di sicurezza di modalità protetta aggiuntiva di Internet Explorer.  
  
<a name="BestPractices"></a>   
## <a name="resources-for-developing-wpf-applications-that-promote-security"></a>Risorse per lo sviluppo di applicazioni WPF che garantiscano la sicurezza  
 Di seguito sono riportate alcune risorse aggiuntive per facilitare lo sviluppo di applicazioni WPF che favoriscono la sicurezza:  
  
|Area|Risorsa|  
|----------|--------------|  
|Codice gestito|[Patterns and Practices Security Guidance for Applications](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)) (Modelli e indicazioni sulla sicurezza per applicazioni)|  
|CAS|[Sicurezza dall'accesso di codice](../misc/code-access-security.md)|  
|ClickOnce|[Sicurezza e distribuzione di ClickOnce](/visualstudio/deployment/clickonce-security-and-deployment)|  
|WPF|[Sicurezza con attendibilità parziale in WPF](wpf-partial-trust-security.md)|  
  
## <a name="see-also"></a>Vedere anche

- [Sicurezza con attendibilità parziale in WPF](wpf-partial-trust-security.md)
- [Strategia di sicurezza di WPF - Sicurezza della piattaforma](wpf-security-strategy-platform-security.md)
- [Strategia di sicurezza WPF - Progettazione della sicurezza](wpf-security-strategy-security-engineering.md)
- [Patterns and Practices Security Guidance for Applications](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)) (Modelli e indicazioni sulla sicurezza per applicazioni)
- [Sicurezza dall'accesso di codice](../misc/code-access-security.md)
- [Sicurezza e distribuzione di ClickOnce](/visualstudio/deployment/clickonce-security-and-deployment)
- [Cenni preliminari su XAML (WPF)](../../desktop-wpf/fundamentals/xaml.md)
