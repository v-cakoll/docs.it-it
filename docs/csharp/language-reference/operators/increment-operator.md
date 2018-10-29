---
title: Operatore ++ (Riferimenti per C#)
ms.date: 07/20/2015
f1_keywords:
- ++_CSharpKeyword
helpviewer_keywords:
- increment operator (++) [C#]
- ++ operator [C#]
ms.assetid: e9dec353-070b-44fb-98ed-eb8fdf753feb
ms.openlocfilehash: a52f614ce1bbfb8e9d9be686b277c1e69f6f9d35
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/02/2018
ms.locfileid: "48030470"
---
# <a name="-operator-c-reference"></a>Operatore ++ (Riferimenti per C#)
L'operatore di incremento (`++`) incrementa il suo operando di 1. L'operatore di incremento può apparire prima o dopo il suo operando: `++variable` e `variable++`.  
  
## <a name="remarks"></a>Note  
 Il primo modulo è un'operazione di incremento prefisso. Il risultato dell'operazione è il valore dell'operando dopo essere stato incrementato.  
  
 Il secondo modulo è un'operazione di incremento suffisso. Il risultato dell'operazione è il valore dell'operando prima di essere incrementato.  
  
 I tipi numerico e di enumerazione hanno operatori di incremento predefiniti. I tipi definiti dall'utente possono eseguire l'overload dell'operatore `++` . Le operazioni sui tipi integrali sono generalmente consentite sull'enumerazione.  
  
## <a name="example"></a>Esempio  
 [!code-csharp[csRefOperators#3](../../../csharp/language-reference/operators/codesnippet/CSharp/increment-operator_1.cs)]  
  
## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../../../csharp/language-reference/index.md)  
- [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
- [Operatori C#](../../../csharp/language-reference/operators/index.md)
