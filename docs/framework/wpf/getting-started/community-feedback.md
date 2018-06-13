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
ms.openlocfilehash: 6394bda1c2bcd4a42f76579d541173e65ecd2dc9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33557836"
---
# <a name="wpf-community-feedback"></a>Commenti e suggerimenti della community WPF

Microsoft mette a disposizione numerose risorse della community di conoscere, discutere e fornire commenti e suggerimenti su Windows Presentation Foundation (WPF). Queste risorse includono forum e [Community di sviluppatori Visual Studio](https://developercommunity.visualstudio.com/) sito. Ogni risorsa della community offre una serie diversa di vantaggi che Descritti di seguito, insieme a un set di procedure consigliate per il loro utilizzo per garantire la migliore risposta dalla community di grandi dimensioni e Microsoft, in particolare.

> [!NOTE]
> Non usare la sezione commenti e suggerimenti nella parte inferiore di ogni pagina per inviare commenti sul prodotto. Questi collegamenti sono dedicati esclusivamente ai commenti e ai suggerimenti sulla documentazione.

## <a name="forums"></a>Forum

Il [forum di WPF](https://social.msdn.microsoft.com/Forums/vstudio/en-US/home?forum=wpf) è la risorsa della community primario per la discussione e risoluzione dei problemi. I forum facilitano la discussione e risoluzione dei problemi, offrendo una serie completa di funzionalità di supporto che includono:

- Ricerca.
- Gestione delle discussioni.
- Formattazione avanzata per testo e codice.
- Integrazione di Visual Studio.
- Coinvolgimento degli MVP (Most Valued Professional) e della community.
- Controllo per garantire una risposta ai post nel più breve tempo possibile.

È anche possibile di domande alla community di WPF [Overflow dello Stack](https://stackoverflow.com/questions/tagged/wpf).

### <a name="forum-best-practices"></a>Procedure consigliate di forum

Utilizzando il miglior seguente procedure consigliate per risolvere i problemi inseriti nel forum WPF nel più breve tempo possibile. Queste procedure sono applicabili a tutti i forum.

#### <a name="search-existing-posts"></a>Cercare post esistenti

Alcuni problemi si verificano piuttosto frequentemente e possono essere già stati affrontati da altri. È quindi possibile risolvere il problema rapidamente oppure aggiungere un contributo a una discussione esistente.

#### <a name="use-meaningful-titles"></a>Usare titoli significativi

Titoli concisi e significativi migliorano l'individuazione dei post. Essi rendono inoltre più semplice per altri membri della community di forum WPF determinare se è possibile risolvere il problema.

#### <a name="include-appropriate-content"></a>Includere il contenuto appropriato

Descrivere il problema e come si è tentato di risolverlo. Se possibile, includere frammenti di codice di supporto o il più semplice esempio possibile che illustri il problema. Tutti questi dettagli aumentano le possibilità di ottenere una risposta rapida alla domanda.

## <a name="visual-studio-developer-community"></a>Community di sviluppatori di Visual Studio

I problemi possono essere a volte difficili o impossibili da risolvere. Tali situazioni si verificano a causa di bug nella tecnologia, difficoltà nell'applicazione della tecnologia a particolari scenari o mancanza di supporto per determinati scenari. Queste informazioni sono importanti per Microsoft e possono essere fornite attraverso il [Community di sviluppatori Visual Studio](https://developercommunity.visualstudio.com/) sito.

Gli elementi inseriti nel centro commenti e suggerimenti prodotto WPF vengono indirizzati al database di un errore interno del team WPF. Di conseguenza, è il modo più affidabile per ottenere commenti e suggerimenti al proprietario della funzionalità WPF. Inoltre, è possibile convalidare e tenere traccia dei bug e suggerimenti nonché un voto, che consente al team WPF per assegnare priorità ai problemi.

### <a name="developer-community-best-practices"></a>Procedure consigliate per Community di sviluppatori

Durante la registrazione alla Community di sviluppatori Visual Studio, la ricerca esistente post, fornendo un titolo significativo e contenuto appropriato sono importanti e le procedure consigliate, esattamente come per la registrazione al forum di WPF. Di seguito vengono indicate procedure consigliate aggiuntive da adottare.

#### <a name="search-existing-posts"></a>Cercare post esistenti

Alcuni problemi si verificano piuttosto frequentemente e possono essere già stati affrontati da altri. Di conseguenza, è possibile risolvere rapidamente il problema oppure è possibile aggiungere l'input dell'utente a un problema esistente.

#### <a name="use-meaningful-titles"></a>Usare titoli significativi

Titoli conciso e significativo aumentano le probabilità che il problema è indirizzato al team di WPF più appropriato in una quantità di tempo più breve. Ciò è particolarmente importante per una tecnologia come WPF, che contiene molte funzionalità correlate.

#### <a name="describe-how-to-reproduce-your-bug"></a>Viene descritto come riprodurre il bug

In un post relativo a un bug è importante includere gli elementi seguenti, se rilevanti:

- Riportare una descrizione chiara del bug.
- Usare frammenti di codice per supportare la descrizione del bug.
- Riportare un elenco di passaggi che illustrano come riprodurre il bug.
- Includere l'esempio di codice più piccolo possibile che riproduca il bug.
- Specificare se il bug è riproducibile in modo coerente o meno.
- Includere informazioni sulle eccezioni rilevanti.

 Se il bug è relativo all'installazione o alla configurazione, allegare i log e gli snapshot di installazione rilevanti (file con prefisso "dd_" presenti nella cartella %temp%).

 Per problemi relativi alla compilazione, allegare i log di compilazione. Il sistema può essere configurato per di MSBuild supporta la registrazione con vari livelli di dettaglio utilizzando l'opzione /v: dalla riga di comando o configurando il livello appropriato da un ambiente di sviluppo (IDE) integrato come Visual Studio.

#### <a name="provide-environment-information"></a>Fornire informazioni sull'ambiente

Le informazioni sul background possono essere spesso utili per aggiungere contesto al post. In particolare, indicare la piattaforma del sistema operativo, famiglia di processori e architettura, ad esempio "Windows 10 versione 1709, Intel (r) Xeon, x64".

Se il problema per il quale si pubblica il post è relativo al rendering, è necessario includere anche i dettagli della scheda grafica e del driver, se possibile. Queste informazioni sono importante perché WPF è un framework di presentazione.

#### <a name="provide-solution-or-project-information"></a>Fornire informazioni di soluzione o progetto

I bug possono essere relativi agli strumenti usati per sviluppare e compilare le applicazioni e ai tipi di applicazioni che si stanno compilando. Può quindi essere utile specificare:

- Il tipo di applicazione che si sta compilando, ad esempio:
  - Applicazione (*.exe*) o una raccolta (*DLL*)
  - Applicazione browser di Extensible Application Markup Language (XAML) (XBAP)
  - Applicazione di XAML separato
  - Applicazioni autonome installata
  - Applicazioni autonome distribuite da ClickOnce
- Lo strumento di sviluppo, ad esempio:
  - MSBuild
  - Finestra di progettazione grafica di espressione
  - Finestra di progettazione interattiva di espressione
  - Visual Studio
- La configurazione della soluzione, ad esempio:
  - Una soluzione
  - Un unico progetto
  - Una soluzione con più progetti dipendenti
- Se l'applicazione dispone di risorse specifiche per la lingua o indipendenti dalla lingua. Se ad esempio è stata specificata la proprietà di progetto `UICulture` o i metadati localizzabili per i tipi `Application`, `Page` e `Resource`.
- Se è stata usata l'impostazione della lingua di sistema nel file AssemblyInfo.cs o AssemblyInfo.vb.

#### <a name="provide-scenario-and-impact-information"></a>Fornire informazioni sull'impatto e di uno scenario

Fornire informazioni sullo scenario in cui si manifesta il bug e l'impatto. Queste informazioni sono estremamente importanti per il team WPF al momento di decidere se, quando e come deve essere corretto un problema o se è possibile utilizzare invece una soluzione accettabile.

Generalmente gli scenari di arresto anomalo e di perdita di dati hanno un impatto elevato e pertanto sono i più semplici a cui assegnare la priorità. Alcuni bug si manifestano tuttavia solo in scenari non comuni, che in alcuni casi possono anche essere scenari principali. Indicazione del contesto dello scenario e dell'impatto consente al team WPF di prendere la decisione giusta.

## <a name="see-also"></a>Vedere anche

[Come segnalare un problema con Visual Studio 2017](/visualstudio/ide/how-to-report-a-problem-with-visual-studio-2017)
