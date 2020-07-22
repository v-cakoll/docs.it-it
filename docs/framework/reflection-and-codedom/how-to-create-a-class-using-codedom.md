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
# <a name="how-to-create-a-class-using-codedom"></a>Procedura: creare una classe tramite CodeDOM
Le procedure seguenti illustrano come creare e compilare un grafo CodeDOM che genera una classe contenente due campi, tre proprietà, un metodo, un costruttore e un punto di ingresso.  
  
1. Creare un'applicazione console che userà codice CodeDOM per generare il codice sorgente per una classe.  
  
     In questo esempio la classe generatrice è denominata `Sample` e il codice generato è una classe denominata `CodeDOMCreatedClass` in un file denominato SampleCode.  
  
2. Nella classe generatrice inizializzare il grafo CodeDOM e usare metodi CodeDOM per definire i membri, il costruttore e il punto di ingresso (metodo `Main`) della classe generata.  
  
     In questo esempio la classe generata ha due campi, tre proprietà, un costruttore, un metodo e un metodo `Main`.  
  
3. Nella classe generatrice creare un provider di codice specifico del linguaggio e chiamare il relativo metodo <xref:System.CodeDom.Compiler.CodeDomProvider.GenerateCodeFromCompileUnit%2A> per generare il codice dal grafo.  
  
4. Compilare ed eseguire l'applicazione per generare il codice.  
  
     In questo esempio il codice generato è contenuto in un file denominato SampleCode. Compilare ed eseguire il codice per visualizzare l'output di esempio.  
  
### <a name="to-create-the-application-that-will-execute-the-codedom-code"></a>Per creare l'applicazione che eseguirà il codice CodeDOM  
  
- Creare una classe di applicazione console in cui sarà contenuto il codice CodeDOM. Definire i campi globali da usare nella classe per fare riferimento all'assembly (<xref:System.CodeDom.CodeCompileUnit>) e alla classe (<xref:System.CodeDom.CodeTypeDeclaration>), specificare il nome del file di origine generato e dichiarare il metodo `Main`.  
  
     [!code-csharp[CodeDOM Class Sample Main#1](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample Main/CS/program.cs#1)]
     [!code-vb[CodeDOM Class Sample Main#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample Main/VB/program.vb#1)]  
  
### <a name="to-initialize-the-codedom-graph"></a>Per inizializzare il grafo CodeDOM  
  
- Nel costruttore della classe di applicazione console inizializzare l'assembly e la classe, quindi aggiungere le dichiarazioni appropriate al grafo CodeDOM.  
  
     [!code-csharp[CodeDOM Class Sample#2](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#2)]
     [!code-vb[CodeDOM Class Sample#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#2)]  
  
### <a name="to-add-members-to-the-codedom-graph"></a>Per aggiungere membri al grafo CodeDOM  
  
- Aggiungere campi al grafo CodeDOM aggiungendo oggetti <xref:System.CodeDom.CodeMemberField> alla proprietà <xref:System.CodeDom.CodeTypeDeclaration.Members%2A> della classe.  
  
     [!code-csharp[CodeDOM Class Sample#3](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#3)]
     [!code-vb[CodeDOM Class Sample#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#3)]  
  
- Aggiungere proprietà al grafo CodeDOM aggiungendo oggetti <xref:System.CodeDom.CodeMemberProperty> alla proprietà <xref:System.CodeDom.CodeTypeDeclaration.Members%2A> della classe.  
  
     [!code-csharp[CodeDOM Class Sample#4](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#4)]
     [!code-vb[CodeDOM Class Sample#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#4)]  
  
- Aggiungere un metodo al grafo CodeDOM aggiungendo un oggetto <xref:System.CodeDom.CodeMemberMethod> alla proprietà <xref:System.CodeDom.CodeTypeDeclaration.Members%2A> della classe.  
  
     [!code-csharp[CodeDOM Class Sample#5](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#5)]
     [!code-vb[CodeDOM Class Sample#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#5)]  
  
- Aggiungere un costruttore al grafo CodeDOM aggiungendo un oggetto <xref:System.CodeDom.CodeConstructor> alla proprietà <xref:System.CodeDom.CodeTypeDeclaration.Members%2A> della classe.  
  
     [!code-csharp[CodeDOM Class Sample#6](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#6)]
     [!code-vb[CodeDOM Class Sample#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#6)]  
  
- Aggiungere un punto di ingresso al grafo CodeDOM aggiungendo un oggetto <xref:System.CodeDom.CodeEntryPointMethod> alla proprietà <xref:System.CodeDom.CodeTypeDeclaration.Members%2A> della classe.  
  
     [!code-csharp[CodeDOM Class Sample#7](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#7)]
     [!code-vb[CodeDOM Class Sample#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#7)]  
  
### <a name="to-generate-the-code-from-the-codedom-graph"></a>Per generare il codice dal grafo CodeDOM  
  
- Generare codice sorgente dal grafo CodeDOM chiamando il metodo <xref:System.CodeDom.Compiler.CodeDomProvider.GenerateCodeFromCompileUnit%2A>.  
  
     [!code-csharp[CodeDOM Class Sample#8](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#8)]
     [!code-vb[CodeDOM Class Sample#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#8)]  
  
### <a name="to-create-the-graph-and-generate-the-code"></a>Per creare il grafo e generare il codice  
  
1. Aggiungere i metodi creati nei passaggi precedenti al metodo `Main` definito nel primo passaggio.  
  
     [!code-csharp[CodeDOM Class Sample#9](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#9)]
     [!code-vb[CodeDOM Class Sample#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#9)]  
  
2. Compilare ed eseguire la classe generatrice.  
  
## <a name="example"></a>Esempio  
 L'esempio di codice seguente illustra il codice dei passaggi precedenti.  
  
 [!code-csharp[CodeDOM Class Sample#1](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#1)]
 [!code-vb[CodeDOM Class Sample#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#1)]  
  
 Quando l'esempio precedente viene compilato ed eseguito, produce il codice sorgente seguente.  
  
 [!code-csharp[CodeDOM Class Sample#99](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/SampleCode.cs#99)]
 [!code-vb[CodeDOM Class Sample#99](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/SampleCode.vb#99)]  
  
 Il codice sorgente generato produce l'output seguente quando viene compilato ed eseguito.  
  
```output
The object:  
 width = 5.3,  
 height = 6.9,  
 area = 36.57  
```  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
  
- Per essere eseguito correttamente, questo esempio di codice richiede il set di autorizzazioni `FullTrust`.  
  
## <a name="see-also"></a>Vedi anche

- [Uso di CodeDOM](using-the-codedom.md)
- [Generazione e compilazione di codice sorgente a partire da un grafo CodeDOM](generating-and-compiling-source-code-from-a-codedom-graph.md)
