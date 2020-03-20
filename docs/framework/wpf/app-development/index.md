---
title: Sviluppo applicazioni
ms.date: 01/26/2018
helpviewer_keywords:
- WPF [WPF], about application development
- application development [WPF], about
ms.assetid: 2996ce5e-81e9-49ae-881b-952db3dd1b7e
ms.openlocfilehash: 5ff9f58b72982f79e70b80f60c10828c3b54e5bb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186009"
---
# <a name="application-development"></a>Sviluppo applicazioni
<a name="introduction"></a>Windows Presentation Foundation (WPF)Windows Presentation Foundation (WPF) è un framework di presentazione che può essere usato per sviluppare i tipi di applicazioni seguenti:Windows Presentation Foundation (WPF) is a presentation framework that can be used to develop the following types of applications:  
  
- Applicazioni autonome (applicazioni Windows in stile tradizionale compilate come assembly eseguibili installati ed eseguiti dal computer client).  
  
- Applicazioni browser XAML (XBAP) (applicazioni composte da pagine di navigazione compilate come assembly eseguibili e ospitate da browser Web come Microsoft Internet Explorer o Mozilla Firefox).  
  
- Librerie di controlli personalizzati, ovvero assembly non eseguibili contenenti controlli riutilizzabili.  
  
- Librerie di classi, ovvero assembly non eseguibili contenenti classi riutilizzabili.  
  
> [!NOTE]
> L'uso di tipi WPF in un servizio Windows è fortemente sconsigliato. Se usate in un servizio Windows, queste funzionalità potrebbero non funzionare nel modo previsto.  
  
 Per compilare questo set di applicazioni, WPFWPF implementa una serie di servizi. Questo argomento offre una panoramica dei servizi, con indicazioni sulle risorse in cui trovare altre informazioni.  

<a name="Application_Management"></a>
## <a name="application-management"></a>Gestione di applicazioni  
 Le applicazioni WPF eseguibili richiedono in genere un set di funzionalità di base che include quanto segue:Executable WPF WPF applications commonly require a core set of functionality that includes the following:  
  
- Creazione e gestione dell'infrastruttura di applicazioni comuni, inclusa la creazione di un metodo del punto di ingresso e di un loop di messaggi di Windows per la ricezione di messaggi di sistema e di input.  
  
- Interazione con il ciclo di vita dell'applicazione e relativa verifica.  
  
- Recupero ed elaborazione di parametri della riga di comando.  
  
- Condivisione di proprietà con ambito di applicazione e risorse dell'[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].  
  
- Rilevamento ed elaborazione di eccezioni non gestite.  
  
- Restituzione di codici di uscita.  
  
- Gestione delle finestre in applicazioni autonome.  
  
- Rilevamento della navigazione nelle applicazioni browser XAML (XBAP) e nelle applicazioni autonome con finestre e frame di spostamento.  
  
 Queste funzionalità vengono implementate dalla classe <xref:System.Windows.Application>, che deve essere aggiunta alle applicazioni usando una *definizione di applicazione*.  
  
 Per altre informazioni, vedere [Cenni preliminari sulla gestione di applicazioni](application-management-overview.md).  
  
<a name="WPF_Application_Resource__Content__and_Data_Files"></a>
## <a name="wpf-application-resource-content-and-data-files"></a>File di dati e di risorse dell'applicazione WPF  
 WPFWPF estende il supporto di base in Microsoft .NET Framework per le risorse incorporate con supporto per tre tipi di file di dati non eseguibili: risorse, contenuto e dati. Per altre informazioni, vedere [File di dati e di risorse dell'applicazione WPF](wpf-application-resource-content-and-data-files.md).  
  
 Un componente chiave del supporto per i file di dati non eseguibili WPF WPF è la possibilità di identificarli e caricarli utilizzando un URI univoco. Per ulteriori informazioni, vedere [URI di tipo pack in WPF](pack-uris-in-wpf.md).  
  
<a name="Windows_and_Dialog_Boxes"></a>
## <a name="windows-and-dialog-boxes"></a>Finestre e finestre di dialogo  
 Gli utenti interagiscono con WPFWPF applicazioni autonome tramite finestre. Lo scopo di una finestra è ospitare il contenuto dell'applicazione ed esporre le funzionalità dell'applicazione che in genere permettono agli utenti di interagire con il contenuto. In WPFWPF, le finestre <xref:System.Windows.Window> sono incapsulate dalla classe , che supporta:In WPFWPF, windows are encapsulated by the class, which supports:  
  
- Creazione e visualizzazione di finestre.  
  
- Definizione di relazioni tra finestre proprietarie/finestre di proprietà.  
  
- Configurazione dell'aspetto delle finestre, ad esempio dimensioni, posizione, icone, testo della barra del titolo e bordo.  
  
- Interazione con il ciclo di vita di una finestra e relativa verifica.  
  
 Per altre informazioni, vedere [Cenni preliminari sulle finestre di WPF](wpf-windows-overview.md).  
  
 <xref:System.Windows.Window> permette di creare un tipo speciale di finestra, chiamata finestra di dialogo. È possibile creare tipi di finestre di dialogo modali e non modali.  
  
 Per comodità e i vantaggi della riusibilità e di un'esperienza utente coerente <xref:Microsoft.Win32.OpenFileDialog> <xref:Microsoft.Win32.SaveFileDialog>tra <xref:System.Windows.Controls.PrintDialog>le applicazioni, WPF espone tre delle finestre di dialogo comuni di Windows: , e .  
  
 Una finestra di messaggio è un tipo speciale di finestra di dialogo che permette di visualizzare agli utenti informazioni testuali importanti e di porre semplici domande con risposta Sì/No/OK/Annulla. Per creare e mostrare finestre di messaggio, è necessario usare la classe <xref:System.Windows.MessageBox>.  
  
 Per altre informazioni, vedere [Cenni preliminari sulle finestre di dialogo](dialog-boxes-overview.md).  
  
<a name="Navigation"></a>
## <a name="navigation"></a>Navigazione  
 WPFWPF supporta lo spostamento in<xref:System.Windows.Controls.Page>stile Web<xref:System.Windows.Documents.Hyperlink>tramite pagine ( ) e collegamenti ipertestuali ( ). La navigazione può essere implementata in svariati modi, tra cui i seguenti:  
  
- Pagine autonome ospitate in un Web browser.  
  
- Pagine compilate in un'applicazione XBAP ospitata in un Web browser.  
  
- Pagine compilate in un'applicazione autonoma e ospitate da una finestra di navigazione (<xref:System.Windows.Navigation.NavigationWindow>).  
  
- Pagine ospitate da un<xref:System.Windows.Controls.Frame>frame ( ), che possono essere ospitate in una pagina autonoma o in una pagina compilata in un'applicazione XBAP o autonoma.  
  
 Per facilitare la navigazione, WPFWPF implementa quanto segue:To facilitate navigation, WPFWPF implements the following:  
  
- <xref:System.Windows.Navigation.NavigationService>, il motore di spostamento condiviso per <xref:System.Windows.Controls.Frame> <xref:System.Windows.Navigation.NavigationWindow>l'elaborazione delle richieste di spostamento utilizzato da , , e XBAP per supportare lo spostamento all'intra-applicazione.  
  
- Metodi di navigazione per avviare la navigazione.  
  
- Eventi di navigazione per interagire con il ciclo di vita della navigazione e verificarlo.  
  
- Memorizzazione della navigazione all'indietro e in avanti tramite un giornale di registrazione, che può essere anche esaminato e modificato.  
  
 Per informazioni, vedere [Cenni preliminari sulla navigazione](navigation-overview.md).  
  
 WPFWPF supporta anche un tipo speciale di spostamento noto come struttura di spostamento. La navigazione strutturata può essere usata per chiamare una o più pagine che restituiscono dati in modo strutturato e prevedibile, coerentemente con le funzioni chiamanti. Questa funzionalità dipende dalla classe <xref:System.Windows.Navigation.PageFunction%601>, che viene descritta in modo più approfondito in [Cenni preliminari sulla navigazione strutturata](structured-navigation-overview.md). <xref:System.Windows.Navigation.PageFunction%601> ha anche lo scopo di semplificare la creazione di topologie di navigazione complesse, descritte in [Cenni preliminari sulle topologie di navigazione](navigation-topologies-overview.md).  
  
<a name="Hosting"></a>
## <a name="hosting"></a>Hosting  
 Le applicazioni XBAP possono essere ospitate in Microsoft Internet Explorer o Firefox. Ogni modello di hosting è associato a un insieme di considerazioni e vincoli descritti in [Hosting](hosting-wpf-applications.md).  
  
<a name="Build_and_Deploy"></a>
## <a name="build-and-deploy"></a>Compilazione e distribuzione  
 Sebbene le applicazioni WPF semplici possano essere compilate da un prompt dei comandi usando compilatori da riga di comando, WPFWPF si integra con Visual Studio per fornire supporto aggiuntivo che semplifica il processo di sviluppo e compilazione. Per altre informazioni, vedere [Compilazione di un'applicazione WPF](building-a-wpf-application-wpf.md).  
  
 A seconda del tipo di applicazione compilato, è possibile scegliere tra una o più opzioni di distribuzione. Per altre informazioni, vedere [Distribuzione di un'applicazione WPF](deploying-a-wpf-application-wpf.md).  
  
<a name="related_topics"></a>
## <a name="related-topics"></a>Argomenti correlati  
  
|Titolo|Descrizione|  
|-----------|-----------------|  
|[Cenni preliminari sulla gestione di applicazioni](application-management-overview.md)|Offre una panoramica della classe <xref:System.Windows.Application>, con informazioni sulla gestione di ciclo di vita dell'applicazione, finestre, risorse dell'applicazione e navigazione.|  
|[Windows in WPF](windows-in-wpf-applications.md)|Offre informazioni dettagliate sulla gestione delle finestre nell'applicazione, tra cui l'uso della classe <xref:System.Windows.Window> e delle finestre di dialogo.|  
|[Cenni preliminari sulla navigazione](navigation-overview.md)|Offre una panoramica della gestione della navigazione tra pagine dell'applicazione.|  
|[Hosting](hosting-wpf-applications.md)|Fornisce una panoramica delle applicazioni browser XAML (XBAP).|  
|[Compilazione e distribuzione](building-and-deploying-wpf-applications.md)|Descrive come compilare e distribuire un'applicazione WPF.|  
|[Introduzione a WPF in Visual Studio](../getting-started/introduction-to-wpf-in-vs.md)|Descrive le principali funzionalità di WPF.|  
|[Procedura dettagliata: Prima applicazione desktop WPF](../getting-started/walkthrough-my-first-wpf-desktop-application.md)|Procedura dettagliata che mostra come creare un'applicazione WPF tramite navigazione tra le pagine, layout, controlli, immagini, stili e binding.|
