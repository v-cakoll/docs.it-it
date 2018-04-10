---
title: Operatore == (Riferimenti per C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- ==_CSharpKeyword
helpviewer_keywords:
- == operator [C#]
- equality operator [C#]
ms.assetid: 34c6b597-caa2-4855-a7cd-38ecdd11bd07
caps.latest.revision: 14
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: ca22846325968519a1f7625461867c0d83a1a9f5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-c-reference"></a>Operatore == (Riferimenti per C#)
Per i tipi valore predefiniti, l'operatore di uguaglianza (`==`) restituisce true se i valori degli operandi sono uguali, in caso contrario `false`. Per i tipi riferimento diversi da [string](../../../csharp/language-reference/keywords/string.md), `==` restituisce `true` se i due operandi fanno riferimento allo stesso oggetto. Per il tipo `string`, `==` confronta i valori delle stringhe.  
  
## <a name="remarks"></a>Note  
 I tipi valore definiti dall'utente possono eseguire l'overload dell'operatore `==` (vedere [operatore](../../../csharp/language-reference/keywords/operator.md)). Lo stesso vale per i tipi riferimento definiti dall'utente, anche se per impostazione predefinita `==` si comporta come descritto in precedenza per entrambi i tipi riferimento predefiniti e definiti dall'utente. Se `==` è sottoposto a overload, deve esserlo anche [!=](../../../csharp/language-reference/operators/not-equal-operator.md). Le operazioni sui tipi integrali sono generalmente consentite sull'enumerazione.  
  
## <a name="example"></a>Esempio  
 [!code-csharp[csRefOperators#36](../../../csharp/language-reference/operators/codesnippet/CSharp/equality-comparison-operator_1.cs)]  
  
## <a name="see-also"></a>Vedere anche  
 [Riferimenti per C#](../../../csharp/language-reference/index.md)  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
 [Operatori C#](../../../csharp/language-reference/operators/index.md)
