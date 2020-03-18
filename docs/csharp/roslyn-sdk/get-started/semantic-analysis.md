---
title: Introduzione all'analisi semantica
description: Questa esercitazione offre una panoramica dell'utilizzo dell'analisi semantica con .NET Compiler SDK.
ms.date: 02/06/2018
ms.custom: mvc
ms.openlocfilehash: a6dcaeeb86acb5c0e1602f01dc5952ffd9d5e3f5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "78240509"
---
# <a name="get-started-with-semantic-analysis"></a>Introduzione all'analisi semantica

In questa esercitazione si presuppone una certa familiarità con l'API Syntax. L'articolo [Introduzione all'analisi della sintassi](syntax-analysis.md) offre informazioni introduttive sufficienti.

In questa esercitazione verranno esplorate le API **Symbol** e **Binding**. Queste API offrono informazioni sul _significato semantico_ di un programma e consentono di porre domande sui tipi rappresentati da qualsiasi simbolo nel programma e ottenere risposte.

È necessario installare **.NET Compiler Platform SDK**:

[!INCLUDE[interactive-note](~/includes/roslyn-installation.md)]

## <a name="understanding-compilations-and-symbols"></a>Informazioni su compilazioni e simboli

Man mano che si lavora con .NET Compiler SDK si acquisirà familiarità con le distinzioni tra API Syntax e API Semantic. L'**API Syntax** consente di esaminare la _struttura_ di un programma. Tuttavia, spesso servono informazioni più dettagliate sulla semantica o il _significato_ di un programma. Mentre un file di codice sciolto o un frammento di codice Visual Basic o C , può essere analizzato sintatticamente in isolamento, non è significativo porre domande come "qual è il tipo di questa variabile" in un vuoto. Il significato di un nome di tipo potrebbe essere dipendente da riferimenti ad assembly, importazioni di spazi dei nomi o altri file di codice. Queste domande possono ottenere risposta tramite l'**API Semantic**, in particolare la classe <xref:Microsoft.CodeAnalysis.Compilation?displayProperty=nameWithType>.

Un'istanza di <xref:Microsoft.CodeAnalysis.Compilation> è paragonabile a un singolo progetto, dal punto di vista del compilatore e rappresenta tutti gli elementi necessari per compilare un programma Visual Basic o C#. La **compilazione** include il set di file di origine da compilare, i riferimenti agli assembly e le opzioni del compilatore. È possibile ragionare sul significato del codice usando tutte le altre informazioni in questo contesto. <xref:Microsoft.CodeAnalysis.Compilation> consente di trovare i **simboli**, ovvero entità come i tipi, gli spazi dei nomi, i membri e le variabili a cui fanno riferimento i nomi e altre espressioni. Il processo di associazione di nomi ed espressioni a **simboli** viene chiamato **associazione**.

Come <xref:Microsoft.CodeAnalysis.SyntaxTree?displayProperty=nameWithType>, <xref:Microsoft.CodeAnalysis.Compilation> è una classe astratta con derivati specifici del linguaggio. Quando si crea un'istanza di Compilation, è necessario richiamare un metodo factory sulla classe <xref:Microsoft.CodeAnalysis.CSharp.CSharpCompilation?displayProperty=nameWithType> (o <xref:Microsoft.CodeAnalysis.VisualBasic.VisualBasicCompilation?displayProperty=nameWithType>).

## <a name="querying-symbols"></a>Esecuzione di query sui simboli

In questa esercitazione, viene esaminato ancora una volta il programma "Hello World". In questo caso si esegue una query sui simboli nel programma per scoprire quali tipi rappresentano questi simboli. Verrà eseguita una query per recuperare i tipi in uno spazio dei nomi e si imparerà a trovare i metodi disponibili per un tipo.

È possibile visualizzare il codice completato per l'esempio nel [repository GitHub](https://github.com/dotnet/samples/tree/master/csharp/roslyn-sdk/SemanticQuickStart).

> [!NOTE]
> I tipi di albero della sintassi usano l'ereditarietà per descrivere i diversi elementi della sintassi validi in posizioni diverse nel programma. L'uso di queste API spesso significa eseguire il cast di proprietà o membri di raccolte in tipi derivati specifici. Negli esempi seguenti, l'assegnazione e i cast sono istruzioni separate, con variabili tipizzate in modo esplicito. È possibile leggere il codice per visualizzare i tipi restituiti dell'API e il tipo di runtime degli oggetti restituiti. In pratica, è più comune usare variabili tipizzate in modo implicito e basarsi sui nomi delle API per descrivere il tipo di oggetti in corso di analisi.

Creare un nuovo progetto C# **Stand-Alone Code Analysis Tool** (Strumento di analisi del codice autonomo):

* In Visual Studio scegliere **File** > **nuovo** > **progetto** per visualizzare la finestra di dialogo Nuovo progetto.
* In**Estensibilità** **di Visual C,** > scegliere **Strumento di analisi**del codice autonomo .
* Denominare il progetto "**SemanticQuickStart**" e fare clic su OK.

Verrà analizzato il semplice programma "Hello World!" mostrato in precedenza.
Aggiungere il testo per il programma Hello World come costante nella classe `Program`:

[!code-csharp[Declare the program test](../../../../samples/snippets/csharp/roslyn-sdk/SemanticQuickStart/Program.cs#1 "Declare a constant string for the program text to analyze")]

Aggiungere poi il codice seguente per creare l'albero della sintassi per il testo del codice nella costante `programText`.  Aggiungere la riga seguente al metodo `Main`:

[!code-csharp[Create the tree](../../../../samples/snippets/csharp/roslyn-sdk/SemanticQuickStart/Program.cs#2 "Create the syntax tree")]

Compilare poi un'istanza di <xref:Microsoft.CodeAnalysis.CSharp.CSharpCompilation> dall'albero già creato. L'esempio "Hello World" si basa sui tipi <xref:System.String> e <xref:System.Console>. È necessario fare riferimento all'assembly che dichiara i due tipi nella compilazione. Aggiungere la riga seguente al metodo `Main` per creare una compilazione dell'albero della sintassi, incluso il riferimento all'assembly appropriato:

[!code-csharp[Create the compilation](../../../../samples/snippets/csharp/roslyn-sdk/SemanticQuickStart/Program.cs#3 "Create the compilation for the semantic model")]

Il metodo <xref:Microsoft.CodeAnalysis.CSharp.CSharpCompilation.AddReferences%2A?displayProperty=nameWithType> aggiunge i riferimenti alla compilazione. Il metodo <xref:Microsoft.CodeAnalysis.MetadataReference.CreateFromFile%2A?displayProperty=nameWithType> carica un assembly come riferimento.

## <a name="querying-the-semantic-model"></a>Esecuzione di query sul modello semantico

Dopo aver creato un <xref:Microsoft.CodeAnalysis.Compilation> è possibile richiedere un <xref:Microsoft.CodeAnalysis.SemanticModel> per qualsiasi <xref:Microsoft.CodeAnalysis.SyntaxTree> contenuto in tale <xref:Microsoft.CodeAnalysis.Compilation>. È possibile considerare il modello semantico come fonte di tutte le informazioni che si ottengono in genere da IntelliSense. Un oggetto <xref:Microsoft.CodeAnalysis.SemanticModel> può rispondere a domande come "Quali nomi sono compresi nell'ambito in questa posizione?", "Quali membri sono accessibili da questo metodo?", "Quali variabili vengono usate in questo blocco di testo?" e "A cosa fa riferimento questa espressione/questo nome?" Aggiungere questa istruzione per creare il modello semantico:

[!code-csharp[Create the semantic model](../../../../samples/snippets/csharp/roslyn-sdk/SemanticQuickStart/Program.cs#4 "Create the semantic model")]

## <a name="binding-a-name"></a>Associazione di un nome

<xref:Microsoft.CodeAnalysis.Compilation> crea <xref:Microsoft.CodeAnalysis.SemanticModel> da <xref:Microsoft.CodeAnalysis.SyntaxTree>. Dopo aver creato il modello, è possibile eseguire query per trovare la prima direttiva `using` e recuperare informazioni sui simboli per lo spazio dei nomi `System`. Aggiungere queste due righe al metodo `Main` per creare il modello semantico e recuperare il simbolo per la prima istruzione using:

[!code-csharp[Find the namespace symbol for the first using](../../../../samples/snippets/csharp/roslyn-sdk/SemanticQuickStart/Program.cs#5 "Find the namespace symbol for the first using")]

Il codice precedente illustra come associare il nome nella prima direttiva `using` per recuperare un <xref:Microsoft.CodeAnalysis.SymbolInfo?displayProperty=nameWithType> per lo spazio dei nomi `System`. Il codice precedente dimostra anche che si usa il **modello della sintassi** per trovare la struttura del codice e il **modello semantico** per comprenderne il significato. Il **modello della sintassi** individua la stringa `System` nell'istruzione using. Il **modello semantico** include tutte le informazioni sui tipi definiti nello spazio dei nomi `System`.

Dall'oggetto <xref:Microsoft.CodeAnalysis.SymbolInfo> è possibile ottenere <xref:Microsoft.CodeAnalysis.ISymbol?displayProperty=nameWithType> usando la proprietà <xref:Microsoft.CodeAnalysis.SymbolInfo.Symbol?displayProperty=nameWithType>. Questa proprietà restituisce il simbolo a cui fa riferimento questa espressione. Per le espressioni che non fanno riferimento ad alcun elemento (ad esempio, i valori letterali numerici) questa proprietà è `null`. Quando <xref:Microsoft.CodeAnalysis.SymbolInfo.Symbol?displayProperty=nameWithType> non è null, <xref:Microsoft.CodeAnalysis.ISymbol.Kind?displayProperty=nameWithType> indica il tipo del simbolo. In questo esempio, la proprietà <xref:Microsoft.CodeAnalysis.ISymbol.Kind?displayProperty=nameWithType> è un <xref:Microsoft.CodeAnalysis.SymbolKind.Namespace?displayProperty=nameWithType>. Aggiungere il codice seguente al metodo `Main`. Recupera il simbolo per lo spazio dei nomi `System` e quindi visualizza tutti gli spazi dei nomi figlio dichiarati nello spazio dei nomi `System`:

[!code-csharp[Display all the child namespaces](../../../../samples/snippets/csharp/roslyn-sdk/SemanticQuickStart/Program.cs#6 "Display all the child namespaces from this compilation")]

Eseguire il programma. L'output dovrebbe essere il seguente:

```output
System.Collections
System.Configuration
System.Deployment
System.Diagnostics
System.Globalization
System.IO
System.Numerics
System.Reflection
System.Resources
System.Runtime
System.Security
System.StubHelpers
System.Text
System.Threading
Press any key to continue . . .
```

> [!NOTE]
> L'output non include ogni spazio dei nomi figlio dello spazio dei nomi `System`. Viene visualizzato ogni spazio dei nomi presente in questa compilazione, che fa riferimento solo all'assembly in cui è dichiarato `System.String`. Gli eventuali spazi dei nomi dichiarati in altri assembly non sono noti per questa compilazione

### <a name="binding-an-expression"></a>Associazione di un'espressione

Il codice precedente mostra come trovare un simbolo mediante l'associazione a un nome. Esistono altre espressioni in un programma C# che possono essere associate e non sono nomi. Per illustrare questa funzionalità, si esaminerà l'associazione a un semplice valore letterale stringa.

Il programma "Hello World" contiene un <xref:Microsoft.CodeAnalysis.CSharp.Syntax.LiteralExpressionSyntax?displayProperty=nameWithType>, ovvero la stringa "Hello, World!" visualizzata nella console.

È possibile trovare la stringa "Hello, World!" individuando il singolo valore letterale stringa nel programma. Dopo aver individuato il nodo della sintassi, è possibile ottenere le informazioni sul tipo per tale nodo dal modello semantico. Aggiungere il codice seguente al metodo `Main`:

[!code-csharp[Find the namespace symbol for the only using](../../../../samples/snippets/csharp/roslyn-sdk/SemanticQuickStart/Program.cs#7 "Find the namespace symbol for the only using")]

Lo struct <xref:Microsoft.CodeAnalysis.TypeInfo?displayProperty=nameWithType> include una proprietà <xref:Microsoft.CodeAnalysis.TypeInfo.Type?displayProperty=nameWithType> che consente l'accesso alle informazioni semantiche sul tipo del valore letterale. In questo esempio, si tratta del tipo `string`. Aggiungere una dichiarazione che assegna questa proprietà a una variabile locale:

[!code-csharp[Find the semantic information about the string type](../../../../samples/snippets/csharp/roslyn-sdk/SemanticQuickStart/Program.cs#8 "Use the string literal to access the semantic information in the string type.")]

Per completare questa esercitazione, verrà definita una query LINQ che crea una sequenza di tutti i metodi pubblici dichiarati nel tipo `string` che restituiscono `string`. Questa query diventa complessa, quindi viene creata riga per riga per poi essere ricostruita come singola query. L'origine per questa query è la sequenza di tutti i membri dichiarati nel tipo `string`:

[!code-csharp[Access the sequence of members on the string type](../../../../samples/snippets/csharp/roslyn-sdk/SemanticQuickStart/Program.cs#9 "Access the sequence of members on the string type.")]

Questa sequenza di origine contiene tutti i membri, inclusi le proprietà e i campi, quindi filtrarla tramite il metodo <xref:System.Collections.Immutable.ImmutableArray%601.OfType%2A?displayProperty=nameWithType> per trovare gli elementi corrispondenti a oggetti <xref:Microsoft.CodeAnalysis.IMethodSymbol?displayProperty=nameWithType>:

[!code-csharp[Filter the sequence to only methods](../../../../samples/snippets/csharp/roslyn-sdk/SemanticQuickStart/Program.cs#10 "Find the subset of the collection that is the methods.")]

Aggiungere poi un altro filtro per restituire solo i metodi pubblici che restituiscono `string`:

[!code-csharp[Filter on return type and accessibility](../../../../samples/snippets/csharp/roslyn-sdk/SemanticQuickStart/Program.cs#11 "Find only the public methods that return a string.")]

Selezionare solo la proprietà del nome e solo i nomi distinti rimuovendo qualsiasi overload:

[!code-csharp[find the distinct names.](../../../../samples/snippets/csharp/roslyn-sdk/SemanticQuickStart/Program.cs#12 "Use the string literal to access the semantic information in the string type.")]

È anche possibile creare la query completa usando la sintassi di query LINQ e quindi visualizzare tutti i nomi di metodo nella console:

[!code-csharp[build and display the results of this query.](../../../../samples/snippets/csharp/roslyn-sdk/SemanticQuickStart/Program.cs#13 "Build and display the results of the query.")]

Compilare ed eseguire il programma. Dovrebbe venire visualizzato l'output seguente.

```output
Join
Substring
Trim
TrimStart
TrimEnd
Normalize
PadLeft
PadRight
ToLower
ToLowerInvariant
ToUpper
ToUpperInvariant
ToString
Insert
Replace
Remove
Format
Copy
Concat
Intern
IsInterned
Press any key to continue . . .
```

È stata usata l'API Semantic per trovare e visualizzare informazioni sui simboli che fanno parte di questo programma.
