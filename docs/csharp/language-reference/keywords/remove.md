---
title: remove (Riferimenti per C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- remove_CSharpKeyword
helpviewer_keywords:
- remove event accessor [C#]
ms.assetid: c8223426-c17b-4fe2-8406-01564cf1dd2b
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 66647dee0c4cc728ae5e19457a4a5ef0e7f72248
ms.sourcegitcommit: 7e99f66ef09d2903e22c789c67ff5a10aa953b2f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/18/2017
---
# <a name="remove-c-reference"></a>remove (Riferimenti per C#)
La parola chiave contestuale `remove` viene usata per definire una funzione di accesso a eventi personalizzata che viene chiamata quando il codice client annulla la sottoscrizione all'[evento](../../../csharp/language-reference/keywords/event.md). Se si specifica una funzione di accesso `remove` personalizzata, è necessario specificare anche una funzione di accesso [add](../../../csharp/language-reference/keywords/add.md).  
  
## <a name="example"></a>Esempio  
 L'esempio seguente mostra un evento con le funzioni di accesso [add](../../../csharp/language-reference/keywords/add.md) personalizzata e `remove`. Per l'esempio completo, vedere [Procedura: Implementare eventi di interfaccia](../../../csharp/programming-guide/events/how-to-implement-interface-events.md).  
  
 [!code-csharp[csrefKeywordsContextual#15](../../../csharp/language-reference/keywords/codesnippet/CSharp/remove_1.cs)]  
  
 In genere, non è necessario fornire funzioni di accesso a eventi personalizzate. Le funzioni di accesso generate automaticamente dal compilatore quando si dichiara un evento sono sufficienti per la maggior parte degli scenari.  
  
## <a name="see-also"></a>Vedere anche  
 [Eventi](../../../csharp/programming-guide/events/index.md)
