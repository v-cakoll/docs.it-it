---
title: Utilizzo di CodeDOM
description: Utilizzare il Code Document Object Model (CodeDOM), che fornisce tipi che rappresentano molti tipi comuni di elementi di codice sorgente, per assemblare un oggetto grafico.
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
ms.openlocfilehash: 476d8c18f386f889855c664147b1ee20995dc6f9
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/21/2020
ms.locfileid: "86865216"
---
# <a name="using-the-codedom"></a>Utilizzo di CodeDOM
Con CodeDOM vengono offerti tipi che rappresentano molti tipi comuni di elementi di codice sorgente. È possibile progettare un programma che compili un modello di codice sorgente usando elementi CodeDOM per assemblare un grafico di oggetti. Da tale grafico è possibile produrre codice sorgente in uno dei linguaggi di programmazione supportati tramite un generatore di codice CodeDOM. CodeDOM può anche essere usato per compilare codice sorgente in un assembly binario.  
  
 Di seguito sono riportati alcuni impieghi comuni di CodeDOM:  
  
- Generazione di codice basata su modelli: generazione di codice per ASP.NET, proxy per client di servizi Web basati su XML, creazioni guidate di codice, strumenti di progettazione e altri sistemi generatori di codice.  
  
- Compilazione dinamica: supporto per la compilazione di codice in uno o più linguaggi.  
  
## <a name="building-a-codedom-graph"></a>Compilazione di un grafico CodeDOM  
 Con lo spazio dei nomi <xref:System.CodeDom> vengono specificate classi che consentono di rappresentare la struttura logica del codice sorgente, indipendentemente dalla sintassi del linguaggio.  
  
### <a name="the-structure-of-a-codedom-graph"></a>Struttura di un grafico CodeDOM  
 La struttura di un grafico CodeDOM può essere paragonata a una struttura ad albero di contenitori. Il contenitore di primo livello, o radice, di ogni grafico CodeDOM compilabile è un <xref:System.CodeDom.CodeCompileUnit>. Ogni elemento del modello di codice sorgente deve essere collegato al grafico tramite una proprietà di un <xref:System.CodeDom.CodeObject> nel grafico.  
  
### <a name="building-a-source-code-model-for-a-sample-hello-world-program"></a>Compilazione di un modello di codice sorgente per un programma di esempio Hello World  
 Di seguito viene illustrato come compilare un grafico di oggetti CodeDOM che rappresenta il codice di una semplice applicazione di esempio Hello World. Per il codice sorgente completo di questo esempio di codice, vedere l'argomento <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType>.  
  
#### <a name="creating-a-compile-unit"></a>Creazione di un'unità di compilazione  
 CodeDOM definisce un oggetto denominato <xref:System.CodeDom.CodeCompileUnit>, in grado di fare riferimento a un grafico di oggetti CodeDOM che modella il codice sorgente da compilare. Una **CodeCompileUnit** possiede proprietà per l'archiviazione di riferimenti ad attributi, spazi dei nomi e assembly.  
  
 Nei provider CodeDom che derivano dalla classe <xref:System.CodeDom.Compiler.CodeDomProvider> sono contenuti i metodi che elaborano il grafico di oggetti a cui fa riferimento una **CodeCompileUnit**.  
  
 Per creare un grafico di oggetti per una semplice applicazione, occorre assemblare il modello di codice sorgente e farvi riferimento da una **CodeCompileUnit**.  
  
 Per creare una nuova unità di compilazione, è possibile usare la sintassi illustrata nel seguente esempio:  
  
 [!code-cpp[CodeDomExample#12](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source2.cpp#12)]
 [!code-csharp[CodeDomExample#12](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source2.cs#12)]
 [!code-vb[CodeDomExample#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source2.vb#12)]  
  
 Una <xref:System.CodeDom.CodeSnippetCompileUnit> può contenere una sezione di codice sorgente che è già nella forma del linguaggio di destinazione, ma non può essere compilata in un altro linguaggio.  
  
#### <a name="defining-a-namespace"></a>Definizione di uno spazio dei nomi  
 Per definire uno spazio dei nomi, creare un <xref:System.CodeDom.CodeNamespace> e assegnarvi un nome usando il costruttore appropriato o impostandone la proprietà **Name**.  
  
 [!code-cpp[CodeDomExample#13](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source2.cpp#13)]
 [!code-csharp[CodeDomExample#13](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source2.cs#13)]
 [!code-vb[CodeDomExample#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source2.vb#13)]  
  
#### <a name="importing-a-namespace"></a>Importazione di uno spazio dei nomi  
 Per aggiungere allo spazio dei nomi una direttiva per l'importazione di uno spazio dei nomi, aggiungere una <xref:System.CodeDom.CodeNamespaceImport> che indica lo spazio dei nomi da importare nella raccolta **CodeNamespace.Imports**.  
  
 Nel codice riportato di seguito viene aggiunta un'importazione dello spazio dei nomi **System** alla raccolta **Imports** di un **CodeNamespace** denominata `samples`:  
  
 [!code-cpp[CodeDomExample#14](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source2.cpp#14)]
 [!code-csharp[CodeDomExample#14](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source2.cs#14)]
 [!code-vb[CodeDomExample#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source2.vb#14)]  
  
#### <a name="linking-code-elements-into-the-object-graph"></a>Collegamento di elementi di codice nel grafico di oggetti  
 Tutti gli elementi di codice che compongono un grafico CodeDOM devono essere collegati alla <xref:System.CodeDom.CodeCompileUnit> che costituisce l'elemento radice della struttura ad albero da una serie di riferimenti tra elementi a cui si fa direttamente riferimento dalle proprietà dell'oggetto radice del grafico. Per stabilire un riferimento da un oggetto contenitore, impostare un oggetto su una proprietà dell'oggetto contenitore.  
  
 L'istruzione seguente aggiunge il `samples` **CodeNamespace** alla proprietà di raccolta **Namespaces** dell'oggetto **CodeCompileUnit** radice.  
  
 [!code-cpp[CodeDomExample#15](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source2.cpp#15)]
 [!code-csharp[CodeDomExample#15](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source2.cs#15)]
 [!code-vb[CodeDomExample#15](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source2.vb#15)]  
  
#### <a name="defining-a-type"></a>Definizione di un tipo  
 Per dichiarare una classe, struttura, interfaccia o enumerazione con CodeDOM, creare un nuovo <xref:System.CodeDom.CodeTypeDeclaration> e assegnarvi un nome. Nell'esempio seguente viene illustrata questa operazione tramite l'overload di un costruttore per impostare la proprietà **Name**:  
  
 [!code-cpp[CodeDomExample#16](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source2.cpp#16)]
 [!code-csharp[CodeDomExample#16](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source2.cs#16)]
 [!code-vb[CodeDomExample#16](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source2.vb#16)]  
  
 Per aggiungere un tipo a uno spazio dei nomi, aggiungere una <xref:System.CodeDom.CodeTypeDeclaration> che rappresenta il tipo da aggiungere allo spazio dei nomi per la raccolta **Types** di un **CodeNamespace**.  
  
 Nell'esempio seguente viene illustrato come aggiungere una classe di nome `class1` a un **CodeNamespace** denominato `samples`:  
  
 [!code-cpp[CodeDomExample#17](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source2.cpp#17)]
 [!code-csharp[CodeDomExample#17](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source2.cs#17)]
 [!code-vb[CodeDomExample#17](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source2.vb#17)]  
  
#### <a name="adding-class-members-to-a-class"></a>Aggiunta di membri a una classe  
 Con lo spazio dei nomi <xref:System.CodeDom> vengono offerti diversi elementi che possono essere usati per rappresentare membri di classi. Ogni membro di classe può essere aggiunto alla raccolta **Members** di una <xref:System.CodeDom.CodeTypeDeclaration>.  
  
#### <a name="defining-a-code-entry-point-method-for-an-executable"></a>Definizione di un metodo di punto di ingresso al codice di un file eseguibile  
 Se si sta compilando il codice di un programma eseguibile, è necessario indicarne il punto d'ingresso creando un <xref:System.CodeDom.CodeEntryPointMethod> che rappresenti il metodo da cui si vuole che l'esecuzione del programma abbia inizio.  
  
 Nell'esempio seguente viene illustrato come definire un punto di ingresso che contenga una <xref:System.CodeDom.CodeMethodInvokeExpression> che chiama **System.Console.WriteLine** per scrivere "Hello World!":  
  
 [!code-cpp[CodeDomExample#18](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source2.cpp#18)]
 [!code-csharp[CodeDomExample#18](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source2.cs#18)]
 [!code-vb[CodeDomExample#18](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source2.vb#18)]  
  
 L'istruzione seguente aggiunge il metodo del punto di ingresso denominato `Start` alla raccolta **Members** di `class1`:  
  
 [!code-cpp[CodeDomExample#19](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source2.cpp#19)]
 [!code-csharp[CodeDomExample#19](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source2.cs#19)]
 [!code-vb[CodeDomExample#19](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source2.vb#19)]  
  
 A questo punto l'oggetto <xref:System.CodeDom.CodeCompileUnit> denominato `compileUnit` contiene il grafico CodeDOM di un semplice programma Hello World. Per informazioni sulla generazione e compilazione di codice da un grafico CodeDOM, vedere [Generazione di codice sorgente e compilazione di un programma a partire da un grafico CodeDOM](generating-and-compiling-source-code-from-a-codedom-graph.md).  
  
### <a name="more-information-on-building-a-codedom-graph"></a>Altre informazioni sulla compilazione di un grafico CodeDOM  
 Con CodeDOM viene offerto il supporto dei tipi di elementi di codice più comuni impiegati dai linguaggi di programmazione che supportano Common Language Runtime. CodeDOM non è progettato per fornire elementi in grado di rappresentare tutte le possibili funzionalità dei linguaggi di programmazione. Il codice che non può essere rappresentato facilmente con gli elementi CodeDOM può essere incapsulato in un <xref:System.CodeDom.CodeSnippetExpression>, <xref:System.CodeDom.CodeSnippetStatement>, <xref:System.CodeDom.CodeSnippetTypeMember>, o un <xref:System.CodeDom.CodeSnippetCompileUnit>. Con CodeDOM non è tuttavia possibile tradurre automaticamente frammenti in altri linguaggi.  
  
 Per la documentazione dei diversi tipi CodeDOM, vedere la documentazione di riferimento relativa allo spazio dei nomi <xref:System.CodeDom>.  
  
 Per una tavola di consultazione rapida che consenta di individuare l'elemento CodeDOM che rappresenta uno specifico tipo di elemento di codice, vedere [Riferimento rapido per CodeDOM](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/f1dfsbhc(v=vs.100)).
