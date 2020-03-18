---
title: Metodi generici - Guida per programmatori C#
ms.date: 07/20/2015
helpviewer_keywords:
- generics [C#], methods
ms.assetid: 673eeea2-4b48-4faa-9c4e-2e89449221b9
ms.openlocfilehash: 5f066ca39c97b70554886e423c37c4ee47d49158
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75712195"
---
# <a name="generic-methods-c-programming-guide"></a>Metodi generici (Guida per programmatori C#)
Un metodo generico è un metodo che viene dichiarato con parametri di tipo, in questo modo:  
  
 [!code-csharp[csProgGuideGenerics#22](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#22)]  
  
 L'esempio di codice seguente mostra un modo per chiamare il metodo usando `int` per l'argomento tipo:  
  
 [!code-csharp[csProgGuideGenerics#23](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#23)]  
  
 È anche possibile omettere l'argomento tipo perché venga dedotto dal compilatore. La chiamata seguente a `Swap` equivale alla chiamata precedente:  
  
 [!code-csharp[csProgGuideGenerics#24](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#24)]  
  
 Ai metodi statici e ai metodi di istanza si applicano le stesse regole relative all'inferenza del tipo. Il compilatore può dedurre i parametri di tipo in base agli argomenti metodo passati, ma non può dedurli solo da un vincolo o da un valore restituito. Di conseguenza, l'inferenza del tipo non funziona con metodi che non includono parametri. L'inferenza del tipo avviene in fase di compilazione prima che il compilatore provi a risolvere le firme dei metodi di overload. Il compilatore applica la logica di inferenza del tipo a tutti i metodi generici che condividono lo stesso nome. Nel passaggio di risoluzione dell'overload, il compilatore include solo i metodi generici per cui l'inferenza del tipo è riuscita.  
  
 All'interno di una classe generica metodi non generici possono accedere ai parametri di tipo a livello di classe, in questo modo:  
  
 [!code-csharp[csProgGuideGenerics#25](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#25)]  
  
 Se si definisce un metodo generico che accetta gli stessi parametri di tipo della classe che lo contiene, il compilatore genera l'avviso [CS0693](../../misc/cs0693.md) perché nell'ambito del metodo l'argomento specificato per il parametro `T` interno nasconde l'argomento specificato per il parametro `T` esterno. Se è necessaria la flessibilità di poter chiamare un metodo di una classe generica con argomenti tipo diversi da quelli specificati alla creazione di un'istanza della classe, provare a specificare un altro identificatore per il parametro di tipo del metodo, come mostrato in `GenericList2<T>` nell'esempio seguente.  
  
 [!code-csharp[csProgGuideGenerics#26](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#26)]  
  
 Usare vincoli per consentire operazioni più specializzate sui parametri di tipo nei metodi. Questa versione di `Swap<T>`, ora chiamata `SwapIfGreater<T>`, può essere usata solo con argomenti tipo che implementano <xref:System.IComparable%601>.  
  
 [!code-csharp[csProgGuideGenerics#27](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#27)]  
  
 È possibile eseguire l'overload di metodi generici in diversi parametri di tipo. Ad esempio, i metodi seguenti possono essere contenuti tutti nella stessa classe:  
  
 [!code-csharp[csProgGuideGenerics#28](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#28)]  
  
## <a name="c-language-specification"></a>Specifiche del linguaggio C#  
 Per ulteriori informazioni, vedere la [specifica del linguaggio C .](~/_csharplang/spec/classes.md#methods)  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Collections.Generic>
- [Guida per programmatori C#](../index.md)
- [Introduzione ai generics](./index.md)
- [Metodi](../classes-and-structs/methods.md)
