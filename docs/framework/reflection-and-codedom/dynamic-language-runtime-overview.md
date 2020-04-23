---
title: Panoramica su Dynamic Language Runtime | Microsoft Docs
ms.date: 03/30/2017
helpviewer_keywords:
- dynamic language runtime
- IronPython
- DLR
- IronRuby
ms.assetid: f769a271-8aff-4bea-bfab-6160217ce23d
ms.openlocfilehash: a38ed15769d1186ef78733d68d9d8b51b3eb262d
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446902"
---
# <a name="dynamic-language-runtime-overview"></a>Cenni preliminari su Dynamic Language Runtime

*Dynamic Language Runtime* (DLR) è un ambiente di runtime che estende Common Language Runtime (CLR) con un set di servizi per linguaggi dinamici. DLR semplifica lo sviluppo di linguaggi dinamici da eseguire in .NET Framework e l'aggiunta di funzionalità dinamiche ai linguaggi tipizzati in modo statico.

I linguaggi dinamici sono in grado di identificare il tipo di un oggetto in fase di esecuzione, mentre nei linguaggi tipizzati in modo statico quali C# e Visual Basic (quando si usa `Option Explicit On`) i tipi di oggetto devono essere specificati in fase di progettazione. Esempi di linguaggi dinamici sono Lisp, Smalltalk, JavaScript, PHP, Ruby, Python, ColdFusion, Lua, Cobra e Groovy.

La maggior parte dei linguaggi dinamici offre agli sviluppatori i vantaggi seguenti:

- Possibilità di usare un ciclo di commenti rapido (REPL o ciclo Read–Eval–Print). Ciò consente di immettere diverse istruzioni e di eseguirle immediatamente per vedere i risultati.

- Supporto per lo sviluppo dall'alto verso il basso e per quello più tradizionale dal basso verso l'alto. Ad esempio, quando si usa un approccio dall'alto verso il basso è possibile chiamare le funzioni non ancora implementate e quindi aggiungere le implementazioni sottostanti quando necessario.

- Semplificazione del refactoring e delle modifiche del codice poiché non è necessario modificare le dichiarazioni di tipo statico in tutto il codice.

I linguaggi dinamici sono eccellenti linguaggi di scripting. Grazie ai linguaggi dinamici, i clienti possono estendere facilmente le applicazioni create con nuovi comandi e funzionalità. I linguaggi dinamici sono spesso usati anche per creare siti Web e test harness, gestire server farm, sviluppare varie utilità ed eseguire trasformazioni di dati.

Lo scopo di DLR è consentire l'esecuzione di un sistema di linguaggi dinamici in .NET Framework e garantire a tali linguaggi l'interoperabilità .NET. DLR introduce gli oggetti dinamici in C# e Visual Basic per supportare il comportamento dinamico in questi linguaggi e consentirne l'interoperabilità con i linguaggi dinamici.

DLR consente inoltre di creare librerie che supportano le operazioni dinamiche. Se ad esempio si dispone di una libreria che usa oggetti XML o JavaScript Object Notation (JSON), questi si presenteranno come oggetti dinamici ai linguaggi che usano DLR. Ciò consente agli utenti della libreria di scrivere codice più naturale e più semplice dal punto di vista della sintassi per operare con gli oggetti e accedere ai relativi membri.

Ad esempio, in XML in C# è possibile usare il codice seguente per incrementare un contatore.

`Scriptobj.SetProperty("Count", ((int)GetProperty("Count")) + 1);`

Con DLR è invece possibile usare il codice seguente per la stessa operazione.

`scriptobj.Count += 1;`

Come CLR, DLR è incluso in .NET Framework e viene fornito con i pacchetti di installazione di .NET Framework e Visual Studio. La versione open source di DLR è anche disponibile per il download nel repository [IronLanguages/dlr](https://github.com/IronLanguages/dlr) in GitHub.

> [!NOTE]
> La versione open source di DLR offre tutte le funzionalità della versione inclusa in Visual Studio e .NET Framework. Fornisce inoltre supporto aggiuntivo ai responsabili dell'implementazione del linguaggio. Per altre informazioni, vedere la documentazione nel repository [IronLanguages/dlr](https://github.com/IronLanguages/dlr) in GitHub.

Gli esempi di linguaggi sviluppati mediante l'uso di DLR includono i seguenti:

- IronPython. Disponibile come software open source nel sito Web [GitHub](https://github.com/IronLanguages/ironpython2).

- IronRuby. Disponibile come software open source dal sito Web [IronRuby](http://ironruby.net/) .

## <a name="primary-dlr-advantages"></a>Vantaggi principali di DLR
 DLR offre i vantaggi seguenti.

### <a name="simplifies-porting-dynamic-languages-to-the-net-framework"></a>Semplifica la portabilità dei linguaggi dinamici in .NET Framework
 Grazie a DLR, i responsabili dell'implementazione del linguaggio possono evitare la creazione di analizzatori lessicali, parser, analizzatori semantici, generatori di codice e di altri strumenti che di norma sono tenuti a creare. Per usare DLR, un linguaggio deve produrre *alberi delle espressioni* che rappresentano il codice a livello di linguaggio in una struttura ad albero, routine di supporto del runtime e oggetti dinamici facoltativi che implementano l'interfaccia <xref:System.Dynamic.IDynamicMetaObjectProvider>. DLR e .NET Framework automatizzano molte attività di analisi e generazione del codice. Ciò consente ai responsabili dell'implementazione del linguaggio di concentrarsi sulle funzionalità peculiari del linguaggio.

### <a name="enables-dynamic-features-in-statically-typed-languages"></a>Abilita le funzionalità dinamiche nei linguaggi tipizzati in modo statico
 I linguaggi .NET Framework esistenti, ad esempio C# e Visual Basic, sono in grado di creare oggetti dinamici e di usarli insieme a oggetti tipizzati in modo statico. Ad esempio, C# e Visual Basic usano oggetti dinamici per HTML, Document Object Model (DOM) e la reflection .NET.

### <a name="provides-future-benefits-of-the-dlr-and-net-framework"></a>Offre i vantaggi futuri di DLR e .NET Framework
 I linguaggi implementati tramite DLR trarranno vantaggio dai miglioramenti che in futuro saranno apportati a DLR e .NET Framework. Se ad esempio viene rilasciata una nuova versione di .NET Framework che include un Garbage Collector migliorato o tempi di caricamento delle assembly più rapidi, i linguaggi implementati tramite DLR beneficeranno immediatamente dello stesso vantaggio. Se DLR viene ottimizzato, ad esempio con una migliore funzionalità di compilazione, le prestazioni miglioreranno anche per tutti i linguaggi implementati tramite DLR.

### <a name="enables-sharing-of-libraries-and-objects"></a>Abilita la condivisione di librerie e oggetti
 Gli oggetti e le librerie implementati in un linguaggio possono essere usati da altri linguaggi. DLR consente inoltre l'interoperabilità tra linguaggi tipizzati in modo statico e dinamici. Ad esempio, C# può dichiarare un oggetto dinamico che usa una libreria scritta in un linguaggio dinamico. Allo stesso tempo, i linguaggi dinamici possono usare le librerie di .NET Framework.

### <a name="provides-fast-dynamic-dispatch-and-invocation"></a>Offre funzionalità di invio e chiamata veloci e dinamiche
 DLR consente l'esecuzione veloce di operazioni dinamiche tramite il supporto di un'avanzata funzionalità polimorfica di memorizzazione nella cache. DLR crea regole per associare le operazioni che usano oggetti alle necessarie implementazioni in fase di esecuzione e quindi le memorizza nella cache per evitare che durante le esecuzioni successive dello stesso codice sugli stessi tipi di oggetti vengano eseguiti calcoli di associazione onerosi in termini di uso delle risorse.

## <a name="dlr-architecture"></a>Architettura di DLR
 Nella figura seguente viene illustrata l'architettura di Dynamic Language Runtime.

 ![Panoramica dell'architettura di Dynamic Language Runtime](./media/dlr-archoverview.png "DLR_ArchOverview") Architettura DLR

 DLR estende CLR con un set di servizi in grado di supportare in modo più efficiente i linguaggi dinamici. Di seguito sono indicati alcuni servizi disponibili:

- Alberi delle espressioni. DLR usa gli alberi delle espressioni per rappresentare la semantica del linguaggio. A questo scopo, DLR ha esteso gli alberi dell'espressione LINQ affinché includano il flusso di controllo, l'assegnazione e altri nodi di modellazione del linguaggio. Per altre informazioni, vedere [Alberi delle espressioni (C#)](../../csharp/programming-guide/concepts/expression-trees/index.md) o [Alberi delle espressioni (Visual Basic)](../../visual-basic/programming-guide/concepts/expression-trees/index.md).

- Memorizzazione nella cache del sito di chiamata. Un *sito di chiamata dinamica* è un punto nel codice in cui si esegue un'operazione come `a + b` o `a.b()` su oggetti dinamici. DLR memorizza nella cache le caratteristiche di `a` e `b` (in genere i tipi di questi oggetti) e le informazioni sull'operazione. Se questa operazione è stata eseguita in precedenza, DLR recupera tutte le informazioni necessarie dalla cache per l'invio rapido.

- Interoperabilità con gli oggetti dinamici. DLR offre un set di classi e interfacce che rappresentano operazioni e oggetti dinamici e che possono essere usate dai responsabili dell'implementazione del linguaggio e dagli autori di librerie dinamiche. Queste classi e interfacce includono <xref:System.Dynamic.IDynamicMetaObjectProvider>, <xref:System.Dynamic.DynamicMetaObject>, <xref:System.Dynamic.DynamicObject> e <xref:System.Dynamic.ExpandoObject>.

DLR usa i binder nei siti di chiamata per comunicare non solo con .NET Framework, ma anche con altri servizi e infrastrutture, tra cui Silverlight e COM. I binder incapsulano la semantica di un linguaggio e specificano la modalità di esecuzione delle operazioni in un sito di chiamata usando gli alberi delle espressioni. Ciò consente ai linguaggi dinamici e a quelli tipizzati in modo statico che usano DLR di condividere le librerie e di accedere a tutte le tecnologie supportate da DLR.

## <a name="dlr-documentation"></a>Documentazione di DLR
 Per altre informazioni su come usare la versione open source di DLR per aggiungere il comportamento dinamico a un linguaggio o su come abilitare l'uso di un linguaggio dinamico con .NET Framework, vedere la documentazione nel repository [IronLanguages/dlr](https://github.com/IronLanguages/dlr/tree/master/Docs) in GitHub.

## <a name="see-also"></a>Vedere anche

- <xref:System.Dynamic.ExpandoObject>
- <xref:System.Dynamic.DynamicObject>
- [Common Language Runtime](../../standard/clr.md)
- [Alberi delle espressioni (C#)](../../csharp/programming-guide/concepts/expression-trees/index.md)
- [Alberi delle espressioni (Visual Basic)](../../visual-basic/programming-guide/concepts/expression-trees/index.md)
- [Procedura dettagliata: creazione e utilizzo di oggetti dinamici](../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md)
