---
title: Distribuzione di un'applicazione WPF (WPF)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WPF applications [WPF], deployment
- deployment [WPF], applications
ms.assetid: 12cadca0-b32c-4064-9a56-e6a306dcc76d
caps.latest.revision: "27"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 860549d444bcef3a25af753923955b2e3e1a3677
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="deploying-a-wpf-application-wpf"></a>Distribuzione di un'applicazione WPF (WPF)
Dopo aver compilato le applicazioni [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)], è necessario distribuirle. [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] e [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] includono diverse tecnologie di distribuzione, che vengono usate per distribuire specifici tipi di applicazioni [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]. Questo argomento offre una breve panoramica delle singole tecnologie di distribuzione e di come vengono usate in relazione ai requisiti di distribuzione di ogni tipo di applicazione [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].  
  
   
<a name="Deployment_Technologies"></a>   
## <a name="deployment-technologies"></a>Tecnologie di distribuzione  
 [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] e [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] includono varie tecnologie di distribuzione, tra cui:  
  
-   Distribuzione con XCopy.  
  
-   Distribuzione con [!INCLUDE[TLA2#tla_wininstall](../../../../includes/tla2sharptla-wininstall-md.md)].  
  
-   Distribuzione con [!INCLUDE[TLA#tla_clickonce](../../../../includes/tlasharptla-clickonce-md.md)].  
  
<a name="XCopy_Deployment"></a>   
### <a name="xcopy-deployment"></a>Distribuzione con XCopy  
 La distribuzione con XCopy si basa sull'utilizzo del programma della riga di comando XCopy per copiare i file da una posizione all'altra. La distribuzione con XCopy è adatta nei casi seguenti:  
  
-   L'applicazione è autonoma e non richiede l'aggiornamento del client per poter essere eseguita.  
  
-   I file dell'applicazione devono essere spostati da una posizione all'altra, ad esempio da un percorso di compilazione (disco locale, condivisione file [!INCLUDE[TLA2#tla_unc](../../../../includes/tla2sharptla-unc-md.md)] e così via) a un percorso di pubblicazione (sito Web, condivisione file [!INCLUDE[TLA2#tla_unc](../../../../includes/tla2sharptla-unc-md.md)] e così via).  
  
-   L'applicazione non richiede l'integrazione della shell (collegamento nel menu Start, icona sul desktop e così via).  
  
 Sebbene XCopy sia adatto a scenari di distribuzione semplici, risulta limitato quando sono necessarie funzionalità di distribuzione più complesse. In particolare, quando si usa XCopy spesso è necessario far fronte al sovraccarico legato alla creazione, esecuzione e gestione di script per gestire la distribuzione in modo affidabile. Inoltre, XCopy non supporta il controllo delle versioni, la disinstallazione o il rollback.  
  
<a name="Windows_Installer"></a>   
### <a name="windows-installer"></a>Windows Installer  
 [!INCLUDE[TLA2#tla_wininstall](../../../../includes/tla2sharptla-wininstall-md.md)] consente di assemblare le applicazioni in file eseguibili indipendenti che possono essere facilmente distribuiti ai client ed eseguiti. Inoltre, [!INCLUDE[TLA2#tla_wininstall](../../../../includes/tla2sharptla-wininstall-md.md)] viene installato con [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] e consente l'integrazione con il desktop, il menu di avvio e il pannello di controllo Programmi.  
  
 [!INCLUDE[TLA2#tla_wininstall](../../../../includes/tla2sharptla-wininstall-md.md)] semplifica l'installazione e la disinstallazione delle applicazioni, ma non fornisce funzionalità per assicurare che le applicazioni installate restino aggiornate dal punto di vista del controllo delle versioni.  
  
 Per altre informazioni su [!INCLUDE[TLA2#tla_wininstall](../../../../includes/tla2sharptla-wininstall-md.md)], vedere [Distribuzione con Windows Installer](http://msdn.microsoft.com/en-us/121be21b-b916-43e2-8f10-8b080516d2a0).  
  
<a name="ClickOnce_Deployment"></a>   
### <a name="clickonce-deployment"></a>Distribuzione ClickOnce  
 [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)] consente la distribuzione di applicazioni sul Web per le applicazioni non Web. Le applicazioni vengono pubblicate in e distribuite da server Web o file server. Sebbene [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)] non supporti la gamma completa di funzionalità client supportata dalle applicazioni installate con [!INCLUDE[TLA2#tla_wininstall](../../../../includes/tla2sharptla-wininstall-md.md)], ne supporta un sottoinsieme che include le funzionalità seguenti:  
  
-   Integrazione con il menu Start e il pannello di controllo Programmi.  
  
-   Controllo delle versioni, rollback e disinstallazione.  
  
-   Modalità di installazione online, che implica sempre l'avvio di un'applicazione dal percorso di distribuzione.  
  
-   Aggiornamento automatico quando vengono rilasciate nuove versioni.  
  
-   Registrazione delle estensioni file.  
  
 Per altre informazioni su [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)], vedere [Sicurezza e distribuzione di ClickOnce](/visualstudio/deployment/clickonce-security-and-deployment).  
  
<a name="Deploying_WPF_Applications"></a>   
## <a name="deploying-wpf-applications"></a>Distribuzione di applicazioni WPF  
 Le opzioni di distribuzione per un'applicazione [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] dipendono dal tipo di applicazione. Dalla prospettiva della distribuzione, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] dispone di tre significativi tipi di applicazione:  
  
-   Applicazioni autonome.  
  
-   Applicazioni [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] solo markup.  
  
-   [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)].  
  
<a name="Deploying_Standalone_Applications"></a>   
### <a name="deploying-standalone-applications"></a>Distribuzione di applicazioni autonome  
 Le applicazioni autonome vengono distribuite tramite [!INCLUDE[TLA#tla_clickonce](../../../../includes/tlasharptla-clickonce-md.md)] o [!INCLUDE[TLA2#tla_wininstall](../../../../includes/tla2sharptla-wininstall-md.md)]. In entrambi i casi, per eseguire le applicazioni autonome è necessaria l'attendibilità totale. L'attendibilità viene concessa automaticamente alle applicazioni autonome che vengono distribuite mediante [!INCLUDE[TLA2#tla_wininstall](../../../../includes/tla2sharptla-wininstall-md.md)]. Alle applicazioni autonome che vengono distribuite mediante [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)] non viene automaticamente concessa l'attendibilità totale. Al contrario, [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)] visualizza una finestra di dialogo Avviso di sicurezza che gli utenti devono accettare prima di installare un'applicazione autonoma. Se si accetta l'avviso, l'applicazione autonoma viene installata e le viene concessa l'attendibilità totale. In caso contrario, l'applicazione autonoma non viene installata.  
  
<a name="Deploying_Markup_Only_XAML_Applications"></a>   
### <a name="deploying-markup-only-xaml-applications"></a>Distribuzione di applicazioni XAML solo sarkup  
 Le pagine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] solo markup vengono generalmente pubblicate in server Web, ad esempio le pagine [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)], e possono essere visualizzate mediante [!INCLUDE[TLA2#tla_iegeneric](../../../../includes/tla2sharptla-iegeneric-md.md)]. Le pagine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] solo markup vengono eseguite in una sandbox di sicurezza con attendibilità parziale, con restrizioni definite dal set di autorizzazioni dell'area Internet. In questo modo si ottiene un sandbox di sicurezza equivalente per le applicazioni Web basate su [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)].  
  
 Per altre informazioni sulla sicurezza per le applicazioni [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], vedere [Sicurezza](../../../../docs/framework/wpf/security-wpf.md).  
  
 Le pagine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] solo markup possono essere installate nel file system locale tramite XCopy o [!INCLUDE[TLA2#tla_wininstall](../../../../includes/tla2sharptla-wininstall-md.md)]. Queste pagine possono essere visualizzate mediante [!INCLUDE[TLA2#tla_iegeneric](../../../../includes/tla2sharptla-iegeneric-md.md)] o [!INCLUDE[TLA2#tla_mswin](../../../../includes/tla2sharptla-mswin-md.md)] Explorer.  
  
 Per altre informazioni, vedere [Cenni preliminari su XAML (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md).  
  
<a name="Deploying_XAML_Browser_Applications"></a>   
### <a name="deploying-xaml-browser-applications"></a>Distribuzione di applicazioni browser XAML  
 Le applicazioni browser XAML (con estensione [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]) sono applicazioni compilate che richiedono i seguenti tre file per essere distribuite:  
  
-   *ApplicationName*.exe: il file dell'applicazione dell'assembly eseguibile .  
  
-   *ApplicationName*.xbap: il manifesto di distribuzione.  
  
-   *ApplicationName*.exe.manifest: il manifesto dell'applicazione.  
  
> [!NOTE]
>  Per ulteriori informazioni sui manifesti dell'applicazione e di distribuzione, vedere [Compilazione di un'applicazione WPF](../../../../docs/framework/wpf/app-development/building-a-wpf-application-wpf.md).  
  
 Questi file vengono prodotti quando si compila un'applicazione [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]. Per altre informazioni, vedere [Procedura: creare un nuovo progetto di applicazione browser WPF](http://msdn.microsoft.com/en-us/72ef4d90-e163-42a1-8df0-ea7ccfd1901f). Analogamente alle pagine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] solo markup, le applicazioni [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] vengono generalmente pubblicate in un server Web e visualizzate tramite [!INCLUDE[TLA2#tla_iegeneric](../../../../includes/tla2sharptla-iegeneric-md.md)].  
  
 Le applicazioni [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] possono essere distribuite ai client usando una qualsiasi delle tecniche di distribuzione. Tuttavia, è consigliabile [!INCLUDE[TLA#tla_clickonce](../../../../includes/tlasharptla-clickonce-md.md)] in quanto fornisce le funzionalità seguenti:  
  
1.  Aggiornamenti automatici quando viene pubblicata una nuova versione.  
  
2.  Elevazione dei privilegi per l'applicazione [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] in esecuzione con attendibilità totale.  
  
 Per impostazione predefinita, ClickOnce pubblica i file dell'applicazione con l'estensione deploy. Questa impostazione può risultare problematica, ma può essere disabilitata. Per altre informazioni, vedere [Problemi relativi alla configurazione del server e del client nelle distribuzioni ClickOnce](/visualstudio/deployment/server-and-client-configuration-issues-in-clickonce-deployments).  
  
 Per altre informazioni sulla distribuzione di [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)], vedere [Panoramica delle applicazioni browser XAML di WPF](../../../../docs/framework/wpf/app-development/wpf-xaml-browser-applications-overview.md).  
  
<a name="Installing__NET_Framework_3_0"></a>   
## <a name="installing-the-net-framework"></a>Installazione di .NET Framework  
 Per eseguire un'applicazione [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], [!INCLUDE[TLA#tla_winfx](../../../../includes/tlasharptla-winfx-md.md)] deve essere installato sul client. [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)] rileva automaticamente se i client sono installati con [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] quando vengono visualizzate applicazioni ospitate da browser [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]. Se [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] non è installato, [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)] richiede agli utenti di installarlo.  
  
 Per rilevare se [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] è installato, [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)] include un'applicazione di avvio automatico che viene registrata come gestore [!INCLUDE[TLA#tla_mime](../../../../includes/tlasharptla-mime-md.md)] di fallback per i file di contenuto con le estensioni seguenti: xaml, xps, xbap e application. Se si passa a questi tipi di file e [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] non è installato nel client, l'applicazione di avvio automatico richiede l'autorizzazione per installarlo. Se l'autorizzazione non viene concessa, né [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] né l'applicazione vengono installati.  
  
 Se l'autorizzazione viene concessa, [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)] scarica e installa [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] usando [!INCLUDE[TLA#tla_bits](../../../../includes/tlasharptla-bits-md.md)]. Dopo l'installazione di [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)], viene aperto il file richiesto in una nuova finestra del browser.  
  
 Il rilevamento automatico di [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] è disponibile nei client [!INCLUDE[TLA#tla_longhorn](../../../../includes/tlasharptla-longhorn-md.md)], [!INCLUDE[TLA#tla_winxpsp2](../../../../includes/tlasharptla-winxpsp2-md.md)] e [!INCLUDE[TLA#tla_winnetsvrfamsp1](../../../../includes/tlasharptla-winnetsvrfamsp1-md.md)] che dispongono di [!INCLUDE[TLA2#tla_ie7](../../../../includes/tla2sharptla-ie7-md.md)] o versione successiva.  
  
 Per altre informazioni, vedere [Distribuzione di .NET Framework e delle applicazioni](../../../../docs/framework/deployment/index.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Compilazione di un'applicazione WPF](../../../../docs/framework/wpf/app-development/building-a-wpf-application-wpf.md)  
 [Sicurezza](../../../../docs/framework/wpf/security-wpf.md)
