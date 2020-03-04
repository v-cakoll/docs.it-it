---
title: Introduzione alla trasformazione della sintassi (API Roslyn)
description: Introduzione all'attraversamento, all'esecuzione di query e all'esplorazione di alberi della sintassi.
ms.date: 06/01/2018
ms.custom: mvc
ms.openlocfilehash: 5045dca839daba1070b34720e72cc9c4f7b94828
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/03/2020
ms.locfileid: "78240610"
---
# <a name="get-started-with-syntax-transformation"></a>Introduzione alla trasformazione della sintassi

Questa esercitazione si basa sui concetti e sulle tecniche descritti nelle guide introduttive [Introduzione all'analisi della sintassi](syntax-analysis.md) e [Introduzione all'analisi semantica](semantic-analysis.md). Se non è già stato fatto, consultare tali guide introduttive prima di procedere con questa.

In questa guida verranno illustrate le tecniche per la creazione e la trasformazione degli alberi della sintassi. In combinazione con le tecniche apprese nelle guide precedenti, sarà possibile creare il primo refactoring dalla riga di comando.

[!INCLUDE[interactive-note](~/includes/roslyn-installation.md)]

## <a name="immutability-and-the-net-compiler-platform"></a>Non modificabilità e piattaforma del compilatore .NET

La **non modificabilità** è un principio fondamentale della piattaforma del compilatore .NET. Le strutture di dati non modificabili non possono essere alterate dopo essere state create. Le strutture di dati non modificabili possono essere condivise in modo sicuro e analizzate da più consumer contemporaneamente. Non vi è alcun rischio che un consumer influisca su un altro in modi imprevedibili. L'analizzatore non richiede blocchi o altre misure di concorrenza. Questa regola si applica ad alberi della sintassi, compilazioni, simboli, modelli semantici e tutte le altre strutture di dati. Invece di modificare le strutture esistenti, le API creano nuovi oggetti in base alle differenze specificate rispetto a quelli precedenti. È possibile applicare questo concetto agli alberi della sintassi per creare nuovi alberi tramite trasformazioni.

## <a name="create-and-transform-trees"></a>Creare e trasformare alberi

È possibile scegliere tra due strategie per le trasformazioni della sintassi. I **metodi factory** sono particolarmente indicati per la ricerca di nodi specifici da sostituire o di posizioni specifiche in cui inserire nuovo codice. I **rewriter** sono la soluzione migliore per analizzare un intero progetto alla ricerca di modelli di codice da sostituire.

### <a name="create-nodes-with-factory-methods"></a>Creare nodi con metodi factory

La prima trasformazione della sintassi illustra i metodi factory. Si sostituirà un'istruzione `using System.Collections;` con un'istruzione `using System.Collections.Generic;`. Questo esempio illustra come creare oggetti <xref:Microsoft.CodeAnalysis.CSharp.CSharpSyntaxNode?displayProperty=nameWithType> mediante i metodi factory <xref:Microsoft.CodeAnalysis.CSharp.SyntaxFactory?displayProperty=nameWithType>. Per ogni tipo di **nodo**, **token** o **elemento semplice** è disponibile un metodo factory che crea un'istanza del tipo corrispondente. È possibile creare alberi della sintassi componendo gerarchicamente i nodi dal basso verso l'alto. Si trasformerà quindi il programma esistente sostituendo i nodi esistenti con il nuovo albero creato.

Avviare Visual Studio e creare un nuovo progetto C# **Stand-Alone Code Analysis Tool** (Strumento di analisi del codice autonomo). In Visual Studio scegliere **File** > **Nuovo** > **Progetto** per visualizzare la finestra di dialogo Nuovo progetto. In **Visual C#** > **Estendibilità** scegliere uno **Stand-Alone Code Analysis Tool** (Strumento di analisi del codice autonomo). Questa guida include due progetti di esempio, quindi denominare la soluzione **SyntaxTransformationQuickStart** e il progetto **ConstructionCS**. Fare clic su **OK**.

Questo progetto usa i metodi della classe <xref:Microsoft.CodeAnalysis.CSharp.SyntaxFactory?displayProperty=nameWithType> per costruire un <xref:Microsoft.CodeAnalysis.CSharp.Syntax.NameSyntax?displayProperty=nameWithType> che rappresenta lo spazio dei nomi `System.Collections.Generic`.

Aggiungere la direttiva using seguente all'inizio del file `Program.cs` per importare i metodi factory della classe <xref:Microsoft.CodeAnalysis.CSharp.SyntaxFactory> e i metodi di <xref:System.Console>, in modo da poterli usare in un secondo momento senza qualificarli:

[!code-csharp[import the SyntaxFactory class](../../../../samples/snippets/csharp/roslyn-sdk/SyntaxTransformationQuickStart/ConstructionCS/Program.cs#StaticUsings "import the Syntax Factory class and the System.Console class")]

Verranno creati i **nodi della sintassi dei nomi** per creare l'albero che rappresenta l'istruzione `using System.Collections.Generic;`. <xref:Microsoft.CodeAnalysis.CSharp.Syntax.NameSyntax> è la classe di base per quattro tipi di nomi disponibili in C#. Questi quattro tipi di nomi possono essere combinati per creare qualsiasi nome disponibile nel linguaggio C#:

* <xref:Microsoft.CodeAnalysis.CSharp.Syntax.NameSyntax?displayProperty=nameWithType>, che rappresenta i nomi di singoli identificatori semplici, come `System` e `Microsoft`.
* <xref:Microsoft.CodeAnalysis.CSharp.Syntax.GenericNameSyntax?displayProperty=nameWithType>, che rappresenta un nome di tipo o di metodo generico, come `List<int>`.
* <xref:Microsoft.CodeAnalysis.CSharp.Syntax.QualifiedNameSyntax?displayProperty=nameWithType>, che rappresenta un nome completo nel formato `<left-name>.<right-identifier-or-generic-name>`, come `System.IO`.
* <xref:Microsoft.CodeAnalysis.CSharp.Syntax.AliasQualifiedNameSyntax?displayProperty=nameWithType>, che rappresenta un nome usando un alias assembly extern, come `LibraryV2::Foo`.

Usare il metodo <xref:Microsoft.CodeAnalysis.CSharp.SyntaxFactory.IdentifierName(System.String)> per creare un nodo <xref:Microsoft.CodeAnalysis.CSharp.Syntax.NameSyntax>. Aggiungere il codice seguente nel metodo `Main` in `Program.cs`:

[!code-csharp[create the system identifier](../../../../samples/snippets/csharp/roslyn-sdk/SyntaxTransformationQuickStart/ConstructionCS/Program.cs#CreateIdentifierName "Create and display the system name identifier")]

Il codice precedente crea un oggetto <xref:Microsoft.CodeAnalysis.CSharp.Syntax.IdentifierNameSyntax> e lo assegna alla variabile `name`. Molte API Roslyn restituiscono classi di base per agevolare l'uso dei tipi correlati. La variabile `name`, un oggetto <xref:Microsoft.CodeAnalysis.CSharp.Syntax.NameSyntax>, può essere riutilizzata durante la creazione di <xref:Microsoft.CodeAnalysis.CSharp.Syntax.QualifiedNameSyntax>. Non usare l'inferenza del tipo durante la creazione dell'esempio. Tale passaggio verrà automatizzato in questo progetto.

Il nome è stato creato. A questo punto, è possibile creare altri nodi nell'albero compilando un oggetto <xref:Microsoft.CodeAnalysis.CSharp.Syntax.QualifiedNameSyntax>. Il nuovo albero usa `name` a sinistra del nome e una nuova <xref:Microsoft.CodeAnalysis.CSharp.Syntax.IdentifierNameSyntax> per lo spazio dei nomi `Collections` come lato destro dell'oggetto <xref:Microsoft.CodeAnalysis.CSharp.Syntax.QualifiedNameSyntax>. Aggiungere il codice seguente a `program.cs`:

[!code-csharp[create the collections identifier](../../../../samples/snippets/csharp/roslyn-sdk/SyntaxTransformationQuickStart/ConstructionCS/Program.cs#CreateQualifiedIdentifierName "Build the System.Collections identifier")]

Eseguire nuovamente il codice e visualizzare i risultati. Si sta creando un albero dei nodi che rappresenta il codice. Si continuerà con questo modello per creare l'oggetto <xref:Microsoft.CodeAnalysis.CSharp.Syntax.QualifiedNameSyntax> per lo spazio dei nomi `System.Collections.Generic`. Aggiungere il codice seguente a `Program.cs`:

[!code-csharp[create the full identifier](../../../../samples/snippets/csharp/roslyn-sdk/SyntaxTransformationQuickStart/ConstructionCS/Program.cs#CreateFullNamespace "Build the System.Collections.Generic identifier")]

Eseguire nuovamente il programma per vedere che è stato creato l'albero per il codice da aggiungere.

### <a name="create-a-modified-tree"></a>Creare una struttura modificata

È stato creato un albero della sintassi di piccole dimensioni che contiene una sola istruzione. Le API per la creazione di nuovi nodi sono la soluzione ideale per creare singole istruzioni o altri piccoli blocchi di codice. Tuttavia, per creare blocchi di codice di maggiori dimensioni, è necessario usare metodi che sostituiscono i nodi o inseriscono i nodi in una struttura esistente. Tenere presente che gli alberi della sintassi non sono modificabili. L'**API Syntax** non offre alcun meccanismo per la modifica di un albero della sintassi esistente dopo la costruzione. Fornisce invece metodi che producono nuovi alberi in base alle modifiche a quelli esistenti. I metodi `With*` sono definiti nelle classi concrete che derivano da <xref:Microsoft.CodeAnalysis.SyntaxNode> o nei metodi di estensione dichiarati nella classe <xref:Microsoft.CodeAnalysis.SyntaxNodeExtensions>. Questi metodi creano un nuovo nodo applicando le modifiche alle proprietà figlio del nodo esistente. Inoltre, il metodo di estensione <xref:Microsoft.CodeAnalysis.SyntaxNodeExtensions.ReplaceNode%2A> può essere usato per sostituire un nodo discendente in un sottoalbero. Anche questo metodo aggiorna l'elemento padre in modo da puntare all'elemento figlio appena creato e ripete il processo per l'intero albero: un processo noto come _re-spinning_ dell'albero.

Il passaggio successivo consiste nel creare un albero che rappresenta un intero programma (di piccole dimensioni) e quindi modificarlo. Aggiungere il codice seguente all'inizio della classe `Program`:

[!code-csharp[create a parse tree](../../../../samples/snippets/csharp/roslyn-sdk/SyntaxTransformationQuickStart/ConstructionCS/Program.cs#DeclareSampleCode "Create a tree that represents a small program")]

> [!NOTE]
> Nell'esempio di codice viene usato lo spazio dei nomi `System.Collections`, invece dello spazio dei nomi `System.Collections.Generic`.

Aggiungere quindi il codice seguente alla fine del metodo `Main` per analizzare il testo e creare un albero:

[!code-csharp[create a parse tree](../../../../samples/snippets/csharp/roslyn-sdk/SyntaxTransformationQuickStart/ConstructionCS/Program.cs#CreateParseTree "Create a tree that represents a small program")]

In questo esempio viene usato il metodo <xref:Microsoft.CodeAnalysis.CSharp.Syntax.UsingDirectiveSyntax.WithName(Microsoft.CodeAnalysis.CSharp.Syntax.NameSyntax)?displayProperty=NameWithType> per sostituire il nome in un nodo <xref:Microsoft.CodeAnalysis.CSharp.Syntax.UsingDirectiveSyntax> con quello creato nel codice precedente.

Creare un nuovo nodo <xref:Microsoft.CodeAnalysis.CSharp.Syntax.UsingDirectiveSyntax> usando il metodo <xref:Microsoft.CodeAnalysis.CSharp.Syntax.UsingDirectiveSyntax.WithName(Microsoft.CodeAnalysis.CSharp.Syntax.NameSyntax)> per aggiornare il nome `System.Collections` con il nome creato nel codice precedente. Aggiungere il codice seguente alla fine del metodo `Main`:

[!code-csharp[create a new subtree](../../../../samples/snippets/csharp/roslyn-sdk/SyntaxTransformationQuickStart/ConstructionCS/Program.cs#BuildNewUsing "Create the subtree with the replaced namespace")]

Eseguire il programma ed esaminare attentamente l'output. `newusing` non è stato inserito nell'albero della radice. La struttura originale non è stata modificata.

Aggiungere il codice seguente usando il metodo di estensione <xref:Microsoft.CodeAnalysis.SyntaxNodeExtensions.ReplaceNode%2A> per creare un nuovo albero. Il nuovo albero è il risultato della sostituzione dell'importazione esistente con il nodo `newUsing` aggiornato. Questo nuovo albero viene assegnato alla variabile `root` esistente:

[!code-csharp[create a new root tree](../../../../samples/snippets/csharp/roslyn-sdk/SyntaxTransformationQuickStart/ConstructionCS/Program.cs#TransformTree "Create the transformed root tree with the replaced namespace")]

Eseguire di nuovo il programma. Questa volta l'albero importa correttamente lo spazio dei nomi `System.Collections.Generic`.

### <a name="transform-trees-using-syntaxrewriters"></a>Trasformare alberi tramite `SyntaxRewriters`

I metodi `With*` e <xref:Microsoft.CodeAnalysis.SyntaxNodeExtensions.ReplaceNode%2A> offrono una pratica soluzione per trasformare singoli rami di un albero della sintassi. La classe <xref:Microsoft.CodeAnalysis.CSharp.CSharpSyntaxRewriter?displayProperty=nameWithType> esegue più trasformazioni in una struttura della sintassi. La classe <xref:Microsoft.CodeAnalysis.CSharp.CSharpSyntaxRewriter?displayProperty=nameWithType> è una sottoclasse di <xref:Microsoft.CodeAnalysis.CSharp.CSharpSyntaxVisitor%601?displayProperty=nameWithType>. <xref:Microsoft.CodeAnalysis.CSharp.CSharpSyntaxRewriter> applica una trasformazione a un tipo specifico di <xref:Microsoft.CodeAnalysis.SyntaxNode>. È possibile applicare trasformazioni a vari tipi di oggetti <xref:Microsoft.CodeAnalysis.SyntaxNode> ogni volta che compaiono in un albero della sintassi. Il secondo progetto in questa guida introduttiva crea un refactoring dalla riga di comando che rimuove i tipi espliciti nelle dichiarazioni di variabili locali ovunque sia possibile usare l'inferenza del tipo.

Creare un nuovo progetto C# **Stand-Alone Code Analysis Tool** (Strumento di analisi del codice autonomo). In Visual Studio fare doppio clic sul nodo `SyntaxTransformationQuickStart` della soluzione. Scegliere **Aggiungi** > **Nuovo progetto** per visualizzare la finestra di dialogo **Nuovo progetto**. In **Visual C#** > **Estendibilità** scegliere **Stand-Alone Code Analysis Tool** (Strumento di analisi del codice autonomo). Assegnare al progetto il nome `TransformationCS` e fare clic su OK.

Il primo passaggio consiste nella creazione di una classe che deriva da <xref:Microsoft.CodeAnalysis.CSharp.CSharpSyntaxRewriter> per eseguire le trasformazioni. Aggiungere un nuovo file di classe al progetto. In Visual Studio scegliere **progetto** > **Aggiungi classe...**. Nella finestra di dialogo **Aggiungi nuovo elemento** Digitare `TypeInferenceRewriter.cs` come nome file.

Aggiungere le direttive using seguenti al file `TypeInferenceRewriter.cs`:

[!code-csharp[add necessary usings](../../../../samples/snippets/csharp/roslyn-sdk/SyntaxTransformationQuickStart/TransformationCS/TypeInferenceRewriter.cs#AddUsings "Add required usings")]

Impostare quindi la classe `TypeInferenceRewriter` in modo da estendere la classe <xref:Microsoft.CodeAnalysis.CSharp.CSharpSyntaxRewriter>:

[!code-csharp[add base class](../../../../samples/snippets/csharp/roslyn-sdk/SyntaxTransformationQuickStart/TransformationCS/TypeInferenceRewriter.cs#BaseClass "Add base class")]

Aggiungere il codice seguente per dichiarare un campo privato di sola lettura che contiene un <xref:Microsoft.CodeAnalysis.SemanticModel> e inizializzarlo nel costruttore. Questo campo sarà necessario in un secondo momento per determinare dove è possibile usare l'inferenza del tipo:

[!code-csharp[initialize members](../../../../samples/snippets/csharp/roslyn-sdk/SyntaxTransformationQuickStart/TransformationCS/TypeInferenceRewriter.cs#Construction "Declare and initialize member variables")]

Eseguire l'override del metodo <xref:Microsoft.CodeAnalysis.CSharp.CSharpSyntaxRewriter.VisitLocalDeclarationStatement(Microsoft.CodeAnalysis.CSharp.Syntax.LocalDeclarationStatementSyntax)>:

```csharp
public override SyntaxNode VisitLocalDeclarationStatement(LocalDeclarationStatementSyntax node)
{

}
```

> [!NOTE]
> Molte API Roslyn dichiarano tipi restituiti che sono classi di base degli effettivi tipi di runtime restituiti. In molti scenari un tipo di nodo può essere interamente sostituito da un altro tipo di nodo o può essere addirittura rimosso. In questo esempio, il metodo <xref:Microsoft.CodeAnalysis.CSharp.CSharpSyntaxRewriter.VisitLocalDeclarationStatement(Microsoft.CodeAnalysis.CSharp.Syntax.LocalDeclarationStatementSyntax)> restituisce un <xref:Microsoft.CodeAnalysis.SyntaxNode>, anziché il tipo derivato <xref:Microsoft.CodeAnalysis.CSharp.Syntax.LocalDeclarationStatementSyntax>. Il rewriter restituisce un nuovo nodo <xref:Microsoft.CodeAnalysis.CSharp.Syntax.LocalDeclarationStatementSyntax> basato su quello esistente.

Questa guida introduttiva gestisce le dichiarazioni di variabili locali. È possibile estenderla ad altre dichiarazioni, ad esempio cicli `foreach`, cicli `for`, espressioni LINQ ed espressioni lambda. Inoltre, il rewriter trasformerà solo le dichiarazioni nella forma più semplice:

```csharp
Type variable = expression;
```

Se si vuole esplorare in autonomia, considerare di estendere l'esempio completato per questi tipi di dichiarazioni di variabili:

```csharp
// Multiple variables in a single declaration.
Type variable1 = expression1,
     variable2 = expression2;
// No initializer.
Type variable;
```

Aggiungere il codice seguente nel corpo del metodo `VisitLocalDeclarationStatement` per ignorare la riscrittura di queste forme di dichiarazioni:

[!code-csharp[exclude other declarations](../../../../samples/snippets/csharp/roslyn-sdk/SyntaxTransformationQuickStart/TransformationCS/TypeInferenceRewriter.cs#Exclusions "Exclude variables declarations not processed by this sample")]

Il metodo indica che non viene eseguita alcuna riscrittura restituendo il parametro `node` senza modifiche. Se nessuna di queste espressioni `if` è true, il nodo rappresenta una possibile dichiarazione con l'inizializzazione. Aggiungere queste istruzioni per estrarre il nome del tipo specificato nella dichiarazione ed eseguirne il binding usando il campo <xref:Microsoft.CodeAnalysis.SemanticModel> per ottenere un simbolo di tipo:

[!code-csharp[extract type name](../../../../samples/snippets/csharp/roslyn-sdk/SyntaxTransformationQuickStart/TransformationCS/TypeInferenceRewriter.cs#ExtractTypeSymbol "Extract the type name specified by the declaration")]

A questo punto, aggiungere l'istruzione seguente per eseguire il binding dell'espressione dell'inizializzatore:

[!code-csharp[bind initializer](../../../../samples/snippets/csharp/roslyn-sdk/SyntaxTransformationQuickStart/TransformationCS/TypeInferenceRewriter.cs#BindInitializer "Bind the initializer expressions")]

Infine, aggiungere l'istruzione `if` seguente per sostituire il nome del tipo esistente con la parola chiave `var` se il tipo di espressione dell'inizializzatore corrisponde al tipo specificato:

[!code-csharp[ReplaceNode](../../../../samples/snippets/csharp/roslyn-sdk/SyntaxTransformationQuickStart/TransformationCS/TypeInferenceRewriter.cs#ReplaceNode "Replace the initializer node")]

L'operazione condizionale è necessaria perché la dichiarazione può esegue il cast dell'espressione dell'inizializzatore su un'interfaccia o una classe di base. Se si vuole ottenere tale risultato, i tipi sul lato sinistro e destro dell'assegnazione non corrispondono. La rimozione del tipo esplicito in questi casi comporterebbe la modifica della semantica di un programma. `var` viene specificato come un identificatore anziché come una parola chiave poiché `var` è una parola chiave contestuale. Gli elementi semplici iniziali e finali (spazio) vengono trasferiti dal nome del tipo precedente alla parola chiave `var` per mantenere lo spazio vuoto verticale e il rientro. È più semplice usare `ReplaceNode` anziché `With*` per trasformare <xref:Microsoft.CodeAnalysis.CSharp.Syntax.LocalDeclarationStatementSyntax>, perché il nome del tipo è di fatto il nipote dell'istruzione di dichiarazione.

`TypeInferenceRewriter` è stato completato. A questo punto, eseguire la restituzione nel file `Program.cs` per completare l'esempio. Creare un <xref:Microsoft.CodeAnalysis.Compilation> di test e ottenere <xref:Microsoft.CodeAnalysis.SemanticModel> da quest'ultimo. Usare tale <xref:Microsoft.CodeAnalysis.SemanticModel> per provare `TypeInferenceRewriter`. Questo passaggio verrà eseguito per ultimo. Nel frattempo dichiarare una variabile segnaposto che rappresenta la compilazione di test:

[!code-csharp[DeclareCompilation](../../../../samples/snippets/csharp/roslyn-sdk/SyntaxTransformationQuickStart/TransformationCS/Program.cs#DeclareTestCompilation "Declare the test compilation")]

Dopo qualche istante, dovrebbe essere visualizzata una sottolineatura ondulata di errore che indica che non è presente alcun metodo `CreateTestCompilation`. Premere **CTRL+PUNTO** per aprire la lampadina e quindi premere INVIO per richiamare il comando **Genera stub di metodo**. Questo comando genererà uno stub di metodo per il metodo `CreateTestCompilation` nella classe `Program`. Si tornerà a questo metodo per la compilazione in un secondo momento:

![Uso della generazione del metodo in C#](./media/syntax-transformation/generate-from-usage.png)

Scrivere il codice seguente per eseguire l'iterazione su ogni <xref:Microsoft.CodeAnalysis.SyntaxTree> nel <xref:Microsoft.CodeAnalysis.Compilation> di test. Per ognuno, inizializzare un nuovo `TypeInferenceRewriter` con il <xref:Microsoft.CodeAnalysis.SemanticModel> per l'albero corrispondente:

[!code-csharp[IterateTrees](../../../../samples/snippets/csharp/roslyn-sdk/SyntaxTransformationQuickStart/TransformationCS/Program.cs#IterateTrees "Iterate all the source trees in the test compilation")]

All'interno dell'istruzione `foreach` che è stata creata, aggiungere il codice seguente per eseguire la trasformazione su ogni albero di origine. Questo codice scrive in modo condizionale il nuovo albero trasformato se sono state apportate modifiche. Il rewriter deve modificare un albero solo se rileva una o più dichiarazioni di variabili locali che potrebbero essere semplificate tramite l'inferenza del tipo:

[!code-csharp[TransformTrees](../../../../samples/snippets/csharp/roslyn-sdk/SyntaxTransformationQuickStart/TransformationCS/Program.cs#TransformTrees "Transform and save any trees that are modified by the rewriter")]

Dovrebbero essere visualizzate sottolineature ondulate sotto il codice `File.WriteAllText`. Selezionare la lampadina e aggiungere l'istruzione `using System.IO;` necessaria.

Ci siamo quasi. Manca solo un passaggio: creare un <xref:Microsoft.CodeAnalysis.Compilation> di test. Poiché non è stata usata l'inferenza del tipo, questa guida introduttiva rappresenterebbe un test case perfetto. Purtroppo, la creazione di una compilazione da un file di progetto C# esula dall'ambito di questa procedura dettagliata. Tuttavia, se le istruzioni sono state seguite con attenzione, esiste una possibilità. Sostituire il contenuto del metodo `CreateTestCompilation` con il codice riportato di seguito. Tale codice crea una compilazione di test che casualmente corrisponde al progetto descritto in questa guida introduttiva:

[!code-csharp[CreateTestCompilation](../../../../samples/snippets/csharp/roslyn-sdk/SyntaxTransformationQuickStart/TransformationCS/Program.cs#CreateTestCompilation "Create a test compilation using the code written for this quickstart.")]

Eseguire il progetto. In Visual Studio scegliere **Debug** > **Avvia debug**. Visual Studio dovrebbe segnalare che i file nel progetto sono stati modificati. Fare clic su **Sì a tutti** per ricaricare i file modificati. Esaminarli per osservare i risultati ottenuti. Si noti quanto risulta più pulito il codice senza tutti gli identificatori di tipi espliciti e ridondanti.

Congratulazioni! Sono state usate le **API del compilatore** per scrivere un refactoring che cerca alcuni modelli sintattici in tutti i file in un progetto C#, analizza la semantica del codice sorgente che corrisponde a tali modelli e la trasforma. A questo punto, la creazione del refactoring è conclusa.
