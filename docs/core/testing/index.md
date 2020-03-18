---
title: Testing unità in .NET Core e .NET Standard
description: Questo articolo offre una breve panoramica del testing unità per i progetti .NET Core e .NET Standard.
author: ardalis
ms.author: wiwagn
ms.date: 08/30/2017
ms.openlocfilehash: 1263bfe337b9d6609c0ca7df70aa299a61a7f1a0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "78157401"
---
# <a name="unit-testing-in-net-core-and-net-standard"></a>Testing unità in .NET Core e .NET Standard

Con .NET Core creare unit test è semplice. Questo articolo include un'introduzione agli unit test e ne descrive le differenze rispetto ad altri tipi di test. Le risorse di collegamento riportate in fondo alla pagina contengono informazioni su come aggiungere un progetto di test alla soluzione. Dopo aver configurato il progetto di test, sarà possibile eseguire gli unit test usando la riga di comando o Visual Studio.

Se si sta testando un progetto **ASP.NET Core,** vedere Test di [integrazione in ASP.NET Core](/aspnet/core/test/integration-tests#test-app-prerequisites).

In .NET Core 2.0 e versioni successive è supportato [.NET Standard 2.0](../../standard/net-standard.md), le cui librerie saranno usate per eseguire una dimostrazione degli unit test.

Come punto di partenza per il progetto personale, è possibile usare i modelli di progetto di unit test predefiniti in .NET Core 2.0 e versioni successive per C#, F# e Visual Basic.

## <a name="what-are-unit-tests"></a>Cosa sono gli unit test?

Usare test automatizzati è un'ottima scelta per verificare che un'applicazione software esegua le operazioni per la quale è stata sviluppata. Esistono più tipi di test per le applicazioni software, tra cui test di integrazione, test Web, test di carico e altri tipi. Gli **unit test** consentono di testare singoli componenti software e metodi. Gli unit test devono essere usati solo per eseguire il test del codice sotto il controllo dello sviluppatore. Non è consigliabile usarli per risolvere problemi che riguardano l'infrastruttura, vale a dire database, file system e risorsa di rete.

È anche utile ricordare che esistono procedure consigliate per la scrittura dei test. Ad esempio, si parla di [sviluppo basato su test (TDD, Test Driven Development) ](https://deviq.com/test-driven-development/) quando si scrive uno unit test prima di sapere che il codice sarà sottoposto a controllo. Il TTD è paragonabile alla stesura di uno schema prima di iniziare a scrivere un libro. Lo scopo del TDD è aiutare gli sviluppatori a creare un codice più semplice, leggibile ed efficiente.

> [!NOTE]
> lI team di ASP.NET segue [queste convenzioni](https://github.com/dotnet/aspnetcore/wiki/Engineering-guidelines#unit-tests-and-functional-tests) per aiutare gli sviluppatori a usare nomi appropriati per classi di test e metodi.

Quando si scrivono unit test, è consigliabile non introdurre dipendenze dall'infrastruttura. Le dipendenze rendono i test lenti e instabili. È consigliabile usarli solo con test di integrazione. È possibile evitare queste dipendenze nell'applicazione seguendo il [principio delle dipendenze esplicite](https://deviq.com/explicit-dependencies-principle/) e usando la tecnica di [inserimento delle dipendenze](/aspnet/core/fundamentals/dependency-injection). È anche possibile mantenere gli unit test in un progetto separato rispetto ai test di integrazione. In questo modo il progetto di unit test non avrà riferimenti o dipendenze dai pacchetti dell'infrastruttura.

## <a name="next-steps"></a>Passaggi successivi

Altre informazioni sul testing unità sono disponibili nei progetti .NET Core:

I progetti di unit test .NET Core sono supportati per i linguaggi seguenti:

- [C #](../../csharp/index.yml)
- [F #](../../fsharp/index.yml)
- [Visual Basic](../../visual-basic/index.yml)

È anche possibile scegliere tra le opzioni seguenti:

- [xUnit](https://xunit.github.io)
- [NUnit](https://nunit.org)
- [MSTest](https://github.com/Microsoft/testfx-docs)

Altre informazioni sono disponibili nelle procedure dettagliate seguenti:

- Creare unit test con [*xUnit* e *C#* con l'interfaccia della riga di comando di .NET Core](unit-testing-with-dotnet-test.md).
- Creare unit test con [*NUnit* e *C#* con l'interfaccia della riga di comando di .NET Core](unit-testing-with-nunit.md).
- Creare unit test con [*MSTest* e *C#* con l'interfaccia della riga di comando di .NET Core](unit-testing-with-mstest.md).
- Creare unit test con [*xUnit* e *F#* con l'interfaccia della riga di comando di .NET Core](unit-testing-fsharp-with-dotnet-test.md).
- Creare unit test con [*NUnit* e *F#* con l'interfaccia della riga di comando di .NET Core](unit-testing-fsharp-with-nunit.md).
- Creare unit test con [*MSTest* e *F#* con l'interfaccia della riga di comando di .NET Core](unit-testing-fsharp-with-mstest.md).
- Creare unit test con [*xUnit* e *Visual Basic* con l'interfaccia della riga di comando di .NET Core](unit-testing-visual-basic-with-dotnet-test.md).
- Creare unit test con [*NUnit* e *Visual Basic* con l'interfaccia della riga di comando di .NET Core](unit-testing-visual-basic-with-nunit.md).
- Creare unit test con [*MSTest* e *Visual Basic* con l'interfaccia della riga di comando di .NET Core](unit-testing-visual-basic-with-mstest.md).

Altre informazioni sono disponibili negli articoli seguenti:

- Visual Studio Enterprise offre ottimi strumenti di test per .NET Core. Per altre informazioni vedere [Live Unit Testing](/visualstudio/test/live-unit-testing) o l'argomento relativo al [code coverage](https://github.com/Microsoft/vstest-docs/blob/master/docs/analyze.md#working-with-code-coverage).
- Per altre informazioni su come eseguire unit test selettivi, vedere [Esecuzione di unit test selettivi](selective-unit-tests.md) o [Includere ed escludere test con Visual Studio](/visualstudio/test/live-unit-testing#include-and-exclude-test-projects-and-test-methods).
- [How to use xUnit with .NET Core and Visual Studio](https://xunit.github.io/docs/getting-started-dotnet-core.html) (Come usare xUnit con .NET Core e Visual Studio).
