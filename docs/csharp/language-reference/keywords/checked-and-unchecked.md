---
title: Checked e Unchecked (Riferimenti per C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- operators [C#], checked and unchecked
- exceptions [C#], overflow checking
- checked statement [C#]
- overflow checking [C#]
- unchecked statement [C#]
- statements [C#], checked and unchecked
ms.assetid: a84bc877-2c7f-4396-8735-1ce97c42f35e
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
ms.openlocfilehash: 744f59dbf7ee8370010ff76d4e9dde20490de403
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="checked-and-unchecked-c-reference"></a>Checked e Unchecked (Riferimenti per C#)
È possibile eseguire istruzioni C# in contesti verificati o non verificati. In un contesto verificato l'overflow aritmetico genera un'eccezione. In un contesto non verificato l'overflow aritmetico viene ignorato e il risultato è troncato.  
  
-   [checked](../../../csharp/language-reference/keywords/checked.md) Specificare il contesto verificato.  
  
-   [unchecked](../../../csharp/language-reference/keywords/unchecked.md) Specificare il contesto non verificato.  
  
 Se né `checked` né `unchecked` vengono specificati, il contesto predefinito dipende da fattori esterni, ad esempio le opzioni del compilatore.  
  
 Le operazioni seguenti sono interessate dal controllo di overflow:  
  
-   Espressioni che usano gli operatori predefiniti seguenti su tipi integrali:  
  
     `++` `--` - (unario)   `+` -   `*` `/`  
  
-   Conversioni numeriche esplicite tra tipi integrali.  
  
 L'opzione del compilatore [/checked](../../../csharp/language-reference/compiler-options/checked-compiler-option.md) consente di specificare il contesto verificato o non verificato per tutte le istruzioni aritmetiche su interi che non rientrano in modo esplicito nell'ambio di una parola chiave `checked` o `unchecked`.  
  
## <a name="see-also"></a>Vedere anche  
 [Riferimenti per C#](../../../csharp/language-reference/index.md)   
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)   
 [Parole chiave di C#](../../../csharp/language-reference/keywords/index.md)   
 [Parole chiave per le istruzioni](../../../csharp/language-reference/keywords/statement-keywords.md)

