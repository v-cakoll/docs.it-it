---
title: "Testing unità in .NET Core"
description: "Il testing unità non è mai stato così facile. Informazioni su come usare il testing unità nei progetti .NET Core e .NET Standard."
keywords: ".NET, .NET Core, .NET Standard, testing unità"
author: ardalis
ms.author: wiwagn
ms.date: 08/30/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: 815ac74c-4bd9-4a94-a87c-78288b27c0e2
ms.openlocfilehash: 666c06b236ad870c5c683749ab57d4488b4b8a39
ms.sourcegitcommit: 7296449e03f747528f9bc59954c74bf4e359cc1e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/01/2017
---
# <a name="unit-testing-in-net-core-and-net-standard"></a>Testing unità in .NET Core e .NET Standard

.NET Core è stato progettato prestando particolare attenzione alla testabilità, in modo da facilitare la creazione di unit test per le applicazioni. Questo articolo include una breve introduzione agli unit test e ne descrive le differenze rispetto agli altri tipi di test. Le risorse collegate illustrano come aggiungere un progetto di test alla soluzione sviluppata e quindi eseguire unit test usando la riga di comando o Visual Studio.

.NET Core 2.0 supporta [.NET 2.0 Standard](../../standard/net-standard.md). Le librerie usate per illustrare la funzionalità di testing unità in questa sezione si basano su .NET Standard e funzioneranno anche in altri tipi di progetto.

A partire da .NET Core 2.0 sono disponibili modelli di progetto di unit test per Visual Basic e F #, nonché C#.

## <a name="getting-started-with-testing"></a>Introduzione al testing

L'uso di un gruppo di test automatizzati è uno dei modi migliori per verificare che un'applicazione software esegua le operazioni per la quale è stata sviluppata. Esistono tipi diversi di test per le applicazioni software, inclusi i test di integrazione, i test Web, i test di carico e altri. Al livello più basso si collocano gli unit test, che consentono di testare singoli metodi o componenti software. Gli unit test devono testare soltanto il codice sotto il controllo dello sviluppatore, senza verificare eventuali problemi dell'infrastruttura, come database, file system o risorse di rete. Gli unit test possono essere scritti usando [Test Driven Development (TDD)](http://deviq.com/test-driven-development/) (Sviluppo basato su test) o possono essere aggiunti al codice esistente per verificarne la correttezza. In entrambi i casi devono essere di piccole dimensioni, ben identificabili e veloci, poiché in teoria può essere necessario eseguirne centinaia prima di effettuare il push delle modifiche nel repository del codice condiviso del progetto.

> [!NOTE]
> Gli sviluppatori hanno spesso difficoltà a scegliere i nomi appropriati per i metodi e le classi di test. Come punto di partenza, è possibile fare riferimento alle [convenzioni](https://github.com/aspnet/Home/wiki/Engineering-guidelines#unit-tests-and-functional-tests) adottate dal team del prodotto ASP.NET.

Quando si scrivono unit test, fare attenzione a non introdurre accidentalmente dipendenze dall'infrastruttura. Queste dipendenze tendono a rendere i test più lenti e fragili ed è quindi consigliabile usarle solo nei test di integrazione. È possibile evitare queste dipendenze nascoste nel codice dell'applicazione seguendo il [principio delle dipendenze esplicite](http://deviq.com/explicit-dependencies-principle/) e usando la tecnica di [inserimento delle dipendenze](/aspnet/core/fundamentals/dependency-injection) per richiedere le dipendenze dal framework. È inoltre possibile mantenere gli unit test in un progetto separato dai test di integrazione e verificare che il progetto di unit test non includa riferimenti o dipendenze relative a pacchetti dell'infrastruttura.

Altre informazioni sul testing unità sono disponibili nei progetti .NET Core:

I progetti di unit test per .NET Core sono supportati per [C#](../../csharp/index.md), [F#](../../fsharp/index.md) e [Visual Basic](../../visual-basic/index.md). È anche possibile scegliere tra [xUnit](http://xunit.github.io) e [MSTest](https://github.com/Microsoft/vstest-docs).

Informazioni su tali combinazioni sono disponibili in queste procedure dettagliate:

* Creare unit test con [*XUnit* e *C#* con l'interfaccia della riga di comando di .NET Core](unit-testing-with-dotnet-test.md).
* Creare unit test con [*MSTest* e *C#* con l'interfaccia della riga di comando di .NET Core](unit-testing-with-mstest.md).
* Creare unit test con [*XUnit* e *F#* con l'interfaccia della riga di comando di .NET Core](unit-testing-fsharp-with-dotnet-test.md).
* Creare unit test con [*MSTest* e *F#* con l'interfaccia della riga di comando di .NET Core](unit-testing-fsharp-with-mstest.md).
* Creare unit test con [*XUnit* e *Visual Basic* con l'interfaccia della riga di comando di .NET Core](unit-testing-visual-basic-with-dotnet-test.md).
* Creare unit test con [*MSTest* e *Visual Basic* con l'interfaccia della riga di comando di .NET Core](unit-testing-visual-basic-with-mstest.md).

È possibile scegliere linguaggi diversi per le librerie di classi e le librerie di unit test. Le istruzioni, per le varie combinazioni, sono disponibili nelle procedure dettagliate indicate in precedenza.

* Visual Studio Enterprise offre ottimi strumenti di test per .NET Core. Per altre informazioni vedere [Live Unit Testing](/visualstudio/test/live-unit-testing) o l'argomento relativo al [code coverage](https://github.com/Microsoft/vstest-docs/blob/master/docs/analyze.md#working-with-code-coverage).
* Per altre informazioni e per esempi sull'uso del filtro degli unit test selettivi, vedere [Esecuzione di unit test selettivi](selective-unit-tests.md) o [Including and excluding tests with Visual Studio](/visualstudio/test/live-unit-testing#including-and-excluding-test-projects-and-test-methods) (Inclusione ed esclusione di test con Visual Studio).
* Il team di xUnit ha scritto un'esercitazione che illustra [come usare xUnit con .NET Core e Visual Studio](http://xunit.github.io/docs/getting-started-dotnet-core.html).
