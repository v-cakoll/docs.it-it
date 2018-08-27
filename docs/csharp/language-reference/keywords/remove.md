---
title: remove (Riferimenti per C#)
ms.date: 07/20/2015
f1_keywords:
- remove_CSharpKeyword
helpviewer_keywords:
- remove event accessor [C#]
ms.assetid: c8223426-c17b-4fe2-8406-01564cf1dd2b
ms.openlocfilehash: 245ef0a16fd2cec2f36c86dd0ac3b8838a76b02e
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "42999771"
---
# <a name="remove-c-reference"></a>remove (Riferimenti per C#)
La parola chiave contestuale `remove` viene usata per definire una funzione di accesso a eventi personalizzata che viene chiamata quando il codice client annulla la sottoscrizione all'[evento](../../../csharp/language-reference/keywords/event.md). Se si specifica una funzione di accesso `remove` personalizzata, è necessario specificare anche una funzione di accesso [add](../../../csharp/language-reference/keywords/add.md).  
  
## <a name="example"></a>Esempio  
 L'esempio seguente mostra un evento con le funzioni di accesso [add](../../../csharp/language-reference/keywords/add.md) personalizzata e `remove`. Per l'esempio completo, vedere [Procedura: Implementare eventi di interfaccia](../../../csharp/programming-guide/events/how-to-implement-interface-events.md).  
  
 [!code-csharp[csrefKeywordsContextual#15](../../../csharp/language-reference/keywords/codesnippet/CSharp/remove_1.cs)]  
  
 In genere, non è necessario fornire funzioni di accesso a eventi personalizzate. Le funzioni di accesso generate automaticamente dal compilatore quando si dichiara un evento sono sufficienti per la maggior parte degli scenari.  
  
## <a name="see-also"></a>Vedere anche

- [Eventi](../../../csharp/programming-guide/events/index.md)
