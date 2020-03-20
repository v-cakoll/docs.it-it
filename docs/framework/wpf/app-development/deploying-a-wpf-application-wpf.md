---
title: Distribuire un'app
ms.date: 03/30/2017
helpviewer_keywords:
- WPF applications [WPF], deployment
- deployment [WPF], applications
ms.assetid: 12cadca0-b32c-4064-9a56-e6a306dcc76d
ms.openlocfilehash: 54d14503a0f65bb50f2dfb14d40af3b47d51589c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186318"
---
# <a name="deploy-a-wpf-application"></a>Distribuire un'applicazione WPFDeploy a WPF Application

Dopo aver compilato le applicazioni Windows Presentation Foundation (WPF), è necessario distribuirle. Windows e .NET Framework includono diverse tecnologie di distribuzione. La tecnologia di distribuzione utilizzata per distribuire un'applicazione WPF DIPENDE dal tipo di applicazione. In questo argomento viene fornita una breve panoramica di ogni tecnologia di distribuzione e del modo in cui vengono utilizzate insieme ai requisiti di distribuzione di ogni tipo di applicazione WPFWPF.

<a name="Deployment_Technologies"></a>
## <a name="deployment-technologies"></a>Tecnologie di distribuzione  
 Windows e .NET Framework includono diverse tecnologie di distribuzione, tra cui:  
  
- Distribuzione con XCopy.  
  
- Distribuzione di Windows Installer.  
  
- Distribuzione ClickOnce.  
  
<a name="XCopy_Deployment"></a>
### <a name="xcopy-deployment"></a>Distribuzione con XCopy  
 La distribuzione con XCopy si basa sull'utilizzo del programma della riga di comando XCopy per copiare i file da una posizione all'altra. La distribuzione con XCopy è adatta nei casi seguenti:  
  
- L'applicazione è autonoma e non richiede l'aggiornamento del client per poter essere eseguita.  
  
- I file dell'applicazione devono essere spostati da una posizione a un'altra, ad esempio da un percorso di compilazione (disco locale, condivisione file UNC e così via) a un percorso di pubblicazione (sito Web, condivisione file UNC e così via).  
  
- L'applicazione non richiede l'integrazione della shell (collegamento nel menu Start, icona sul desktop e così via).  
  
 Sebbene XCopy sia adatto a scenari di distribuzione semplici, risulta limitato quando sono necessarie funzionalità di distribuzione più complesse. In particolare, quando si usa XCopy spesso è necessario far fronte al sovraccarico legato alla creazione, esecuzione e gestione di script per gestire la distribuzione in modo affidabile. Inoltre, XCopy non supporta il controllo delle versioni, la disinstallazione o il rollback.  
  
<a name="Windows_Installer"></a>
### <a name="windows-installer"></a>Windows Installer  
 Windows Installer consente alle applicazioni di essere inserite nel pacchetto come file eseguibili autonomi che possono essere facilmente distribuiti ai client ed eseguiti. Inoltre, Windows Installer viene installato con Windows e consente l'integrazione con il desktop, il menu Start e il pannello di controllo Programmi.  
  
 Windows Installer semplifica l'installazione e la disinstallazione delle applicazioni, ma non fornisce funzionalità per garantire che le applicazioni installate vengano mantenute aggiornate dal punto di vista del controllo delle versioni.  
  
 Per ulteriori informazioni su Windows Installer, vedere Distribuzione di [Windows Installer](/visualstudio/deployment/deploying-applications-services-and-components#create-an-installer-package-windows-desktop).
  
<a name="ClickOnce_Deployment"></a>
### <a name="clickonce-deployment"></a>Distribuzione ClickOnce  
 ClickOnceClickOnce consente la distribuzione di applicazioni di tipo Web per le applicazioni non Web. Le applicazioni vengono pubblicate in e distribuite da server Web o file server. Sebbene ClickOnce ClickOnce non supporti l'intera gamma di funzionalità client eseguite dalle applicazioni installate in Windows Installer, supporta un sottoinsieme che include quanto segue:  
  
- Integrazione con il menu Start e il pannello di controllo Programmi.  
  
- Controllo delle versioni, rollback e disinstallazione.  
  
- Modalità di installazione online, che implica sempre l'avvio di un'applicazione dal percorso di distribuzione.  
  
- Aggiornamento automatico quando vengono rilasciate nuove versioni.  
  
- Registrazione delle estensioni file.  
  
 Per ulteriori informazioni su ClickOnceClickOnce, vedere [Sicurezza e distribuzione ClickOnce](/visualstudio/deployment/clickonce-security-and-deployment).  
  
<a name="Deploying_WPF_Applications"></a>
## <a name="deploying-wpf-applications"></a>Distribuzione di applicazioni WPF  
 Le opzioni di distribuzione per un'applicazione WPFWPF dipendono dal tipo di applicazione. Dal punto di vista della distribuzione, WPFWPF ha tre tipi di applicazione significativi:From a deployment perspective, WPFWPF has three significant application types:  
  
- Applicazioni autonome.  
  
- Applicazioni [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] solo markup.  
  
- Applicazioni browser XAML (XBAP).  
  
<a name="Deploying_Standalone_Applications"></a>
### <a name="deploying-standalone-applications"></a>Distribuzione di applicazioni autonome  
 Le applicazioni autonome vengono distribuite tramite ClickOnce o Windows Installer. In entrambi i casi, per eseguire le applicazioni autonome è necessaria l'attendibilità totale. L'attendibilità totale viene concessa automaticamente alle applicazioni autonome distribuite tramite Windows Installer. Alle applicazioni autonome distribuite tramite ClickOnce non viene concessa automaticamente l'attendibilità totale. Al contrario, ClickOnceClickOnce visualizza una finestra di dialogo di avviso di sicurezza che gli utenti devono accettare prima di installare un'applicazione autonoma. Se si accetta l'avviso, l'applicazione autonoma viene installata e le viene concessa l'attendibilità totale. In caso contrario, l'applicazione autonoma non viene installata.  
  
<a name="Deploying_Markup_Only_XAML_Applications"></a>
### <a name="deploying-markup-only-xaml-applications"></a>Distribuzione di applicazioni XAML solo sarkup  
 Le pagine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] solo markup vengono in genere pubblicate nei server Web, ad esempio le pagine HTML, e possono essere visualizzate tramite Internet Explorer. Le pagine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] solo markup vengono eseguite in una sandbox di sicurezza con attendibilità parziale, con restrizioni definite dal set di autorizzazioni dell'area Internet. Ciò fornisce una sandbox di sicurezza equivalente alle applicazioni Web basate su HTML.  
  
 Per altre informazioni sulla sicurezza per le applicazioni WPFWPF, vedere [Sicurezza](../security-wpf.md).  
  
 Le pagine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] di solo markup possono essere installate nel file system locale utilizzando XCopy o Windows Installer. Queste pagine possono essere visualizzate utilizzando Internet Explorer o Esplora risorse.  
  
 Per altre informazioni, vedere [Cenni preliminari su XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md).  
  
<a name="Deploying_XAML_Browser_Applications"></a>
### <a name="deploying-xaml-browser-applications"></a>Distribuzione di applicazioni browser XAML  
 Le applicazioni XBAP sono applicazioni compilate che richiedono la distribuzione dei tre file seguenti:  
  
- *ApplicationName*.exe: il file dell'applicazione dell'assembly eseguibile .  
  
- *ApplicationName*.xbap: il manifesto di distribuzione.  
  
- *ApplicationName*.exe.manifest: il manifesto dell'applicazione.  
  
> [!NOTE]
> Per ulteriori informazioni sui manifesti dell'applicazione e di distribuzione, vedere [Compilazione di un'applicazione WPF](building-a-wpf-application-wpf.md).  
  
 Questi file vengono generati quando viene compilato un'applicazione XBAP. Per altre informazioni, vedere [Procedura: creare un nuovo progetto di applicazione browser WPF](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb628663(v=vs.100)). Analogamente [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] alle pagine di solo markup, le applicazioni XBAP vengono in genere pubblicate in un server Web e visualizzate tramite Internet Explorer.  
  
 Le applicazioni XBAP possono essere distribuite ai client utilizzando una qualsiasi delle tecniche di distribuzione. Tuttavia, ClickOnceClickOnce è consigliato poiché fornisce le seguenti funzionalità:  
  
1. Aggiornamenti automatici quando viene pubblicata una nuova versione.  
  
2. Privilegi di elevazione per l'xBAP in esecuzione con attendibilità totale.  
  
 Per impostazione predefinita, ClickOnce pubblica i file dell'applicazione con l'estensione deploy. Questa impostazione può risultare problematica, ma può essere disabilitata. Per altre informazioni, vedere [Problemi relativi alla configurazione del server e del client nelle distribuzioni ClickOnce](/visualstudio/deployment/server-and-client-configuration-issues-in-clickonce-deployments).  
  
 Per altre informazioni sulla distribuzione di applicazioni browser XAML (XBAP), vedere [Cenni](wpf-xaml-browser-applications-overview.md)preliminari sulle applicazioni browser XAML WPF .  
  
<a name="Installing__NET_Framework_3_0"></a>
## <a name="installing-the-net-framework"></a>Installazione di .NET Framework  
 Per eseguire un'applicazione WPF, è necessario che Microsoft .NET Framework sia installato nel client. Internet Explorer rileva automaticamente se i client vengono installati con .NET Framework quando vengono visualizzate le applicazioni ospitate da browser WPF. Se .NET Framework non è installato, Internet Explorer richiede agli utenti di installarlo.  
  
 Per rilevare se .NET Framework è installato, Internet Explorer include un'applicazione del programma di avvio automatico registrata come gestore MIME (Multipurpose Internet Mail Extensions) di fallback per i file di contenuto con le seguenti estensioni: .xaml, .xps, .xbap e .application. Se si passa a questi tipi di file e .NET Framework non è installato nel client, l'applicazione del programma di avvio automatico richiede l'autorizzazione per installarlo. Se non viene fornita l'autorizzazione, non viene installato né .NET Framework né l'applicazione.  
  
 Se viene concessa l'autorizzazione, Internet Explorer scarica e installa .NET Framework utilizzando il Servizio trasferimento intelligente in background (BITS, Background Intelligent Transfer Service) di Microsoft. Dopo la corretta installazione di .NET Framework, il file richiesto in origine viene aperto in una nuova finestra del browser.  
  
 Per altre informazioni, vedere [Distribuzione di .NET Framework e delle applicazioni](../../deployment/index.md).  
  
## <a name="see-also"></a>Vedere anche

- [Compilazione di un'applicazione WPF](building-a-wpf-application-wpf.md)
- [Sicurezza](../security-wpf.md)
