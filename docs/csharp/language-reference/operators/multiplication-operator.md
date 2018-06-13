---
title: '* Operatore (Riferimenti per C#)'
ms.date: 04/04/2018
f1_keywords:
- '*_CSharpKeyword'
helpviewer_keywords:
- multiplication operator (*) [C#]
- '* operator [C#]'
ms.assetid: abd9a5f0-9b24-431e-971a-09ee1c45c50e
ms.openlocfilehash: 6c5d4de587b67e5ade158c163a87e8dea6bece5a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33275841"
---
# <a name="-operator-c-reference"></a>Operatore * (Riferimenti per C#)
L'operatore di moltiplicazione (`*`) calcola il prodotto degli operandi. Tutti i tipi numerici hanno operatori di moltiplicazione predefiniti.  

`*` funge anche da operatore di dereferenziazione, che consente la lettura e scrittura in un puntatore.
  
## <a name="remarks"></a>Note  
 L'operatore `*` viene anche usato per dichiarare i tipi di puntatore e dereferenziare i puntatori. Questo operatore può essere usato solo in contesti non sicuri, che sono identificati dall'uso della parola chiave [unsafe](../../../csharp/language-reference/keywords/unsafe.md) e richiedono l'opzione [/unsafe](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md) del compilatore.  L'operatore di dereferenziazione è noto anche come operatore di riferimento indiretto.  
  
 I tipi definiti dall'utente possono eseguire l'overload dell'operatore `*` (vedere [operator](../../../csharp/language-reference/keywords/operator.md)). Quando viene eseguito l'overload di un operatore binario, viene anche eseguito in modo implicito l'overload dell'operatore di assegnazione corrispondente, se presente.  
  
## <a name="example"></a>Esempio  
 [!code-csharp[csRefOperators#50](../../../csharp/language-reference/operators/codesnippet/CSharp/multiplication-operator_1.cs)]  
  
## <a name="example"></a>Esempio  
 [!code-csharp[csRefOperators#51](../../../csharp/language-reference/operators/codesnippet/CSharp/multiplication-operator_2.cs)]  
  
## <a name="see-also"></a>Vedere anche  
 [Riferimenti per C#](../../../csharp/language-reference/index.md)  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
 [Codice unsafe e puntatori](../../../csharp/programming-guide/unsafe-code-pointers/index.md)  
 [Operatori C#](../../../csharp/language-reference/operators/index.md)
