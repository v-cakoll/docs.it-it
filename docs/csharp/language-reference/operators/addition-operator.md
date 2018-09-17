---
title: + Operatore (Riferimenti per C#)
ms.date: 07/20/2015
f1_keywords:
- +_CSharpKeyword
helpviewer_keywords:
- + operator [C#]
- concatenation operator [C#]
- addition operator [C#]
ms.assetid: 93e56486-bb42-43c1-bd43-60af11e64e67
ms.openlocfilehash: b49694bc8937c58bd295f0f8e57c378802d0dfb9
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2018
ms.locfileid: "45594598"
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

- [Riferimenti per C#](../../../csharp/language-reference/index.md)  
- [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
- [Operatori C#](../../../csharp/language-reference/operators/index.md)  
- [operatore (Riferimenti per C#)](../../../csharp/language-reference/keywords/operator.md)
