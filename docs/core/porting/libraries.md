---
title: Convertire librerie per .NET Core
description: Informazioni su come convertire progetti di libreria da .NET Framework a .NET Core.
author: cartermp
ms.date: 12/7/2018
ms.custom: seodec18
ms.openlocfilehash: 8190dcfd3ffed9051c7724752a19d88e7bef4f4d
ms.sourcegitcommit: c6f69b0cf149f6b54483a6d5c2ece222913f43ce
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/08/2019
ms.locfileid: "55904692"
---
# <a name="port-net-framework-libraries-to-net-core"></a>Convertire librerie .NET Framework a .NET Core

Informazioni su come convertire il codice delle librerie .NET Framework a .NET Core, per l'esecuzione multipiattaforma e l'estensione della copertura delle app che lo usano.

## <a name="prerequisites"></a>Prerequisiti

In questo articolo si presuppone che:

- Venga usato Visual Studio 2017 o versione successiva.
  - .NET Core non è supportato nelle versioni precedenti di Visual Studio
- Si conosca il [processo di conversione consigliato](index.md).
- Siano stati risolti eventuali problemi di [dipendenze di terze parti](third-party-deps.md).

È anche consigliabile avere familiarità con il contenuto degli argomenti seguenti:

[.NET Standard](~/docs/standard/net-standard.md)   
Questo argomento descrive la specifica formale delle API .NET che devono essere disponibili in tutte le implementazioni di .NET.

[Pacchetti, metapacchetti e framework](~/docs/core/packages.md)   
Questo articolo descrive le modalità di definizione e uso dei pacchetti in .NET Core e come i pacchetti supportano l'esecuzione del codice in più implementazioni di .NET.

[Sviluppo di librerie con strumenti multipiattaforma](~/docs/core/tutorials/libraries.md)   
Questo argomento spiega come scrivere librerie per .NET usando gli strumenti dell'interfaccia della riga di comando multipiattaforma.

[Aggiunte al formato *csproj* per .NET Core](~/docs/core/tools/csproj.md)   
Questo documento descrive le modifiche aggiunte ai file di progetto nell'ambito del passaggio a *csproj* e a MSBuild.

[Portabilità in .NET Core - Analisi delle dipendenze di terze parti](~/docs/core/porting/third-party-deps.md)   
Questo argomento illustra la portabilità delle dipendenze di terze parti e le operazioni da eseguire quando una dipendenza per un pacchetto NuGet non può essere eseguita su .NET Core.

## <a name="retargeting-your-net-framework-code-to-net-framework-472"></a>Ridestinazione del codice .NET Framework a .NET Framework 4.7.2

Se il codice non ha come destinazione .NET Framework 4.7.2, è consigliabile ridestinarlo a .NET Framework 4.7.2. Questa operazione assicura la disponibilità delle più recenti alternative alle API nei casi in cui .NET Standard non supporta le API esistenti.

Per ciascuno dei progetti Visual Studio che si vuole trasferire, effettuare le operazioni seguenti:

1. Fare clic con il pulsante destro del mouse sul progetto e scegliere **Proprietà**.
1. Nell'elenco a discesa **Versione .NET Framework di destinazione** selezionare **.NET Framework 4.7.2**.
1. Ricompilare i progetti.

Poiché i progetti hanno ora come destinazione .NET Framework 4.7.2, usare tale versione come base per la conversione del codice.

## <a name="determining-the-portability-of-your-code"></a>Determinazione della portabilità del codice

Il passaggio successivo consiste nell'esecuzione di ApiPort (API Portability Analyzer) per generare un report sulla portabilità per l'analisi.

Assicurarsi di comprendere lo strumento [API Portability Analyzer (ApiPort)](../../standard/analyzers/portability-analyzer.md) e come generare report sulla portabilità per usare .NET Core come destinazione. La procedura dipende probabilmente dalle esigenze e dai gusti personali. Di seguito sono descritti alcuni approcci diversi. A seconda della strutturazione del codice, potrebbe essere necessario usare una combinazione di tali strategie.

### <a name="dealing-primarily-with-the-compiler"></a>Gestire prima di tutto il compilatore

Questo approccio può rivelarsi la scelta migliore per progetti di piccole dimensioni o per progetti che non usano un numero elevato di API .NET Framework. L'approccio è semplice:

1. Eseguire facoltativamente ApiPort sul progetto. Se si esegue ApiPort, esaminare il report per ottenere informazioni sui problemi che si dovrà affrontare.
1. Copiare tutto il codice in un nuovo progetto .NET Core.
1. Facendo riferimento al report sulla portabilità, se generato, risolvere gli eventuali errori del compilatore fino a ottenere una compilazione completa del progetto.

Anche se poco strutturato, questo approccio incentrato sul codice può consentire la rapida risoluzione dei problemi e può costituire la scelta migliore per i progetti o le librerie di minori dimensioni. Un progetto contenente solo modelli di dati potrebbe essere un candidato ideale per questo approccio.

### <a name="staying-on-the-net-framework-until-portability-issues-are-resolved"></a>Rimanere in .NET Framework fino alla risoluzione dei problemi di portabilità

Questo approccio potrebbe costituire la scelta migliore se si preferisce che il codice venga compilato durante l'intero processo. Di seguito viene riportata la descrizione di questo approccio:

1. Eseguire ApiPort su un progetto.
1. Risolvere i problemi usando diverse API portabili.
1. Prendere nota delle aree in cui non è possibile usare un'alternativa diretta.
1. Ripetere i passaggi precedenti per tutti i progetti da convertire, fino a quando non si è certi che ciascuno di essi è pronto per essere copiato in un nuovo progetto .NET Core.
1. Copiare il codice in un nuovo progetto .NET Core.
1. Risolvere eventuali problemi per i quali non esiste un'alternativa diretta.

Questo approccio attento è più strutturato rispetto alla semplice risoluzione degli errori del compilatore, ma è ancora relativamente incentrato sul codice e offre il vantaggio di consentirne sempre la compilazione. I modi in cui vengono corretti i problemi non risolvibili mediante il semplice uso di un'altra API possono variare notevolmente. È possibile che si ritenga necessario sviluppare un piano più completo per determinati progetti, approccio descritto nella sezione seguente.

### <a name="developing-a-comprehensive-plan-of-attack"></a>Sviluppare un piano di attacco completo

Questo approccio potrebbe costituire la scelta migliore per progetti più complessi e di maggiori dimensioni, in cui per supportare .NET Core può essere necessaria la ristrutturazione del codice o la riscrittura completa di determinate aree. Di seguito viene riportata la descrizione di questo approccio:

1. Eseguire ApiPort su un progetto.
1. Determinare le posizioni in cui viene usato ciascun tipo non portabile e stabilire l'entità dell'impatto sulla portabilità complessiva.
   - Comprendere la natura di tali tipi. Sono in numero limitato, ma di uso frequente? Sono numerosi, ma usati raramente? Il loro uso è concentrato o distribuito in tutto il codice?
   - È possibile isolare facilmente il codice non portabile per gestirlo in modo più efficace?
   - È necessario effettuare il refactoring del codice?
   - Per i tipi non portabili, esistono API alternative che svolgono la stessa attività? Ad esempio, se si usa la classe <xref:System.Net.WebClient>, si potrebbe usare la classe <xref:System.Net.Http.HttpClient> in alternativa.
   - Sono disponibili API portabili differenti che è possibile usare per eseguire un'attività, anche se non si tratta di una sostituzione vera e propria? Ad esempio, se si usa <xref:System.Xml.Schema.XmlSchema> per l'analisi del codice XML ma non è necessaria l'individuazione dello schema XML, si potrebbero usare le API <xref:System.Xml.Linq> e implementare manualmente l'analisi, anziché affidarsi a un'API.
1. Se sono presenti assembly difficili da trasferire, è opportuno lasciarli per il momento in .NET Framework? Di seguito sono riportati alcuni aspetti da prendere in considerazione:
   - Alcune funzionalità della libreria possono non essere compatibili con .NET Core poiché sono basate in misura eccessiva su funzionalità specifiche di .NET Framework o di Windows. È opportuno trascurare momentaneamente tali funzionalità non compatibili e rilasciare una versione .NET Core della libreria con un numero minore di funzionalità temporaneamente fino a quando non sono disponibili le risorse per convertire le funzionalità?
   - Un'operazione di refactoring può essere utile?
1. La scrittura di una propria implementazione di un'API .NET Framework non disponibile è una scelta ragionevole?
   Si potrebbe prendere in considerazione di copiare, modificare e usare codice tratto da [.NET Framework Reference Source](https://github.com/Microsoft/referencesource) (Codice sorgente di riferimento .NET Framework). Il codice sorgente di riferimento è concesso in licenza con la [licenza MIT](https://github.com/Microsoft/referencesource/blob/master/LICENSE.txt), quindi esiste un ampio margine di libertà per usare il codice sorgente come base per il proprio codice. È sufficiente assicurarsi di aggiungere le attribuzioni appropriate per Microsoft nel codice.
1. Ripetere questo processo in base alle esigenze per i diversi progetti.
 
A seconda delle dimensioni della codebase, la fase di analisi può richiedere diverso tempo. Il tempo dedicato a questa fase per comprendere appieno la portata delle modifiche necessarie e per elaborare un piano consente in genere di risparmiare tempo nel lungo termine, in particolare se la codebase è complessa.

Il piano può comportare la necessità di modifiche significative della codebase, mantenendo tuttavia come destinazione .NET Framework 4.7.2. Si tratta di una versione più strutturata dell'approccio precedente. La modalità di esecuzione del piano dipende dalle caratteristiche della codebase.

### <a name="mixing-approaches"></a>Approcci combinati

È probabile che, in base al tipo di progetto, sia necessario combinare gli approcci descritti in precedenza. È consigliabile effettuare le scelte più corrette per il progetto e la CodeBase.

## <a name="porting-your-tests"></a>Conversione dei test

Il modo migliore per verificare un codice trasferito consiste nell'eseguirne il test durante il trasferimento in .NET Core. A tale scopo è necessario usare un framework di test che supporta la compilazione e l'esecuzione dei test per .NET Core. Attualmente sono disponibili le tre opzioni seguenti:

- [xUnit](https://xunit.github.io/)
  * [Introduzione](https://xunit.github.io/docs/getting-started-dotnet-core.html)
  * [Strumento per trasferire un progetto MSTest in xUnit](https://github.com/dotnet/codeformatter/tree/master/src/XUnitConverter)
- [NUnit](https://nunit.org/)
  * [Introduzione](https://github.com/nunit/docs/wiki/Installation)
  * [Post di blog sulla migrazione da MSTest a NUnit](https://www.florian-rappl.de/News/Page/275/convert-mstest-to-nunit)
- [MSTest](https://docs.microsoft.com/visualstudio/test/unit-test-basics)

## <a name="recommended-approach-to-porting"></a>Approccio consigliato per la conversione

In definitiva, l'entità del lavoro di conversione dipende in larga misura dal modo in cui è strutturato il codice .NET Framework. Un buon metodo per convertire il codice consiste nell'iniziare con la *base* della libreria, ovvero i componenti fondamentali del codice. Può trattarsi di modelli di dati o di altri metodi e classi fondamentali usati dagli altri elementi in modo diretto o indiretto.

1. Convertire il progetto di test che verifica il livello della libreria attualmente in fase di conversione.
1. Copiare la base della libreria in un nuovo progetto .NET Core e selezionare la versione di .NET Standard che si vuole supportare.
1. Apportare le modifiche necessarie per consentire la compilazione del codice. Può essere necessario aggiungere le dipendenze di un pacchetto NuGet al file *csproj*.
1. Eseguire i test e apportare le modifiche eventualmente necessarie.
1. Selezionare il successivo livello di codice da convertire e ripetere i passaggi precedenti.

Iniziando con la base della libreria e spostandosi metodicamente dalla base testando ogni livello nel modo appropriato, la conversione diventa un processo sistematico in cui i problemi vengono isolati in un livello del codice alla volta.

>[!div class="step-by-step"]
>[avanti](project-structure.md)
