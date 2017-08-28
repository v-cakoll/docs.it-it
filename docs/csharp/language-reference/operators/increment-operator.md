---
title: Operatore ++ (Riferimenti per C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- ++_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- increment operator (++) [C#]
- ++ operator [C#]
ms.assetid: e9dec353-070b-44fb-98ed-eb8fdf753feb
caps.latest.revision: 18
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 9f481dbe2437495b109d6d41cd24c8b4bb5b6a5b
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a>Operatore ++ (Riferimenti per C#)
L'operatore di incremento (`++`) incrementa il suo operando di 1. L'operatore di incremento può apparire prima o dopo il suo operando: `++variable` e `variable++`.  
  
## <a name="remarks"></a>Note  
 Il primo modulo è un'operazione di incremento prefisso. Il risultato dell'operazione è il valore dell'operando dopo essere stato incrementato.  
  
 Il secondo modulo è un'operazione di incremento suffisso. Il risultato dell'operazione è il valore dell'operando prima di essere incrementato.  
  
 I tipi numerico e di enumerazione hanno operatori di incremento predefiniti. I tipi definiti dall'utente possono eseguire l'overload dell'operatore `++` . Le operazioni sui tipi integrali sono generalmente consentite sull'enumerazione.  
  
## <a name="example"></a>Esempio  
 [!code-cs[csRefOperators#3](../../../csharp/language-reference/operators/codesnippet/CSharp/increment-operator_1.cs)]  
  
## <a name="see-also"></a>Vedere anche  
 [Riferimenti per C#](../../../csharp/language-reference/index.md)   
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)   
 [Operatori C#](../../../csharp/language-reference/operators/index.md)

