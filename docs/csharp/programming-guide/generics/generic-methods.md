---
title: Metodi generici (Guida per programmatori C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- generics [C#], methods
ms.assetid: 673eeea2-4b48-4faa-9c4e-2e89449221b9
caps.latest.revision: 27
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 14461773303bafc098f79c3686b1f76827f11005
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="generic-methods-c-programming-guide"></a>Metodi generici (Guida per programmatori C#)
Un metodo generico è un metodo che viene dichiarato con parametri di tipo, in questo modo:  
  
 [!code-cs[csProgGuideGenerics#22](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-methods_1.cs)]  
  
 L'esempio di codice seguente mostra un modo per chiamare il metodo usando `int` per l'argomento tipo:  
  
 [!code-cs[csProgGuideGenerics#23](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-methods_2.cs)]  
  
 È anche possibile omettere l'argomento tipo perché venga dedotto dal compilatore. La chiamata seguente a `Swap` equivale alla chiamata precedente:  
  
 [!code-cs[csProgGuideGenerics#24](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-methods_3.cs)]  
  
 Ai metodi statici e ai metodi di istanza si applicano le stesse regole relative all'inferenza del tipo. Il compilatore può dedurre i parametri di tipo in base agli argomenti metodo passati, ma non può dedurli solo da un vincolo o da un valore restituito. Di conseguenza, l'inferenza del tipo non funziona con metodi che non includono parametri. L'inferenza del tipo avviene in fase di compilazione prima che il compilatore provi a risolvere le firme dei metodi di overload. Il compilatore applica la logica di inferenza del tipo a tutti i metodi generici che condividono lo stesso nome. Nel passaggio di risoluzione dell'overload, il compilatore include solo i metodi generici per cui l'inferenza del tipo è riuscita.  
  
 All'interno di una classe generica metodi non generici possono accedere ai parametri di tipo a livello di classe, in questo modo:  
  
 [!code-cs[csProgGuideGenerics#25](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-methods_4.cs)]  
  
 Se si definisce un metodo generico che accetta gli stessi parametri di tipo della classe che lo contiene, il compilatore genera l'avviso CS0693 perché nell'ambito del metodo l'argomento specificato per il parametro `T` interno nasconde l'argomento specificato per il parametro `T` esterno. Se è necessaria la flessibilità di poter chiamare un metodo di una classe generica con argomenti tipo diversi da quelli specificati alla creazione di un'istanza della classe, provare a specificare un altro identificatore per il parametro di tipo del metodo, come mostrato in `GenericList2<T>` nell'esempio seguente.  
  
 [!code-cs[csProgGuideGenerics#26](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-methods_5.cs)]  
  
 Usare vincoli per consentire operazioni più specializzate sui parametri di tipo nei metodi. Questa versione di `Swap<T>`, ora chiamata `SwapIfGreater<T>`, può essere usata solo con argomenti tipo che implementano <xref:System.IComparable%601>.  
  
 [!code-cs[csProgGuideGenerics#27](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-methods_6.cs)]  
  
 È possibile eseguire l'overload di metodi generici in diversi parametri di tipo. Ad esempio, i metodi seguenti possono essere contenuti tutti nella stessa classe:  
  
 [!code-cs[csProgGuideGenerics#28](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-methods_7.cs)]  
  
## <a name="c-language-specification"></a>Specifiche del linguaggio C#  
 Per altre informazioni, vedere la [specifica del linguaggio C#](../../../csharp/language-reference/language-specification/index.md).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Collections.Generic>   
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)   
 [Introduzione ai generics](../../../csharp/programming-guide/generics/introduction-to-generics.md)   
 [Metodi](../../../csharp/programming-guide/classes-and-structs/methods.md)

