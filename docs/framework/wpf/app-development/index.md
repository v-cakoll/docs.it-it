---
title: Sviluppo applicazioni
description: Informazioni su come creare un'ampia gamma di applicazioni usando il Framework di Windows Presentation Foundation (WPF).
ms.date: 01/26/2018
helpviewer_keywords:
- WPF [WPF], about application development
- application development [WPF], about
ms.assetid: 2996ce5e-81e9-49ae-881b-952db3dd1b7e
ms.openlocfilehash: ac4227785f2fc398217b3aa8984176844264bbaa
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85613735"
---
# <a name="application-development"></a>Sviluppo applicazioni
<a name="introduction"></a>Windows Presentation Foundation (WPF) è un Framework di presentazione che può essere utilizzato per sviluppare i seguenti tipi di applicazioni:  
  
- Applicazioni autonome (applicazioni Windows di stile tradizionale compilate come assembly eseguibili installate ed eseguite dal computer client).  
  
- Applicazioni browser XAML (XBAPs) (applicazioni composte da pagine di navigazione compilate come assembly eseguibili e ospitate da Web browser quali Microsoft Internet Explorer o Mozilla Firefox).  
  
- Librerie di controlli personalizzati, ovvero assembly non eseguibili contenenti controlli riutilizzabili.  
  
- Librerie di classi, ovvero assembly non eseguibili contenenti classi riutilizzabili.  
  
> [!NOTE]
> L'uso di tipi WPF in un servizio Windows è fortemente sconsigliato. Se usate in un servizio Windows, queste funzionalità potrebbero non funzionare nel modo previsto.  
  
 Per compilare questo set di applicazioni, WPF implementa un host di servizi. Questo argomento offre una panoramica dei servizi, con indicazioni sulle risorse in cui trovare altre informazioni.  

<a name="Application_Management"></a>
## <a name="application-management"></a>Gestione applicazioni  
 Per le applicazioni WPF eseguibili è in genere necessario un set di funzionalità di base che include quanto segue:  
  
- Creazione e gestione dell'infrastruttura di applicazioni comuni, inclusa la creazione di un metodo del punto di ingresso e di un loop di messaggi di Windows per la ricezione di messaggi di sistema e di input.  
  
- Interazione con il ciclo di vita dell'applicazione e relativa verifica.  
  
- Recupero ed elaborazione di parametri della riga di comando.  
  
- Condivisione di proprietà con ambito di applicazione e risorse dell'[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].  
  
- Rilevamento ed elaborazione di eccezioni non gestite.  
  
- Restituzione di codici di uscita.  
  
- Gestione delle finestre in applicazioni autonome.  
  
- Esplorazione del rilevamento nelle applicazioni browser XAML (XBAP) e applicazioni autonome con finestre e frame di navigazione.  
  
 Queste funzionalità vengono implementate dalla classe <xref:System.Windows.Application>, che deve essere aggiunta alle applicazioni usando una *definizione di applicazione*.  
  
 Per altre informazioni, vedere [Cenni preliminari sulla gestione di applicazioni](application-management-overview.md).  
  
<a name="WPF_Application_Resource__Content__and_Data_Files"></a>
## <a name="wpf-application-resource-content-and-data-files"></a>File di dati e di risorse dell'applicazione WPF  
 WPF estende il supporto principale nel Framework Microsoft .NET per le risorse incorporate con supporto per tre tipi di file di dati non eseguibili: risorse, contenuto e dati. Per altre informazioni, vedere [File di dati e di risorse dell'applicazione WPF](wpf-application-resource-content-and-data-files.md).  
  
 Un componente chiave del supporto per i file di dati non eseguibili WPF è la possibilità di identificare e caricare i file utilizzando un URI univoco. Per altre informazioni, vedere [URI di Pack in WPF](pack-uris-in-wpf.md).  
  
<a name="Windows_and_Dialog_Boxes"></a>
## <a name="windows-and-dialog-boxes"></a>Finestre e finestre di dialogo  
 Gli utenti interagiscono con applicazioni autonome WPF tramite Windows. Lo scopo di una finestra è ospitare il contenuto dell'applicazione ed esporre le funzionalità dell'applicazione che in genere permettono agli utenti di interagire con il contenuto. In WPF, le finestre sono incapsulate dalla <xref:System.Windows.Window> classe che supporta:  
  
- Creazione e visualizzazione di finestre.  
  
- Definizione di relazioni tra finestre proprietarie/finestre di proprietà.  
  
- Configurazione dell'aspetto delle finestre, ad esempio dimensioni, posizione, icone, testo della barra del titolo e bordo.  
  
- Interazione con il ciclo di vita di una finestra e relativa verifica.  
  
 Per altre informazioni, vedere [Cenni preliminari sulle finestre di WPF](wpf-windows-overview.md).  
  
 <xref:System.Windows.Window> permette di creare un tipo speciale di finestra, chiamata finestra di dialogo. È possibile creare tipi di finestre di dialogo modali e non modali.  
  
 Per praticità e i vantaggi della riusabilità e di un'esperienza utente coerente tra le applicazioni, WPF espone tre delle finestre di dialogo comuni di Windows: <xref:Microsoft.Win32.OpenFileDialog> , <xref:Microsoft.Win32.SaveFileDialog> e <xref:System.Windows.Controls.PrintDialog> .  
  
 Una finestra di messaggio è un tipo speciale di finestra di dialogo che permette di visualizzare agli utenti informazioni testuali importanti e di porre semplici domande con risposta Sì/No/OK/Annulla. Per creare e mostrare finestre di messaggio, è necessario usare la classe <xref:System.Windows.MessageBox>.  
  
 Per altre informazioni, vedere [Cenni preliminari sulle finestre di dialogo](dialog-boxes-overview.md).  
  
<a name="Navigation"></a>
## <a name="navigation"></a>Navigazione  
 WPF supporta la navigazione Web tramite pagine ( <xref:System.Windows.Controls.Page> ) e collegamenti ipertestuali ( <xref:System.Windows.Documents.Hyperlink> ). La navigazione può essere implementata in svariati modi, tra cui i seguenti:  
  
- Pagine autonome ospitate in un Web browser.  
  
- Pagine compilate in un'applicazione XBAP ospitata in un Web browser.  
  
- Pagine compilate in un'applicazione autonoma e ospitate da una finestra di navigazione (<xref:System.Windows.Navigation.NavigationWindow>).  
  
- Pagine ospitate da un frame ( <xref:System.Windows.Controls.Frame> ), che può essere ospitato in una pagina autonoma, oppure una pagina compilata in un'applicazione XBAP o autonoma.  
  
 Per semplificare la navigazione, WPF implementa gli elementi seguenti:  
  
- <xref:System.Windows.Navigation.NavigationService>, il motore di navigazione condiviso per l'elaborazione delle richieste di navigazione utilizzate dalle <xref:System.Windows.Controls.Frame> XBAP di, <xref:System.Windows.Navigation.NavigationWindow> e per supportare la navigazione all'interno dell'applicazione.  
  
- Metodi di navigazione per avviare la navigazione.  
  
- Eventi di navigazione per interagire con il ciclo di vita della navigazione e verificarlo.  
  
- Memorizzazione della navigazione all'indietro e in avanti tramite un giornale di registrazione, che può essere anche esaminato e modificato.  
  
 Per informazioni, vedere [Cenni preliminari sulla navigazione](navigation-overview.md).  
  
 WPF supporta anche un tipo speciale di navigazione noto come navigazione strutturata. La navigazione strutturata può essere usata per chiamare una o più pagine che restituiscono dati in modo strutturato e prevedibile, coerentemente con le funzioni chiamanti. Questa funzionalità dipende dalla classe <xref:System.Windows.Navigation.PageFunction%601>, che viene descritta in modo più approfondito in [Cenni preliminari sulla navigazione strutturata](structured-navigation-overview.md). <xref:System.Windows.Navigation.PageFunction%601> ha anche lo scopo di semplificare la creazione di topologie di navigazione complesse, descritte in [Cenni preliminari sulle topologie di navigazione](navigation-topologies-overview.md).  
  
<a name="Hosting"></a>
## <a name="hosting"></a>Hosting  
 Le applicazioni XBAPs possono essere ospitate in Microsoft Internet Explorer o Firefox. Ogni modello di hosting è associato a un insieme di considerazioni e vincoli descritti in [Hosting](hosting-wpf-applications.md).  
  
<a name="Build_and_Deploy"></a>
## <a name="build-and-deploy"></a>Compilazione e distribuzione  
 Sebbene sia possibile compilare semplici applicazioni WPF da un prompt dei comandi utilizzando i compilatori della riga di comando, WPF si integra con Visual Studio per fornire supporto aggiuntivo che semplifica il processo di sviluppo e compilazione. Per altre informazioni, vedere [Compilazione di un'applicazione WPF](building-a-wpf-application-wpf.md).  
  
 A seconda del tipo di applicazione compilato, è possibile scegliere tra una o più opzioni di distribuzione. Per altre informazioni, vedere [Distribuzione di un'applicazione WPF](deploying-a-wpf-application-wpf.md).  
  
<a name="related_topics"></a>
## <a name="related-topics"></a>Argomenti correlati  
  
|Titolo|Descrizione|  
|-----------|-----------------|  
|[Cenni preliminari sulla gestione di applicazioni](application-management-overview.md)|Offre una panoramica della classe <xref:System.Windows.Application>, con informazioni sulla gestione di ciclo di vita dell'applicazione, finestre, risorse dell'applicazione e navigazione.|  
|[Windows in WPF](windows-in-wpf-applications.md)|Offre informazioni dettagliate sulla gestione delle finestre nell'applicazione, tra cui l'uso della classe <xref:System.Windows.Window> e delle finestre di dialogo.|  
|[Cenni preliminari sulla navigazione](navigation-overview.md)|Offre una panoramica della gestione della navigazione tra pagine dell'applicazione.|  
|[Hosting](hosting-wpf-applications.md)|Viene fornita una panoramica delle applicazioni browser XAML (XBAPs).|  
|[Compilazione e distribuzione](building-and-deploying-wpf-applications.md)|Descrive come compilare e distribuire un'applicazione WPF.|  
|[Introduzione a WPF in Visual Studio](../getting-started/introduction-to-wpf-in-vs.md)|Descrive le principali funzionalità di WPF.|  
|[Procedura dettagliata: Prima applicazione desktop WPF](../getting-started/walkthrough-my-first-wpf-desktop-application.md)|Procedura dettagliata che mostra come creare un'applicazione WPF tramite navigazione tra le pagine, layout, controlli, immagini, stili e binding.|
