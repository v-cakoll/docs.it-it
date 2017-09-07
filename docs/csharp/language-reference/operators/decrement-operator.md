---
title: Operatore -- (Riferimenti per C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- --_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- -- operator [C#]
- decrement operator (--) [C#]
ms.assetid: 6b9cfe86-63c7-421f-9379-c9690fea8720
caps.latest.revision: 17
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
ms.openlocfilehash: 100e68f3b07164b0cfb398a32f47137f2726943f
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="---operator-c-reference"></a>Operatore -- (Riferimenti per C#)
L'operatore di decremento (`--`) decrementa il proprio operando di 1. L'operatore di decremento può apparire prima o dopo il proprio operando: `--variable` e `variable--`. Il primo esempio è un'operazione di decremento prefisso. Il risultato dell'operazione è il valore dell'operando "dopo" essere stato decrementato. Il secondo esempio è un'operazione di decremento suffisso. Il risultato dell'operazione è il valore dell'operando "prima" di essere decrementato.  
  
## <a name="remarks"></a>Note  
 I tipi numerico e di enumerazione hanno operatori di decremento predefiniti.  
  
 I tipi definiti dall'utente possono eseguire l'overload dell'operatore `--` (vedere [operatore](../../../csharp/language-reference/keywords/operator.md)). Le operazioni sui tipi integrali sono generalmente consentite sull'enumerazione.  
  
## <a name="example"></a>Esempio  
 [!code-cs[csRefOperators#8](../../../csharp/language-reference/operators/codesnippet/CSharp/decrement-operator_1.cs)]  
  
## <a name="see-also"></a>Vedere anche  
 [Riferimenti per C#](../../../csharp/language-reference/index.md)   
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)   
 [Operatori C#](../../../csharp/language-reference/operators/index.md)

