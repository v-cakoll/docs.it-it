---
title: 'Procedura: differenza tra il passaggio a un metodo di uno struct e di un riferimento a una classe (Guida per programmatori C#)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- structs [C#], passing as method parameter
- passing parameters [C#], structs vs. classes
- methods [C#], passing classes vs. structs
ms.assetid: 9c1313a6-32a8-4ea7-a59f-450f66af628b
caps.latest.revision: 25
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
ms.openlocfilehash: 1a4508c8765ac678fd371180cb0c3ece3e1d9a44
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-know-the-difference-between-passing-a-struct-and-passing-a-class-reference-to-a-method-c-programming-guide"></a>Procedura: differenza tra il passaggio a un metodo di uno struct e di un riferimento a una classe (Guida per programmatori C#)
L'esempio seguente mostra la differenza tra passare uno [struct](../../../csharp/language-reference/keywords/struct.md) a un metodo e passare un'istanza di una [classe](../../../csharp/language-reference/keywords/class.md) a un metodo. Nell'esempio entrambi gli argomenti (struct e istanza di classe) vengono passati in base al valore ed entrambi i metodi modificano il valore di un campo dell'argomento. I risultati dei due metodi non sono tuttavia uguali perché ciò che viene passato quando si passa uno struct è diverso da ciò che viene passato quando si passa un'istanza di una classe.  
  
 Poiché uno struct è un [tipo valore](../../../csharp/language-reference/keywords/value-types.md), quando si [passa uno struct in base al valore](../../../csharp/programming-guide/classes-and-structs/passing-value-type-parameters.md) a un metodo, il metodo riceve una copia dell'argomento dello struct, su cui opera. Il metodo non ha accesso allo struct originale nella chiamata e quindi non può modificarlo in alcun modo. Il metodo può modificare solo la copia.  
  
 Un'istanza di classe è un [tipo riferimento](../../../csharp/language-reference/keywords/reference-types.md), non un tipo valore. Quando si [passa un tipo riferimento in base al valore](../../../csharp/programming-guide/classes-and-structs/passing-reference-type-parameters.md) a un metodo, il metodo riceve una copia del riferimento all'istanza di classe. Ciò significa che il metodo riceve una copia dell'indirizzo dell'istanza, non una copia dell'istanza stessa. L'istanza di classe nel metodo chiamante ha un indirizzo, il parametro nel metodo chiamato ha una copia dell'indirizzo ed entrambi gli indirizzi fanno riferimento allo stesso oggetto. Poiché il parametro contiene solo una copia dell'indirizzo, il metodo chiamato non può modificare l'indirizzo dell'istanza di classe nel metodo chiamante. Il metodo chiamato può tuttavia usare l'indirizzo per accedere ai membri della classe a cui fanno riferimento sia l'indirizzo originale che la copia. Se il metodo chiamato modifica un membro della classe, viene modificata anche l'istanza di classe originale nel metodo chiamante.  
  
 L'output dell'esempio seguente illustra la differenza. Il valore del campo `willIChange` dell'istanza di classe viene modificato dalla chiamata al metodo `ClassTaker` perché il metodo usa l'indirizzo nel parametro per trovare il campo specificato dell'istanza di classe. Il campo `willIChange` dello struct nel metodo chiamante non viene modificato dalla chiamata al metodo `StructTaker` perché il valore dell'argomento è una copia dello struct, non una copia del relativo indirizzo. `StructTaker` modifica la copia e la copia viene persa quando la chiamata a `StructTaker` viene completata.  
  
## <a name="example"></a>Esempio  
 [!code-cs[csProgGuideObjects#32](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-know-the-difference-passing-a-struct-and-passing-a-class-to-a-method_1.cs)]  
  
## <a name="see-also"></a>Vedere anche  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)   
 [Classi](../../../csharp/programming-guide/classes-and-structs/classes.md)   
 [Struct](../../../csharp/programming-guide/classes-and-structs/structs.md)   
 [Passaggio di parametri](../../../csharp/programming-guide/classes-and-structs/passing-parameters.md)

