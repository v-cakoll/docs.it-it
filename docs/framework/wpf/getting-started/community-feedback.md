---
title: Risorse della community
ms.date: 03/01/2018
helpviewer_keywords:
- community resources [WPF]
- forums [WPF]
- bug descriptions [WPF]
ms.assetid: 468b060a-d54b-4900-a74a-9faccb554045
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a9e903045195d6f464659876334f7fedc5c695e9
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76733803"
---
# <a name="wpf-community-feedback"></a>Commenti sulla community WPF

Microsoft espone un'ampia gamma di risorse della community per conoscere, discutere e fornire commenti e suggerimenti su Windows Presentation Foundation (WPF). Queste risorse includono i forum e il sito della [community degli sviluppatori di Visual Studio](https://developercommunity.visualstudio.com/) . Ogni risorsa della community offre una serie diversa di vantaggi che Questi vantaggi sono descritti di seguito, come un set di procedure consigliate per l'uso di ciascuno di essi per garantire la migliore risposta da parte della community di grandi dimensioni e Microsoft in particolare.

> [!NOTE]
> Non usare la sezione feedback disponibile nella parte inferiore di ogni pagina per inviare commenti e suggerimenti sul prodotto. Questi collegamenti sono dedicati esclusivamente ai commenti e ai suggerimenti sulla documentazione.

## <a name="forums"></a>Forums

Il [forum WPF](https://social.msdn.microsoft.com/Forums/vstudio/home?forum=wpf) è la risorsa principale della community per la discussione e la risoluzione dei problemi. I forum facilitano la discussione e risoluzione dei problemi, offrendo una serie completa di funzionalità di supporto che includono:

- Ricerca.
- Gestione delle discussioni.
- Formattazione avanzata per testo e codice.
- Integrazione con Visual Studio.
- Coinvolgimento degli MVP (Most Valued Professional) e della community.
- Controllo per garantire una risposta ai post nel più breve tempo possibile.

Un'altra opzione per porre domande alla community su WPF è [stack overflow](https://stackoverflow.com/questions/tagged/wpf).

### <a name="forum-best-practices"></a>Procedure consigliate per i forum

L'utilizzo delle procedure consigliate seguenti consente di risolvere i problemi pubblicati nel forum WPF nel minor tempo possibile. Queste procedure sono applicabili a tutti i forum.

#### <a name="search-existing-posts"></a>Cerca nei post esistenti

Alcuni problemi si verificano piuttosto frequentemente e possono essere già stati affrontati da altri. È quindi possibile risolvere il problema rapidamente oppure aggiungere un contributo a una discussione esistente.

#### <a name="use-meaningful-titles"></a>Usare titoli significativi

Titoli concisi e significativi che consentono di migliorare l'individuabilità dei post. Consentono inoltre agli altri membri della community di forum WPF di determinare se è possibile risolvere il problema.

#### <a name="include-appropriate-content"></a>Includi contenuto appropriato

Descrivere il problema e il modo in cui si è provato a risolverlo. Se possibile, includere frammenti di codice di supporto o il più semplice esempio possibile che illustri il problema. Tutti questi dettagli aumentano le possibilità di ottenere una risposta rapida alla domanda.

## <a name="visual-studio-developer-community"></a>Community di sviluppatori di Visual Studio

I problemi possono essere a volte difficili o impossibili da risolvere. Tali situazioni si verificano a causa di bug nella tecnologia, difficoltà nell'applicazione della tecnologia a particolari scenari o mancanza di supporto per determinati scenari. Queste informazioni sono importanti per Microsoft e possono essere fornite tramite il sito della [community degli sviluppatori di Visual Studio](https://developercommunity.visualstudio.com/) .

Gli elementi pubblicati nel centro commenti e suggerimenti sul prodotto WPF vengono indirizzati al database dei bug interni del team WPF. Di conseguenza, è il modo più affidabile per inviare commenti e suggerimenti al proprietario della funzionalità WPF. Inoltre, è possibile convalidare e tenere traccia di suggerimenti e bug, nonché votare, che consentono al team WPF di assegnare priorità ai problemi.

### <a name="developer-community-best-practices"></a>Procedure consigliate per la community degli sviluppatori

Quando si pubblica una pubblicazione nella community di sviluppatori di Visual Studio, la ricerca dei post esistenti, fornendo un titolo significativo e il contenuto appropriato sono le procedure consigliate più importanti, così come sono per la pubblicazione nel forum WPF. Di seguito vengono indicate procedure consigliate aggiuntive da adottare.

#### <a name="search-existing-posts"></a>Cerca nei post esistenti

Alcuni problemi si verificano piuttosto frequentemente e possono essere già stati affrontati da altri. Di conseguenza, è possibile risolvere rapidamente il problema oppure aggiungere l'input a un problema esistente.

#### <a name="use-meaningful-titles"></a>Usare titoli significativi

I titoli concisi e significativi aumentano la probabilità che il problema venga indirizzato al team WPF più appropriato nel minor tempo possibile. Questo aspetto è particolarmente importante per una tecnologia come WPF, che contiene molte funzionalità correlate.

#### <a name="describe-how-to-reproduce-your-bug"></a>Descrivere come riprodurre il bug

In un post relativo a un bug è importante includere gli elementi seguenti, se rilevanti:

- Riportare una descrizione chiara del bug.
- Usare frammenti di codice per supportare la descrizione del bug.
- Riportare un elenco di passaggi che illustrano come riprodurre il bug.
- Includere l'esempio di codice più piccolo possibile che riproduca il bug.
- Specificare se il bug è riproducibile in modo coerente o meno.
- Includere informazioni sulle eccezioni rilevanti.

 Se il bug è relativo all'installazione o alla configurazione, allegare i log e gli snapshot di installazione rilevanti (file con prefisso "dd_" presenti nella cartella %temp%).

 Per problemi relativi alla compilazione, allegare i log di compilazione. Il sistema MSBuild può essere configurato in modo da supportare la registrazione con diversi livelli di dettaglio usando l'opzione/v: dalla riga di comando o configurando il livello appropriato da un ambiente di sviluppo integrato (IDE) come Visual Studio.

#### <a name="provide-environment-information"></a>Fornire informazioni sull'ambiente

Le informazioni sul background possono essere spesso utili per aggiungere contesto al post. In particolare, menzionare la piattaforma del sistema operativo, la famiglia di processori e l'architettura, ad esempio "Windows 10 versione 1709, Intel (R) Xeon (R), x64".

Se il problema per il quale si pubblica il post è relativo al rendering, è necessario includere anche i dettagli della scheda grafica e del driver, se possibile. Queste informazioni sono importanti perché WPF è un Framework di presentazione.

#### <a name="provide-solution-or-project-information"></a>Fornire informazioni sulla soluzione o sul progetto

I bug possono essere relativi agli strumenti usati per sviluppare e compilare le applicazioni e ai tipi di applicazioni che si stanno compilando. Può quindi essere utile specificare:

- Il tipo di applicazione che si sta compilando, ad esempio:
  - Applicazione ( *. exe*) o libreria ( *. dll*)
  - Applicazione browser Extensible Application Markup Language (XAML) (XBAP)
  - Applicazione XAML separata
  - Applicazioni installate autonome
  - Applicazioni autonome distribuite ClickOnce
- Lo strumento di sviluppo, ad esempio:
  - MSBuild
  - Graphic designer Expression
  - Finestra di progettazione interattiva espressioni
  - Visual Studio
- La configurazione della soluzione, ad esempio:
  - Soluzione
  - Un singolo progetto
  - Una soluzione con più progetti dipendenti
- Se l'applicazione dispone di risorse specifiche per la lingua o indipendenti dalla lingua. Se ad esempio è stata specificata la proprietà di progetto `UICulture` o i metadati localizzabili per i tipi `Application`, `Page` e `Resource`.
- Se è stata usata l'impostazione della lingua di sistema nel file AssemblyInfo.cs o AssemblyInfo.vb.

#### <a name="provide-scenario-and-impact-information"></a>Fornire informazioni sullo scenario e sull'effetto

Fornire informazioni sullo scenario che manifesti il bug e il relativo effetto. Queste informazioni sono molto importanti per il team WPF quando decide se, quando e come risolvere un problema o se è possibile utilizzare una soluzione alternativa accettabile.

Generalmente gli scenari di arresto anomalo e di perdita di dati hanno un impatto elevato e pertanto sono i più semplici a cui assegnare la priorità. Alcuni bug si manifestano tuttavia solo in scenari non comuni, che in alcuni casi possono anche essere scenari principali. Fornire al contesto lo scenario e l'effetto aiuta il team WPF a prendere la decisione giusta.

## <a name="see-also"></a>Vedere anche

- [Come segnalare un problema con Visual Studio](/visualstudio/ide/how-to-report-a-problem-with-visual-studio)
