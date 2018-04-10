---
title: Operatore &lt;= (Riferimenti per C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- <=_CSharpKeyword
helpviewer_keywords:
- less than or equal to operator (<=) [C#]
- <= operator [C#]
ms.assetid: bb0caec9-d253-4105-b8bc-5252233251e4
caps.latest.revision: 16
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: a74af852451a193aaee70fea2a68ca8ff29cc215
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="lt-operator-c-reference"></a>Operatore &lt;= (Riferimenti per C#)
Tutti i tipi numerici e di enumerazione definiscono un operatore relazionale "minore o uguale a" (`<=`), che restituisce `true` se il primo operando è inferiore o uguale al secondo, in caso contrario `false`.  
  
## <a name="remarks"></a>Note  
 I tipi definiti dall'utente possono eseguire l'overload dell'operatore `<=`. Per altre informazioni, vedere l'argomento relativo all'[operatore](../../../csharp/language-reference/keywords/operator.md). Se `<=` è sottoposto a overload, deve esserlo anche [>=](../../../csharp/language-reference/operators/greater-than-equal-operator.md). Le operazioni sui tipi integrali sono generalmente consentite sull'enumerazione.  
  
## <a name="example"></a>Esempio  
 [!code-csharp[csRefOperators#32](../../../csharp/language-reference/operators/codesnippet/CSharp/less-than-equal-operator_1.cs)]  
  
## <a name="see-also"></a>Vedere anche  
 [Riferimenti per C#](../../../csharp/language-reference/index.md)  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
 [Operatori C#](../../../csharp/language-reference/operators/index.md)  
 [explicit](../../../csharp/language-reference/keywords/explicit.md)
