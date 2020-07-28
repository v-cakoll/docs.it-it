---
title: Convertire librerie per .NET Core
description: Informazioni su come convertire progetti di libreria da .NET Framework a .NET Core.
author: cartermp
ms.date: 12/07/2018
ms.openlocfilehash: ac9da2f850bf1e4e36367ad2154849a0c7efd535
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87164292"
---
# <a name="port-net-framework-libraries-to-net-core"></a>Convertire librerie .NET Framework a .NET Core

Informazioni su come trasferire .NET Framework codice della libreria in .NET Core, in cui viene eseguito multipiattaforma ed espande la portata delle app che lo usano.

## <a name="prerequisites"></a>Prerequisiti

In questo articolo si presuppone che:

- Venga usato Visual Studio 2017 o versione successiva. .NET Core non è supportato nelle versioni precedenti di Visual Studio.
- Si conosca il [processo di conversione consigliato](index.md).
- Siano stati risolti eventuali problemi di [dipendenze di terze parti](third-party-deps.md).

È anche necessario acquisire familiarità con il contenuto degli articoli seguenti:

[.NET Standard](../../standard/net-standard.md)\
Questo articolo descrive la specifica formale delle API .NET che devono essere disponibili in tutte le implementazioni di .NET.

[Sviluppo di librerie con strumenti multipiattaforma](../tutorials/libraries.md)\
Questo articolo illustra come scrivere librerie usando il interfaccia della riga di comando di .NET Core.

[Aggiunte al formato *csproj* per .NET Core](../tools/csproj.md)\
Questo documento descrive le modifiche aggiunte ai file di progetto nell'ambito del passaggio a *csproj* e a MSBuild.

[Porting in .NET Core-analisi delle dipendenze di terze parti](third-party-deps.md)\
Questo articolo illustra la portabilità delle dipendenze di terze parti e le operazioni da eseguire quando una dipendenza del pacchetto NuGet non viene eseguita in .NET Core.

## <a name="retarget-to-net-framework-472"></a>Ridestina a .NET Framework 4.7.2

Se il codice non ha come destinazione .NET Framework 4.7.2, è consigliabile ridestinarlo a .NET Framework 4.7.2. Questa operazione assicura la disponibilità delle più recenti alternative alle API nei casi in cui .NET Standard non supporta le API esistenti.

Per ogni progetto che si desidera trasferire, eseguire le operazioni seguenti in Visual Studio:

1. Fare clic con il pulsante destro del mouse sul progetto e scegliere **Proprietà**.
1. Nell'elenco a discesa **Versione .NET Framework di destinazione** selezionare **.NET Framework 4.7.2**.
1. Ricompilare il progetto.

Poiché i progetti hanno ora come destinazione .NET Framework 4.7.2, usare tale versione come base per la conversione del codice.

## <a name="determine-portability"></a>Determinare la portabilità

Il passaggio successivo consiste nell'esecuzione di ApiPort (API Portability Analyzer) per generare un report sulla portabilità per l'analisi.

Assicurarsi di comprendere lo strumento [API Portability Analyzer (ApiPort)](../../standard/analyzers/portability-analyzer.md) e come generare report sulla portabilità per usare .NET Core come destinazione. La procedura dipende probabilmente dalle esigenze e dai gusti personali. Le sezioni seguenti illustrano in dettaglio alcuni approcci diversi. A seconda della strutturazione del codice, potrebbe essere necessario usare una combinazione di tali strategie.

### <a name="deal-primarily-with-the-compiler"></a>Gestire principalmente il compilatore

Questo approccio funziona bene per progetti di piccole dimensioni o per progetti che non usano molte API .NET Framework. L'approccio è semplice:

1. Eseguire facoltativamente ApiPort sul progetto. Se si esegue ApiPort, esaminare il report per ottenere informazioni sui problemi che si dovrà affrontare.
1. Copiare tutto il codice in un nuovo progetto .NET Core.
1. Facendo riferimento al report sulla portabilità, se generato, risolvere gli eventuali errori del compilatore fino a ottenere una compilazione completa del progetto.

Sebbene non sia strutturato, questo approccio incentrato sul codice spesso risolve rapidamente i problemi. Un progetto contenente solo modelli di dati potrebbe essere un candidato ideale per questo approccio.

### <a name="stay-on-the-net-framework-until-portability-issues-are-resolved"></a>Rimanere aggiornati sui .NET Framework fino a quando non vengono risolti i problemi di portabilità

Questo approccio potrebbe costituire la scelta migliore se si preferisce che il codice venga compilato durante l'intero processo. Di seguito viene riportata la descrizione di questo approccio:

1. Eseguire ApiPort su un progetto.
1. Risolvere i problemi usando diverse API portabili.
1. Prendere nota delle aree in cui non è possibile usare un'alternativa diretta.
1. Ripetere i passaggi precedenti per tutti i progetti da convertire, fino a quando non si è certi che ciascuno di essi è pronto per essere copiato in un nuovo progetto .NET Core.
1. Copiare il codice in un nuovo progetto .NET Core.
1. Risolvere eventuali problemi per i quali non esiste un'alternativa diretta.

Questo approccio attento è più strutturato rispetto alla semplice risoluzione degli errori del compilatore, ma è ancora relativamente incentrato sul codice e offre il vantaggio di consentirne sempre la compilazione. I modi in cui vengono corretti i problemi non risolvibili mediante il semplice uso di un'altra API possono variare notevolmente. Si potrebbe scoprire che è necessario sviluppare un piano più completo per determinati progetti, che verrà trattato nell'approccio successivo.

### <a name="develop-a-comprehensive-plan-of-attack"></a>Sviluppare un piano di attacco completo

Questo approccio potrebbe costituire la scelta migliore per progetti più complessi e di maggiori dimensioni, in cui per supportare .NET Core può essere necessaria la ristrutturazione del codice o la riscrittura completa di determinate aree. Di seguito viene riportata la descrizione di questo approccio:

1. Eseguire ApiPort su un progetto.
1. Determinare le posizioni in cui viene usato ciascun tipo non portabile e stabilire l'entità dell'impatto sulla portabilità complessiva.
   - Comprendere la natura di tali tipi. Sono in numero limitato, ma di uso frequente? Sono numerosi, ma usati raramente? Il loro uso è concentrato o distribuito in tutto il codice?
   - È possibile isolare facilmente il codice non portabile per gestirlo in modo più efficace?
   - È necessario effettuare il refactoring del codice?
   - Per i tipi non portabili, esistono API alternative che svolgono la stessa attività? Se ad esempio si usa la <xref:System.Net.WebClient> classe, potrebbe essere possibile usare la <xref:System.Net.Http.HttpClient> classe.
   - Sono disponibili API portabili differenti che è possibile usare per eseguire un'attività, anche se non si tratta di una sostituzione vera e propria? Se, ad esempio, si usa <xref:System.Xml.Schema.XmlSchema> per analizzare XML ma non è necessario XML schema l'individuazione, è possibile usare <xref:System.Xml.Linq> le API e implementare l'analisi in modo autonomo, anziché affidarsi a un'API.
1. Se sono presenti assembly difficili da trasferire, è opportuno lasciarli per il momento in .NET Framework? Di seguito sono illustrati alcuni aspetti da considerare:
   - Alcune funzionalità della libreria possono non essere compatibili con .NET Core poiché sono basate in misura eccessiva su funzionalità specifiche di .NET Framework o di Windows. Vale la pena abbandonare questa funzionalità per ora e rilasciare una versione temporanea di .NET Core della libreria con meno funzionalità fino a quando le risorse non saranno disponibili per trasferire le funzionalità?
   - Un'operazione di refactoring può essere utile?
1. La scrittura di una propria implementazione di un'API .NET Framework non disponibile è una scelta ragionevole?
   È possibile prendere in considerazione la copia, la modifica e l'uso del codice dalla [.NET Framework origine riferimento](https://github.com/Microsoft/referencesource). Il codice sorgente di riferimento è concesso in licenza con la [licenza MIT](https://github.com/Microsoft/referencesource/blob/master/LICENSE.txt), quindi esiste un ampio margine di libertà per usare il codice sorgente come base per il proprio codice. È sufficiente assicurarsi di aggiungere le attribuzioni appropriate per Microsoft nel codice.
1. Ripetere questo processo in base alle esigenze per i diversi progetti.

A seconda delle dimensioni della codebase, la fase di analisi può richiedere diverso tempo. Il tempo dedicato a questa fase per comprendere appieno la portata delle modifiche necessarie e per elaborare un piano consente in genere di risparmiare tempo nel lungo termine, in particolare se la codebase è complessa.

Il piano può comportare la necessità di modifiche significative della codebase, mantenendo tuttavia come destinazione .NET Framework 4.7.2. Si tratta di una versione più strutturata dell'approccio precedente. La modalità di esecuzione del piano dipende dalle caratteristiche della codebase.

### <a name="mixed-approach"></a>Approccio misto

È probabile che, in base al tipo di progetto, sia necessario combinare gli approcci descritti in precedenza. È consigliabile effettuare le scelte più corrette per il progetto e la CodeBase.

## <a name="port-your-tests"></a>Trasferire i test

Il modo migliore per verificare un codice trasferito consiste nell'eseguirne il test durante il trasferimento in .NET Core. A tale scopo è necessario usare un framework di test che supporta la compilazione e l'esecuzione dei test per .NET Core. Attualmente sono disponibili le tre opzioni seguenti:

- [xUnit](https://xunit.github.io/)
  - [Per iniziare](https://xunit.github.io/docs/getting-started-dotnet-core.html)
  - [Strumento per trasferire un progetto MSTest in xUnit](https://github.com/dotnet/codeformatter/tree/master/src/XUnitConverter)
- [NUnit](https://nunit.org/)
  - [Per iniziare](https://github.com/nunit/docs/wiki/Installation)
  - [Post di blog sulla migrazione da MSTest a NUnit](https://www.florian-rappl.de/News/Page/275/convert-mstest-to-nunit)
- [MSTest](/visualstudio/test/unit-test-basics)

## <a name="recommended-approach"></a>Approccio consigliato

In definitiva, l'entità del lavoro di conversione dipende in larga misura dal modo in cui è strutturato il codice .NET Framework. Un modo efficace per trasferire il codice consiste nell'iniziare con la *base* della libreria, ovvero i componenti fondamentali del codice. Può trattarsi di modelli di dati o di altri metodi e classi fondamentali usati dagli altri elementi in modo diretto o indiretto.

1. Convertire il progetto di test che verifica il livello della libreria attualmente in fase di conversione.
1. Copiare la base della libreria in un nuovo progetto .NET Core e selezionare la versione di .NET Standard che si vuole supportare.
1. Apportare le modifiche necessarie per consentire la compilazione del codice. Può essere necessario aggiungere le dipendenze di un pacchetto NuGet al file *csproj*.
1. Eseguire i test e apportare le modifiche eventualmente necessarie.
1. Selezionare il successivo livello di codice da convertire e ripetere i passaggi precedenti.

Iniziando con la base della libreria e spostandosi metodicamente dalla base testando ogni livello nel modo appropriato, la conversione diventa un processo sistematico in cui i problemi vengono isolati in un livello del codice alla volta.

## <a name="next-steps"></a>Passaggi successivi

>[!div class="nextstepaction"]
>[Organizzare progetti per .NET Core](project-structure.md)
