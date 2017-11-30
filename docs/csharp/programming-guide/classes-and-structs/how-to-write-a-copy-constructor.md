---
title: 'Procedura: scrivere un costruttore di copia (Guida per programmatori C#)'
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- C# Language, copy constructor
- copy constructor [C#]
ms.assetid: fba899b5-fc41-428e-a745-3ebdbf37990a
caps.latest.revision: "20"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: f15d8fabc49cbff5515b78a7d2fb6f9e49d0704e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-write-a-copy-constructor-c-programming-guide"></a>Procedura: scrivere un costruttore di copia (Guida per programmatori C#)
C# non include un costruttore di copia per gli oggetti. È tuttavia possibile scriverne uno manualmente.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente, nella `Person`[classe](../../../csharp/language-reference/keywords/class.md) viene definito un costruttore di copia che accetta come argomento un'istanza di `Person`. I valori delle proprietà dell'argomento vengono assegnati alle proprietà della nuova istanza di `Person`. Il codice contiene un costruttore di copia alternativo che invia le proprietà `Name` e `Age` dell'istanza che si vuole copiare nel costruttore di istanza della classe.  
  
 [!code-csharp[csProgGuideObjects#16](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-write-a-copy-constructor_1.cs)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ICloneable>  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
 [Classi e struct](../../../csharp/programming-guide/classes-and-structs/index.md)  
 [Costruttori](../../../csharp/programming-guide/classes-and-structs/constructors.md)  
 [Finalizzatori](../../../csharp/programming-guide/classes-and-structs/destructors.md)
