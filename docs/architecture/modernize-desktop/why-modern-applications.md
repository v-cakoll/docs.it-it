---
title: Motivi per scegliere applicazioni desktop moderne
description: Informazioni sulle tecnologie desktop, ad esempio Windows Forms, WPF e UWP nel mondo moderno.
ms.date: 09/16/2019
ms.openlocfilehash: f8b70ba9e0ee97a6e0938e3219ecd0d2324248ae
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2020
ms.locfileid: "83423278"
---
# <a name="why-modern-desktop-applications"></a>Motivi per scegliere applicazioni desktop moderne

## <a name="introduction"></a>Introduzione

### <a name="a-story-of-one-company"></a>Una storia di una società

Nei primi anni 2000, una società multinazionale ha iniziato a sviluppare una soluzione desktop distribuita per lo scambio di informazioni tra diversi rami della società e l'esecuzione di operazioni ottimizzate sulle unità centralizzate. Hanno scelto un Framework completamente nuovo denominato Windows Forms (noto anche come WinForms) per lo sviluppo di applicazioni. Nel corso degli anni il progetto si è evoluto in un'applicazione maturata, ben collaudata e collaudata nel tempo con centinaia di migliaia di righe di codice. Il tempo trascorso e .NET Framework 2,0 non è più la nuova tecnologia a caldo. Gli sviluppatori che lavorano a questa applicazione si trovano a fronte di un dilemma. Desiderano utilizzare lo stack di tecnologie più recente nel loro sviluppo e avere l'aspetto dell'applicazione e "ritengono" moderno. Allo stesso tempo, non desiderano abbandonare il prodotto straordinario creato più di 15 anni e riscrivere l'intera applicazione da zero.

### <a name="your-story"></a>La tua storia

Ci si potrebbe trovare nella stessa barca, in cui sono state rilevate Windows Forms o Windows Presentation Foundation (WPF) applicazioni che hanno dimostrato la loro affidabilità negli anni. È probabile che si voglia usare queste applicazioni per molti anni. Allo stesso tempo, poiché le applicazioni sono state scritte un po' di tempo fa, potrebbero mancare funzionalità come l'aspetto moderno, le prestazioni, l'integrazione con nuovi dispositivi e funzionalità della piattaforma e così via, che offre loro un'idea di "tecnologia obsoleta". Si è verificato un altro problema che potrebbe interessare gli sviluppatori. Quando si lavora con le versioni precedenti del .NET Framework e si gestiscono le applicazioni che sono state scritte un po' di tempo fa, è possibile che non si stiano imparando nuove tecnologie senza compromettere la creazione di competenze tecniche moderne. Se si tratta di una storia, questo libro è per te.

## <a name="desktop-applications-nowadays"></a>Applicazioni desktop al giorno

Prima del lancio di Internet, le applicazioni desktop erano l'approccio principale per la creazione di sistemi software. Gli sviluppatori possono scegliere qualsiasi linguaggio di programmazione, ad esempio COBOL, FORTRAN, VB6 o C++. Ma dove sviluppano strumenti di piccole dimensioni o architetture distribuite complesse, sono tutte applicazioni desktop.

Quindi, le tecnologie Internet hanno iniziato a scuotere il mondo di sviluppo e a conquistare un maggior numero di ingegneri con vantaggi come la semplice distribuzione e i processi di distribuzione semplificati. Quando un'applicazione Web è stata distribuita nell'ambiente di produzione, tutti gli utenti hanno ottenuto aggiornamenti automatici hanno avuto un notevole effetto sull'agilità del software.

L'infrastruttura Internet, i protocolli sottostanti e gli standard come HTTP e HTML, tuttavia, non sono stati progettati per la compilazione di applicazioni complesse. In realtà, il principale sforzo di sviluppo è stato quello di puntare a un solo obiettivo: offrire alle applicazioni Web le stesse funzionalità delle applicazioni desktop, ad esempio l'input rapido dei dati e la gestione dello stato.

Anche se le applicazioni Web e per dispositivi mobili hanno raggiunto una velocità incredibile, per alcune attività desktop le applicazioni desktop conservano il numero una posizione in termini di efficienza e prestazioni. Questo spiega perché sono presenti milioni di sviluppatori che compilano progetti con WPF e WinForms e la quantità di tali applicazioni è in continua crescita.

Ecco alcuni motivi per scegliere le applicazioni desktop nello sviluppo:

- Le app desktop offrono una migliore interazione con il PC dell'utente.
- Le prestazioni delle applicazioni desktop per calcoli complessi sono molto più elevate rispetto alle prestazioni delle applicazioni Web.
- L'esecuzione di una logica personalizzata sul lato client è possibile ma molto più complessa con un'applicazione Web.
- L'uso del multithreading è più semplice e più efficiente in un'applicazione desktop.
- La curva di apprendimento per la progettazione di interfacce utente (UI) non è ripida. Per WinForms è completamente intuitivo grazie all'esperienza di trascinamento della finestra di progettazione Windows Forms.
- È facile iniziare a scrivere codice e testare gli algoritmi senza dover configurare un'infrastruttura server o preoccuparsi di problemi di connettività, firewall e compatibilità del browser.
- Il debug è potente rispetto al debug Web.
- L'accesso ai dispositivi hardware, ad esempio la fotocamera, il Bluetooth o i lettori di schede, è facile.
- Poiché la tecnologia è stata interstata per un certo periodo di tempo, sono disponibili numerosi esperti e una Knowledge base per lo sviluppo di applicazioni desktop.

Quindi, come si può vedere, lo sviluppo per desktop è ideale per diversi motivi. La tecnologia è matura e ora testata, il ciclo di sviluppo è veloce, il debug è potente e probabilmente le app desktop hanno meno complessità e sono più facili da usare.

Microsoft ha offerto numerose tecnologie desktop dell'interfaccia utente per tutti gli anni da Win32 introdotte in 1995 a piattaforma UWP (Universal Windows Platform) (UWP) rilasciate nel 2016.

![Tecnologie desktop Microsoft](./media/why-modern-applications/microsoft-desktop-technologies.png)

In base a un sondaggio pubblicato da Telerik il 2016 aprile, le tecnologie più diffuse per la creazione di app desktop di Windows sono Windows Forms, WPF e UWP.

![Sondaggio Telerik che Mostra Windows Forms, WPF e UWP come le tecnologie desktop più diffuse](./media/why-modern-applications/telerik-survey.png)

È possibile eseguire lo sviluppo in uno qualsiasi di questi elementi usando C# e Visual Basic, ma è opportuno esaminare più in dettaglio.

### <a name="windows-forms"></a>Windows Forms

Rilasciato per la prima volta nel 2002, Windows Forms è un Framework gestito ed è la tecnologia desktop più vecchia, più utilizzata, basata sul motore GDI (Graphics Device Interface) di Windows. Offre un'esperienza di trascinamento della selezione per lo sviluppo di interfacce utente in Visual Studio.  Allo stesso tempo, Windows Forms si basa su Visual Studio designer come il modo principale per sviluppare l'interfaccia utente, la creazione di componenti visivi dal codice non è semplice.

Nell'elenco seguente sono riepilogate le principali caratteristiche di Windows Forms:

- Tecnologia avanzata con molti esempi di codice e documentazione.
- Designer potente e produttivo. Non è così comodo progettare l'interfaccia utente "dal codice".
- Facile e intuitiva da apprendere, grazie all'esperienza di trascinamento della progettazione.
- Supportato in qualsiasi versione di Windows.
- Supportato in .NET Core 3,0 e versioni successive.

### <a name="wpf"></a>WPF

In base alla specifica del linguaggio XAML, WPF predilige una netta separazione tra l'interfaccia utente e il codice. In XAML sono disponibili funzionalità quali la creazione di modelli, lo stile e l'associazione, ideali per la compilazione di applicazioni di grandi dimensioni. Come Windows Forms, si tratta di un Framework gestito, ma la progettazione è modulare e riutilizzabile.

Di seguito sono riportate le funzionalità principali di WPF:

- Tecnologia avanzata.
- La finestra di progettazione è disponibile, ma gli sviluppatori in genere preferiscono creare la progettazione dal codice usando XAML dichiarativo.
- La curva di apprendimento è più ripida del Windows Forms.
- Supportato in qualsiasi versione di Windows.
- Supportato in .NET Core 3,0 e versioni successive.

### <a name="uwp"></a>Piattaforma UWP

UWP non è solo un Framework di presentazione come WPF e Windows Forms, ma è anche una piattaforma. Questa piattaforma include:

- Il proprio set di API (l'API Windows Runtime).
- Un nuovo sistema di distribuzione (MSIX)
- Un modello di ciclo di vita delle applicazioni moderno (per un consumo di batteria ridotto).
- Un nuovo sistema di gestione delle risorse (basato sui file PRI).

La piattaforma è stata creata per supportare tutti i tipi di sistemi di input (ad esempio input penna, tocco, gamepad, mouse, tastiera, sguardo e così via) in tutti i fattori di forma, con prestazioni e consumo di batteria insufficiente. Per questi motivi, la shell del sistema operativo Windows 10 usa parti della piattaforma UWP.

![Struttura UWP](./media/why-modern-applications/uwp-structure.png)

UWP contiene un Framework di presentazione basato su XAML, ad esempio WPF, ma presenta alcune differenze importanti, ad esempio:

- Le applicazioni vengono eseguite nei contenitori di app. I contenitori di app controllano a quali risorse può accedere un'app UWP.
- Supportato solo in Windows 10.
- Le app possono essere distribuite tramite Microsoft Store per semplificare la distribuzione.
- Progettato come parte dell'API Windows Runtime.
- Contiene un ampio set di controlli incorporati avanzati e controlli aggiuntivi disponibili tramite i pacchetti NuGet della libreria dell'interfaccia utente Microsoft (libreria WinUI) aggiornati a intervalli di pochi mesi.

## <a name="a-tale-of-two-platforms"></a>Una storia di due piattaforme

Negli ultimi 20 anni, mentre le tecnologie desktop dell'interfaccia utente stavano crescendo e seguendo il percorso da Windows Forms a UWP, l'hardware è stato anche in evoluzione da unità PC pesanti con piccoli monitoraggi CRT a monitor ad alta risoluzione e tablet e telefoni leggeri con diverse tecniche di input dei dati come il tocco e l'input penna. Queste modifiche hanno comportato la creazione di due concetti diversi: un'applicazione desktop e un'applicazione moderna. Un'applicazione moderna si basa su un modello che considera diversi fattori di forma dei dispositivi, diversi metodi di input e di output e utilizza funzionalità desktop moderne mentre è in esecuzione in un modello di esecuzione in modalità sandbox. D'altra parte, l'applicazione desktop (tradizionale) è un'applicazione per la quale è necessaria un'interfaccia utente solida con densità elevata di controlli che funziona meglio con un mouse e una tastiera.

Nella tabella seguente vengono descritte le differenze tra i due concetti:

|   | Applicazione moderna | Applicazione desktop |
| --- | --- | --- |
| Sicurezza | Nozioni fondamentali sull'esecuzione contenuta &amp; . Progettato da zero per rispettare la privacy degli utenti, gestire la durata della batteria e concentrare l'attenzione su come garantire la sicurezza del dispositivo.  | &amp;Livello di sicurezza dell'amministratore dell'utente. Si dispone dell'accesso nativo al registro di sistema e alle cartelle del disco rigido. |
| Distribuzione | L'installazione e gli aggiornamenti sono gestiti dalla piattaforma.   | MSI, aggiornamenti per i programmi di installazione personalizzati &amp; . Tradizionalmente una fonte di problemi per gli sviluppatori e i responsabili IT.  |
| Distribuzione | Pacchetti firmati di distribuzione attendibile &amp; . La distribuzione viene eseguita da un'origine attendibile e mai dal Web.  | Web, &amp; distribuzione personalizzata SCCM. Nessun controllo sugli elementi installati, influiscono sull'intero computer.   |
| Interfaccia utente | Interfaccia utente moderna. Diversi meccanismi di input, input penna, tocco, gamepad, tastiera, mouse e così via.  | Windows Forms, WPF, MFC. Progettato per il mouse e la tastiera per un'interfaccia utente densa e per ottenere la massima produttività dal desktop.  |
| Data | Primo dati cloud con informazioni dettagliate. Fonte di verità nel cloud. Informazioni dettagliate per sapere cosa accade con l'app e come viene eseguita.  | Dati locali. Le applicazioni desktop tradizionali in genere richiedono alcuni dati locali.  |
| Progettazione | Progettato per il riutilizzo. Si può riutilizzare tra piattaforme diverse, front-end e back-end, eseguendo gli asset in molte posizioni.  | Progettato solo per Windows Desktop  |

Come parte dell'impegno a fornire agli sviluppatori gli strumenti migliori per creare applicazioni, Microsoft ha messo a frutto un notevole impegno per realizzare questi concetti, oppure è possibile persino definire piattaforme, più vicini per consentire agli sviluppatori di sfruttare al meglio entrambi i mondi. A tale scopo, Microsoft ha eseguito un lavoro bidirezionale tra le due piattaforme.

![Impegno bidirezionale tra applicazioni moderne e applicazioni desktop](./media/why-modern-applications/bidirectional-effort.png)

1. Spostare scenari di applicazioni desktop in una piattaforma applicativa moderna. Lo sviluppo desktop tradizionale è ancora molto diffuso perché risolve alcuni scenari in modo ottimale. È opportuno adottare questi scenari desktop comuni e portarli nella piattaforma desktop moderna per rendere la piattaforma completamente compatibile.

    ![Spostare scenari di applicazioni desktop in una piattaforma applicativa moderna](./media/why-modern-applications/desktop-to-modern.png)

1. Spostare le funzionalità dell'applicazione moderna in applicazioni desktop. Per le app desktop esistenti che richiedono un modo per sfruttare le funzionalità moderne senza riscrivere da zero, le funzionalità della piattaforma applicativa moderna vengono inserite nell'applicazione desktop.

    ![Spostare le funzionalità delle applicazioni moderne in applicazioni desktop](./media/why-modern-applications/modern-to-desktop.png)

In questo libro, ci concentreremo sulla seconda parte e mostreremo come è possibile modernizzare le applicazioni desktop esistenti.

## <a name="paths-to-modernization"></a>Percorsi per la modernizzazione

La struttura di questa guida riflette tre assi diversi per realizzare la modernizzazione: funzionalità moderne, distribuzione e installazione.

### <a name="modern-features"></a>Funzionalità moderne

Supponiamo di avere un Windows Forms Application funzionante che un rappresentante della società USA per compilare un ordine cliente. Un nuovo requisito è necessario per consentire al cliente di firmare l'ordine utilizzando una penna del tablet. Inking è nativo nei sistemi operativi e nelle tecnologie odierni, ma non era disponibile quando l'app è stata sviluppata.

Questo percorso mostrerà come è possibile sfruttare le moderne funzionalità desktop nello sviluppo di applicazioni desktop esistenti.

### <a name="deployment"></a>Distribuzione

I cicli di sviluppo moderni sono stati sottolineati per offrire agilità sul modo in cui le nuove versioni delle applicazioni vengono distribuite a ogni singolo utente. Poiché le applicazioni Windows Forms e WPF sono basate su una versione specifica del .NET Framework che devono essere presenti nel computer, non possono avvalersi delle nuove funzionalità della versione .NET Framework senza l'intervento degli utenti IT con il rischio di avere effetti collaterali per le altre applicazioni in esecuzione nello stesso computer. Ha limitato il ritmo di innovazione per gli sviluppatori che li forzano a rimanere nelle versioni obsolete del .NET Framework.

Dal lancio di .NET Core 3,0, è possibile sfruttare un nuovo approccio per la distribuzione affiancata di più versioni di .NET Core e la specifica della versione di .NET Core a cui ogni applicazione deve essere destinata. In questo modo, è possibile usare le funzionalità più recenti in un'unica applicazione pur avendo la certezza di non interrompere altre applicazioni.

### <a name="installation"></a>Installazione

Le applicazioni desktop si basano sempre su una sorta di processo di installazione prima che l'utente possa iniziare a utilizzarle. Questo fatto ha introdotto nel gioco un set di tecnologie, da MSI e ClickOnce ai programmi di installazione personalizzati o anche alla distribuzione di XCOPY. Uno di questi metodi riguarda problemi delicati perché le applicazioni necessitano di un modo per accedere alle risorse condivise nel computer. A volte l'installazione deve accedere al registro di sistema per inserire o aggiornare i nuovi valori di chiave, talvolta per aggiornare le DLL condivise a cui fa riferimento l'applicazione principale. Questo causa un problema continuo per gli utenti, creando questa percezione che dopo l'installazione di un'applicazione, il computer non sarà mai lo stesso, anche se viene disinstallato in seguito.

In questo libro verrà introdotta una nuova modalità di installazione delle applicazioni con MSIX che risolve il problema descritto in precedenza. Si apprenderà come è possibile configurare facilmente un pacchetto, un'installazione e aggiornamenti per l'applicazione.

>[!div class="step-by-step"]
>[Precedente](index.md) 
> [Avanti](whats-new-dotnet-core.md)
