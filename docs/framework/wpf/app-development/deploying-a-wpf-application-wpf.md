---
title: Distribuzione di un'applicazione WPF (WPF)
ms.date: 03/30/2017
helpviewer_keywords:
- WPF applications [WPF], deployment
- deployment [WPF], applications
ms.assetid: 12cadca0-b32c-4064-9a56-e6a306dcc76d
ms.openlocfilehash: 0ffd4fb05a5a409d74f8a9401a5fb021db0cd99b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61981534"
---
# <a name="deploying-a-wpf-application-wpf"></a>Distribuzione di un'applicazione WPF (WPF)
Dopo che le applicazioni Windows Presentation Foundation (WPF) sono compilate, devono essere distribuiti. [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] e .NET Framework include varie tecnologie di distribuzione. che vengono usate per distribuire specifici tipi di applicazioni [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]. Questo argomento offre una breve panoramica delle singole tecnologie di distribuzione e di come vengono usate in relazione ai requisiti di distribuzione di ogni tipo di applicazione [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].  

<a name="Deployment_Technologies"></a>   
## <a name="deployment-technologies"></a>Tecnologie di distribuzione  
 [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] e .NET Framework sono incluse diverse tecnologie di distribuzione, tra cui:  
  
- Distribuzione con XCopy.  
  
- Distribuzione con [!INCLUDE[TLA2#tla_wininstall](../../../../includes/tla2sharptla-wininstall-md.md)].  
  
- Distribuzione con [!INCLUDE[TLA#tla_clickonce](../../../../includes/tlasharptla-clickonce-md.md)].  
  
<a name="XCopy_Deployment"></a>   
### <a name="xcopy-deployment"></a>Distribuzione con XCopy  
 La distribuzione con XCopy si basa sull'utilizzo del programma della riga di comando XCopy per copiare i file da una posizione all'altra. La distribuzione con XCopy è adatta nei casi seguenti:  
  
- L'applicazione è autonoma e non richiede l'aggiornamento del client per poter essere eseguita.  
  
- I file dell'applicazione devono essere spostati da una posizione all'altra, ad esempio da un percorso di compilazione (disco locale, condivisione file [!INCLUDE[TLA2#tla_unc](../../../../includes/tla2sharptla-unc-md.md)] e così via) a un percorso di pubblicazione (sito Web, condivisione file [!INCLUDE[TLA2#tla_unc](../../../../includes/tla2sharptla-unc-md.md)] e così via).  
  
- L'applicazione non richiede l'integrazione della shell (collegamento nel menu Start, icona sul desktop e così via).  
  
 Sebbene XCopy sia adatto a scenari di distribuzione semplici, risulta limitato quando sono necessarie funzionalità di distribuzione più complesse. In particolare, quando si usa XCopy spesso è necessario far fronte al sovraccarico legato alla creazione, esecuzione e gestione di script per gestire la distribuzione in modo affidabile. Inoltre, XCopy non supporta il controllo delle versioni, la disinstallazione o il rollback.  
  
<a name="Windows_Installer"></a>   
### <a name="windows-installer"></a>Windows Installer  
 [!INCLUDE[TLA2#tla_wininstall](../../../../includes/tla2sharptla-wininstall-md.md)] consente di assemblare le applicazioni in file eseguibili indipendenti che possono essere facilmente distribuiti ai client ed eseguiti. Inoltre, [!INCLUDE[TLA2#tla_wininstall](../../../../includes/tla2sharptla-wininstall-md.md)] viene installato con [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] e consente l'integrazione con il desktop, il menu di avvio e il pannello di controllo Programmi.  
  
 [!INCLUDE[TLA2#tla_wininstall](../../../../includes/tla2sharptla-wininstall-md.md)] semplifica l'installazione e la disinstallazione delle applicazioni, ma non fornisce funzionalità per assicurare che le applicazioni installate restino aggiornate dal punto di vista del controllo delle versioni.  
  
 Per altre informazioni su Windows Installer, vedere [distribuzione di Windows Installer](/visualstudio/deployment/deploying-applications-services-and-components#create-an-installer-package-windows-desktop).
  
<a name="ClickOnce_Deployment"></a>   
### <a name="clickonce-deployment"></a>Distribuzione ClickOnce  
 [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)] consente la distribuzione di applicazioni sul Web per le applicazioni non Web. Le applicazioni vengono pubblicate in e distribuite da server Web o file server. Sebbene [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)] non supporti la gamma completa di funzionalità client supportata dalle applicazioni installate con [!INCLUDE[TLA2#tla_wininstall](../../../../includes/tla2sharptla-wininstall-md.md)], ne supporta un sottoinsieme che include le funzionalità seguenti:  
  
- Integrazione con il menu Start e il pannello di controllo Programmi.  
  
- Controllo delle versioni, rollback e disinstallazione.  
  
- Modalità di installazione online, che implica sempre l'avvio di un'applicazione dal percorso di distribuzione.  
  
- Aggiornamento automatico quando vengono rilasciate nuove versioni.  
  
- Registrazione delle estensioni file.  
  
 Per altre informazioni su [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)], vedere [Sicurezza e distribuzione di ClickOnce](/visualstudio/deployment/clickonce-security-and-deployment).  
  
<a name="Deploying_WPF_Applications"></a>   
## <a name="deploying-wpf-applications"></a>Distribuzione di applicazioni WPF  
 Le opzioni di distribuzione per un'applicazione [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] dipendono dal tipo di applicazione. Dalla prospettiva della distribuzione, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] dispone di tre significativi tipi di applicazione:  
  
- Applicazioni autonome.  
  
- Applicazioni [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] solo markup.  
  
- [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)].  
  
<a name="Deploying_Standalone_Applications"></a>   
### <a name="deploying-standalone-applications"></a>Distribuzione di applicazioni autonome  
 Le applicazioni autonome vengono distribuite tramite [!INCLUDE[TLA#tla_clickonce](../../../../includes/tlasharptla-clickonce-md.md)] o [!INCLUDE[TLA2#tla_wininstall](../../../../includes/tla2sharptla-wininstall-md.md)]. In entrambi i casi, per eseguire le applicazioni autonome è necessaria l'attendibilità totale. L'attendibilità viene concessa automaticamente alle applicazioni autonome che vengono distribuite mediante [!INCLUDE[TLA2#tla_wininstall](../../../../includes/tla2sharptla-wininstall-md.md)]. Alle applicazioni autonome che vengono distribuite mediante [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)] non viene automaticamente concessa l'attendibilità totale. Al contrario, [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)] visualizza una finestra di dialogo Avviso di sicurezza che gli utenti devono accettare prima di installare un'applicazione autonoma. Se si accetta l'avviso, l'applicazione autonoma viene installata e le viene concessa l'attendibilità totale. In caso contrario, l'applicazione autonoma non viene installata.  
  
<a name="Deploying_Markup_Only_XAML_Applications"></a>   
### <a name="deploying-markup-only-xaml-applications"></a>Distribuzione di applicazioni XAML solo sarkup  
 Le pagine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] solo markup vengono generalmente pubblicate in server Web, ad esempio le pagine [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)], e possono essere visualizzate mediante [!INCLUDE[TLA2#tla_iegeneric](../../../../includes/tla2sharptla-iegeneric-md.md)]. Le pagine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] solo markup vengono eseguite in una sandbox di sicurezza con attendibilità parziale, con restrizioni definite dal set di autorizzazioni dell'area Internet. In questo modo si ottiene un sandbox di sicurezza equivalente per le applicazioni Web basate su [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)].  
  
 Per altre informazioni sulla sicurezza per le applicazioni [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], vedere [Sicurezza](../security-wpf.md).  
  
 Le pagine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] solo markup possono essere installate nel file system locale tramite XCopy o [!INCLUDE[TLA2#tla_wininstall](../../../../includes/tla2sharptla-wininstall-md.md)]. Queste pagine possono essere visualizzate tramite [!INCLUDE[TLA2#tla_iegeneric](../../../../includes/tla2sharptla-iegeneric-md.md)] o Windows Explorer.  
  
 Per altre informazioni, vedere [Cenni preliminari su XAML (WPF)](../advanced/xaml-overview-wpf.md).  
  
<a name="Deploying_XAML_Browser_Applications"></a>   
### <a name="deploying-xaml-browser-applications"></a>Distribuzione di applicazioni browser XAML  
 Le applicazioni browser XAML (con estensione [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]) sono applicazioni compilate che richiedono i seguenti tre file per essere distribuite:  
  
- *ApplicationName*.exe: Il file di assembly eseguibile dell'applicazione.  
  
- *ApplicationName*. xbap: Il manifesto di distribuzione.  
  
- *ApplicationName*. manifest: Manifesto dell'applicazione.  
  
> [!NOTE]
>  Per ulteriori informazioni sui manifesti dell'applicazione e di distribuzione, vedere [Compilazione di un'applicazione WPF](building-a-wpf-application-wpf.md).  
  
 Questi file vengono prodotti quando si compila un'applicazione [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]. Per altre informazioni, vedere [Procedura: Creare un nuovo progetto di applicazione Browser WPF](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb628663(v=vs.100)). Analogamente alle pagine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] solo markup, le applicazioni [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] vengono generalmente pubblicate in un server Web e visualizzate tramite [!INCLUDE[TLA2#tla_iegeneric](../../../../includes/tla2sharptla-iegeneric-md.md)].  
  
 Le applicazioni [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] possono essere distribuite ai client usando una qualsiasi delle tecniche di distribuzione. Tuttavia, è consigliabile [!INCLUDE[TLA#tla_clickonce](../../../../includes/tlasharptla-clickonce-md.md)] in quanto fornisce le funzionalità seguenti:  
  
1. Aggiornamenti automatici quando viene pubblicata una nuova versione.  
  
2. Elevazione dei privilegi per l'applicazione [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] in esecuzione con attendibilità totale.  
  
 Per impostazione predefinita, ClickOnce pubblica i file dell'applicazione con l'estensione deploy. Questa impostazione può risultare problematica, ma può essere disabilitata. Per altre informazioni, vedere [Problemi relativi alla configurazione del server e del client nelle distribuzioni ClickOnce](/visualstudio/deployment/server-and-client-configuration-issues-in-clickonce-deployments).  
  
 Per altre informazioni sulla distribuzione di [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)], vedere [Panoramica delle applicazioni browser XAML di WPF](wpf-xaml-browser-applications-overview.md).  
  
<a name="Installing__NET_Framework_3_0"></a>   
## <a name="installing-the-net-framework"></a>Installazione di .NET Framework  
 Per eseguire un [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] un'applicazione, Microsoft .NET Framework deve essere installato nel client. [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)] rileva automaticamente se i client vengono installati con .NET Framework quando [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] vengono visualizzate applicazioni ospitate da browser. Se non è installato .NET Framework, [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)] richiede agli utenti di installarla.  
  
 Per verificare se è installato .NET Framework, [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)] include un'applicazione di avvio automatico che viene registrata come il fallback [!INCLUDE[TLA#tla_mime](../../../../includes/tlasharptla-mime-md.md)] gestore per i file di contenuto con le seguenti estensioni:. XAML, XPS, XBAP e Application. Se si passa a questi tipi di file e .NET Framework non è installato nel client, l'applicazione di avvio automatico richiede l'autorizzazione per installarlo. Se l'autorizzazione non viene specificata, viene installata .NET Framework né l'applicazione.  
  
 Se l'autorizzazione viene concessa, [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)] Scarica e installa .NET Framework tramite la [!INCLUDE[TLA#tla_bits](../../../../includes/tlasharptla-bits-md.md)]. Al termine dell'installazione di .NET Framework, il file richiesto originariamente viene aperto in una nuova finestra del browser.  
  
 Il rilevamento automatico di .NET framework è disponibile nel [!INCLUDE[TLA#tla_longhorn](../../../../includes/tlasharptla-longhorn-md.md)], [!INCLUDE[TLA#tla_winxpsp2](../../../../includes/tlasharptla-winxpsp2-md.md)], e [!INCLUDE[TLA#tla_winnetsvrfamsp1](../../../../includes/tlasharptla-winnetsvrfamsp1-md.md)] client che dispongono di [!INCLUDE[TLA2#tla_ie7](../../../../includes/tla2sharptla-ie7-md.md)] installato o versione successiva.  
  
 Per altre informazioni, vedere [Distribuzione di .NET Framework e delle applicazioni](../../deployment/index.md).  
  
## <a name="see-also"></a>Vedere anche

- [Compilazione di un'applicazione WPF](building-a-wpf-application-wpf.md)
- [Sicurezza](../security-wpf.md)
