---
title: 'Procedura: Scrivere un costruttore di copia - Guida per programmatori C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- C# Language, copy constructor
- copy constructor [C#]
ms.assetid: fba899b5-fc41-428e-a745-3ebdbf37990a
ms.openlocfilehash: 252e66229b75c545c85aa175267ea267c138a087
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54573124"
---
# <a name="how-to-write-a-copy-constructor-c-programming-guide"></a>Procedura: Scrivere un costruttore di copia (Guida per programmatori C#)
C# non include un costruttore di copia per gli oggetti. È tuttavia possibile scriverne uno manualmente.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente, nella `Person`[classe](../../../csharp/language-reference/keywords/class.md) viene definito un costruttore di copia che accetta come argomento un'istanza di `Person`. I valori delle proprietà dell'argomento vengono assegnati alle proprietà della nuova istanza di `Person`. Il codice contiene un costruttore di copia alternativo che invia le proprietà `Name` e `Age` dell'istanza che si vuole copiare nel costruttore di istanza della classe.  
  
 [!code-csharp[csProgGuideObjects#16](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-write-a-copy-constructor_1.cs)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ICloneable>
- [Guida per programmatori C#](../../../csharp/programming-guide/index.md)
- [Classi e struct](../../../csharp/programming-guide/classes-and-structs/index.md)
- [Costruttori](../../../csharp/programming-guide/classes-and-structs/constructors.md)
- [Finalizzatori](../../../csharp/programming-guide/classes-and-structs/destructors.md)
