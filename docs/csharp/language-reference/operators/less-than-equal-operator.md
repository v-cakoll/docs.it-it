---
title: Operatore &lt;= (Riferimenti per C#)
ms.date: 07/20/2015
f1_keywords:
- <=_CSharpKeyword
helpviewer_keywords:
- less than or equal to operator (<=) [C#]
- <= operator [C#]
ms.assetid: bb0caec9-d253-4105-b8bc-5252233251e4
ms.openlocfilehash: afbb932c1be010790236bec73a36acf0f01b97f4
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/15/2018
ms.locfileid: "45595061"
---
# <a name="lt-operator-c-reference"></a>Operatore &lt;= (Riferimenti per C#)
Tutti i tipi numerici e di enumerazione definiscono un operatore relazionale "minore o uguale a" (`<=`), che restituisce `true` se il primo operando è inferiore o uguale al secondo, in caso contrario `false`.  
  
## <a name="remarks"></a>Note  
 I tipi definiti dall'utente possono eseguire l'overload dell'operatore `<=`. Per altre informazioni, vedere l'argomento relativo all'[operatore](../../../csharp/language-reference/keywords/operator.md). Se `<=` è sottoposto a overload, deve esserlo anche [>=](../../../csharp/language-reference/operators/greater-than-equal-operator.md). Le operazioni sui tipi integrali sono generalmente consentite sull'enumerazione.  
  
## <a name="example"></a>Esempio  
 [!code-csharp[csRefOperators#32](../../../csharp/language-reference/operators/codesnippet/CSharp/less-than-equal-operator_1.cs)]  
  
## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../../../csharp/language-reference/index.md)  
- [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
- [Operatori C#](../../../csharp/language-reference/operators/index.md)  
- [explicit](../../../csharp/language-reference/keywords/explicit.md)
