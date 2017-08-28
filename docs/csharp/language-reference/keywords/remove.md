---
title: remove (Riferimenti per C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- remove_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- remove event accessor [C#]
ms.assetid: c8223426-c17b-4fe2-8406-01564cf1dd2b
caps.latest.revision: 8
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
ms.openlocfilehash: b34d653a40e1309e281235416c0399abc6dd9a0d
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="remove-c-reference"></a>remove (Riferimenti per C#)
La parola chiave contestuale `remove` viene usata per definire una funzione di accesso a eventi personalizzata che viene chiamata quando il codice client annulla la sottoscrizione all'[evento](../../../csharp/language-reference/keywords/event.md). Se si specifica una funzione di accesso `remove` personalizzata, è necessario specificare anche una funzione di accesso [add](../../../csharp/language-reference/keywords/add.md).  
  
## <a name="example"></a>Esempio  
 L'esempio seguente mostra un evento con le funzioni di accesso [add](../../../csharp/language-reference/keywords/add.md) personalizzata e `remove`. Per l'esempio completo, vedere [Procedura: Implementare eventi di interfaccia](../../../csharp/programming-guide/events/how-to-implement-interface-events.md).  
  
 [!code-cs[csrefKeywordsContextual#15](../../../csharp/language-reference/keywords/codesnippet/CSharp/remove_1.cs)]  
  
 In genere, non è necessario fornire funzioni di accesso a eventi personalizzate. Le funzioni di accesso generate automaticamente dal compilatore quando si dichiara un evento sono sufficienti per la maggior parte degli scenari.  
  
## <a name="see-also"></a>Vedere anche  
 [Eventi](../../../csharp/programming-guide/events/index.md)

