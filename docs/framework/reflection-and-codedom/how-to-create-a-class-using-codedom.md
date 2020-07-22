---
title: 'Procedura: creare una classe tramite CodeDOM'
description: Vedere un esempio dettagliato in cui viene illustrato come creare una classe utilizzando il Code Document Object Model (CodeDOM).
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Code Document Object Model, graphs
- Code Document Object Model, creating classes
- graphing with CodeDOM
- CodeDOM, creating classes
- CodeDOM, graphs
ms.assetid: 0ceb70fe-36e1-49bb-922b-e9f615c20a14
ms.openlocfilehash: 3d7151d384402dba6fbb5da8fe54621346251f7b
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/21/2020
ms.locfileid: "86865307"
---
# <a name="how-to-create-a-class-using-codedom"></a><span data-ttu-id="67a88-103">Procedura: creare una classe tramite CodeDOM</span><span class="sxs-lookup"><span data-stu-id="67a88-103">How to: Create a Class Using CodeDOM</span></span>
<span data-ttu-id="67a88-104">Le procedure seguenti illustrano come creare e compilare un grafo CodeDOM che genera una classe contenente due campi, tre proprietà, un metodo, un costruttore e un punto di ingresso.</span><span class="sxs-lookup"><span data-stu-id="67a88-104">The following procedures illustrate how to create and compile a CodeDOM graph that generates a class containing two fields, three properties, a method, a constructor, and an entry point.</span></span>  
  
1. <span data-ttu-id="67a88-105">Creare un'applicazione console che userà codice CodeDOM per generare il codice sorgente per una classe.</span><span class="sxs-lookup"><span data-stu-id="67a88-105">Create a console application that will use CodeDOM code to generate the source code for a class.</span></span>  
  
     <span data-ttu-id="67a88-106">In questo esempio la classe generatrice è denominata `Sample` e il codice generato è una classe denominata `CodeDOMCreatedClass` in un file denominato SampleCode.</span><span class="sxs-lookup"><span data-stu-id="67a88-106">In this example, the generating class is named `Sample`, and the generated code is a class named `CodeDOMCreatedClass` in a file named SampleCode.</span></span>  
  
2. <span data-ttu-id="67a88-107">Nella classe generatrice inizializzare il grafo CodeDOM e usare metodi CodeDOM per definire i membri, il costruttore e il punto di ingresso (metodo `Main`) della classe generata.</span><span class="sxs-lookup"><span data-stu-id="67a88-107">In the generating class, initialize the CodeDOM graph and use CodeDOM methods to define the members, constructor, and entry point (`Main` method) of the generated class.</span></span>  
  
     <span data-ttu-id="67a88-108">In questo esempio la classe generata ha due campi, tre proprietà, un costruttore, un metodo e un metodo `Main`.</span><span class="sxs-lookup"><span data-stu-id="67a88-108">In this example, the generated class has two fields, three properties, a constructor, a method, and a `Main` method.</span></span>  
  
3. <span data-ttu-id="67a88-109">Nella classe generatrice creare un provider di codice specifico del linguaggio e chiamare il relativo metodo <xref:System.CodeDom.Compiler.CodeDomProvider.GenerateCodeFromCompileUnit%2A> per generare il codice dal grafo.</span><span class="sxs-lookup"><span data-stu-id="67a88-109">In the generating class, create a language-specific code provider and call its <xref:System.CodeDom.Compiler.CodeDomProvider.GenerateCodeFromCompileUnit%2A> method to generate the code from the graph.</span></span>  
  
4. <span data-ttu-id="67a88-110">Compilare ed eseguire l'applicazione per generare il codice.</span><span class="sxs-lookup"><span data-stu-id="67a88-110">Compile and execute the application to generate the code.</span></span>  
  
     <span data-ttu-id="67a88-111">In questo esempio il codice generato è contenuto in un file denominato SampleCode.</span><span class="sxs-lookup"><span data-stu-id="67a88-111">In this example, the generated code is in a file named SampleCode.</span></span> <span data-ttu-id="67a88-112">Compilare ed eseguire il codice per visualizzare l'output di esempio.</span><span class="sxs-lookup"><span data-stu-id="67a88-112">Compile and execute that code to see the sample output.</span></span>  
  
### <a name="to-create-the-application-that-will-execute-the-codedom-code"></a><span data-ttu-id="67a88-113">Per creare l'applicazione che eseguirà il codice CodeDOM</span><span class="sxs-lookup"><span data-stu-id="67a88-113">To create the application that will execute the CodeDOM code</span></span>  
  
- <span data-ttu-id="67a88-114">Creare una classe di applicazione console in cui sarà contenuto il codice CodeDOM.</span><span class="sxs-lookup"><span data-stu-id="67a88-114">Create a console application class to contain the CodeDOM code.</span></span> <span data-ttu-id="67a88-115">Definire i campi globali da usare nella classe per fare riferimento all'assembly (<xref:System.CodeDom.CodeCompileUnit>) e alla classe (<xref:System.CodeDom.CodeTypeDeclaration>), specificare il nome del file di origine generato e dichiarare il metodo `Main`.</span><span class="sxs-lookup"><span data-stu-id="67a88-115">Define the global fields that are to be used in the class to reference the assembly (<xref:System.CodeDom.CodeCompileUnit>) and class (<xref:System.CodeDom.CodeTypeDeclaration>), specify the name of the generated source file, and declare the `Main` method.</span></span>  
  
     [!code-csharp[CodeDOM Class Sample Main#1](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample Main/CS/program.cs#1)]
     [!code-vb[CodeDOM Class Sample Main#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample Main/VB/program.vb#1)]  
  
### <a name="to-initialize-the-codedom-graph"></a><span data-ttu-id="67a88-116">Per inizializzare il grafo CodeDOM</span><span class="sxs-lookup"><span data-stu-id="67a88-116">To initialize the CodeDOM graph</span></span>  
  
- <span data-ttu-id="67a88-117">Nel costruttore della classe di applicazione console inizializzare l'assembly e la classe, quindi aggiungere le dichiarazioni appropriate al grafo CodeDOM.</span><span class="sxs-lookup"><span data-stu-id="67a88-117">In the constructor for the console application class, initialize the assembly and class, and add the appropriate declarations to the CodeDOM graph.</span></span>  
  
     [!code-csharp[CodeDOM Class Sample#2](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#2)]
     [!code-vb[CodeDOM Class Sample#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#2)]  
  
### <a name="to-add-members-to-the-codedom-graph"></a><span data-ttu-id="67a88-118">Per aggiungere membri al grafo CodeDOM</span><span class="sxs-lookup"><span data-stu-id="67a88-118">To add members to the CodeDOM graph</span></span>  
  
- <span data-ttu-id="67a88-119">Aggiungere campi al grafo CodeDOM aggiungendo oggetti <xref:System.CodeDom.CodeMemberField> alla proprietà <xref:System.CodeDom.CodeTypeDeclaration.Members%2A> della classe.</span><span class="sxs-lookup"><span data-stu-id="67a88-119">Add fields to the CodeDOM graph by adding <xref:System.CodeDom.CodeMemberField> objects to the <xref:System.CodeDom.CodeTypeDeclaration.Members%2A> property of the class.</span></span>  
  
     [!code-csharp[CodeDOM Class Sample#3](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#3)]
     [!code-vb[CodeDOM Class Sample#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#3)]  
  
- <span data-ttu-id="67a88-120">Aggiungere proprietà al grafo CodeDOM aggiungendo oggetti <xref:System.CodeDom.CodeMemberProperty> alla proprietà <xref:System.CodeDom.CodeTypeDeclaration.Members%2A> della classe.</span><span class="sxs-lookup"><span data-stu-id="67a88-120">Add properties to the CodeDOM graph by adding <xref:System.CodeDom.CodeMemberProperty> objects to the <xref:System.CodeDom.CodeTypeDeclaration.Members%2A> property of the class.</span></span>  
  
     [!code-csharp[CodeDOM Class Sample#4](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#4)]
     [!code-vb[CodeDOM Class Sample#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#4)]  
  
- <span data-ttu-id="67a88-121">Aggiungere un metodo al grafo CodeDOM aggiungendo un oggetto <xref:System.CodeDom.CodeMemberMethod> alla proprietà <xref:System.CodeDom.CodeTypeDeclaration.Members%2A> della classe.</span><span class="sxs-lookup"><span data-stu-id="67a88-121">Add a method to the CodeDOM graph by adding a <xref:System.CodeDom.CodeMemberMethod> object to the <xref:System.CodeDom.CodeTypeDeclaration.Members%2A> property of the class.</span></span>  
  
     [!code-csharp[CodeDOM Class Sample#5](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#5)]
     [!code-vb[CodeDOM Class Sample#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#5)]  
  
- <span data-ttu-id="67a88-122">Aggiungere un costruttore al grafo CodeDOM aggiungendo un oggetto <xref:System.CodeDom.CodeConstructor> alla proprietà <xref:System.CodeDom.CodeTypeDeclaration.Members%2A> della classe.</span><span class="sxs-lookup"><span data-stu-id="67a88-122">Add a constructor to the CodeDOM graph by adding a <xref:System.CodeDom.CodeConstructor> object to the <xref:System.CodeDom.CodeTypeDeclaration.Members%2A> property of the class.</span></span>  
  
     [!code-csharp[CodeDOM Class Sample#6](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#6)]
     [!code-vb[CodeDOM Class Sample#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#6)]  
  
- <span data-ttu-id="67a88-123">Aggiungere un punto di ingresso al grafo CodeDOM aggiungendo un oggetto <xref:System.CodeDom.CodeEntryPointMethod> alla proprietà <xref:System.CodeDom.CodeTypeDeclaration.Members%2A> della classe.</span><span class="sxs-lookup"><span data-stu-id="67a88-123">Add an entry point to the CodeDOM graph by adding a <xref:System.CodeDom.CodeEntryPointMethod> object to the <xref:System.CodeDom.CodeTypeDeclaration.Members%2A> property of the class.</span></span>  
  
     [!code-csharp[CodeDOM Class Sample#7](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#7)]
     [!code-vb[CodeDOM Class Sample#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#7)]  
  
### <a name="to-generate-the-code-from-the-codedom-graph"></a><span data-ttu-id="67a88-124">Per generare il codice dal grafo CodeDOM</span><span class="sxs-lookup"><span data-stu-id="67a88-124">To generate the code from the CodeDOM graph</span></span>  
  
- <span data-ttu-id="67a88-125">Generare codice sorgente dal grafo CodeDOM chiamando il metodo <xref:System.CodeDom.Compiler.CodeDomProvider.GenerateCodeFromCompileUnit%2A>.</span><span class="sxs-lookup"><span data-stu-id="67a88-125">Generate source code from the CodeDOM graph by calling the <xref:System.CodeDom.Compiler.CodeDomProvider.GenerateCodeFromCompileUnit%2A> method.</span></span>  
  
     [!code-csharp[CodeDOM Class Sample#8](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#8)]
     [!code-vb[CodeDOM Class Sample#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#8)]  
  
### <a name="to-create-the-graph-and-generate-the-code"></a><span data-ttu-id="67a88-126">Per creare il grafo e generare il codice</span><span class="sxs-lookup"><span data-stu-id="67a88-126">To create the graph and generate the code</span></span>  
  
1. <span data-ttu-id="67a88-127">Aggiungere i metodi creati nei passaggi precedenti al metodo `Main` definito nel primo passaggio.</span><span class="sxs-lookup"><span data-stu-id="67a88-127">Add the methods created in the preceding steps to the `Main` method defined in the first step.</span></span>  
  
     [!code-csharp[CodeDOM Class Sample#9](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#9)]
     [!code-vb[CodeDOM Class Sample#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#9)]  
  
2. <span data-ttu-id="67a88-128">Compilare ed eseguire la classe generatrice.</span><span class="sxs-lookup"><span data-stu-id="67a88-128">Compile and execute the generating class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="67a88-129">Esempio</span><span class="sxs-lookup"><span data-stu-id="67a88-129">Example</span></span>  
 <span data-ttu-id="67a88-130">L'esempio di codice seguente illustra il codice dei passaggi precedenti.</span><span class="sxs-lookup"><span data-stu-id="67a88-130">The following code example shows the code from the preceding steps.</span></span>  
  
 [!code-csharp[CodeDOM Class Sample#1](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#1)]
 [!code-vb[CodeDOM Class Sample#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#1)]  
  
 <span data-ttu-id="67a88-131">Quando l'esempio precedente viene compilato ed eseguito, produce il codice sorgente seguente.</span><span class="sxs-lookup"><span data-stu-id="67a88-131">When the preceding example is compiled and executed, it produces the following source code.</span></span>  
  
 [!code-csharp[CodeDOM Class Sample#99](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/SampleCode.cs#99)]
 [!code-vb[CodeDOM Class Sample#99](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/SampleCode.vb#99)]  
  
 <span data-ttu-id="67a88-132">Il codice sorgente generato produce l'output seguente quando viene compilato ed eseguito.</span><span class="sxs-lookup"><span data-stu-id="67a88-132">The generated source code produces the following output when compiled and executed.</span></span>  
  
```output
The object:  
 width = 5.3,  
 height = 6.9,  
 area = 36.57  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="67a88-133">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="67a88-133">Compiling the Code</span></span>  
  
- <span data-ttu-id="67a88-134">Per essere eseguito correttamente, questo esempio di codice richiede il set di autorizzazioni `FullTrust`.</span><span class="sxs-lookup"><span data-stu-id="67a88-134">This code example requires the `FullTrust` permission set to execute successfully.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67a88-135">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="67a88-135">See also</span></span>

- [<span data-ttu-id="67a88-136">Uso di CodeDOM</span><span class="sxs-lookup"><span data-stu-id="67a88-136">Using the CodeDOM</span></span>](using-the-codedom.md)
- [<span data-ttu-id="67a88-137">Generazione e compilazione di codice sorgente a partire da un grafo CodeDOM</span><span class="sxs-lookup"><span data-stu-id="67a88-137">Generating and Compiling Source Code from a CodeDOM Graph</span></span>](generating-and-compiling-source-code-from-a-codedom-graph.md)
