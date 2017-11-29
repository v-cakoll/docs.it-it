---
title: + Operatore (Riferimenti per C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: +_CSharpKeyword
helpviewer_keywords:
- + operator [C#]
- concatenation operator [C#]
- addition operator [C#]
ms.assetid: 93e56486-bb42-43c1-bd43-60af11e64e67
caps.latest.revision: "19"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: b15d5d1a304569b92b2f811a9ea714e4b30d60d7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-c-reference"></a>Operatore + (Riferimenti per C#)
L'operatore `+` ha la funzione di operatore unario o binario.  
  
## <a name="remarks"></a>Note  
 Gli operatori `+` unari sono predefiniti per tutti i tipi numerici. Il risultato di un'operazione `+` unaria su un tipo numerico corrisponde al valore dell'operando.  
  
 Gli operatori `+` binari sono predefiniti per i tipi numerici e stringa. Per i tipi numerici, + calcola la somma dei due operandi. Quando uno o entrambi gli operandi sono di tipo stringa, + concatena le rappresentazioni di stringa degli operandi.  
  
 I tipi delegati offrono anche un operatore `+` binario, che esegue la concatenazione dei delegati.  
  
 I tipi definiti dall'utente possono eseguire l'overload degli operatori `+` unari e `+` binari. Le operazioni sui tipi integrali sono generalmente consentite sull'enumerazione. Per altre informazioni, vedere [operatore (Riferimenti per C#)](../../../csharp/language-reference/keywords/operator.md).  
  
## <a name="example"></a>Esempio  
 [!code-csharp[csRefOperators#28](../../../csharp/language-reference/operators/codesnippet/CSharp/addition-operator_1.cs)]  
  
## <a name="c-language-specification"></a>Specifiche del linguaggio C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Riferimenti per C#](../../../csharp/language-reference/index.md)  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
 [Operatori C#](../../../csharp/language-reference/operators/index.md)  
 [operatore (Riferimenti per C#)](../../../csharp/language-reference/keywords/operator.md)
