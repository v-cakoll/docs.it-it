---
title: Operatore = (Riferimenti per C#)
ms.date: 07/20/2015
f1_keywords:
- =_CSharpKeyword
helpviewer_keywords:
- = operator [C#]
ms.assetid: d802a6d5-32f0-42b8-b180-12f5a081bfc1
ms.openlocfilehash: 9cd1af400a9afdb7942a49dee7e7f7bb78387f2d
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/03/2018
ms.locfileid: "43477932"
---
# <a name="-operator-c-reference"></a>Operatore = (Riferimenti per C#)
L'operatore di assegnazione (`=`) archivia il valore dell'operando a destra nella posizione di archiviazione, nella proprietà o nell'indicizzatore indicati dall'operando a sinistra e restituisce il valore come risultato. Gli operandi devono essere dello stesso tipo (o l'operando destro deve essere convertibile in modo implicito nel tipo dell'operando a sinistra).  
  
## <a name="remarks"></a>Note  
 Non è possibile sottoporre l'operatore di assegnazione a overload. Tuttavia, è possibile definire operatori di conversione implicita per un tipo, che consentono di usare l'operatore di assegnazione con tali tipi. Per altre informazioni, vedere [Uso degli operatori di conversione](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md).  
  
## <a name="example"></a>Esempio  
 [!code-csharp[csRefOperators#49](../../../csharp/language-reference/operators/codesnippet/CSharp/assignment-operator_1.cs)]  
  
## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../../../csharp/language-reference/index.md)  
- [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
- [Operatori C#](../../../csharp/language-reference/operators/index.md)
