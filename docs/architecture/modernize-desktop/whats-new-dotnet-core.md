---
title: Quali sono le novità di .NET Core per desktop?
description: Informazioni su .NET Core, sulle differenze tra .NET Core e .NET Framework e sulle nuove funzionalità aggiunte.
ms.date: 05/12/2020
ms.openlocfilehash: 9ec4f3002dc9d9ea80fd2b6db8095930867a5c65
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2020
ms.locfileid: "83423264"
---
# <a name="whats-new-with-net-core-for-desktop"></a>Quali sono le novità di .NET Core per desktop?

A partire da .NET Core 3,0, .NET Core supporta Windows Forms e WPF. Ora è possibile scegliere tra .NET Framework e .NET Core per le applicazioni desktop. In questo capitolo vengono descritte le funzionalità di .NET Core e i vantaggi per le applicazioni desktop.

## <a name="the-motivation-behind-net-core"></a>Motivazione alla base di .NET Core

Dal suo avvio nel 2002, .NET Framework si è evoluto negli anni per supportare molte tecnologie come Windows Forms, ASP.NET, Entity Framework, Windows Store e molti altri. Tutti sono di natura diversa. Microsoft si è quindi avvicinato a questa evoluzione, prendendo parte del .NET Framework e creando uno stack di applicazioni diverso per ogni tecnologia. In questo modo, le funzionalità di sviluppo possono essere personalizzate in base alle esigenze dello stack specifico, ottimizzando così il potenziale di ogni piattaforma. Questo comporta la frammentazione sulle versioni del .NET Framework gestite da diversi team indipendenti. Tutti questi stack hanno una struttura comune, che contiene un modello di app, un Framework e un runtime, ma si differenziano per l'implementazione di ognuna di queste parti.

Se la destinazione è solo una di queste piattaforme, è possibile usare questo modello. In molti casi, tuttavia, potrebbe essere necessaria più di una piattaforma di destinazione nella stessa soluzione. Ad esempio, è possibile che l'applicazione disponga di un amministratore desktop, di un sito Web che condivide la logica back-end in esecuzione su un server e anche di un client per dispositivi mobili. In questo caso, è necessaria un'esperienza di codifica unificata che può estendersi a tutte le verticali .NET.

Al momento del rilascio di Windows 8, è Nato il concetto di librerie di classi portabili (classi portabili). In origine, il .NET Framework è stato progettato per il presupposto che venisse sempre distribuito come una singola unità, quindi il [factoring](http://en.wikipedia.org/wiki/Decomposition_(computer_science)) non era un problema. Per affrontare il problema della condivisione del codice tra le verticali, la forza motrice è stata quella di eseguire il refactoring del Framework. Il concetto di contratti è fornire una superficie di attacco dell'API ben fattorizzata. I contratti sono semplicemente assembly su cui si esegue la compilazione e sono progettati con un fattore appropriato per tenere conto delle dipendenze tra di essi.

In questo modo è possibile ragionare sulle differenze di API tra le verticali a livello di assembly, a differenza del livello API singolo precedente. Questo aspetto ha consentito un'esperienza di libreria di classi che può essere destinata a più verticali, note anche come librerie di classi portabili.

![Cronologia delle versioni di .NET Framework](./media/whats-new-dotnet-core/release-history.png)

Con la libreria di classi portabile, l'esperienza di sviluppo viene unificata tra le verticali in base alla forma API. Viene anche risolta la necessità più urgente di creare librerie in esecuzione su verticali diversi. Tuttavia, c'è una grande sfida: le API sono portabili solo quando l'implementazione viene spostata in una posizione verticale.

Un approccio migliore consiste nell'unificare le implementazioni tra le verticali, fornendo un'implementazione ben calcolata anziché una visualizzazione ben fattorizzata. È molto più semplice richiedere a ogni team proprietario di un componente specifico di considerare il funzionamento delle API su tutte le verticali rispetto al tentativo di fornire in modo retroattivo uno stack API coerente. Qui viene .NET Standard. Vedere i dettagli nella sezione successiva.

Un'altra sfida importante riguarda la modalità di distribuzione del .NET Framework. Il .NET Framework è un Framework a livello di computer. Tutte le modifiche apportate hanno effetto su tutte le applicazioni che assumono una dipendenza. Sebbene questo modello di distribuzione presenta molti vantaggi, ad esempio la riduzione dello spazio su disco e l'accesso centralizzato ai servizi, presenta alcune insidie.

Per iniziare, è difficile per gli sviluppatori di applicazioni assumere una dipendenza da un Framework rilasciato di recente. Devono assumere una dipendenza dal sistema operativo più recente o fornire un programma di installazione dell'applicazione che installa il .NET Framework insieme all'applicazione. Se si è uno sviluppatore Web, è possibile che questa opzione non sia presente anche quando il reparto IT stabilisce la versione supportata del server.

Anche se si è disposti ad affrontare il problema di fornire un programma di installazione da concatenare nell'installazione di .NET Framework, è possibile che l'aggiornamento del .NET Framework possa comportare l'indisponibilità di altre applicazioni.

Nonostante l'impegno a fornire versioni compatibili con le versioni precedenti del Framework, sono presenti modifiche compatibili che possono interrompere le applicazioni. Ad esempio, l'aggiunta di un'interfaccia a un tipo esistente può modificare il modo in cui questo tipo viene serializzato e causare problemi di rilievo a seconda del codice esistente. Poiché la base installata di .NET Framework è molto grande, la lotta contro questi scenari di interruzione rallenta il ritmo delle innovazioni all'interno del .NET Framework.

Per risolvere tutti questi problemi, Microsoft ha sviluppato .NET Core per affrontare l'evoluzione della piattaforma .NET.

## <a name="introduction-to-net-core"></a>Introduzione a .NET Core

.NET Core è l'evoluzione della tecnologia .NET di Microsoft in una piattaforma modulare, multipiattaforma, open source e pronta per il cloud. Viene eseguito in Windows, macOS e Linux con piani per l'esecuzione anche in architetture basate su ARM come Android e Internet.

Lo scopo di .NET Core è fornire una piattaforma unificata per tutti i tipi di applicazioni, incluse le applicazioni Windows, multipiattaforma e per dispositivi mobili. [.NET standard](../../standard/net-standard.md) consente di fornire API di base condivise, a cui ogni modello applicativo necessita ed escludere qualsiasi API specifica del modello di applicazione.

Questo Framework offre alle applicazioni molti vantaggi in termini di efficienza e prestazioni, semplificando la creazione di pacchetti e la distribuzione nelle diverse piattaforme supportate.

I vantaggi di .NET Core provengono da queste tre caratteristiche:

- **Multipiattaforma:** Consente l'esecuzione di applicazioni su piattaforme diverse (Windows, macOS e Linux).
- **Open Source:** la piattaforma .NET Core è open source e disponibile tramite GitHub, che promuove la trasparenza e i contributi della community.
- **Supportato:** Microsoft supporta ufficialmente .NET Core.

A partire da .NET Core 3,0, oltre al supporto esistente per il Web e il cloud, è disponibile anche il supporto per i domini desktop, Internet e di intelligenza artificiale. L'obiettivo di questo Framework è impressionante: destinare a ogni tipo di sviluppo .NET presente e futuro. Microsoft prevede di completare questa visione con .NET 5 alla fine del 2020. Il nome "core" è stato rimosso per rinforzarne l'univocità nel mondo .NET.

![Tutti i domini di .NET 5](./media/whats-new-dotnet-core/all-domains-of-dotnet5.png)

## <a name="net-framework-vs-net-core"></a>.NET Framework rispetto a .NET Core

Ora che si comprende la pertinenza di .NET Core all'interno della strategia Microsoft per .NET, è possibile chiedersi cosa accade con .NET Framework. È possibile porre domande come: è necessario abbandonarlo? Scomparirà? Quali sono le scelte per modernizzare le applicazioni di cui si dispone .NET Framework?

In 2019 è stata rilasciata l'ultima versione di **.NET Framework-4,8** . Sono stati inclusi tre miglioramenti principali per le applicazioni desktop:

- **Controlli browser e multimediali moderni**: attualmente, le applicazioni desktop .NET utilizzano Internet Explorer e Windows Media Player per la visualizzazione di file HTML e la riproduzione di file multimediali. Poiché questi controlli legacy non visualizzano il codice HTML più recente o riproducono i file multimediali più recenti, sono stati aggiunti nuovi controlli che sfruttano i vantaggi offerti da Microsoft Edge e lettori multimediali più recenti che supportano gli standard più recenti.
- **Accesso ai controlli UWP**: UWP contiene nuovi controlli che sfruttano le funzionalità di Windows più recenti e gli schermi touch. Non è necessario riscrivere le applicazioni per l'uso di queste nuove funzionalità e controlli, quindi è possibile usare queste nuove funzionalità nel codice WPF o Windows Forms esistente.
- **Miglioramenti a valori DPI alti**: la risoluzione degli schermi sta aumentando alle risoluzioni 4K e 8K. Quindi, .NET Framework 4,8 aggiunge nuovi miglioramenti HDPI per assicurarsi che le applicazioni Windows Forms e WPF esistenti possano avere un aspetto interessante in questi nuovi schermi.

Poiché .NET Framework viene installato su milioni di computer, Microsoft continuerà a supportarlo, ma non aggiungerà nuove funzionalità.

.NET Core è la versione open source, multipiattaforma e in rapida evoluzione di .NET. A causa della natura affiancata, è possibile che vengano apportate modifiche senza la necessità di suddividere le applicazioni. Questo significa che .NET Core otterrà nuove API e funzionalità del linguaggio nel tempo in cui non .NET Framework. Inoltre, **.NET Core** dispone già di funzionalità non possibili per .NET Framework, ad esempio:

- **Versioni affiancate di .NET che supportano Windows Forms e WPF**: questo risolve il problema degli effetti collaterali quando si aggiorna la versione del Framework del computer. È possibile installare più versioni di .NET Core nello stesso computer e ogni applicazione specifica la versione di .NET Core da usare. Ancora più, ora è possibile sviluppare ed eseguire Windows Forms e WPF in .NET Core.
- **Incorporare .NET direttamente in un'applicazione**: è possibile distribuire .NET Core come parte del pacchetto dell'applicazione. Questo consente di sfruttare la versione più recente, le funzionalità e le API senza dover attendere l'installazione di una versione specifica nel computer.
- Sfruttare le **funzionalità di .NET Core**: .NET Core è la versione open source di .NET in rapida evoluzione. La natura affiancata consente di introdurre rapidamente nuove API innovative e miglioramenti di librerie di classi base (BCL) senza il rischio di interruzioni della compatibilità. Ora Windows Forms e le applicazioni WPF possono sfruttare le funzionalità più recenti di .NET Core, che includono anche correzioni più fondamentali per le prestazioni in fase di esecuzione, il supporto di valori DPI elevati e così via.

Una parte essenziale della roadmap per Microsoft era semplificare gli sviluppatori per spostare le applicazioni in .NET Core e in futuro in .NET 5. Tuttavia, se si dispone di applicazioni .NET Framework esistenti, non è consigliabile passare a .NET Core. .NET Framework saranno completamente supportati e faranno sempre parte di Windows. Tuttavia, se si vogliono usare le nuove funzionalità del linguaggio e le API in futuro, è necessario spostare le applicazioni in .NET Core.

Per le nuove applicazioni desktop, è consigliabile iniziare direttamente in .NET Core. È leggero e multipiattaforma, viene eseguito affiancato, offre prestazioni elevate e si adatta perfettamente a contenitori e architetture di microservizi.

![È possibile aggiornare le applicazioni di .NET Framework usando la versione più recente di .NET Framework o trasferire le applicazioni in .NET Core](./media/whats-new-dotnet-core/framework-vs-core.png)

## <a name="net-standard-vs-pcl"></a>.NET Standard rispetto a PCL

[.NET Standard](../../standard/net-standard.md) è una specifica formale delle API .NET che devono essere disponibili in tutte le implementazioni di .NET. La motivazione alla base di .NET Standard è l'esigenza di creare maggiore uniformità nell'ecosistema .NET. .NET Standard è una specifica di API .NET che costituiscono un set di contratti uniforme per la compilazione del codice. Questi contratti sono implementati in ogni versione di .NET, consentendo così la portabilità tra diverse implementazioni di .NET.

.NET Standard abilita gli scenari chiave seguenti:

- Definisce un set uniforme di API delle librerie di classi base per tutte le implementazioni di .NET da implementare, indipendentemente dal carico di lavoro.
- Consente agli sviluppatori di creare librerie portabili utilizzabili in più implementazioni di .NET usando questo stesso set di API.

.NET Standard è l'evoluzione di classi portabili e nell'elenco seguente vengono illustrate le differenze fondamentali tra .NET Standard e classi portabili:

- .NET Standard è un set di API curate, raccolte da Microsoft. Classi portabili non è.
- Le API contenute in una libreria PCL dipendono dalle piattaforme che si sceglie di specificare come destinazione durante la creazione. In questo modo, una libreria di classi portabile è condivisibile solo per le destinazioni specifiche selezionate.
- .NET Standard è indipendente dalla piattaforma, può essere eseguito ovunque, in Windows, macOS, Linux e così via.
- Classi portabili può anche eseguire multipiattaforma, ma hanno una copertura più limitata. Classi portabili può essere destinato solo a un set limitato di piattaforme.

## <a name="new-desktop-features-in-net-core"></a>Nuove funzionalità desktop in .NET Core

### <a name="support-for-windows-forms-and-wpf"></a>Supporto per Windows Forms e WPF

Windows Forms e WPF fanno parte di .NET Core a partire dalla versione 3,0. Entrambi i Framework di presentazione sono solo per Windows, quindi non sono multipiattaforma. È possibile considerare WPF come un livello avanzato rispetto a DirectX e Windows Forms come livello più sottile rispetto a GDI+. WPF e Windows Forms hanno un ottimo lavoro per esporre e esercitare gran parte delle funzionalità delle applicazioni desktop di Windows. Sono quindi disponibili Windows Forms e WPF per .NET Core e .NET Framework. È ora possibile avviare le nuove applicazioni desktop destinate a .NET Core ed eseguire la migrazione di quelle esistenti da .NET Framework a .NET Core.

Una nuova versione di .NET Standard, versione 2,1, è stata rilasciata contemporaneamente a .NET Core 3,0. Come previsto, le versioni di .NET Core 3. x supportano .NET Standard 2,1 e versioni precedenti.

È anche importante notare che le implementazioni di Windows Forms e WPF per .NET Core sono open source.

### <a name="xaml-islands"></a>Isole XAML

Le [isole XAML](/windows/apps/desktop/modernize/xaml-islands) sono un set di componenti che consentono agli sviluppatori di usare i nuovi controlli Windows 10 (UWP XAML Controls) nelle applicazioni Win32, Windows Forms e native correnti, ad esempio MFC. È possibile disporre di "isole" di controlli XAML UWP ovunque si desideri all'interno delle app Win32.

Queste isole XAML sono possibili perché Windows 10, versione 1903 introduce un set di API che consente di ospitare il contenuto XAML di UWP in Windows Win32 usando i gestori Windows (HWnd). Si noti che solo le app in esecuzione in Windows 10 1903 e versioni successive possono usare le isole XAML.

Per semplificare la creazione di isole XAML per gli sviluppatori Windows Forms e WPF, Windows community Toolkit introduce un set di wrapper .NET in diversi pacchetti NuGet. Questi wrapper sono i controlli di hosting e di cui è stato eseguito il wrapping:

- I controlli [WebView](/windows/communitytoolkit/controls/wpf-winforms/webview), [WebViewCompatible](/windows/communitytoolkit/controls/wpf-winforms/webviewcompatible), [InkCanvas](/windows/communitytoolkit/controls/wpf-winforms/inkcanvas), [mediaplayerelement](/windows/communitytoolkit/controls/wpf-winforms/mediaplayerelement)e [MapControl](/windows/communitytoolkit/controls/wpf-winforms/mapcontrol) di cui è stato eseguito il wrapping incapsulano alcuni controlli XAML UWP in controlli Windows Forms o WPF, nascondendo i concetti di UWP per tali sviluppatori.
- Il controllo [WindowsXamlHost](/windows/communitytoolkit/controls/wpf-winforms/windowsxamlhost) per Windows Forms e WPF consente il caricamento di altri controlli XAML UWP senza incapsulamento e controlli personalizzati in un'isola XAML.

### <a name="access-to-all-windows-10-apis"></a>Accesso a tutte le API di Windows 10

Windows 10 offre una grande quantità di API che gli sviluppatori possono usare. Queste API consentono di accedere a un'ampia gamma di funzionalità, ad esempio autenticazione, Bluetooth, appuntamenti e contatti. Ora queste API vengono esposte tramite .NET Core e offrono agli sviluppatori Windows la possibilità di creare app desktop potenti sfruttando le funzionalità presenti in Windows 10.

### <a name="side-by-side-support-and-self-contained-exes"></a>Supporto side-by-side e exe autonomi

Il modello di distribuzione di .NET Core è uno dei vantaggi principali che gli sviluppatori di Windows Desktop utilizzeranno con .NET Core. La possibilità di installare globalmente .NET Core offre gran parte degli stessi vantaggi di installazione e manutenzione centrale dei .NET Framework, senza richiedere aggiornamenti sul posto.

Quando viene rilasciata una nuova versione di .NET Core, è possibile aggiornare ogni app in un computer in base alle esigenze senza influire sulle altre applicazioni. Le nuove versioni di .NET Core vengono installate nelle rispettive directory ed esisteranno "side-by-side" tra loro.

Se è necessario eseguire la distribuzione con isolamento, è possibile distribuire .NET Core con l'applicazione. .NET Core aggrega l'app al runtime di .NET Core come in un unico file eseguibile.

Queste opzioni di distribuzione sono state richieste dagli sviluppatori per molto tempo, ma erano difficili da raggiungere con .NET Framework. L'architettura modulare usata da .NET Core rende possibili le opzioni di distribuzione flessibili.

### <a name="performance"></a>Prestazioni

Fin dall'inizio, destinando i carichi di lavoro Web e cloud, .NET Core ha avuto le prestazioni collegate al suo DNA. Il codice lato server deve essere sufficientemente efficiente per soddisfare gli scenari di concorrenza elevata e i punteggi di .NET Core oggi come piattaforma Web per le prestazioni ottimali sul mercato.

È possibile sfruttare questi miglioramenti delle prestazioni quando si usa .NET Core per creare applicazioni desktop di prossima generazione.

## <a name="benefits-of-open-source"></a>Vantaggi dell'open source

Solo alcune parole su .NET Core sono open source. La creazione di uno stack multipiattaforma è un'operazione complessa che richiede l'interazione di team specializzati in ognuna delle piattaforme di destinazione. Questo sforzo richiede molta collaborazione dall'interno e dall'esterno di Microsoft. Rendendola open source e aprendo così la collaborazione pubblica, otterrai lo stile di sviluppo agile più ampio, aumentando il livello di qualità perché i problemi vengono rilevati da una community di sviluppatori molto grande e attiva.

Si tratta di un fattore di successo fondamentale di .NET Core che continuerà ad accelerare la roadmap indicata in precedenza: come unica piattaforma .NET che tutti gli sviluppatori dovranno avere per compilare un'applicazione.

>[!div class="step-by-step"]
>[Precedente](why-modern-applications.md) 
> [Avanti](migrate-modern-applications.md)
