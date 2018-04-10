---
title: Operatore = (Riferimenti per C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- =_CSharpKeyword
helpviewer_keywords:
- = operator [C#]
ms.assetid: d802a6d5-32f0-42b8-b180-12f5a081bfc1
caps.latest.revision: 14
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 4c7188abe54cb69678720b4dbbf4dbdea1be4abe
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-c-reference"></a>Operatore = (Riferimenti per C#)
L'operatore di assegnazione (`=`) archivia il valore dell'operando a destra nella posizione di archiviazione, nella proprietà o nell'indicizzatore indicati dall'operando a sinistra e restituisce il valore come risultato. Gli operandi devono essere dello stesso tipo (o l'operando destro deve essere convertibile in modo implicito nel tipo dell'operando a sinistra).  
  
## <a name="remarks"></a>Note  
 Non è possibile sottoporre l'operatore di assegnazione a overload. Tuttavia, è possibile definire operatori di conversione implicita per un tipo, che consentono di usare l'operatore di assegnazione con tali tipi. Per altre informazioni, vedere [Uso degli operatori di conversione](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md).  
  
## <a name="example"></a>Esempio  
 [!code-csharp[csRefOperators#49](../../../csharp/language-reference/operators/codesnippet/CSharp/assignment-operator_1.cs)]  
  
## <a name="see-also"></a>Vedere anche  
 [Riferimenti per C#](../../../csharp/language-reference/index.md)  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
 [Operatori C#](../../../csharp/language-reference/operators/index.md)
