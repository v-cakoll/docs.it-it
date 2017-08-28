---
title: Parametri di tipo generico (Guida per programmatori C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- generics [C#], type parameters
- type parameters [C#]
ms.assetid: a03b0ab2-0606-4b41-b7bf-e64d5bb4d18f
caps.latest.revision: 23
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
ms.openlocfilehash: ce1024215a381afb3a7b42f2127fe5e8c212d378
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="generic-type-parameters-c-programming-guide"></a>Parametri di tipo generico (Guida per programmatori C#)
In una definizione di tipo o metodo generico un parametro di tipo è un segnaposto per un determinato tipo specificato da un client durante la creazione di un'istanza di una variabile del tipo generico. Una classe generica, ad esempio `GenericList<T>`, elencata in [Introduzione ai generics](../../../csharp/programming-guide/generics/introduction-to-generics.md), non può essere usata in quanto tale perché non è effettivamente un tipo, ma è piuttosto un progetto iniziale per un tipo. Per usare `GenericList<T>`, il codice client deve dichiarare un tipo costruito e crearne un'istanza specificando un argomento tipo racchiuso tra parentesi angolari. L'argomento tipo per questa classe specifica può essere qualsiasi tipo riconosciuto dal compilatore. È possibile creare un numero qualsiasi di istanze del tipo costruito, ognuna con un argomento tipo diverso, in questo modo:  
  
 [!code-cs[csProgGuideGenerics#7](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-type-parameters_1.cs)]  
  
 In ognuna di queste istanze di `GenericList<T>` ogni occorrenza di `T` nella classe verrà sostituita in fase di esecuzione con l'argomento tipo. Per mezzo di questa sostituzione, sono stati creati tre oggetti efficienti e indipendenti dai tipi separati usando un'unica definizione di classe. Per altre informazioni su come viene eseguita questa sostituzione da CLR, vedere [Generics nel runtime](../../../csharp/programming-guide/generics/generics-in-the-run-time.md).  
  
## <a name="type-parameter-naming-guidelines"></a>Linee guida per la denominazione dei parametri di tipo  
  
-   **Assegnare** ai parametri di tipo generico nomi descrittivi, a meno che un nome di una sola lettera non sia già completamente comprensibile, senza che sia necessario un nome descrittivo più lungo.  
  
     [!code-cs[csProgGuideGenerics#8](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-type-parameters_2.cs)]  
  
-   **Provare** a usare T come nome del parametro di tipo per i tipi con parametro di tipo di una sola lettera.  
  
     [!code-cs[csProgGuideGenerics#9](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-type-parameters_3.cs)]  
  
-   **Aggiungere** ai nomi di parametro di tipo descrittivi il prefisso "T".  
  
     [!code-cs[csProgGuideGenerics#10](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-type-parameters_4.cs)]  
  
-   **Provare** a indicare i vincoli applicati a un parametro di tipo nel nome del parametro. Ad esempio, assegnare a un parametro vincolato a `ISession` il nome `TSession`.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Collections.Generic>   
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)   
 [Generics](../../../csharp/programming-guide/generics/index.md)   
 [Differenze tra modelli C++ e generics C#](../../../csharp/programming-guide/generics/differences-between-cpp-templates-and-csharp-generics.md)

