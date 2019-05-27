---
title: Commenti e suggerimenti della community WPF
ms.date: 03/01/2018
helpviewer_keywords:
- community resources [WPF]
- forums [WPF]
- bug descriptions [WPF]
ms.assetid: 468b060a-d54b-4900-a74a-9faccb554045
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6f62fbe13b42202a2eaca212236ee5fd9aa4df05
ms.sourcegitcommit: 7e129d879ddb42a8b4334eee35727afe3d437952
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/23/2019
ms.locfileid: "66053145"
---
# <a name="wpf-community-feedback"></a>Commenti e suggerimenti della community WPF

Microsoft mette a disposizione numerose risorse della community per conoscere, discutere e fornire commenti e suggerimenti su Windows Presentation Foundation (WPF). Queste risorse includono forum e il [Visual Studio Developer Community](https://developercommunity.visualstudio.com/) sito. Ogni risorsa della community offre una serie diversa di vantaggi che Questi vantaggi sono descritte in questo caso, a una serie di procedure consigliate per il loro uso in modo da garantire la migliore risposta l'intera community e Microsoft in particolare.

> [!NOTE]
> Non usare la sezione commenti e suggerimenti nella parte inferiore di ogni pagina per inviare commenti sul prodotto. Questi collegamenti sono dedicati esclusivamente ai commenti e ai suggerimenti sulla documentazione.

## <a name="forums"></a>Forum

Il [forum di WPF](https://social.msdn.microsoft.com/Forums/vstudio/home?forum=wpf) è la risorsa principale della community per la discussione e la risoluzione dei problemi. I forum facilitano la discussione e risoluzione dei problemi, offrendo una serie completa di funzionalità di supporto che includono:

- Ricerca.
- Gestione delle discussioni.
- Formattazione avanzata per testo e codice.
- Integrazione con Visual Studio.
- Coinvolgimento degli MVP (Most Valued Professional) e della community.
- Controllo per garantire una risposta ai post nel più breve tempo possibile.

Un'altra opzione per poter porre domande alla community su WPF consiste [Stack Overflow](https://stackoverflow.com/questions/tagged/wpf).

### <a name="forum-best-practices"></a>Le procedure consigliate di forum

Le risposte seguenti definisce meglio usando procedure consigliate per risolvere i problemi registrati nei forum di WPF in più breve tempo possibile. Queste procedure sono applicabili a tutti i forum.

#### <a name="search-existing-posts"></a>Cercare post esistenti

Alcuni problemi si verificano piuttosto frequentemente e possono essere già stati affrontati da altri. È quindi possibile risolvere il problema rapidamente oppure aggiungere un contributo a una discussione esistente.

#### <a name="use-meaningful-titles"></a>Usare titoli significativi

Titoli concisi e significativi migliorano l'individuazione dei post. Essi rendono anche più semplice per gli altri membri della community di forum WPF determinare se è possibile risolvere il problema.

#### <a name="include-appropriate-content"></a>Includere contenuto appropriato

Descrivere il problema e modo in cui si è provato a questa Guida. Se possibile, includere frammenti di codice di supporto o il più semplice esempio possibile che illustri il problema. Tutti questi dettagli aumentano le possibilità di ottenere una risposta rapida alla domanda.

## <a name="visual-studio-developer-community"></a>Community di sviluppatori di Visual Studio

I problemi possono essere a volte difficili o impossibili da risolvere. Tali situazioni si verificano a causa di bug nella tecnologia, difficoltà nell'applicazione della tecnologia a particolari scenari o mancanza di supporto per determinati scenari. Queste informazioni sono importanti per Microsoft e possono essere offerte tramite il [Visual Studio Developer Community](https://developercommunity.visualstudio.com/) sito.

Gli elementi pubblicati su WPF Product Feedback Center vengono indirizzati al database dei bug interno del team WPF. Di conseguenza, è il modo più affidabile per ottenere commenti e suggerimenti al proprietario della funzionalità WPF. Inoltre, è possibile convalidare e tenere traccia dei bug e suggerimenti nonché assegnare un voto, che consente al team WPF per assegnare priorità ai problemi.

### <a name="developer-community-best-practices"></a>Procedure consigliate della Community per sviluppatori

Durante la registrazione alla Community degli sviluppatori Visual Studio, la ricerca esistente post, fornire un titolo significativo e contenuto appropriato sono procedure consigliate importanti, esattamente come lo sono per la registrazione al forum di WPF. Di seguito vengono indicate procedure consigliate aggiuntive da adottare.

#### <a name="search-existing-posts"></a>Cercare post esistenti

Alcuni problemi si verificano piuttosto frequentemente e possono essere già stati affrontati da altri. Di conseguenza, è possibile risolvere il problema rapidamente oppure è possibile aggiungere un contributo a un problema esistente.

#### <a name="use-meaningful-titles"></a>Usare titoli significativi

Titoli concisi e significativi aumentano le probabilità che il problema venga indirizzato al team di WPF più appropriato in quanto più breve tempo. Ciò è particolarmente importante per una tecnologia come WPF, che contiene molte funzionalità interrelate.

#### <a name="describe-how-to-reproduce-your-bug"></a>Viene descritto come riprodurre il bug

In un post relativo a un bug è importante includere gli elementi seguenti, se rilevanti:

- Riportare una descrizione chiara del bug.
- Usare frammenti di codice per supportare la descrizione del bug.
- Riportare un elenco di passaggi che illustrano come riprodurre il bug.
- Includere l'esempio di codice più piccolo possibile che riproduca il bug.
- Specificare se il bug è riproducibile in modo coerente o meno.
- Includere informazioni sulle eccezioni rilevanti.

 Se il bug è relativo all'installazione o alla configurazione, allegare i log e gli snapshot di installazione rilevanti (file con prefisso "dd_" presenti nella cartella %temp%).

 Per problemi relativi alla compilazione, allegare i log di compilazione. MSBuild sistema può essere configurato per supportare la registrazione con vari livelli di dettaglio usando l'opzione /v: dalla riga di comando o configurando il livello appropriato da un ambiente di sviluppo (IDE) integrato come Visual Studio.

#### <a name="provide-environment-information"></a>Fornire informazioni sull'ambiente

Le informazioni sul background possono essere spesso utili per aggiungere contesto al post. In particolare, indicare la piattaforma del sistema operativo, famiglia di processori e architettura, ad esempio "Windows 10 versione 1709, Intel (r) Xeon, x64."

Se il problema per il quale si pubblica il post è relativo al rendering, è necessario includere anche i dettagli della scheda grafica e del driver, se possibile. Queste informazioni sono importanti perché WPF è un framework di presentazione.

#### <a name="provide-solution-or-project-information"></a>Fornire informazioni di soluzione o progetto

I bug possono essere relativi agli strumenti usati per sviluppare e compilare le applicazioni e ai tipi di applicazioni che si stanno compilando. Può quindi essere utile specificare:

- Il tipo di applicazione che si sta compilando, ad esempio:
  - Applicazione (*.exe*) o una libreria (*DLL*)
  - Applicazione browser di Extensible Application Markup Language (XAML) (XBAP)
  - Applicazione XAML Loose
  - Applicazioni installate autonome
  - Applicazioni autonome distribuite da ClickOnce
- Lo strumento di sviluppo, ad esempio:
  - MSBuild
  - Espressione Graphic Designer
  - Espressione Designer interattivo
  - Visual Studio
- La configurazione della soluzione, ad esempio:
  - Una soluzione
  - Un singolo progetto
  - Una soluzione con più progetti dipendenti
- Se l'applicazione dispone di risorse specifiche per la lingua o indipendenti dalla lingua. Se ad esempio è stata specificata la proprietà di progetto `UICulture` o i metadati localizzabili per i tipi `Application`, `Page` e `Resource`.
- Se è stata usata l'impostazione della lingua di sistema nel file AssemblyInfo.cs o AssemblyInfo.vb.

#### <a name="provide-scenario-and-impact-information"></a>Fornire informazioni di scenario e dell'impatto

Fornire informazioni sullo scenario che si manifesta il bug e sul suo impatto. Queste informazioni sono estremamente importanti per il team WPF al momento di decidere se, quando e come un problema deve essere corretto o se è possibile utilizzare invece una soluzione alternativa accettabile.

Generalmente gli scenari di arresto anomalo e di perdita di dati hanno un impatto elevato e pertanto sono i più semplici a cui assegnare la priorità. Alcuni bug si manifestano tuttavia solo in scenari non comuni, che in alcuni casi possono anche essere scenari principali. Indicazione del contesto dello scenario e dell'impatto aiuta il team WPF di prendere le decisioni giuste.

## <a name="see-also"></a>Vedere anche

- [Come segnalare un problema con Visual Studio 2017](/visualstudio/ide/how-to-report-a-problem-with-visual-studio-2017)
