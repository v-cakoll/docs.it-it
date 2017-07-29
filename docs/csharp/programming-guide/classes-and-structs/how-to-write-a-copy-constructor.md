---
title: 'Procedura: scrivere un costruttore di copia (Guida per programmatori C#)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- C# Language, copy constructor
- copy constructor [C#]
ms.assetid: fba899b5-fc41-428e-a745-3ebdbf37990a
caps.latest.revision: 20
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
ms.openlocfilehash: 712d9d5e792d025dd7c91d4c1809eeba96759757
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-write-a-copy-constructor-c-programming-guide"></a>Procedura: scrivere un costruttore di copia (Guida per programmatori C#)
C# non include un costruttore di copia per gli oggetti. È tuttavia possibile scriverne uno manualmente.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente, nella `Person`classe[ ](../../../csharp/language-reference/keywords/class.md) viene definito un costruttore di copia che accetta come argomento un'istanza di `Person`. I valori delle proprietà dell'argomento vengono assegnati alle proprietà della nuova istanza di `Person`. Il codice contiene un costruttore di copia alternativo che invia le proprietà `Name` e `Age` dell'istanza che si vuole copiare nel costruttore di istanza della classe.  
  
 [!code-cs[csProgGuideObjects#16](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-write-a-copy-constructor_1.cs)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ICloneable>   
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)   
 [Classi e struct](../../../csharp/programming-guide/classes-and-structs/index.md)   
 [Costruttori](../../../csharp/programming-guide/classes-and-structs/constructors.md)   
 [Finalizzatori](../../../csharp/programming-guide/classes-and-structs/destructors.md)

