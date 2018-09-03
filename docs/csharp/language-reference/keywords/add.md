---
title: add (Riferimenti per C#)
ms.date: 07/20/2015
f1_keywords:
- add_CSharpKeyword
helpviewer_keywords:
- add event accessor [C#]
ms.assetid: faf30b99-10e8-45cd-ab9a-57585d4d1d8d
ms.openlocfilehash: b55827b60a89da2569fad9da135c84571a24b094
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/03/2018
ms.locfileid: "43390968"
---
# <a name="add-c-reference"></a>add (Riferimenti per C#)
La parola chiave contestuale `add` viene usata per definire una funzione di accesso a eventi personalizzata che viene chiamata quando il codice client sottoscrive l'[evento](../../../csharp/language-reference/keywords/event.md). Se si specifica una funzione di accesso `add` personalizzata, è necessario specificare anche una funzione di accesso [remove](../../../csharp/language-reference/keywords/remove.md).  
  
## <a name="example"></a>Esempio  
 L'esempio seguente mostra un evento con le funzioni di accesso `add` personalizzata e [remove](../../../csharp/language-reference/keywords/remove.md). Per l'esempio completo, vedere [Procedura: Implementare eventi di interfaccia](../../../csharp/programming-guide/events/how-to-implement-interface-events.md).  
  
[!code-csharp[csrefKeywordsContextual#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#15)]
  
 In genere, non è necessario fornire funzioni di accesso a eventi personalizzate. Le funzioni di accesso generate automaticamente dal compilatore quando si dichiara un evento sono sufficienti per la maggior parte degli scenari.  
  
## <a name="see-also"></a>Vedere anche  
- [Eventi](../../../csharp/programming-guide/events/index.md)
