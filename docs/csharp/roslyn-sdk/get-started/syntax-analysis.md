---
title: Introduzione all'analisi della sintassi (API Roslyn)
description: Introduzione all'attraversamento, all'esecuzione di query e all'esplorazione di alberi della sintassi.
ms.date: 02/05/2018
ms.custom: mvc
ms.openlocfilehash: 22d1303c9daa2ae35cf130b0c857cd7a5efdbe76
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/03/2020
ms.locfileid: "78240519"
---
# <a name="get-started-with-syntax-analysis"></a>Introduzione all'analisi della sintassi

In questa esercitazione verrà esaminata l'**API Syntax**. L'API Syntax consente l'accesso alle strutture di dati che descrivono un programma C# o Visual Basic. Queste strutture di dati includono dettagli sufficienti per rappresentare completamente un programma di qualsiasi dimensione. Queste strutture possono descrivere programmi completi che vengono compilati ed eseguiti correttamente. Possono anche descrivere programmi incompleti, durante la scrittura, nell'editor.

Per rendere possibile questa espressione elaborata, le strutture di dati e le API che costituiscono l'API Syntax sono necessariamente complesse. Per iniziare, verrà esaminato l'aspetto della struttura dei dati per il tipico programma "Hello World":

```csharp
using System;
using System.Collections.Generic;
using System.Linq;

namespace HelloWorld
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Hello World!");
        }
    }
}
```

Esaminando il testo del programma precedente si riconoscono elementi noti. L'intero testo rappresenta un singolo file di origine, ovvero un'**unità di compilazione**. Le prime tre righe di tale file di origine sono **direttive using**. L'origine rimanente è contenuta in una **dichiarazione dello spazio dei nomi**. La dichiarazione dello spazio dei nomi contiene una **dichiarazione di classe** figlio. La dichiarazione di classe contiene una **dichiarazione di metodo**.

L'API Syntax crea una struttura ad albero con la radice che rappresenta l'unità di compilazione. I nodi nell'albero rappresentano le direttive using, la dichiarazione dello spazio dei nomi e tutti gli altri elementi del programma. La struttura ad albero continua fino ai livelli più bassi: la stringa "Hello World!" è un **token letterale di stringa** che è un discendente di un **argomento**. L'API Syntax consente l'accesso alla struttura del programma. È possibile eseguire query per ottenere specifiche procedure consigliate per la scrittura del codice, ripercorrere l'intera struttura ad albero per comprendere il codice e creare nuovi alberi modificando quello esistente.

Questa breve descrizione offre una panoramica del tipo di informazioni accessibili tramite l'API Syntax. L'API Syntax non è altro che un'API formale che descrive i costrutti di codice familiari, già noti da C#. Le funzionalità complete includono informazioni sulla formattazione del codice, inclusi spazi vuoti, interruzioni di riga e rientri. Usando queste informazioni è possibile rappresentare completamente il codice nel modo in cui viene scritto e letto dai programmatori umani o dal compilatore. L'uso di questa struttura consente di interagire con il codice sorgente su un livello molto significativo. Non si tratta più di semplici stringhe di testo, ma di dati che rappresentano la struttura di un programma C#.

Per iniziare, è necessario installare **.NET Compiler Platform SDK**:

[!INCLUDE[interactive-note](~/includes/roslyn-installation.md)]

## <a name="understanding-syntax-trees"></a>Informazioni sugli alberi della sintassi

È possibile usare l'API Syntax per qualsiasi analisi della struttura di codice C#. L'**API Syntax** espone i parser, gli alberi della sintassi e le utilità per l'analisi e costruzione di alberi della sintassi. Si tratta del modo in cui si cercano elementi di sintassi specifici nel codice o si legge il codice per un programma.

Un albero della sintassi è una struttura di dati usata dai compilatori C# e Visual Basic per comprendere i programmi C# e Visual Basic. Gli alberi della sintassi vengono prodotti dallo stesso parser eseguito quando viene compilato un progetto o uno sviluppatore preme F5. Gli alberi della sintassi garantiscono la totale fedeltà al linguaggio. Ogni elemento di informazioni in un file di codice è rappresentato nell'albero. La scrittura di un albero della sintassi in formato di testo riproduce l'esatto testo originale analizzato. Gli alberi di sintassi sono anche **non modificabili**, ovvero non possono essere mai modificati dopo la creazione. I consumer degli alberi possono analizzarli su più thread, senza blocchi o altre misure di concorrenza, dando per scontato che i dati non cambiano mai. È possibile usare le API per creare nuovi alberi risultanti dalla modifica di un albero esistente.

I quattro principali blocchi predefiniti degli alberi della sintassi sono:

* La classe <xref:Microsoft.CodeAnalysis.SyntaxTree?displayProperty=nameWithType>, un'istanza della quale rappresenta l'intero albero di analisi. <xref:Microsoft.CodeAnalysis.SyntaxTree> è una classe astratta con derivati specifici del linguaggio. Usare i metodi Parse della classe <xref:Microsoft.CodeAnalysis.CSharp.CSharpSyntaxTree?displayProperty=nameWithType> (o <xref:Microsoft.CodeAnalysis.VisualBasic.VisualBasicSyntaxTree?displayProperty=nameWithType>) per analizzare il testo in C# o Visual Basic.
* La classe <xref:Microsoft.CodeAnalysis.SyntaxNode?displayProperty=nameWithType>, le cui istanze rappresentano costrutti sintattici, come dichiarazioni, istruzioni, clausole ed espressioni.
* La struttura <xref:Microsoft.CodeAnalysis.SyntaxToken?displayProperty=nameWithType>, che rappresenta parole chiave, identificatori, operatori o segni di punteggiatura singoli.
* E infine la struttura <xref:Microsoft.CodeAnalysis.SyntaxTrivia?displayProperty=nameWithType>, che rappresenta elementi di informazioni sintatticamente non significativi, come lo spazio vuoto tra i token, le direttive di pre-elaborazione e i commenti.

Gli elementi semplici, i token e i nodi sono composti in modo gerarchico per formare un albero che rappresenta completamente tutti gli elementi in un frammento di codice Visual Basic o C#. È possibile visualizzare questa struttura usando la finestra **Syntax Visualizer** (Visualizzatore sintassi). In Visual Studio scegliere **Visualizza** > **Altre finestre** > **Syntax Visualizer** (Visualizzatore sintassi). Ad esempio, il file di origine C# precedente esaminato nella finestra **Syntax Visualizer** (Visualizzatore sintassi) ha l'aspetto illustrato nella figura seguente:

**SyntaxNode**: blu | **SyntaxToken**: verde | **SyntaxTrivia**: rosso ![File di codice C#](media/walkthrough-csharp-syntax-figure1.png)

Esplorando questa struttura ad albero, è possibile trovare qualsiasi istruzione, espressione, token o spazio vuoto in un file di codice.

Anche se è possibile trovare qualsiasi elemento in un file di codice usando le API Syntax, la maggior parte degli scenari d'uso riguarda l'analisi di piccoli frammenti di codice o la ricerca di istruzioni o frammenti specifici. Gli esempi che seguono mostrano due usi tipici per esplorare la struttura del codice o cercare singole istruzioni.

## <a name="traversing-trees"></a>Attraversamento degli alberi

È possibile esaminare i nodi in un albero della sintassi in due modi. È possibile attraversare l'albero per esaminare ogni nodo oppure è possibile eseguire query per recuperare elementi o nodi specifici.

### <a name="manual-traversal"></a>Attraversamento manuale

È possibile visualizzare il codice completato per l'esempio nel [repository GitHub](https://github.com/dotnet/samples/tree/master/csharp/roslyn-sdk/SyntaxQuickStart).

> [!NOTE]
> I tipi di albero della sintassi usano l'ereditarietà per descrivere i diversi elementi della sintassi validi in posizioni diverse nel programma. L'uso di queste API spesso significa eseguire il cast di proprietà o membri di raccolte in tipi derivati specifici. Negli esempi seguenti, l'assegnazione e i cast sono istruzioni separate, con variabili tipizzate in modo esplicito. È possibile leggere il codice per visualizzare i tipi restituiti dell'API e il tipo di runtime degli oggetti restituiti. In pratica, è più comune usare variabili tipizzate in modo implicito e basarsi sui nomi delle API per descrivere il tipo di oggetti in corso di analisi.

Creare un nuovo progetto C# **Stand-Alone Code Analysis Tool** (Strumento di analisi del codice autonomo):

* In Visual Studio scegliere **File** > **Nuovo** > **Progetto** per visualizzare la finestra di dialogo Nuovo progetto.
* In **Visual C#** > **Estendibilità** scegliere **Stand-Alone Code Analysis Tool** (Strumento di analisi del codice autonomo).
* Denominare il progetto "**SyntaxTreeManualTraversal**" e fare clic su OK.

Verrà analizzato il semplice programma "Hello World!" mostrato in precedenza.
Aggiungere il testo per il programma Hello World come costante nella classe `Program`:

[!code-csharp[Declare the program text](../../../../samples/snippets/csharp/roslyn-sdk/SyntaxQuickStart/HelloSyntaxTree/Program.cs#1 "Declare a constant string for the program text to analyze")]

Aggiungere poi il codice seguente per creare l'**albero della sintassi** per il testo del codice nella costante `programText`.  Aggiungere la riga seguente al metodo `Main`:

[!code-csharp[Create the tree](../../../../samples/snippets/csharp/roslyn-sdk/SyntaxQuickStart/HelloSyntaxTree/Program.cs#2 "Create the syntax tree")]

Queste due righe creano l'albero e ne recuperano il nodo radice. È ora possibile esaminare i nodi dell'albero. Aggiungere queste righe al metodo `Main` per visualizzare alcune delle proprietà del nodo radice nell'albero:

[!code-csharp[Examine the root node](../../../../samples/snippets/csharp/roslyn-sdk/SyntaxQuickStart/HelloSyntaxTree/Program.cs#3 "Examine the root node")]

Eseguire l'applicazione per vedere cosa ha individuato il codice sul nodo radice in questo albero.

In genere, l'attraversamento del codice viene eseguito per acquisire informazioni sul codice. In questo esempio, viene analizzato codice noto per esplorare le API. Aggiungere il codice seguente per esaminare il primo membro del nodo `root`:

[!code-csharp[Find the first member](../../../../samples/snippets/csharp/roslyn-sdk/SyntaxQuickStart/HelloSyntaxTree/Program.cs#4 "Find the first member")]

Tale membro è di tipo <xref:Microsoft.CodeAnalysis.CSharp.Syntax.NamespaceDeclarationSyntax?displayProperty=nameWithType> e rappresenta tutto nell'ambito della dichiarazione `namespace HelloWorld`. Aggiungere il codice seguente per individuare i nodi dichiarati all'interno dello spazio dei nomi `HelloWorld`:

[!code-csharp[Find the class declaration](../../../../samples/snippets/csharp/roslyn-sdk/SyntaxQuickStart/HelloSyntaxTree/Program.cs#5 "Find the class declaration")]

Eseguire il programma per verificare quanto appreso.

Ora che è noto che la dichiarazione è un <xref:Microsoft.CodeAnalysis.CSharp.Syntax.ClassDeclarationSyntax?displayProperty=nameWithType>, dichiarare una nuova variabile di quel tipo per esaminare la dichiarazione di classe. Questa classe contiene solo un membro: il metodo `Main`. Aggiungere il codice seguente per trovare il metodo `Main` ed eseguirne il cast su <xref:Microsoft.CodeAnalysis.CSharp.Syntax.MethodDeclarationSyntax?displayProperty=nameWithType>.

[!code-csharp[Find the main declaration](../../../../samples/snippets/csharp/roslyn-sdk/SyntaxQuickStart/HelloSyntaxTree/Program.cs#6 "Find the main declaration")]

Il nodo della dichiarazione del metodo contiene tutte le informazioni sintattiche sul metodo. A questo punto verranno visualizzati il tipo restituito del metodo `Main`, il numero e i tipi degli argomenti e il testo del corpo del metodo. Aggiungere il codice seguente:

[!code-csharp[Examine the syntax of the main method](../../../../samples/snippets/csharp/roslyn-sdk/SyntaxQuickStart/HelloSyntaxTree/Program.cs#7 "Display information about the main method")]

Eseguire il programma per visualizzare tutte le informazioni individuate su questo programma:

```text
The tree is a CompilationUnit node.
The tree has 1 elements in it.
The tree has 4 using statements. They are:
        System
        System.Collections
        System.Linq
        System.Text
The first member is a NamespaceDeclaration.
There are 1 members declared in this namespace.
The first member is a ClassDeclaration.
There are 1 members declared in the Program class.
The first member is a MethodDeclaration.
The return type of the Main method is void.
The method has 1 parameters.
The type of the args parameter is string[].
The body text of the Main method follows:
        {
            Console.WriteLine("Hello, World!");
        }
```

### <a name="query-methods"></a>Metodi di query

Oltre ad attraversare gli alberi, è anche possibile esplorare l'albero della sintassi usando i metodi di query definiti in <xref:Microsoft.CodeAnalysis.SyntaxNode?displayProperty=nameWithType>. Questi metodi dovrebbero essere immediatamente familiari a chiunque abbia familiarità con XPath. Per trovare rapidamente elementi in un albero, è possibile usare questi metodi con LINQ. <xref:Microsoft.CodeAnalysis.SyntaxNode> include metodi di query, come <xref:Microsoft.CodeAnalysis.SyntaxNode.DescendantNodes%2A>, <xref:Microsoft.CodeAnalysis.SyntaxNode.AncestorsAndSelf%2A> e <xref:Microsoft.CodeAnalysis.SyntaxNode.ChildNodes%2A>.

È possibile usare questi metodi di query per trovare l'argomento del metodo `Main`, in alternativa all'esplorazione dell'albero. Aggiungere il codice seguente alla fine del metodo `Main`:

[!code-csharp[Query the tree for the arguments to Main](../../../../samples/snippets/csharp/roslyn-sdk/SyntaxQuickStart/HelloSyntaxTree/Program.cs#8 "Query the tree for the arguments to Main")]

La prima istruzione usa un'espressione LINQ e il metodo <xref:Microsoft.CodeAnalysis.SyntaxNode.DescendantNodes%2A> per individuare lo stesso parametro, come nell'esempio precedente.

Eseguire il programma. Si può notare che l'espressione LINQ ha trovato lo stesso parametro individuato con l'esplorazione manuale dell'albero.

L'esempio usa istruzioni `WriteLine` per visualizzare informazioni sugli alberi della sintassi durante l'attraversamento. È anche possibile ottenere molte più informazioni eseguendo il programma terminato nel debugger. È possibile esaminare molti più metodi e proprietà che fanno parte dell'albero della sintassi creato per il programma Hello World.

## <a name="syntax-walkers"></a>Percorrere in modo ricorsivo la sintassi

Spesso è necessario trovare tutti i nodi di un tipo specifico in un albero della sintassi, ad esempio ogni dichiarazione di proprietà in un file. Con l'estensione della classe <xref:Microsoft.CodeAnalysis.CSharp.CSharpSyntaxWalker?displayProperty=nameWithType> e l'override del metodo <xref:Microsoft.CodeAnalysis.CSharp.CSharpSyntaxVisitor.VisitPropertyDeclaration(Microsoft.CodeAnalysis.CSharp.Syntax.PropertyDeclarationSyntax)>, si elabora ogni dichiarazione di proprietà in un albero della sintassi senza conoscerne in anticipo la struttura. <xref:Microsoft.CodeAnalysis.CSharp.CSharpSyntaxWalker> è un tipo specifico di <xref:Microsoft.CodeAnalysis.CSharp.CSharpSyntaxVisitor> che visita in modo ricorsivo un nodo e tutti i relativi nodi figlio.

Questo esempio implementa un <xref:Microsoft.CodeAnalysis.CSharp.CSharpSyntaxWalker> che esamina un albero della sintassi. Raccoglie le direttive `using` individuate, che non importano uno spazio dei nomi `System`.

Creare un nuovo progetto C# **Stand-Alone Code Analysis Tool** (Strumento di analisi del codice autonomo) e denominarlo "**SyntaxWalker**."

È possibile visualizzare il codice completato per l'esempio nel [repository GitHub](https://github.com/dotnet/samples/tree/master/csharp/roslyn-sdk/SyntaxQuickStart). L'esempio su GitHub contiene entrambi i progetti descritti in questa esercitazione.

Come nell'esempio precedente, è possibile definire una costante stringa per contenere il testo del programma che verrà analizzato:

[!code-csharp[Define the code text to analyzer](../../../../samples/snippets/csharp/roslyn-sdk/SyntaxQuickStart/SyntaxWalker/Program.cs#1 "Define the program text to analyze")]

Questo testo di origine contiene direttive `using` distribuite in quattro diverse posizioni: nel livello file, nello spazio dei nomi di livello superiore e nei due spazi dei nomi annidati. Questo esempio mette in evidenza uno scenario fondamentale per l'uso della classe <xref:Microsoft.CodeAnalysis.CSharp.CSharpSyntaxWalker> per eseguire query nel codice. Sarebbe un'operazione complessa visitare ogni nodo nell'albero della sintassi radice per trovare le dichiarazioni using. Si crea invece una classe derivata e si esegue l'override del metodo che viene chiamato solo quando il nodo corrente nell'albero è una direttiva using. Non vengono eseguite altre operazioni su qualsiasi altro tipo di nodo. Questo singolo metodo esamina ogni istruzione `using` e crea una raccolta degli spazi dei nomi non inclusi nello spazio dei nomi `System`. Si compila un <xref:Microsoft.CodeAnalysis.CSharp.CSharpSyntaxWalker> che esamina tutte le istruzioni `using`, ma solo le istruzioni `using`.

Dopo aver definito il testo del programma, è necessario creare un `SyntaxTree` e ottenere la radice di tale albero:

[!code-csharp[Create the Syntax tree and access the root](../../../../samples/snippets/csharp/roslyn-sdk/SyntaxQuickStart/SyntaxWalker/Program.cs#2 "Create the Syntax tree and access the root node.")]

Creare poi una nuova classe. In Visual Studio scegliere **Progetto** > **Aggiungi nuovo elemento**. Nella finestra di dialogo **Aggiungi nuovo elemento** digitare *UsingCollector.cs* come nome del file.

Implementare la funzionalità del visitatore di `using` nella classe `UsingCollector`. Per iniziare, far derivare la classe `UsingCollector` da <xref:Microsoft.CodeAnalysis.CSharp.CSharpSyntaxWalker>.

[!code-csharp[Declare the base class for the using collector](../../../../samples/snippets/csharp/roslyn-sdk/SyntaxQuickStart/SyntaxWalker/UsingCollector.cs#3 "Declare the base class for the UsingCollector")]

È necessario spazio di archiviazione per i nodi dello spazio dei nomi raccolti.  Dichiarare una proprietà pubblica di sola lettura nella classe `UsingCollector`. Questa variabile viene usata per archiviare i nodi <xref:Microsoft.CodeAnalysis.CSharp.Syntax.UsingDirectiveSyntax> trovati:

[!code-csharp[Declare storage for the using syntax nodes](../../../../samples/snippets/csharp/roslyn-sdk/SyntaxQuickStart/SyntaxWalker/UsingCollector.cs#4 "Declare storage for the using syntax nodes")]

La classe di base, <xref:Microsoft.CodeAnalysis.CSharp.CSharpSyntaxWalker> implementa la logica per visitare ogni nodo nell'albero della sintassi. La classe derivata esegue l'override dei metodi chiamati per i nodi specifici a cui si è interessati. In questo caso, si è interessati a qualsiasi direttiva `using`. Questo significa che è necessario eseguire l'override del metodo <xref:Microsoft.CodeAnalysis.CSharp.CSharpSyntaxVisitor.VisitUsingDirective(Microsoft.CodeAnalysis.CSharp.Syntax.UsingDirectiveSyntax)>. L'unico argomento di questo metodo è un oggetto <xref:Microsoft.CodeAnalysis.CSharp.Syntax.UsingDirectiveSyntax?displayProperty=nameWithType>. Ciò rappresenta un vantaggio importante rispetto all'uso dei visitatori: i metodi sottoposti a override vengono chiamati con argomenti di cui è già stato eseguito il cast al tipo di nodo specifico. La classe <xref:Microsoft.CodeAnalysis.CSharp.Syntax.UsingDirectiveSyntax?displayProperty=nameWithType> include una proprietà <xref:Microsoft.CodeAnalysis.CSharp.Syntax.UsingDirectiveSyntax.Name> che archivia il nome dello spazio dei nomi importato. Si tratta di un oggetto <xref:Microsoft.CodeAnalysis.CSharp.Syntax.NameSyntax?displayProperty=nameWithType>. Aggiungere il codice seguente nell'override di <xref:Microsoft.CodeAnalysis.CSharp.CSharpSyntaxVisitor.VisitUsingDirective(Microsoft.CodeAnalysis.CSharp.Syntax.UsingDirectiveSyntax)>:

[!code-csharp[Examine using nodes for the System namespace](../../../../samples/snippets/csharp/roslyn-sdk/SyntaxQuickStart/SyntaxWalker/UsingCollector.cs#5 "Examine all using nodes for the System namespace.")]

Come per l'esempio precedente, sono state aggiunte svariate istruzioni `WriteLine` per facilitare la comprensione di questo metodo. È possibile vedere quando viene chiamato e quali argomenti vengono passati al metodo ogni volta.

Infine, è necessario aggiungere due righe di codice per creare `UsingCollector` e fare in modo che visiti il nodo radice raccogliendo tutte le istruzioni `using`. Aggiungere quindi un ciclo `foreach` per visualizzare tutte le istruzioni `using` trovate dallo strumento di raccolta:

[!code-csharp[Create the UsingCollector and visit the root node.](../../../../samples/snippets/csharp/roslyn-sdk/SyntaxQuickStart/SyntaxWalker/Program.cs#6 "Create the UsingCollector and visit the root node.")]

Compilare ed eseguire il programma. Dovrebbe venire visualizzato l'output seguente.

```console
        VisitUsingDirective called with System.
        VisitUsingDirective called with System.Collections.Generic.
        VisitUsingDirective called with System.Linq.
        VisitUsingDirective called with System.Text.
        VisitUsingDirective called with Microsoft.CodeAnalysis.
                Success. Adding Microsoft.CodeAnalysis.
        VisitUsingDirective called with Microsoft.CodeAnalysis.CSharp.
                Success. Adding Microsoft.CodeAnalysis.CSharp.
        VisitUsingDirective called with Microsoft.
                Success. Adding Microsoft.
        VisitUsingDirective called with System.ComponentModel.
        VisitUsingDirective called with Microsoft.Win32.
                Success. Adding Microsoft.Win32.
        VisitUsingDirective called with System.Runtime.InteropServices.
        VisitUsingDirective called with System.CodeDom.
        VisitUsingDirective called with Microsoft.CSharp.
                Success. Adding Microsoft.CSharp.
Microsoft.CodeAnalysis
Microsoft.CodeAnalysis.CSharp
Microsoft
Microsoft.Win32
Microsoft.CSharp
Press any key to continue . . .
```

Congratulazioni! È stata usata l'**API Syntax** per individuare tipi specifici di istruzioni e dichiarazioni C# in codice sorgente C#.
