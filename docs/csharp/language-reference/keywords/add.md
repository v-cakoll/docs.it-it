---
title: add (Riferimenti per C#)
ms.date: 07/20/2015
f1_keywords:
- add_CSharpKeyword
helpviewer_keywords:
- add event accessor [C#]
ms.assetid: faf30b99-10e8-45cd-ab9a-57585d4d1d8d
ms.openlocfilehash: c1fa8c130475a67ac175205fe3491a32654ea475
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="add-c-reference"></a>add (Riferimenti per C#)
La parola chiave contestuale `add` viene usata per definire una funzione di accesso a eventi personalizzata che viene chiamata quando il codice client sottoscrive l'[evento](../../../csharp/language-reference/keywords/event.md). Se si specifica una funzione di accesso `add` personalizzata, è necessario specificare anche una funzione di accesso [remove](../../../csharp/language-reference/keywords/remove.md).  
  
## <a name="example"></a>Esempio  
 L'esempio seguente mostra un evento con le funzioni di accesso `add` personalizzata e [remove](../../../csharp/language-reference/keywords/remove.md). Per l'esempio completo, vedere [Procedura: Implementare eventi di interfaccia](../../../csharp/programming-guide/events/how-to-implement-interface-events.md).  
  
 [!code-csharp[csrefKeywordsContextual#15](../../../csharp/language-reference/keywords/codesnippet/CSharp/add_1.cs)]  
  
 In genere, non è necessario fornire funzioni di accesso a eventi personalizzate. Le funzioni di accesso generate automaticamente dal compilatore quando si dichiara un evento sono sufficienti per la maggior parte degli scenari.  
  
## <a name="see-also"></a>Vedere anche  
 [Eventi](../../../csharp/programming-guide/events/index.md)
