---
title: Distribuire un'app
ms.date: 03/30/2017
helpviewer_keywords:
- WPF applications [WPF], deployment
- deployment [WPF], applications
ms.assetid: 12cadca0-b32c-4064-9a56-e6a306dcc76d
ms.openlocfilehash: 9d4b7dd0464960441410d8ff2a196f0912354e5f
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741940"
---
# <a name="deploy-a-wpf-application"></a>Distribuire un'applicazione WPF

Una volta compilate le applicazioni Windows Presentation Foundation (WPF), è necessario distribuirle. Windows e il .NET Framework includono diverse tecnologie di distribuzione. La tecnologia di distribuzione utilizzata per distribuire un'applicazione WPF dipende dal tipo di applicazione. In questo argomento viene fornita una breve panoramica di ogni tecnologia di distribuzione e viene illustrato come vengono utilizzate in combinazione con i requisiti di distribuzione di ogni tipo di applicazione WPF.

<a name="Deployment_Technologies"></a>   
## <a name="deployment-technologies"></a>Tecnologie di distribuzione  
 Windows e il .NET Framework includono diverse tecnologie di distribuzione, tra cui:  
  
- Distribuzione con XCopy.  
  
- Windows Installer la distribuzione.  
  
- Distribuzione ClickOnce.  
  
<a name="XCopy_Deployment"></a>   
### <a name="xcopy-deployment"></a>Distribuzione con XCopy  
 La distribuzione con XCopy si basa sull'utilizzo del programma della riga di comando XCopy per copiare i file da una posizione all'altra. La distribuzione con XCopy è adatta nei casi seguenti:  
  
- L'applicazione è autonoma e non richiede l'aggiornamento del client per poter essere eseguita.  
  
- I file dell'applicazione devono essere spostati da una posizione all'altra, ad esempio da un percorso di compilazione (disco locale, condivisione file UNC e così via) a un percorso di pubblicazione (sito Web, condivisione file UNC e così via).  
  
- L'applicazione non richiede l'integrazione della shell (collegamento nel menu Start, icona sul desktop e così via).  
  
 Sebbene XCopy sia adatto a scenari di distribuzione semplici, risulta limitato quando sono necessarie funzionalità di distribuzione più complesse. In particolare, quando si usa XCopy spesso è necessario far fronte al sovraccarico legato alla creazione, esecuzione e gestione di script per gestire la distribuzione in modo affidabile. Inoltre, XCopy non supporta il controllo delle versioni, la disinstallazione o il rollback.  
  
<a name="Windows_Installer"></a>   
### <a name="windows-installer"></a>Windows Installer  
 Windows Installer consente di creare pacchetti di applicazioni come file eseguibili autonomi che possono essere facilmente distribuiti ai client ed eseguiti. Inoltre, Windows Installer viene installato con Windows e Abilita l'integrazione con il desktop, il menu Start e il pannello di controllo programmi.  
  
 Windows Installer semplifica l'installazione e la disinstallazione delle applicazioni, ma non fornisce funzionalità per garantire che le applicazioni installate siano mantenute aggiornate dal punto di vista del controllo delle versioni.  
  
 Per ulteriori informazioni su Windows Installer, vedere [Windows Installer Deployment](/visualstudio/deployment/deploying-applications-services-and-components#create-an-installer-package-windows-desktop).
  
<a name="ClickOnce_Deployment"></a>   
### <a name="clickonce-deployment"></a>Distribuzione ClickOnce  
 ClickOnce consente la distribuzione di applicazioni in stile Web per applicazioni non Web. Le applicazioni vengono pubblicate in e distribuite da server Web o file server. Sebbene ClickOnce non supporti l'intera gamma di funzionalità client eseguite da Windows Installer applicazioni installate, supporta un subset che include quanto segue:  
  
- Integrazione con il menu Start e il pannello di controllo Programmi.  
  
- Controllo delle versioni, rollback e disinstallazione.  
  
- Modalità di installazione online, che implica sempre l'avvio di un'applicazione dal percorso di distribuzione.  
  
- Aggiornamento automatico quando vengono rilasciate nuove versioni.  
  
- Registrazione delle estensioni file.  
  
 Per ulteriori informazioni su ClickOnce, vedere [sicurezza e distribuzione di ClickOnce](/visualstudio/deployment/clickonce-security-and-deployment).  
  
<a name="Deploying_WPF_Applications"></a>   
## <a name="deploying-wpf-applications"></a>Distribuzione di applicazioni WPF  
 Le opzioni di distribuzione per un'applicazione WPF dipendono dal tipo di applicazione. Dal punto di vista della distribuzione, WPF prevede tre tipi di applicazioni significativi:  
  
- Applicazioni autonome.  
  
- Applicazioni [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] solo markup.  
  
- Applicazioni browser XAML (XBAPs).  
  
<a name="Deploying_Standalone_Applications"></a>   
### <a name="deploying-standalone-applications"></a>Distribuzione di applicazioni autonome  
 Le applicazioni autonome vengono distribuite tramite ClickOnce o Windows Installer. In entrambi i casi, per eseguire le applicazioni autonome è necessaria l'attendibilità totale. L'attendibilità totale viene concessa automaticamente alle applicazioni autonome distribuite mediante Windows Installer. Alle applicazioni autonome distribuite tramite ClickOnce non viene concessa automaticamente l'attendibilità totale. Al contrario, ClickOnce Visualizza una finestra di dialogo di avviso di sicurezza che gli utenti devono accettare prima di installare un'applicazione autonoma. Se si accetta l'avviso, l'applicazione autonoma viene installata e le viene concessa l'attendibilità totale. In caso contrario, l'applicazione autonoma non viene installata.  
  
<a name="Deploying_Markup_Only_XAML_Applications"></a>   
### <a name="deploying-markup-only-xaml-applications"></a>Distribuzione di applicazioni XAML solo sarkup  
 Le pagine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] solo markup vengono in genere pubblicate in server Web, come le pagine HTML, e possono essere visualizzate utilizzando Internet Explorer. Le pagine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] solo markup vengono eseguite in una sandbox di sicurezza con attendibilità parziale, con restrizioni definite dal set di autorizzazioni dell'area Internet. In questo modo viene fornita una sandbox di sicurezza equivalente per le applicazioni Web basate su HTML.  
  
 Per ulteriori informazioni sulla sicurezza per le applicazioni WPF, vedere [sicurezza](../security-wpf.md).  
  
 Le pagine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] solo markup possono essere installate nella file system locale utilizzando XCopy o Windows Installer. Queste pagine possono essere visualizzate utilizzando Internet Explorer o Esplora risorse.  
  
 Per altre informazioni, vedere [Cenni preliminari su XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md).  
  
<a name="Deploying_XAML_Browser_Applications"></a>   
### <a name="deploying-xaml-browser-applications"></a>Distribuzione di applicazioni browser XAML  
 Le applicazioni XBAPs sono applicazioni compilate che richiedono la distribuzione dei tre file seguenti:  
  
- *ApplicationName*.exe: il file dell'applicazione dell'assembly eseguibile .  
  
- *ApplicationName*.xbap: il manifesto di distribuzione.  
  
- *ApplicationName*.exe.manifest: il manifesto dell'applicazione.  
  
> [!NOTE]
> Per ulteriori informazioni sui manifesti dell'applicazione e di distribuzione, vedere [Compilazione di un'applicazione WPF](building-a-wpf-application-wpf.md).  
  
 Questi file vengono generati quando viene compilata un'applicazione XBAP. Per altre informazioni, vedere [Procedura: creare un nuovo progetto di applicazione browser WPF](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb628663(v=vs.100)). Come solo markup [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] pagine, le XBAP vengono in genere pubblicate in un server Web e visualizzate con Internet Explorer.  
  
 È possibile distribuire le applicazioni XBAP ai client usando una delle tecniche di distribuzione. Tuttavia, è consigliabile usare ClickOnce poiché fornisce le funzionalità seguenti:  
  
1. Aggiornamenti automatici quando viene pubblicata una nuova versione.  
  
2. Privilegi di elevazione per l'applicazione XBAP eseguita con attendibilità totale.  
  
 Per impostazione predefinita, ClickOnce pubblica i file dell'applicazione con l'estensione deploy. Questa impostazione può risultare problematica, ma può essere disabilitata. Per altre informazioni, vedere [Problemi relativi alla configurazione del server e del client nelle distribuzioni ClickOnce](/visualstudio/deployment/server-and-client-configuration-issues-in-clickonce-deployments).  
  
 Per ulteriori informazioni sulla distribuzione di applicazioni browser XAML (XBAPs), vedere [Cenni preliminari sulle applicazioni browser XAML WPF](wpf-xaml-browser-applications-overview.md).  
  
<a name="Installing__NET_Framework_3_0"></a>   
## <a name="installing-the-net-framework"></a>Installazione di .NET Framework  
 Per eseguire un'applicazione WPF, è necessario che nel client sia installato il Framework Microsoft .NET. Internet Explorer rileva automaticamente se i client vengono installati con .NET Framework quando vengono visualizzate le applicazioni WPF ospitate da browser. Se il .NET Framework non è installato, Internet Explorer richiede agli utenti di installarlo.  
  
 Per rilevare se la .NET Framework è installata, Internet Explorer include un'applicazione del programma di avvio automatico registrata come gestore di fallback Multipurpose Internet Mail Extensions (MIME) per i file di contenuto con le estensioni seguenti:. XAML,. XPS,. XBAP , e. Application. Se si passa a questi tipi di file e il .NET Framework non è installato nel client, l'applicazione del programma di avvio automatico richiede l'autorizzazione per l'installazione. Se non viene fornita l'autorizzazione, né l'.NET Framework né l'applicazione sono installate.  
  
 Se l'autorizzazione viene concessa, Internet Explorer Scarica e installa il .NET Framework utilizzando Microsoft Servizio trasferimento intelligente in background (BITS). Una volta completata l'installazione del .NET Framework, il file richiesto originariamente viene aperto in una nuova finestra del browser.  
  
 Per altre informazioni, vedere [Distribuzione di .NET Framework e delle applicazioni](../../deployment/index.md).  
  
## <a name="see-also"></a>Vedere anche

- [Compilazione di un'applicazione WPF](building-a-wpf-application-wpf.md)
- [Sicurezza](../security-wpf.md)
