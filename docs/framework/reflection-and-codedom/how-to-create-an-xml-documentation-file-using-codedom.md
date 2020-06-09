---
title: 'Procedura: creare un file di documentazione XML tramite CodeDOM'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- CodeDOM, generating XML documentation
- XML documentation, creating using CodeDOM
- Code Document Object Model, generating XML documentation
ms.assetid: e3b80484-36b9-41dd-9d21-a2f9a36381dc
ms.openlocfilehash: b9e11a51048733dbfc42ff9f575e18effc80db07
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84596246"
---
# <a name="how-to-create-an-xml-documentation-file-using-codedom"></a><span data-ttu-id="34cc6-102">Procedura: creare un file di documentazione XML tramite CodeDOM</span><span class="sxs-lookup"><span data-stu-id="34cc6-102">How to: Create an XML documentation file using CodeDOM</span></span>

<span data-ttu-id="34cc6-103">CodeDOM consente di creare codice che genera documentazione XML.</span><span class="sxs-lookup"><span data-stu-id="34cc6-103">CodeDOM can be used to create code that generates XML documentation.</span></span> <span data-ttu-id="34cc6-104">Il processo comporta la creazione del grafo CodeDOM contenente i commenti per la documentazione XML, la generazione del codice e la compilazione del codice generato con l'opzione del compilatore che crea l'output della documentazione XML.</span><span class="sxs-lookup"><span data-stu-id="34cc6-104">The process involves creating the CodeDOM graph that contains the XML documentation comments, generating the code, and compiling the generated code with the compiler option that creates the XML documentation output.</span></span>  
  
## <a name="create-a-codedom-graph"></a><span data-ttu-id="34cc6-105">Creare un grafo CodeDOM</span><span class="sxs-lookup"><span data-stu-id="34cc6-105">Create a CodeDOM graph</span></span>
  
1. <span data-ttu-id="34cc6-106">Creare un oggetto <xref:System.CodeDom.CodeCompileUnit> contenente il grafo CodeDOM per l'applicazione di esempio.</span><span class="sxs-lookup"><span data-stu-id="34cc6-106">Create a <xref:System.CodeDom.CodeCompileUnit> containing the CodeDOM graph for the sample application.</span></span>  
  
2. <span data-ttu-id="34cc6-107">Usare il costruttore <xref:System.CodeDom.CodeCommentStatement.%23ctor%2A> con il parametro `docComment` impostato su `true` per creare il testo e gli elementi di commento della documentazione XML.</span><span class="sxs-lookup"><span data-stu-id="34cc6-107">Use the <xref:System.CodeDom.CodeCommentStatement.%23ctor%2A> constructor with the `docComment` parameter set to `true` to create the XML documentation comment elements and text.</span></span>  
  
     [!code-csharp[CodeDomHelloWorldSample#4](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomHelloWorldSample/cs/program.cs#4)]
     [!code-vb[CodeDomHelloWorldSample#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomHelloWorldSample/vb/program.vb#4)]  
  
### <a name="generate-the-code-from-the-codecompileunit"></a><span data-ttu-id="34cc6-108">Generare il codice da CodeCompileUnit</span><span class="sxs-lookup"><span data-stu-id="34cc6-108">Generate the code from the CodeCompileUnit</span></span>
  
1. <span data-ttu-id="34cc6-109">Usare il metodo <xref:System.CodeDom.Compiler.CodeDomProvider.GenerateCodeFromCompileUnit%2A> per generare il codice e creare un file di origine da compilare.</span><span class="sxs-lookup"><span data-stu-id="34cc6-109">Use the <xref:System.CodeDom.Compiler.CodeDomProvider.GenerateCodeFromCompileUnit%2A> method to generate the code and create a source file to be compiled.</span></span>  
  
     [!code-csharp[CodeDomHelloWorldSample#5](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomHelloWorldSample/cs/program.cs#5)]
     [!code-vb[CodeDomHelloWorldSample#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomHelloWorldSample/vb/program.vb#5)]  
  
### <a name="compile-the-code-and-generate-the-documentation-file"></a><span data-ttu-id="34cc6-110">Compilare il codice e generare il file di documentazione</span><span class="sxs-lookup"><span data-stu-id="34cc6-110">Compile the code and generate the documentation file</span></span>
  
1. <span data-ttu-id="34cc6-111">Aggiungere l'opzione del compilatore **/doc** alla proprietà <xref:System.CodeDom.Compiler.CompilerParameters.CompilerOptions%2A> di un oggetto <xref:System.CodeDom.Compiler.CompilerParameters> e passare l'oggetto al metodo <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromFile%2A> per creare il file di documentazione XML quando il codice viene compilato.</span><span class="sxs-lookup"><span data-stu-id="34cc6-111">Add the **/doc** compiler option to the <xref:System.CodeDom.Compiler.CompilerParameters.CompilerOptions%2A> property of a <xref:System.CodeDom.Compiler.CompilerParameters> object and pass the object to the <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromFile%2A> method to create the XML documentation file when the code is compiled.</span></span>  
  
     [!code-csharp[CodeDomHelloWorldSample#6](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomHelloWorldSample/cs/program.cs#6)]
     [!code-vb[CodeDomHelloWorldSample#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomHelloWorldSample/vb/program.vb#6)]  
  
## <a name="example"></a><span data-ttu-id="34cc6-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="34cc6-112">Example</span></span>

<span data-ttu-id="34cc6-113">L'esempio di codice seguente crea un grafo CodeDOM con i commenti della documentazione, genera un file di codice dal grafo e compila il file e crea un file di documentazione XML associato.</span><span class="sxs-lookup"><span data-stu-id="34cc6-113">The following code example creates a CodeDOM graph with documentation comments, generates a code file from the graph, and compiles the file and creates an associated XML documentation file.</span></span>  
  
 [!code-csharp[CodeDomHelloWorldSample#1](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomHelloWorldSample/cs/program.cs#1)]
 [!code-vb[CodeDomHelloWorldSample#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomHelloWorldSample/vb/program.vb#1)]  
  
 <span data-ttu-id="34cc6-114">Nell'esempio di codice viene creata la seguente documentazione XML nel file *HelloWorldDoc. XML* .</span><span class="sxs-lookup"><span data-stu-id="34cc6-114">The code example creates the following XML documentation in the *HelloWorldDoc.xml* file.</span></span>  
  
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
      </summary>
      <seealso cref="M:Samples.Class1.Main" />
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
  
## <a name="compile-permissions"></a><span data-ttu-id="34cc6-115">Autorizzazioni di compilazione</span><span class="sxs-lookup"><span data-stu-id="34cc6-115">Compile permissions</span></span>
  
<span data-ttu-id="34cc6-116">Per essere eseguito correttamente, questo esempio di codice richiede il set di autorizzazioni `FullTrust`.</span><span class="sxs-lookup"><span data-stu-id="34cc6-116">This code example requires the `FullTrust` permission set to execute successfully.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="34cc6-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="34cc6-117">See also</span></span>

- [<span data-ttu-id="34cc6-118">Documentare il codice con XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="34cc6-118">Document your code with XML (Visual Basic)</span></span>](../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)
- [<span data-ttu-id="34cc6-119">Commenti relativi alla documentazione XML</span><span class="sxs-lookup"><span data-stu-id="34cc6-119">XML documentation comments</span></span>](../../csharp/programming-guide/xmldoc/index.md)
- [<span data-ttu-id="34cc6-120">Documentazione XML (C++)</span><span class="sxs-lookup"><span data-stu-id="34cc6-120">XML documentation (C++)</span></span>](/cpp/ide/xml-documentation-visual-cpp)
