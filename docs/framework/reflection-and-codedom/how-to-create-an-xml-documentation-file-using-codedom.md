---
title: 'Procedura: creare un file di documentazione XML tramite CodeDOM'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- CodeDOM, generating XML documentation
- XML documentation, creating using CodeDOM
- Code Document Object Model, generating XML documentation
ms.assetid: e3b80484-36b9-41dd-9d21-a2f9a36381dc
caps.latest.revision: 8
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 7d5569fd22cc8469052cc318fd50a5f8ef94c1a9
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-create-an-xml-documentation-file-using-codedom"></a><span data-ttu-id="99d28-102">Procedura: creare un file di documentazione XML tramite CodeDOM</span><span class="sxs-lookup"><span data-stu-id="99d28-102">How to: Create an XML Documentation File Using CodeDOM</span></span>
<span data-ttu-id="99d28-103">CodeDOM consente di creare codice che genera documentazione XML.</span><span class="sxs-lookup"><span data-stu-id="99d28-103">CodeDOM can be used to create code that generates XML documentation.</span></span> <span data-ttu-id="99d28-104">Il processo comporta la creazione del grafo CodeDOM contenente i commenti per la documentazione XML, la generazione del codice e la compilazione del codice generato con l'opzione del compilatore che crea l'output della documentazione XML.</span><span class="sxs-lookup"><span data-stu-id="99d28-104">The process involves creating the CodeDOM graph that contains the XML documentation comments, generating the code, and compiling the generated code with the compiler option that creates the XML documentation output.</span></span>  
  
### <a name="to-create-a-codedom-graph-that-contains-xml-documentation-comments"></a><span data-ttu-id="99d28-105">Per creare un grafo CodeDOM contenente i commenti per la documentazione XML</span><span class="sxs-lookup"><span data-stu-id="99d28-105">To create a CodeDOM graph that contains XML documentation comments</span></span>  
  
1.  <span data-ttu-id="99d28-106">Creare un oggetto <xref:System.CodeDom.CodeCompileUnit> contenente il grafo CodeDOM per l'applicazione di esempio.</span><span class="sxs-lookup"><span data-stu-id="99d28-106">Create a <xref:System.CodeDom.CodeCompileUnit> containing the CodeDOM graph for the sample application.</span></span>  
  
2.  <span data-ttu-id="99d28-107">Usare il costruttore <xref:System.CodeDom.CodeCommentStatement.%23ctor%2A> con il parametro `docComment` impostato su `true` per creare il testo e gli elementi di commento della documentazione XML.</span><span class="sxs-lookup"><span data-stu-id="99d28-107">Use the <xref:System.CodeDom.CodeCommentStatement.%23ctor%2A> constructor with the `docComment` parameter set to `true` to create the XML documentation comment elements and text.</span></span>  
  
     <span data-ttu-id="99d28-108">[!code-csharp[CodeDomHelloWorldSample#4](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomHelloWorldSample/cs/program.cs#4)]  [!code-vb[CodeDomHelloWorldSample#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomHelloWorldSample/vb/program.vb#4)]</span><span class="sxs-lookup"><span data-stu-id="99d28-108">[!code-csharp[CodeDomHelloWorldSample#4](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomHelloWorldSample/cs/program.cs#4)]  [!code-vb[CodeDomHelloWorldSample#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomHelloWorldSample/vb/program.vb#4)]</span></span>  
  
### <a name="to-generate-the-code-from-the-codecompileunit"></a><span data-ttu-id="99d28-109">Per generare il codice da CodeCompileUnit</span><span class="sxs-lookup"><span data-stu-id="99d28-109">To generate the code from the CodeCompileUnit</span></span>  
  
1.  <span data-ttu-id="99d28-110">Usare il metodo <xref:System.CodeDom.Compiler.CodeDomProvider.GenerateCodeFromCompileUnit%2A> per generare il codice e creare un file di origine da compilare.</span><span class="sxs-lookup"><span data-stu-id="99d28-110">Use the <xref:System.CodeDom.Compiler.CodeDomProvider.GenerateCodeFromCompileUnit%2A> method to generate the code and create a source file to be compiled.</span></span>  
  
     <span data-ttu-id="99d28-111">[!code-csharp[CodeDomHelloWorldSample#5](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomHelloWorldSample/cs/program.cs#5)]  [!code-vb[CodeDomHelloWorldSample#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomHelloWorldSample/vb/program.vb#5)]</span><span class="sxs-lookup"><span data-stu-id="99d28-111">[!code-csharp[CodeDomHelloWorldSample#5](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomHelloWorldSample/cs/program.cs#5)]  [!code-vb[CodeDomHelloWorldSample#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomHelloWorldSample/vb/program.vb#5)]</span></span>  
  
### <a name="to-compile-the-code-and-generate-the-documentation-file"></a><span data-ttu-id="99d28-112">Per compilare il codice e generare il file di documentazione</span><span class="sxs-lookup"><span data-stu-id="99d28-112">To compile the code and generate the documentation file</span></span>  
  
1.  <span data-ttu-id="99d28-113">Aggiungere l'opzione del compilatore **/doc** alla proprietà <xref:System.CodeDom.Compiler.CompilerParameters.CompilerOptions%2A> di un oggetto <xref:System.CodeDom.Compiler.CompilerParameters> e passare l'oggetto al metodo <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromFile%2A> per creare il file di documentazione XML quando il codice viene compilato.</span><span class="sxs-lookup"><span data-stu-id="99d28-113">Add the **/doc** compiler option to the <xref:System.CodeDom.Compiler.CompilerParameters.CompilerOptions%2A> property of a <xref:System.CodeDom.Compiler.CompilerParameters> object and pass the object to the <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromFile%2A> method to create the XML documentation file when the code is compiled.</span></span>  
  
     <span data-ttu-id="99d28-114">[!code-csharp[CodeDomHelloWorldSample#6](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomHelloWorldSample/cs/program.cs#6)]  [!code-vb[CodeDomHelloWorldSample#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomHelloWorldSample/vb/program.vb#6)]</span><span class="sxs-lookup"><span data-stu-id="99d28-114">[!code-csharp[CodeDomHelloWorldSample#6](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomHelloWorldSample/cs/program.cs#6)]  [!code-vb[CodeDomHelloWorldSample#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomHelloWorldSample/vb/program.vb#6)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="99d28-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="99d28-115">Example</span></span>  
 <span data-ttu-id="99d28-116">L'esempio di codice seguente crea un grafo CodeDOM con i commenti della documentazione, genera un file di codice dal grafo e compila il file e crea un file di documentazione XML associato.</span><span class="sxs-lookup"><span data-stu-id="99d28-116">The following code example creates a CodeDOM graph with documentation comments, generates a code file from the graph, and compiles the file and creates an associated XML documentation file.</span></span>  
  
 <span data-ttu-id="99d28-117">[!code-csharp[CodeDomHelloWorldSample#1](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomHelloWorldSample/cs/program.cs#1)] [!code-vb[CodeDomHelloWorldSample#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomHelloWorldSample/vb/program.vb#1)]</span><span class="sxs-lookup"><span data-stu-id="99d28-117">[!code-csharp[CodeDomHelloWorldSample#1](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomHelloWorldSample/cs/program.cs#1)] [!code-vb[CodeDomHelloWorldSample#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomHelloWorldSample/vb/program.vb#1)]</span></span>  
  
 <span data-ttu-id="99d28-118">L'esempio di codice crea la documentazione XML seguente nel file HelloWorldDoc.xml.</span><span class="sxs-lookup"><span data-stu-id="99d28-118">The code example creates the following XML documentation in the HelloWorldDoc.xml file.</span></span>  
  
```xml  
<?xml version="1.0" ?>   
<doc>  
  <assembly>  
    <name>HelloWorld</name>   
  </assembly>  
  <members>  
    <member name="T:Samples.Class1">  
      <summary>  
        Create a Hello World application.   
        <seealso cref="M:Samples.Class1.Main" />   
      </summary>  
    </member>  
    <member name="M:Samples.Class1.Main">  
      <summary>  
        Main method for HelloWorld application.   
        <para>Add a new paragraph to the description.</para>   
      </summary>  
    </member>  
  </members>  
</doc>  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="99d28-119">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="99d28-119">Compiling the Code</span></span>  
  
-   <span data-ttu-id="99d28-120">Per essere eseguito correttamente, questo esempio di codice richiede il set di autorizzazioni `FullTrust`.</span><span class="sxs-lookup"><span data-stu-id="99d28-120">This code example requires the `FullTrust` permission set to execute successfully.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99d28-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="99d28-121">See Also</span></span>  
 <span data-ttu-id="99d28-122">[Documentazione del codice tramite XML](~/docs/visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md) </span><span class="sxs-lookup"><span data-stu-id="99d28-122">[Documenting Your Code with XML](~/docs/visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md) </span></span>  
 <span data-ttu-id="99d28-123">[Commenti relativi alla documentazione XML](~/docs/csharp/programming-guide/xmldoc/xml-documentation-comments.md) </span><span class="sxs-lookup"><span data-stu-id="99d28-123">[XML Documentation Comments](~/docs/csharp/programming-guide/xmldoc/xml-documentation-comments.md) </span></span>  
 [<span data-ttu-id="99d28-124">Documentazione di XML</span><span class="sxs-lookup"><span data-stu-id="99d28-124">XML Documentation</span></span>](/cpp/ide/xml-documentation-visual-cpp)

