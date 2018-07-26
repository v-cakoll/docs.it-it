---
title: Operatore [] (Riferimenti per C#)
ms.date: 07/20/2015
f1_keywords:
- '[]_CSharpKeyword'
helpviewer_keywords:
- subscript operator [C#]
- square brackets [ ] operator [C#]
- '[] operator [C#]'
- indexing operator [C#]
ms.assetid: 5c16bb45-88f7-45ff-b42c-1af1972b042c
ms.openlocfilehash: 65908bb3bcd8912ef81fc094e5958ae8dc4ae1f1
ms.sourcegitcommit: 60645077dc4b62178403145f8ef691b13ffec28e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2018
ms.locfileid: "37961445"
---
# <a name="-operator-c-reference"></a>Operatore [] (Riferimenti per C#)
Le parentesi quadre (`[]`) sono usate per le matrici, gli indicizzatori e gli attributi ma possono essere usate anche per i puntatori.  
  
## <a name="remarks"></a>Note  
 Un tipo matrice è un tipo seguito da `[]`:  
  
 [!code-csharp[csRefOperators#43](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_1.cs)]  
  
 Per consentire l'accesso a un elemento di una matrice, l'indice dell'elemento desiderato viene racchiuso tra parentesi:  
  
 [!code-csharp[csRefOperators#44](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_2.cs)]  
  
 Se l'indice di una matrice non è incluso nell'intervallo, viene generata un'eccezione.  
  
 L'operatore di indicizzazione della matrice non può essere sottoposto a overload. I tipi, tuttavia, possono definire gli indicizzatori nonché le proprietà che accettano uno o più parametri. I parametri dell'indicizzatore sono racchiusi tra parentesi quadre, come gli indici di matrice, ma a differenza di questi ultimi, che devono essere integrali, possono essere dichiarati come appartenenti a un tipo qualsiasi.  
  
 In .NET Framework, ad esempio, è possibile definire un tipo `Hashtable` che associa chiavi e valori di tipo arbitrario:  
  
 [!code-csharp[csRefOperators#45](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_3.cs)]  
  
 Le parentesi quadre vengono usate anche per specificare [attributi](../../../csharp/programming-guide/concepts/attributes/index.md):  
  
 [!code-csharp[csRefOperators#46](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_4.cs)]  
  
 È possibile usare le parentesi quadre per effettuare l'indicizzazione a partire da un puntatore:  
  
 [!code-csharp[csRefOperators#47](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_5.cs)]  
  
 Non viene eseguito alcun controllo dei limiti.  
  
## <a name="c-language-specification"></a>Specifiche del linguaggio C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Riferimenti per C#](../../../csharp/language-reference/index.md)  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
 [Operatori C#](../../../csharp/language-reference/operators/index.md)  
 [Array](../../../csharp/programming-guide/arrays/index.md)  
 [Indicizzatori](../../../csharp/programming-guide/indexers/index.md)  
 [unsafe](../../../csharp/language-reference/keywords/unsafe.md)  
 [Istruzione fixed](../../../csharp/language-reference/keywords/fixed-statement.md)
