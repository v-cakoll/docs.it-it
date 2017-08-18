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
# <a name="how-to-create-an-xml-documentation-file-using-codedom"></a>Procedura: creare un file di documentazione XML tramite CodeDOM
CodeDOM consente di creare codice che genera documentazione XML. Il processo comporta la creazione del grafo CodeDOM contenente i commenti per la documentazione XML, la generazione del codice e la compilazione del codice generato con l'opzione del compilatore che crea l'output della documentazione XML.  
  
### <a name="to-create-a-codedom-graph-that-contains-xml-documentation-comments"></a>Per creare un grafo CodeDOM contenente i commenti per la documentazione XML  
  
1.  Creare un oggetto <xref:System.CodeDom.CodeCompileUnit> contenente il grafo CodeDOM per l'applicazione di esempio.  
  
2.  Usare il costruttore <xref:System.CodeDom.CodeCommentStatement.%23ctor%2A> con il parametro `docComment` impostato su `true` per creare il testo e gli elementi di commento della documentazione XML.  
  
     [!code-csharp[CodeDomHelloWorldSample#4](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomHelloWorldSample/cs/program.cs#4)]  [!code-vb[CodeDomHelloWorldSample#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomHelloWorldSample/vb/program.vb#4)]  
  
### <a name="to-generate-the-code-from-the-codecompileunit"></a>Per generare il codice da CodeCompileUnit  
  
1.  Usare il metodo <xref:System.CodeDom.Compiler.CodeDomProvider.GenerateCodeFromCompileUnit%2A> per generare il codice e creare un file di origine da compilare.  
  
     [!code-csharp[CodeDomHelloWorldSample#5](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomHelloWorldSample/cs/program.cs#5)]  [!code-vb[CodeDomHelloWorldSample#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomHelloWorldSample/vb/program.vb#5)]  
  
### <a name="to-compile-the-code-and-generate-the-documentation-file"></a>Per compilare il codice e generare il file di documentazione  
  
1.  Aggiungere l'opzione del compilatore **/doc** alla proprietà <xref:System.CodeDom.Compiler.CompilerParameters.CompilerOptions%2A> di un oggetto <xref:System.CodeDom.Compiler.CompilerParameters> e passare l'oggetto al metodo <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromFile%2A> per creare il file di documentazione XML quando il codice viene compilato.  
  
     [!code-csharp[CodeDomHelloWorldSample#6](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomHelloWorldSample/cs/program.cs#6)]  [!code-vb[CodeDomHelloWorldSample#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomHelloWorldSample/vb/program.vb#6)]  
  
## <a name="example"></a>Esempio  
 L'esempio di codice seguente crea un grafo CodeDOM con i commenti della documentazione, genera un file di codice dal grafo e compila il file e crea un file di documentazione XML associato.  
  
 [!code-csharp[CodeDomHelloWorldSample#1](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomHelloWorldSample/cs/program.cs#1)] [!code-vb[CodeDomHelloWorldSample#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomHelloWorldSample/vb/program.vb#1)]  
  
 L'esempio di codice crea la documentazione XML seguente nel file HelloWorldDoc.xml.  
  
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
  
## <a name="compiling-the-code"></a>Compilazione del codice  
  
-   Per essere eseguito correttamente, questo esempio di codice richiede il set di autorizzazioni `FullTrust`.  
  
## <a name="see-also"></a>Vedere anche  
 [Documentazione del codice tramite XML](~/docs/visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)   
 [Commenti relativi alla documentazione XML](~/docs/csharp/programming-guide/xmldoc/xml-documentation-comments.md)   
 [Documentazione di XML](/cpp/ide/xml-documentation-visual-cpp)

