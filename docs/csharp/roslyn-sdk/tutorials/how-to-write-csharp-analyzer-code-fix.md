---
title: 'Esercitazione: compilare il primo analizzatore con correzione del codice'
description: In questa esercitazione vengono fornite istruzioni dettagliate per creare un analizzatore e una correzione del codice con .NET Compiler Platform SDK (API Roslyn).
ms.date: 08/01/2018
ms.custom: mvc
ms.openlocfilehash: 23ebf4befc75e08592890d85f2dda51251f59cd6
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396287"
---
# <a name="tutorial-write-your-first-analyzer-and-code-fix"></a>Esercitazione: compilare il primo analizzatore con correzione del codice

.NET Compiler Platform SDK fornisce gli strumenti necessari per creare avvisi personalizzati destinati a codice C# o Visual Basic. L'**analizzatore** contiene il codice che riconosce le violazioni della regola. La **correzione del codice** contiene il codice che corregge la violazione. Le regole implementate possono essere di qualsiasi tipo: struttura del codice, stile di codifica, convenzioni di denominazione e altro ancora. .NET Compiler Platform fornisce il framework per l'esecuzione di analisi mentre gli sviluppatori scrivono il codice e tutte le funzionalità dell'interfaccia utente di Visual Studio per la correzione del codice: visualizzazione di linee ondulate nell'editor, informazioni dell'Elenco errori di Visual Studio, creazione di suggerimenti "lampadina" e visualizzazione di un'anteprima dettagliata delle correzioni suggerite.

In questa esercitazione verrà esaminata la creazione di un **analizzatore** e una **correzione del codice** associato usando le API Roslyn. Un analizzatore è un modo per eseguire analisi del codice sorgente e segnalare un problema all'utente. Facoltativamente, un analizzatore può anche fornire una correzione del codice che rappresenta una modifica del codice sorgente per l'utente. In questa esercitazione verrà creato un analizzatore per trovare le dichiarazioni di variabili locali che potrebbero essere dichiarate tramite il modificatore `const` ma che lo non sono. La correzione del codice associata modifica tali dichiarazioni per aggiungere il modificatore `const`.

## <a name="prerequisites"></a>Prerequisiti

- [Visual Studio 2017](https://visualstudio.microsoft.com/vs/older-downloads/#visual-studio-2017-and-other-products)
- [Visual Studio 2019](https://www.visualstudio.com/downloads)

È necessario installare **.NET Compiler Platform SDK** tramite il programma di installazione di Visual Studio:

[!INCLUDE[interactive-note](~/includes/roslyn-installation.md)]

La creazione e la convalida dell'analizzatore comprendono diversi passaggi:

1. Creare la soluzione.
1. Registrare il nome e la descrizione dell'analizzatore.
1. Segnalare gli avvisi e i suggerimenti dell'analizzatore.
1. Implementare la correzione del codice per accettare i suggerimenti.
1. Migliorare l'analisi tramite unit test.

## <a name="explore-the-analyzer-template"></a>Esplorare il modello dell'analizzatore

L'analizzatore segnala all'utente eventuali dichiarazioni di variabili locali che possono essere convertite in costanti locali. Si consideri il codice di esempio seguente:

```csharp
int x = 0;
Console.WriteLine(x);
```

Nel codice precedente, a `x` viene assegnato un valore costante che non viene mai modificato. Può essere dichiarato usando il modificatore `const`:

```csharp
const int x = 0;
Console.WriteLine(x);
```

Per determinare se una variabile può essere resa una costante, è necessaria un'analisi che richiede un'analisi sintattica, l'analisi delle costanti dell'espressione dell'inizializzatore e l'analisi del flusso di dati per garantire che non vengano mai eseguite operazioni di scrittura nella variabile. .NET Compiler Platform fornisce API che rendono più semplice l'esecuzione di questa analisi. Il primo passaggio consiste nel creare un nuovo progetto di **analizzatore con correzione del codice** C#.

- In Visual Studio scegliere **File > Nuovo > Progetto** per visualizzare la finestra di dialogo Nuovo progetto.
- In **Visual C# > Estendibilità** scegliere **Analyzer with code fix (.NET Standard)** (Analizzatore con correzione del codice - .NET Standard).
- Assegnare al progetto il nome "**MakeConst**" e fare clic su OK.

Il modello di analizzatore con correzione del codice crea tre progetti: uno contiene l'analizzatore e la correzione del codice, il secondo è un progetto unit test e il terzo è il progetto VSIX. Il progetto di avvio predefinito è il progetto VSIX. Premere **F5** per avviare il progetto VSIX. Verrà avviata una seconda istanza di Visual Studio e sarà caricato il nuovo analizzatore.

> [!TIP]
> Quando si esegue l'analizzatore, si avvia una seconda copia di Visual Studio. Questa seconda copia usa un diverso hive del Registro di sistema per archiviare le impostazioni. Questo consente di distinguere le impostazioni di visualizzazione nelle due copie di Visual Studio. È possibile scegliere un tema diverso per l'esecuzione sperimentale di Visual Studio. Inoltre, non eseguire il roaming delle impostazioni o accedere all'account di Visual Studio usando l'istanza sperimentale di Visual Studio. Ciò consente di mantenere diverse le impostazioni.

Nella seconda istanza di Visual Studio appena avviata creare un nuovo progetto di applicazione console C# (.NET Core o .NET Framework progetto funzionerà--Analyzers funziona a livello di origine). Passare il puntatore del mouse sul token con una sottolineatura ondulata e viene visualizzato il testo di avviso fornito da un analizzatore.

Il modello crea un analizzatore che genera un avviso per ogni dichiarazione di tipo in cui il nome del tipo contiene lettere minuscole, come illustrato nella figura seguente:

![Avviso di segnalazione dell'analizzatore](media/how-to-write-csharp-analyzer-code-fix/report-warning.png)

Il modello fornisce inoltre una correzione del codice che converte in lettere maiuscole qualsiasi nome di un tipo contenente caratteri minuscoli. È possibile fare clic sulla lampadina visualizzata con il messaggio di avviso per vedere le modifiche suggerite. Accettando le modifiche suggerite, vengono aggiornati il nome del tipo e tutti i riferimenti a tale tipo nella soluzione. Dopo aver osservato l'analizzatore iniziale in azione, chiudere la seconda istanza di Visual Studio e tornare al progetto dell'analizzatore.

Non è necessario avviare una seconda copia di Visual Studio e creare nuovo codice per testare ogni modifica nell'analizzatore. Il modello crea automaticamente anche un progetto unit test. Tale progetto contiene due test. `TestMethod1` illustra il formato tipico di un test che analizza il codice senza attivare la diagnostica. `TestMethod2` illustra il formato di un test che attiva la diagnostica e quindi applica una correzione del codice suggerita. Durante la creazione dell'analizzatore e della correzione del codice, si scriveranno i test per le diverse strutture di codice per verificare il proprio lavoro. Gli unit test per gli analizzatori sono molto più rapidi rispetto ai test in modalità interattiva con Visual Studio.

> [!TIP]
> Gli unit test per gli analizzatori sono uno strumento molto utile quando si sa quali costrutti di codice devono attivare o meno l'analizzatore. Il caricamento dell'analizzatore in un'altra copia di Visual Studio è una soluzione ideale per esplorare e trovare costrutti a cui ancora non si è pensato.

## <a name="create-analyzer-registrations"></a>Creare registrazioni per l'analizzatore

Il modello crea la classe `DiagnosticAnalyzer` iniziale nel file **MakeConstAnalyzer.cs**. Questo analizzatore iniziale mostra due importanti proprietà di ogni analizzatore.

- Ogni analizzatore diagnostico deve fornire un attributo `[DiagnosticAnalyzer]` che descrive il linguaggio su cui opera.
- Ogni analizzatore diagnostico deve derivare dalla classe <xref:Microsoft.CodeAnalysis.Diagnostics.DiagnosticAnalyzer>.

Il modello illustra anche le funzionalità di base che fanno parte di qualsiasi analizzatore:

1. Registrare le azioni. Le azioni rappresentano le modifiche del codice che devono attivare l'analizzatore per esaminare le violazioni del codice. Quando Visual Studio rileva modifiche del codice che corrispondono a un'azione registrata, esegue una chiamata al metodo registrato dell'analizzatore.
1. Creare la diagnostica. Quando l'analizzatore rileva una violazione, crea un oggetto di diagnostica usato da Visual Studio per notificare all'utente la violazione.

Le azioni vengono registrate nell'override del metodo <xref:Microsoft.CodeAnalysis.Diagnostics.DiagnosticAnalyzer.Initialize(Microsoft.CodeAnalysis.Diagnostics.AnalysisContext)?displayProperty=nameWithType>. In questa esercitazione verranno esaminati i **nodi di sintassi** alla ricerca delle dichiarazioni locali, per determinare quali di queste hanno valori costanti. Se una dichiarazione può essere costante, l'analizzatore crea e segnala una diagnostica.

Il primo passaggio consiste nell'aggiornare le costanti di registrazione e il metodo `Initialize`, in modo che queste costanti specifichino l'analizzatore "MakeConst". La maggior parte delle costanti di stringa è definita nel file della risorsa stringa. È consigliabile attenersi a tale pratica per semplificare l'individuazione. Aprire il file **Resources.resx** per il progetto dell'analizzatore **MakeConst**. Verrà visualizzato l'editor di risorse. Aggiornare le risorse stringa come segue:

- Modificare `AnalyzerTitle` in "Variable can be made constant".
- Modificare `AnalyzerMessageFormat` in "Can be made constant".
- Modificare `AnalyzerDescription` in "Make Constant".

Modificare inoltre l'elenco a discesa **Modificatore di accesso** in `public`. Ciò rende più semplice usare queste costanti negli unit test. Al termine, l'editor di risorse dovrebbe apparire come mostrato di seguito:

![Aggiornare le risorse stringa](media/how-to-write-csharp-analyzer-code-fix/update-string-resources.png)

Le modifiche rimanenti sono da apportare al file dell'analizzatore. Aprire **MakeConstAnalyzer.cs** in Visual Studio. Modificare l'azione registrata da una che opera sui simboli in una che opera sulla sintassi. Nel metodo `MakeConstAnalyzerAnalyzer.Initialize` trovare la riga che esegue la registrazione dell'azione sui simboli:

```csharp
context.RegisterSymbolAction(AnalyzeSymbol, SymbolKind.NamedType);
```

Sostituirla con la riga seguente:

[!code-csharp[Register the node action](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst/MakeConstAnalyzer.cs#RegisterNodeAction "Register a node action")]

Dopo questa modifica, è possibile eliminare il metodo `AnalyzeSymbol`. Questo analizzatore esamina le istruzioni <xref:Microsoft.CodeAnalysis.CSharp.SyntaxKind.LocalDeclarationStatement?displayProperty=nameWithType>, non le istruzioni <xref:Microsoft.CodeAnalysis.SymbolKind.NamedType?displayProperty=nameWithType>. È possibile notare che sotto `AnalyzeNode` sono visualizzate delle linee ondulate. Il codice appena aggiunto fa riferimento a un metodo `AnalyzeNode` che non è stato dichiarato. Dichiarare tale metodo usando il codice seguente:

```csharp
private void AnalyzeNode(SyntaxNodeAnalysisContext context)
{
}
```

Modificare `Category` in "Usage" in **MakeConstAnalyzer.cs**, come illustrato nel codice seguente:

```csharp
private const string Category = "Usage";
```

## <a name="find-local-declarations-that-could-be-const"></a>Trovare le dichiarazioni locali che potrebbero essere costanti

È ora possibile scrivere la prima versione del metodo `AnalyzeNode`. Deve cercare una singola dichiarazione locale che può essere `const` ma non lo è, come ad esempio il codice seguente:

```csharp
int x = 0;
Console.WriteLine(x);
```

Il primo passaggio è trovare le dichiarazioni locali. Aggiungere il codice seguente a `AnalyzeNode` in **MakeConstAnalyzer.cs**:

```csharp
var localDeclaration = (LocalDeclarationStatementSyntax)context.Node;
```

Questo cast ha sempre esito positivo, perché l'analizzatore ha eseguito la registrazione per le modifiche delle dichiarazioni locali e solo per le dichiarazioni locali. Nessun altro tipo di nodo attiva una chiamata al metodo `AnalyzeNode`. Controllare quindi se nella dichiarazione sono presenti modificatori `const`. Se vengono rilevati, restituire immediatamente un risultato. Il codice seguente cerca eventuali modificatori `const` nella dichiarazione locale:

```csharp
// make sure the declaration isn't already const:
if (localDeclaration.Modifiers.Any(SyntaxKind.ConstKeyword))
{
    return;
}
```

Infine, è necessario verificare che la variabile possa essere `const`. In altre parole, occorre verificare che non venga mai assegnata dopo l'inizializzazione.

Si eseguiranno alcune analisi semantiche usando <xref:Microsoft.CodeAnalysis.Diagnostics.SyntaxNodeAnalysisContext>. Verrà usato l'argomento `context` per determinare se la dichiarazione di variabile locale può essere resa `const`. Un oggetto <xref:Microsoft.CodeAnalysis.SemanticModel?displayProperty=nameWithType> rappresenta tutte le informazioni semantiche in un singolo file di origine. Per altre informazioni, vedere l'articolo relativo ai [modelli semantici](../work-with-semantics.md). Si userà <xref:Microsoft.CodeAnalysis.SemanticModel?displayProperty=nameWithType> per eseguire l'analisi del flusso dei dati nell'istruzione della dichiarazione locale. Sarà quindi possibile usare i risultati di questa analisi del flusso di dati per assicurarsi che non venga mai eseguita la scrittura di un nuovo valore nella variabile locale. Chiamare il metodo di estensione <xref:Microsoft.CodeAnalysis.ModelExtensions.GetDeclaredSymbol%2A> per recuperare <xref:Microsoft.CodeAnalysis.ILocalSymbol> per la variabile e verificare che non sia contenuto nella raccolta <xref:Microsoft.CodeAnalysis.DataFlowAnalysis.WrittenOutside%2A?displayProperty=nameWithType> dell'analisi del flusso di dati. Aggiungere il codice seguente alla fine del metodo `AnalyzeNode`:

```csharp
// Perform data flow analysis on the local declaration.
var dataFlowAnalysis = context.SemanticModel.AnalyzeDataFlow(localDeclaration);

// Retrieve the local symbol for each variable in the local declaration
// and ensure that it is not written outside of the data flow analysis region.
var variable = localDeclaration.Declaration.Variables.Single();
var variableSymbol = context.SemanticModel.GetDeclaredSymbol(variable);
if (dataFlowAnalysis.WrittenOutside.Contains(variableSymbol))
{
    return;
}
```

Il codice appena aggiunto garantisce che la variabile non viene modificata e quindi può essere resa `const`. È ora possibile generare la diagnostica. Aggiungere il codice seguente come ultima riga in `AnalyzeNode`:

```csharp
context.ReportDiagnostic(Diagnostic.Create(Rule, context.Node.GetLocation()));
```

È possibile controllare lo stato di avanzamento premendo **F5** per eseguire l'analizzatore. È possibile caricare l'applicazione console creata in precedenza e quindi aggiungere il codice di test seguente:

```csharp
int x = 0;
Console.WriteLine(x);
```

Verrà visualizzata la lampadina e l'analizzatore segnalerà la diagnostica. Tuttavia, la lampadina usa ancora la correzione del codice del modello generato e indica che l'elemento può essere reso maiuscolo. Nella sezione successiva viene descritto come scrivere la correzione del codice.

## <a name="write-the-code-fix"></a>Scrivere la correzione del codice

Un analizzatore può fornire una o più correzioni del codice. Una correzione del codice definisce una modifica in grado di risolvere il problema segnalato. Per l'analizzatore che è stato creato, è possibile fornire una correzione del codice che inserisce la parola chiave const:

```csharp
const int x = 0;
Console.WriteLine(x);
```

L'utente la sceglie dall'interfaccia utente della lampadina dell'editor e Visual Studio modifica il codice.

Aprire il file **MakeConstCodeFixProvider.cs** aggiunto dal modello.  Questa correzione del codice è già collegata all'ID di diagnostica prodotto dall'analizzatore di diagnostica, ma non implementa ancora la trasformazione del codice corretta. È innanzitutto necessario rimuovere parte del codice del modello. Modificare la stringa del titolo in "Make constant":

[!code-csharp[Update the CodeFix title](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst/MakeConstCodeFixProvider.cs#CodeFixTitle "Update the CodeFix title")]

Eliminare quindi il metodo `MakeUppercaseAsync`. Tale metodo non è più applicabile.

Tutti i provider di correzione del codice derivano da <xref:Microsoft.CodeAnalysis.CodeFixes.CodeFixProvider> e sostituiscono <xref:Microsoft.CodeAnalysis.CodeFixes.CodeFixProvider.RegisterCodeFixesAsync(Microsoft.CodeAnalysis.CodeFixes.CodeFixContext)?displayProperty=nameWithType> per segnalare le correzioni del codice disponibili. In `RegisterCodeFixesAsync` modificare il tipo di nodo predecessore in cui eseguire la ricerca in <xref:Microsoft.CodeAnalysis.CSharp.Syntax.LocalDeclarationStatementSyntax>, in modo che corrisponda alla diagnostica:

[!code-csharp[Find local declaration node](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst/MakeConstCodeFixProvider.cs#FindDeclarationNode  "Find the local declaration node that raised the diagnostic")]

Modificare quindi l'ultima riga per registrare una correzione del codice. La correzione creerà un nuovo documento risultante dall'aggiunta del modificatore `const` a una dichiarazione esistente:

[!code-csharp[Register the new code fix](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst/MakeConstCodeFixProvider.cs#RegisterCodeFix  "Register the new code fix")]

Si noteranno delle sottolineature rosse ondulate nel codice appena aggiunto sul simbolo `MakeConstAsync`. Aggiungere una dichiarazione per `MakeConstAsync`, come il codice seguente:

```csharp
private async Task<Document> MakeConstAsync(Document document,
   LocalDeclarationStatementSyntax localDeclaration,
   CancellationToken cancellationToken)
{
}
```

Il nuovo metodo `MakeConstAsync` trasforma l'oggetto <xref:Microsoft.CodeAnalysis.Document> che rappresenta il file di origine dell'utente in un nuovo <xref:Microsoft.CodeAnalysis.Document> che ora contiene una dichiarazione `const`.

Creare un nuovo token di parola chiave `const` da inserire all'inizio dell'istruzione di dichiarazione. Prestare attenzione a rimuovere eventuali elementi semplici iniziali dal primo token dell'istruzione di dichiarazione e associarlo al token `const`. Aggiungere il codice seguente al metodo `MakeConstAsync`:

[!code-csharp[Create a new const keyword token](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst/MakeConstCodeFixProvider.cs#CreateConstToken  "Create the new const keyword token")]

Aggiungere quindi il token `const` alla dichiarazione mediante il codice seguente:

```csharp
// Insert the const token into the modifiers list, creating a new modifiers list.
var newModifiers = trimmedLocal.Modifiers.Insert(0, constToken);
// Produce the new local declaration.
var newLocal = trimmedLocal
    .WithModifiers(newModifiers)
    .WithDeclaration(localDeclaration.Declaration);
```

Formattare la nuova dichiarazione in modo che corrisponda alle regole di formattazione di C#. La formattazione delle modifiche in modo che corrispondano al codice esistente consente di migliorare l'esperienza. Aggiungere l'istruzione seguente subito dopo il codice esistente:

[!code-csharp[Format the new declaration](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst/MakeConstCodeFixProvider.cs#FormatLocal  "Format the new declaration")]

È necessario un nuovo spazio dei nomi per il codice. Aggiungere la `using` direttiva seguente all'inizio del file:

```csharp
using Microsoft.CodeAnalysis.Formatting;
```

Il passaggio finale consiste nell'apportare la modifica. Questo processo comprende tre passaggi:

1. Ottenere un handle per il documento esistente.
1. Creare un nuovo documento, sostituendo la dichiarazione esistente con la nuova dichiarazione.
1. Restituire il nuovo documento.

Aggiungere il codice seguente alla fine del metodo `MakeConstAsync`:

[!code-csharp[replace the declaration](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst/MakeConstCodeFixProvider.cs#ReplaceDocument  "Generate a new document by replacing the declaration")]

A questo punto, è possibile provare la correzione del codice.  Premere F5 per eseguire il progetto dell'analizzatore in una seconda istanza di Visual Studio. Nella seconda istanza di Visual Studio creare un nuovo progetto di applicazione console C# e aggiungere alcune dichiarazioni di variabili locali inizializzate con valori costanti al metodo Main. Si noterà che vengono segnalate come avvisi, come indicato di seguito.

![Avvisi relativi alla possibilità di usare una costante](media/how-to-write-csharp-analyzer-code-fix/make-const-warning.png)

Sono stati compiuti notevoli progressi. Sono presenti linee ondulate sotto le dichiarazioni che possono essere rese `const`. Ma c'è ancora qualche operazione da eseguire. Questa soluzione funziona se si aggiunge `const` a dichiarazioni che iniziano con `i`, quindi con `j` e infine con `k`. Tuttavia, se si aggiunge il modificatore `const` in un ordine diverso, a partire da `k`, l'analizzatore genera errori: `k` non può essere dichiarato `const`, a meno che `i` e `j` non siano già entrambi `const`. È necessario eseguire altre analisi per poter gestire i diversi modi in cui possono essere dichiarate e inizializzate le variabili.

## <a name="build-data-driven-tests"></a>Compilare test basati sui dati

L'analizzatore e la correzione del codice funzionano nel caso semplice di una singola dichiarazione che può essere resa const. Vi sono numerose possibili istruzioni di dichiarazione in cui questa implementazione genera errori. Questi casi possono essere gestiti usando la libreria di unit test scritta dal modello. È molto più veloce che aprire ripetutamente una seconda copia di Visual Studio.

Aprire il file **MakeConstUnitTests.cs** nel progetto di unit test. Il modello ha creato due test che seguono i due modelli comuni per gli unit test di un analizzatore e una correzione del codice. `TestMethod1` illustra il modello per un test che assicura l'analizzatore non segnali una diagnostica quando non deve. `TestMethod2` illustra il modello per la segnalazione di una diagnostica e l'esecuzione della correzione del codice.

Il codice per quasi ogni test dell'analizzatore segue uno di questi due modelli. Per il primo passaggio, è possibile rielaborare questi test come test basati sui dati. Sarà quindi possibile creare facilmente nuovi test mediante l'aggiunta di nuove costanti stringa per rappresentare diversi input di test.

Per motivi di efficienza, il primo passaggio consiste nel refactoring dei due test come test basati sui dati. Sarà quindi sufficiente definire due costanti stringa per ogni nuovo test. Durante il refactoring, rinominare entrambi i metodi in nomi migliori. Sostituire `TestMethod1` con questo test, che assicura che non venga generata la diagnostica:

```csharp
[DataTestMethod]
[DataRow("")]
public void WhenTestCodeIsValidNoDiagnosticIsTriggered(string testCode)
{
    VerifyCSharpDiagnostic(testCode);
}
```

È possibile creare una nuova riga di dati per questo test definendo un frammento di codice che non deve causare l'attivazione di un avviso di diagnostica. Questo overload di `VerifyCSharpDiagnostic` ha esito positivo quando non viene attivata alcuna diagnostica per il frammento di codice sorgente.

Sostituire quindi `TestMethod2` con questo test, che assicura che venga generata una diagnostica e applicata una correzione del codice per il frammento di codice sorgente:

```csharp
[DataTestMethod]
[DataRow(LocalIntCouldBeConstant, LocalIntCouldBeConstantFixed, 10, 13)]
public void WhenDiagnosticIsRaisedFixUpdatesCode(
    string test,
    string fixTest,
    int line,
    int column)
{
    var expected = new DiagnosticResult
    {
        Id = MakeConstAnalyzer.DiagnosticId,
        Message = new LocalizableResourceString(nameof(MakeConst.Resources.AnalyzerMessageFormat), MakeConst.Resources.ResourceManager, typeof(MakeConst.Resources)).ToString(),
        Severity = DiagnosticSeverity.Warning,
        Locations =
            new[] {
                    new DiagnosticResultLocation("Test0.cs", line, column)
                }
    };

    VerifyCSharpDiagnostic(test, expected);

    VerifyCSharpFix(test, fixTest);
}
```

Il codice precedente apporta anche due modifiche al codice che genera il risultato di diagnostica previsto. Usa le costanti pubbliche registrate nell'analizzatore `MakeConst`. Usa inoltre due costanti stringa per l'origine di input e fissa. Aggiungere le costanti stringa seguenti alla classe `UnitTest`:

[!code-csharp[string constants for fix test](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#FirstFixTest "string constants for fix test")]

Eseguire i due test per assicurarsi che vengano superati. In Visual Studio aprire **Esplora test** selezionando **Test** > **Windows** > **Esplora test**.  Fare clic sul collegamento **Esegui tutto**.

## <a name="create-tests-for-valid-declarations"></a>Creare test per le dichiarazioni valide

Come regola generale, gli analizzatori devono essere chiusi appena possibile ed eseguire attività minime. Visual Studio esegue chiamate agli analizzatori registrati mentre l'utente modifica il codice. La velocità di risposta è un requisito essenziale. Esistono diversi casi di test per il codice che non devono generare la diagnostica. L'analizzatore gestisce già uno di tali test, il caso in cui una variabile viene assegnata dopo l'inizializzazione. Aggiungere la seguente costante stringa ai test per rappresentare tale caso:

[!code-csharp[variable assigned](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#VariableAssigned "a variable that is assigned after being initialized won't raise the diagnostic")]

Aggiungere quindi una riga di dati per questo test, come illustrato nel frammento di codice seguente:

```csharp
[DataTestMethod]
[DataRow(""),
 DataRow(VariableAssigned)]
public void WhenTestCodeIsValidNoDiagnosticIsTriggered(string testCode)
```

Anche questo test ha esito positivo. Aggiungere le costanti per le condizioni che non sono ancora state gestite:

- Dichiarazioni che sono già `const`, perché sono già costanti:

   [!code-csharp[already const declaration](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#AlreadyConst "a declaration that is already const should not raise the diagnostic")]

- Dichiarazioni senza alcun inizializzatore, perché non è presente alcun valore da usare:

   [!code-csharp[declarations that have no initializer](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#NoInitializer "a declaration that has no initializer should not raise the diagnostic")]

- Dichiarazioni in cui l'inizializzatore non è una costante, perché non possono essere costanti in fase di compilazione:

   [!code-csharp[declarations where the initializer isn't const](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#InitializerNotConstant "a declaration where the initializer is not a compile-time constant should not raise the diagnostic")]

Può essere ancora più complicato perché C# consente più dichiarazioni come un'unica istruzione. Prendere in considerazione la costante stringa di test case seguente:

[!code-csharp[multiple initializers](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#MultipleInitializers "A declaration can be made constant only if all variables in that statement can be made constant")]

La variabile `i` può essere resa costante, ma per la variabile `j` non è possibile. Questa istruzione non può quindi essere resa una dichiarazione const. Aggiungere le dichiarazioni `DataRow` per tutti questi test:

```csharp
[DataTestMethod]
[DataRow(""),
    DataRow(VariableAssigned),
    DataRow(AlreadyConst),
    DataRow(NoInitializer),
    DataRow(InitializerNotConstant),
    DataRow(MultipleInitializers)]
public void WhenTestCodeIsValidNoDiagnosticIsTriggered(string testCode)
```

Eseguendo nuovamente i test, si noterà che i nuovi test case hanno esito negativo.

## <a name="update-your-analyzer-to-ignore-correct-declarations"></a>Aggiornare l'analizzatore per ignorare le dichiarazioni corrette

Sono necessari alcuni miglioramenti del metodo `AnalyzeNode` dell'analizzatore per filtrare le code che soddisfano queste condizioni. Sono tutte condizioni correlate, di conseguenza modifiche simili consentiranno di correggere tutte le condizioni. Modificare `AnalyzeNode` nel modo seguente:

- L'analisi semantica ha esaminato una singola dichiarazione di variabile. Questo codice deve essere inserito in un ciclo `foreach`, che esamina tutte le variabili dichiarate nella stessa istruzione.
- Ogni variabile dichiarata deve avere un inizializzatore.
- L'inizializzatore di ogni variabile dichiarata deve essere una costante in fase di compilazione.

Nel metodo `AnalyzeNode` sostituire l'analisi semantica originale:

```csharp
// Perform data flow analysis on the local declaration.
var dataFlowAnalysis = context.SemanticModel.AnalyzeDataFlow(localDeclaration);

// Retrieve the local symbol for each variable in the local declaration
// and ensure that it is not written outside of the data flow analysis region.
var variable = localDeclaration.Declaration.Variables.Single();
var variableSymbol = context.SemanticModel.GetDeclaredSymbol(variable);
if (dataFlowAnalysis.WrittenOutside.Contains(variableSymbol))
{
    return;
}
```

con il frammento di codice seguente:

```csharp
// Ensure that all variables in the local declaration have initializers that
// are assigned with constant values.
foreach (var variable in localDeclaration.Declaration.Variables)
{
    var initializer = variable.Initializer;
    if (initializer == null)
    {
        return;
    }

    var constantValue = context.SemanticModel.GetConstantValue(initializer.Value);
    if (!constantValue.HasValue)
    {
        return;
    }
}

// Perform data flow analysis on the local declaration.
var dataFlowAnalysis = context.SemanticModel.AnalyzeDataFlow(localDeclaration);

foreach (var variable in localDeclaration.Declaration.Variables)
{
    // Retrieve the local symbol for each variable in the local declaration
    // and ensure that it is not written outside of the data flow analysis region.
    var variableSymbol = context.SemanticModel.GetDeclaredSymbol(variable);
    if (dataFlowAnalysis.WrittenOutside.Contains(variableSymbol))
    {
        return;
    }
}
```

Il primo ciclo `foreach` esamina ogni dichiarazione di variabile tramite l'analisi sintattica. Il primo controllo garantisce che la variabile disponga di un inizializzatore. Il secondo controllo garantisce che l'inizializzatore sia una costante. Il secondo ciclo contiene l'analisi semantica originale. I controlli semantici sono in un ciclo distinto perché ha un maggiore impatto sulle prestazioni. Eseguendo nuovamente i test, dovrebbero tutti avere esito positivo.

## <a name="add-the-final-polish"></a>Aggiungere le ultime modifiche

La procedura è quasi terminata. Esistono alcune altre condizioni che l'analizzatore deve gestire. Visual Studio esegue chiamate agli analizzatori mentre l'utente scrive il codice. Spesso l'analizzatore viene chiamato per codice che non viene compilato. Il metodo `AnalyzeNode` dell'analizzatore diagnostico non verifica se il valore costante può essere convertito nel tipo variabile. Pertanto, l'implementazione corrente convertirà una dichiarazione errata come int i = "abc"' in una costante locale. Aggiungere una costante stringa di origine per tale condizione:

[!code-csharp[Mismatched types don't raise diagnostics](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#DeclarationIsInvalid "When the variable type and the constant type don't match, there's no diagnostic")]

Inoltre, i tipi di riferimento non sono gestiti correttamente. L'unico valore costante consentito per un tipo di riferimento è `null`, tranne che nel caso di <xref:System.String?displayProperty=nameWithType>, che consente valori letterali stringa. In altre parole, `const string s = "abc"` è consentito, mentre `const object s = "abc"` non lo è. Tale condizione viene verificata da questo frammento di codice:

[!code-csharp[Reference types don't raise diagnostics](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#DeclarationIsntString "When the variable type is a reference type other than string, there's no diagnostic")]

Per completezza, è necessario aggiungere un altro test per assicurarsi che sia possibile creare una dichiarazione di costante per una stringa. Il frammento di codice seguente definisce sia il codice che genera il messaggio di diagnostica che il codice dopo l'applicazione della correzione:

[!code-csharp[string reference types raise diagnostics](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#ConstantIsString "When the variable type is string, it can be constant")]

Infine, se una variabile viene dichiarata con la parola chiave `var`, la correzione esegue l'operazione errata e genera una dichiarazione `const var`, che non è supportata dal linguaggio C#. Per correggere questo bug, la correzione del codice deve sostituire la parola chiave `var` con il nome del tipo dedotto:

[!code-csharp[var references need to use the inferred types](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#VarDeclarations "Declarations made using var must have the type replaced with the inferred type")]

Queste modifiche aggiornano le dichiarazioni delle righe di dati per entrambi i test. Il codice seguente illustra questi test con tutti gli attributi della riga di dati:

[!code-csharp[The finished tests](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst.Test/MakeConstUnitTests.cs#FinishedTests "The finished tests for the make const analyzer")]

Fortunatamente, tutti i bug precedenti possono essere corretti con le stesse tecniche appena descritte.

Per correggere il primo bug, aprire **DiagnosticAnalyzer.cs** e individuare il ciclo foreach in cui viene controllato ognuno degli inizializzatori della dichiarazione locale per garantire che gli vengano assegnati valori costanti. Subito _prima_ del primo ciclo foreach, chiamare `context.SemanticModel.GetTypeInfo()` per recuperare informazioni dettagliate sul tipo dichiarato della dichiarazione locale:

```csharp
var variableTypeName = localDeclaration.Declaration.Type;
var variableType = context.SemanticModel.GetTypeInfo(variableTypeName).ConvertedType;
```

Quindi, all'interno del ciclo `foreach`, controllare ogni inizializzatore per assicurarsi che possa essere convertito nel tipo di variabile. Aggiungere il controllo seguente dopo aver verificato che l'inizializzatore sia una costante:

```csharp
// Ensure that the initializer value can be converted to the type of the
// local declaration without a user-defined conversion.
var conversion = context.SemanticModel.ClassifyConversion(initializer.Value, variableType);
if (!conversion.Exists || conversion.IsUserDefined)
{
    return;
}
```

La modifica successiva si basa su quest'ultima. Prima della parentesi graffa di chiusura del primo ciclo foreach, aggiungere il codice seguente per verificare il tipo di dichiarazione locale quando la costante è una stringa o null.

```csharp
// Special cases:
//  * If the constant value is a string, the type of the local declaration
//    must be System.String.
//  * If the constant value is null, the type of the local declaration must
//    be a reference type.
if (constantValue.Value is string)
{
    if (variableType.SpecialType != SpecialType.System_String)
    {
        return;
    }
}
else if (variableType.IsReferenceType && constantValue.Value != null)
{
    return;
}
```

È necessario scrivere codice aggiuntivo nel provider della correzione del codice per sostituire la parola chiave var' con il nome del tipo corretto. Tornare a **CodeFixProvider.cs**. Il codice che verrà aggiunto esegue i passaggi seguenti:

- Controllare se la dichiarazione è una dichiarazione `var` e in tal caso:
- Creare un nuovo tipo per il tipo dedotto.
- Assicurarsi che la dichiarazione del tipo non sia un alias. In tal caso, è consentito dichiarare `const var`.
- Verificare che `var` non sia un nome di tipo in questo programma. In tal caso, `const var` è consentito.
- Semplificare il nome completo del tipo

Può sembrare necessaria una notevole quantità di codice, ma non è così. Sostituire la riga che dichiara e inizializza `newLocal` con il codice seguente. Deve essere inserita subito dopo l'inizializzazione di `newModifiers`:

[!code-csharp[Replace Var designations](~/samples/snippets/csharp/roslyn-sdk/Tutorials/MakeConst/MakeConst/MakeConstCodeFixProvider.cs#ReplaceVar "Replace a var designation with the explicit type")]

È necessario aggiungere una `using` direttiva per usare il <xref:Microsoft.CodeAnalysis.Simplification.Simplifier> tipo:

```csharp
using Microsoft.CodeAnalysis.Simplification;
```

Eseguire i test. Avranno tutti esito positivo. Per concludere, è possibile eseguire l'analizzatore completato. Premere CTRL+F5 per eseguire il progetto dell'analizzatore in una seconda istanza di Visual Studio con l'estensione in anteprima di Roslyn caricata.

- Nella seconda istanza di Visual Studio creare un nuovo progetto di applicazione console C# e aggiungere `int x = "abc";` al metodo Main. Grazie alla correzione del primo bug, non dovrebbe essere segnalato alcun messaggio di avviso per questa dichiarazione di variabile locale (anche se si verifica un errore del compilatore come previsto).
- Aggiungere quindi `object s = "abc";` al metodo Main. A causa della correzione del secondo bug, non dovrebbe essere segnalato alcun avviso.
- Infine, aggiungere un'altra variabile locale che usa la parola chiave `var`. Si noterà che viene segnalato un avviso e viene visualizzato un suggerimento in basso a sinistra.
- Spostare il cursore dell'editor sulla sottolineatura ondulata, quindi premere CTRL+. per visualizzare la correzione del codice suggerita. Dopo aver selezionato la correzione del codice, si noterà che la parola chiave var' viene gestita correttamente.

Infine, aggiungere il codice seguente:

```csharp
int i = 2;
int j = 32;
int k = i + j;
```

Dopo queste modifiche, vengono visualizzate linee rosse ondulate solo per le prime due variabili. Aggiungere `const` sia a `i` che a `j`. Verrà visualizzato un nuovo avviso per `k`, perché può ora essere `const`.

Congratulazioni! È stata creata la prima estensione .NET Compiler Platform che esegue l'analisi del codice in tempo reale per rilevare un problema e fornisce una correzione rapida per l'errore. Nel corso di questo processo sono state descritte molte delle API di codice che fanno parte di .NET Compiler Platform SDK (API Roslyn). È possibile confrontare il proprio lavoro con l'[esempio completato](https://github.com/dotnet/samples/tree/master/csharp/roslyn-sdk/Tutorials/MakeConst) disponibile nel repository GitHub degli esempi.

## <a name="other-resources"></a>Altre risorse

- [Introduzione all'analisi della sintassi](../get-started/syntax-analysis.md)
- [Introduzione all'analisi semantica](../get-started/semantic-analysis.md)
