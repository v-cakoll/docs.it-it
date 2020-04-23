---
title: Utilizzo di CodeDOM
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- code compilers
- Code Document Object Model
- Code Document Object Model, graphs
- types, CodeDOM
- namespaces [.NET Framework], CodeDOM
- templated code generation
- dynamically representing source code
- source code models
- CodeDOM
- graphing with CodeDOM
- dynamic compilation
- code generators
- CodeDOM, graphs
ms.assetid: 0444ddf3-c3f6-44ed-a999-f710d9c3e0cf
ms.openlocfilehash: c4cab79976acae236de5a8eaad5a42cdba7d04f9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130005"
---
# <a name="using-the-codedom"></a><span data-ttu-id="7e431-102">Utilizzo di CodeDOM</span><span class="sxs-lookup"><span data-stu-id="7e431-102">Using the CodeDOM</span></span>
<span data-ttu-id="7e431-103">Con CodeDOM vengono offerti tipi che rappresentano molti tipi comuni di elementi di codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="7e431-103">The CodeDOM provides types that represent many common types of source code elements.</span></span> <span data-ttu-id="7e431-104">È possibile progettare un programma che compili un modello di codice sorgente usando elementi CodeDOM per assemblare un grafico di oggetti.</span><span class="sxs-lookup"><span data-stu-id="7e431-104">You can design a program that builds a source code model using CodeDOM elements to assemble an object graph.</span></span> <span data-ttu-id="7e431-105">Da tale grafico è possibile produrre codice sorgente in uno dei linguaggi di programmazione supportati tramite un generatore di codice CodeDOM.</span><span class="sxs-lookup"><span data-stu-id="7e431-105">This object graph can be rendered as source code using a CodeDOM code generator for a supported programming language.</span></span> <span data-ttu-id="7e431-106">CodeDOM può anche essere usato per compilare codice sorgente in un assembly binario.</span><span class="sxs-lookup"><span data-stu-id="7e431-106">The CodeDOM can also be used to compile source code into a binary assembly.</span></span>  
  
 <span data-ttu-id="7e431-107">Di seguito sono riportati alcuni impieghi comuni di CodeDOM:</span><span class="sxs-lookup"><span data-stu-id="7e431-107">Some common uses for the CodeDOM include:</span></span>  
  
- <span data-ttu-id="7e431-108">Generazione di codice basata su modelli: generazione di codice per ASP.NET, proxy per client di servizi Web basati su XML, creazioni guidate di codice, strumenti di progettazione e altri sistemi generatori di codice.</span><span class="sxs-lookup"><span data-stu-id="7e431-108">Templated code generation: generating code for ASP.NET, XML Web services client proxies, code wizards, designers, or other code-emitting mechanisms.</span></span>  
  
- <span data-ttu-id="7e431-109">Compilazione dinamica: supporto per la compilazione di codice in uno o più linguaggi.</span><span class="sxs-lookup"><span data-stu-id="7e431-109">Dynamic compilation: supporting code compilation in single or multiple languages.</span></span>  
  
## <a name="building-a-codedom-graph"></a><span data-ttu-id="7e431-110">Compilazione di un grafico CodeDOM</span><span class="sxs-lookup"><span data-stu-id="7e431-110">Building a CodeDOM Graph</span></span>  
 <span data-ttu-id="7e431-111">Con lo spazio dei nomi <xref:System.CodeDom> vengono specificate classi che consentono di rappresentare la struttura logica del codice sorgente, indipendentemente dalla sintassi del linguaggio.</span><span class="sxs-lookup"><span data-stu-id="7e431-111">The <xref:System.CodeDom> namespace provides classes for representing the logical structure of source code, independent of language syntax.</span></span>  
  
### <a name="the-structure-of-a-codedom-graph"></a><span data-ttu-id="7e431-112">Struttura di un grafico CodeDOM</span><span class="sxs-lookup"><span data-stu-id="7e431-112">The Structure of a CodeDOM Graph</span></span>  
 <span data-ttu-id="7e431-113">La struttura di un grafico CodeDOM può essere paragonata a una struttura ad albero di contenitori.</span><span class="sxs-lookup"><span data-stu-id="7e431-113">The structure of a CodeDOM graph is like a tree of containers.</span></span> <span data-ttu-id="7e431-114">Il contenitore di primo livello, o radice, di ogni grafico CodeDOM compilabile è un <xref:System.CodeDom.CodeCompileUnit>.</span><span class="sxs-lookup"><span data-stu-id="7e431-114">The top-most, or root, container of each compilable CodeDOM graph is a <xref:System.CodeDom.CodeCompileUnit>.</span></span> <span data-ttu-id="7e431-115">Ogni elemento del modello di codice sorgente deve essere collegato al grafico tramite una proprietà di un <xref:System.CodeDom.CodeObject> nel grafico.</span><span class="sxs-lookup"><span data-stu-id="7e431-115">Every element of your source code model must be linked into the graph through a property of a <xref:System.CodeDom.CodeObject> in the graph.</span></span>  
  
### <a name="building-a-source-code-model-for-a-sample-hello-world-program"></a><span data-ttu-id="7e431-116">Compilazione di un modello di codice sorgente per un programma di esempio Hello World</span><span class="sxs-lookup"><span data-stu-id="7e431-116">Building a Source Code Model for a Sample Hello World Program</span></span>  
 <span data-ttu-id="7e431-117">Di seguito viene illustrato come compilare un grafico di oggetti CodeDOM che rappresenta il codice di una semplice applicazione di esempio Hello World.</span><span class="sxs-lookup"><span data-stu-id="7e431-117">The following walkthrough provides an example of how to build a CodeDOM object graph that represents the code for a simple Hello World application.</span></span> <span data-ttu-id="7e431-118">Per il codice sorgente completo di questo esempio di codice, vedere l'argomento <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="7e431-118">For the complete source code for this code example, see the <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType> topic.</span></span>  
  
#### <a name="creating-a-compile-unit"></a><span data-ttu-id="7e431-119">Creazione di un'unità di compilazione</span><span class="sxs-lookup"><span data-stu-id="7e431-119">Creating a compile unit</span></span>  
 <span data-ttu-id="7e431-120">CodeDOM definisce un oggetto denominato <xref:System.CodeDom.CodeCompileUnit>, in grado di fare riferimento a un grafico di oggetti CodeDOM che modella il codice sorgente da compilare.</span><span class="sxs-lookup"><span data-stu-id="7e431-120">The CodeDOM defines an object called a <xref:System.CodeDom.CodeCompileUnit>, which can reference a CodeDOM object graph that models the source code to compile.</span></span> <span data-ttu-id="7e431-121">Una **CodeCompileUnit** possiede proprietà per l'archiviazione di riferimenti ad attributi, spazi dei nomi e assembly.</span><span class="sxs-lookup"><span data-stu-id="7e431-121">A **CodeCompileUnit** has properties for storing references to attributes, namespaces, and assemblies.</span></span>  
  
 <span data-ttu-id="7e431-122">Nei provider CodeDom che derivano dalla classe <xref:System.CodeDom.Compiler.CodeDomProvider> sono contenuti i metodi che elaborano il grafico di oggetti a cui fa riferimento una **CodeCompileUnit**.</span><span class="sxs-lookup"><span data-stu-id="7e431-122">The CodeDom providers that derive from the <xref:System.CodeDom.Compiler.CodeDomProvider> class contain methods that process the object graph referenced by a **CodeCompileUnit**.</span></span>  
  
 <span data-ttu-id="7e431-123">Per creare un grafico di oggetti per una semplice applicazione, occorre assemblare il modello di codice sorgente e farvi riferimento da una **CodeCompileUnit**.</span><span class="sxs-lookup"><span data-stu-id="7e431-123">To create an object graph for a simple application, you must assemble the source code model and reference it from a **CodeCompileUnit**.</span></span>  
  
 <span data-ttu-id="7e431-124">Per creare una nuova unità di compilazione, è possibile usare la sintassi illustrata nel seguente esempio:</span><span class="sxs-lookup"><span data-stu-id="7e431-124">You can create a new compile unit with the syntax demonstrated in this example:</span></span>  
  
 [!code-cpp[CodeDomExample#12](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source2.cpp#12)]
 [!code-csharp[CodeDomExample#12](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source2.cs#12)]
 [!code-vb[CodeDomExample#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source2.vb#12)]  
  
 <span data-ttu-id="7e431-125">Una <xref:System.CodeDom.CodeSnippetCompileUnit> può contenere una sezione di codice sorgente che è già nella forma del linguaggio di destinazione, ma non può essere compilata in un altro linguaggio.</span><span class="sxs-lookup"><span data-stu-id="7e431-125">A <xref:System.CodeDom.CodeSnippetCompileUnit> can contain a section of source code that is already in the target language, but cannot be rendered to another language.</span></span>  
  
#### <a name="defining-a-namespace"></a><span data-ttu-id="7e431-126">Definizione di uno spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="7e431-126">Defining a namespace</span></span>  
 <span data-ttu-id="7e431-127">Per definire uno spazio dei nomi, creare un <xref:System.CodeDom.CodeNamespace> e assegnarvi un nome usando il costruttore appropriato o impostandone la proprietà **Name**.</span><span class="sxs-lookup"><span data-stu-id="7e431-127">To define a namespace, create a <xref:System.CodeDom.CodeNamespace> and assign a name for it using the appropriate constructor or by setting its **Name** property.</span></span>  
  
 [!code-cpp[CodeDomExample#13](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source2.cpp#13)]
 [!code-csharp[CodeDomExample#13](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source2.cs#13)]
 [!code-vb[CodeDomExample#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source2.vb#13)]  
  
#### <a name="importing-a-namespace"></a><span data-ttu-id="7e431-128">Importazione di uno spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="7e431-128">Importing a namespace</span></span>  
 <span data-ttu-id="7e431-129">Per aggiungere allo spazio dei nomi una direttiva per l'importazione di uno spazio dei nomi, aggiungere una <xref:System.CodeDom.CodeNamespaceImport> che indica lo spazio dei nomi da importare nella raccolta **CodeNamespace.Imports**.</span><span class="sxs-lookup"><span data-stu-id="7e431-129">To add a namespace import directive to the namespace, add a <xref:System.CodeDom.CodeNamespaceImport> that indicates the namespace to import to the **CodeNamespace.Imports** collection.</span></span>  
  
 <span data-ttu-id="7e431-130">Nel codice riportato di seguito viene aggiunta un'importazione dello spazio dei nomi **System** alla raccolta **Imports** di un **CodeNamespace** denominata `samples`:</span><span class="sxs-lookup"><span data-stu-id="7e431-130">The following code adds an import for the **System** namespace to the **Imports** collection of a **CodeNamespace** named `samples`:</span></span>  
  
 [!code-cpp[CodeDomExample#14](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source2.cpp#14)]
 [!code-csharp[CodeDomExample#14](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source2.cs#14)]
 [!code-vb[CodeDomExample#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source2.vb#14)]  
  
#### <a name="linking-code-elements-into-the-object-graph"></a><span data-ttu-id="7e431-131">Collegamento di elementi di codice nel grafico di oggetti</span><span class="sxs-lookup"><span data-stu-id="7e431-131">Linking code elements into the object graph</span></span>  
 <span data-ttu-id="7e431-132">Tutti gli elementi di codice che compongono un grafico CodeDOM devono essere collegati alla <xref:System.CodeDom.CodeCompileUnit> che costituisce l'elemento radice della struttura ad albero da una serie di riferimenti tra elementi a cui si fa direttamente riferimento dalle proprietà dell'oggetto radice del grafico.</span><span class="sxs-lookup"><span data-stu-id="7e431-132">All code elements that form a CodeDOM graph must be linked to the <xref:System.CodeDom.CodeCompileUnit> that is the root element of the tree by a series of references between elements directly referenced from the properties of the root object of the graph.</span></span> <span data-ttu-id="7e431-133">Per stabilire un riferimento da un oggetto contenitore, impostare un oggetto su una proprietà dell'oggetto contenitore.</span><span class="sxs-lookup"><span data-stu-id="7e431-133">Set an object to a property of a container object to establish a reference from the container object.</span></span>  
  
 <span data-ttu-id="7e431-134">L'istruzione seguente aggiunge il `samples` **CodeNamespace** alla proprietà di raccolta **Namespaces** dell'oggetto **CodeCompileUnit** radice.</span><span class="sxs-lookup"><span data-stu-id="7e431-134">The following statement adds the `samples` **CodeNamespace** to the **Namespaces** collection property of the root **CodeCompileUnit**.</span></span>  
  
 [!code-cpp[CodeDomExample#15](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source2.cpp#15)]
 [!code-csharp[CodeDomExample#15](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source2.cs#15)]
 [!code-vb[CodeDomExample#15](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source2.vb#15)]  
  
#### <a name="defining-a-type"></a><span data-ttu-id="7e431-135">Definizione di un tipo</span><span class="sxs-lookup"><span data-stu-id="7e431-135">Defining a type</span></span>  
 <span data-ttu-id="7e431-136">Per dichiarare una classe, struttura, interfaccia o enumerazione con CodeDOM, creare un nuovo <xref:System.CodeDom.CodeTypeDeclaration> e assegnarvi un nome.</span><span class="sxs-lookup"><span data-stu-id="7e431-136">To declare a class, structure, interface, or enumeration using the CodeDOM, create a new <xref:System.CodeDom.CodeTypeDeclaration>, and assign it a name.</span></span> <span data-ttu-id="7e431-137">Nell'esempio seguente viene illustrata questa operazione tramite l'overload di un costruttore per impostare la proprietà **Name**:</span><span class="sxs-lookup"><span data-stu-id="7e431-137">The following example demonstrates this using a constructor overload to set the **Name** property:</span></span>  
  
 [!code-cpp[CodeDomExample#16](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source2.cpp#16)]
 [!code-csharp[CodeDomExample#16](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source2.cs#16)]
 [!code-vb[CodeDomExample#16](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source2.vb#16)]  
  
 <span data-ttu-id="7e431-138">Per aggiungere un tipo a uno spazio dei nomi, aggiungere una <xref:System.CodeDom.CodeTypeDeclaration> che rappresenta il tipo da aggiungere allo spazio dei nomi per la raccolta **Types** di un **CodeNamespace**.</span><span class="sxs-lookup"><span data-stu-id="7e431-138">To add a type to a namespace, add a <xref:System.CodeDom.CodeTypeDeclaration> that represents the type to add to the namespace to the **Types** collection of a **CodeNamespace**.</span></span>  
  
 <span data-ttu-id="7e431-139">Nell'esempio seguente viene illustrato come aggiungere una classe di nome `class1` a un **CodeNamespace** denominato `samples`:</span><span class="sxs-lookup"><span data-stu-id="7e431-139">The following example demonstrates how to add a class named `class1` to a **CodeNamespace** named `samples`:</span></span>  
  
 [!code-cpp[CodeDomExample#17](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source2.cpp#17)]
 [!code-csharp[CodeDomExample#17](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source2.cs#17)]
 [!code-vb[CodeDomExample#17](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source2.vb#17)]  
  
#### <a name="adding-class-members-to-a-class"></a><span data-ttu-id="7e431-140">Aggiunta di membri a una classe</span><span class="sxs-lookup"><span data-stu-id="7e431-140">Adding class members to a class</span></span>  
 <span data-ttu-id="7e431-141">Con lo spazio dei nomi <xref:System.CodeDom> vengono offerti diversi elementi che possono essere usati per rappresentare membri di classi.</span><span class="sxs-lookup"><span data-stu-id="7e431-141">The <xref:System.CodeDom> namespace provides a variety of elements that can be used to represent class members.</span></span> <span data-ttu-id="7e431-142">Ogni membro di classe può essere aggiunto alla raccolta **Members** di una <xref:System.CodeDom.CodeTypeDeclaration>.</span><span class="sxs-lookup"><span data-stu-id="7e431-142">Each class member can be added to the **Members** collection of a <xref:System.CodeDom.CodeTypeDeclaration>.</span></span>  
  
#### <a name="defining-a-code-entry-point-method-for-an-executable"></a><span data-ttu-id="7e431-143">Definizione di un metodo di punto di ingresso al codice di un file eseguibile</span><span class="sxs-lookup"><span data-stu-id="7e431-143">Defining a code entry point method for an executable</span></span>  
 <span data-ttu-id="7e431-144">Se si sta compilando il codice di un programma eseguibile, è necessario indicarne il punto d'ingresso creando un <xref:System.CodeDom.CodeEntryPointMethod> che rappresenti il metodo da cui si vuole che l'esecuzione del programma abbia inizio.</span><span class="sxs-lookup"><span data-stu-id="7e431-144">If you are building code for an executable program, it is necessary to indicate the entry point of a program by creating a <xref:System.CodeDom.CodeEntryPointMethod> to represent the method at which program execution should begin.</span></span>  
  
 <span data-ttu-id="7e431-145">Nell'esempio seguente viene illustrato come definire un punto di ingresso che contenga una <xref:System.CodeDom.CodeMethodInvokeExpression> che chiama **System.Console.WriteLine** per scrivere "Hello World!":</span><span class="sxs-lookup"><span data-stu-id="7e431-145">The following example demonstrates how to define an entry point method that contains a <xref:System.CodeDom.CodeMethodInvokeExpression> that calls **System.Console.WriteLine** to print "Hello World!":</span></span>  
  
 [!code-cpp[CodeDomExample#18](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source2.cpp#18)]
 [!code-csharp[CodeDomExample#18](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source2.cs#18)]
 [!code-vb[CodeDomExample#18](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source2.vb#18)]  
  
 <span data-ttu-id="7e431-146">L'istruzione seguente aggiunge il metodo del punto di ingresso denominato `Start` alla raccolta **Members** di `class1`:</span><span class="sxs-lookup"><span data-stu-id="7e431-146">The following statement adds the entry point method named `Start` to the **Members** collection of `class1`:</span></span>  
  
 [!code-cpp[CodeDomExample#19](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source2.cpp#19)]
 [!code-csharp[CodeDomExample#19](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source2.cs#19)]
 [!code-vb[CodeDomExample#19](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source2.vb#19)]  
  
 <span data-ttu-id="7e431-147">A questo punto l'oggetto <xref:System.CodeDom.CodeCompileUnit> denominato `compileUnit` contiene il grafico CodeDOM di un semplice programma Hello World.</span><span class="sxs-lookup"><span data-stu-id="7e431-147">Now the <xref:System.CodeDom.CodeCompileUnit> named `compileUnit` contains the CodeDOM graph for a simple Hello World program.</span></span> <span data-ttu-id="7e431-148">Per informazioni sulla generazione e compilazione di codice da un grafico CodeDOM, vedere [Generazione di codice sorgente e compilazione di un programma a partire da un grafico CodeDOM](generating-and-compiling-source-code-from-a-codedom-graph.md).</span><span class="sxs-lookup"><span data-stu-id="7e431-148">For information on generating and compiling code from a CodeDOM graph, see [Generating Source Code and Compiling a Program from a CodeDOM Graph](generating-and-compiling-source-code-from-a-codedom-graph.md).</span></span>  
  
### <a name="more-information-on-building-a-codedom-graph"></a><span data-ttu-id="7e431-149">Altre informazioni sulla compilazione di un grafico CodeDOM</span><span class="sxs-lookup"><span data-stu-id="7e431-149">More information on building a CodeDOM graph</span></span>  
 <span data-ttu-id="7e431-150">Con CodeDOM viene offerto il supporto dei tipi di elementi di codice più comuni impiegati dai linguaggi di programmazione che supportano Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="7e431-150">The CodeDOM supports the many common types of code elements found in programming languages that support the common language runtime.</span></span> <span data-ttu-id="7e431-151">CodeDOM non è progettato per fornire elementi in grado di rappresentare tutte le possibili funzionalità dei linguaggi di programmazione.</span><span class="sxs-lookup"><span data-stu-id="7e431-151">The CodeDOM was not designed to provide elements to represent all possible programming language features.</span></span> <span data-ttu-id="7e431-152">Il codice che non può essere rappresentato facilmente con gli elementi CodeDOM può essere incapsulato in un <xref:System.CodeDom.CodeSnippetExpression>, <xref:System.CodeDom.CodeSnippetStatement>, <xref:System.CodeDom.CodeSnippetTypeMember>, o un <xref:System.CodeDom.CodeSnippetCompileUnit>.</span><span class="sxs-lookup"><span data-stu-id="7e431-152">Code that cannot be represented easily with CodeDOM elements can be encapsulated in a <xref:System.CodeDom.CodeSnippetExpression>, a <xref:System.CodeDom.CodeSnippetStatement>, a <xref:System.CodeDom.CodeSnippetTypeMember>, or a <xref:System.CodeDom.CodeSnippetCompileUnit>.</span></span> <span data-ttu-id="7e431-153">Con CodeDOM non è tuttavia possibile tradurre automaticamente frammenti in altri linguaggi.</span><span class="sxs-lookup"><span data-stu-id="7e431-153">However, snippets cannot be translated to other languages automatically by the CodeDOM.</span></span>  
  
 <span data-ttu-id="7e431-154">Per la documentazione dei diversi tipi CodeDOM, vedere la documentazione di riferimento relativa allo spazio dei nomi <xref:System.CodeDom>.</span><span class="sxs-lookup"><span data-stu-id="7e431-154">For documentation for the each of the CodeDOM types, see the reference documentation for the <xref:System.CodeDom> namespace.</span></span>  
  
 <span data-ttu-id="7e431-155">Per una tavola di consultazione rapida che consenta di individuare l'elemento CodeDOM che rappresenta uno specifico tipo di elemento di codice, vedere [Riferimento rapido per CodeDOM](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/f1dfsbhc(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="7e431-155">For a quick chart to locate the CodeDOM element that represents a specific type of code element, see the [CodeDOM Quick Reference](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/f1dfsbhc(v=vs.100)).</span></span>
