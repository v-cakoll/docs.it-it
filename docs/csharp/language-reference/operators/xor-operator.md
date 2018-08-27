---
title: Operatore ^ (Riferimenti per C#)
ms.date: 07/20/2015
f1_keywords:
- ^_CSharpKeyword
helpviewer_keywords:
- ^ operator [C#]
- bitwise exclusive OR operator [C#]
ms.assetid: b09bc815-570f-4db6-a637-5b4ed99d014a
ms.openlocfilehash: b1333f9d06e2804029550e6364a225558e096431
ms.sourcegitcommit: 412bbc2e43c3b6ca25b358cdf394be97336f0c24
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/25/2018
ms.locfileid: "42925298"
---
# <a name="-operator-c-reference"></a>Operatore ^ (Riferimenti per C#)
Gli operatori `^` binari sono predefiniti per i tipi integrali e `bool`. Per i tipi integrali, `^` calcola l'operazione di OR esclusivo bit per bit dei relativi operandi. Per gli operandi `bool`, `^` calcola l'operazione di OR esclusivo logico dei relativi operandi, ovvero, il risultato è `true` se e solo se esattamente uno degli operandi è `true`.  
  
## <a name="remarks"></a>Note  
 I tipi definiti dall'utente possono eseguire l'overload dell'operatore `^` (vedere [operatore](../../../csharp/language-reference/keywords/operator.md)). Le operazioni sui tipi integrali sono generalmente consentite sull'enumerazione.  
  
## <a name="example"></a>Esempio  
 [!code-csharp[csRefOperators#30](../../../csharp/language-reference/operators/codesnippet/CSharp/xor-operator_1.cs)]  
  
 Il calcolo di `0xf8 ^ 0x3f` nell'esempio precedente esegue un'operazione di OR esclusivo bit per bit dei due valori binari seguenti, che corrispondono ai valori esadecimali F8 e 3F:  
  
 `1111 1000`  
  
 `0011 1111`  
  
 Il risultato dell'operazione di OR esclusivo è `1100 0111`, ovvero C7 in formato esadecimale.  
  
## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../../../csharp/language-reference/index.md)  
- [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
- [Operatori C#](../../../csharp/language-reference/operators/index.md)
