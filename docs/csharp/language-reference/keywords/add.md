---
title: add - Riferimenti per C#
ms.date: 07/20/2015
f1_keywords:
- add_CSharpKeyword
helpviewer_keywords:
- add event accessor [C#]
ms.assetid: faf30b99-10e8-45cd-ab9a-57585d4d1d8d
ms.openlocfilehash: 323064dcbe7596b5f1d2f0f6aa566b07cee45789
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75713802"
---
# <a name="add-c-reference"></a>add (Riferimenti per C#)
La parola chiave contestuale `add` viene usata per definire una funzione di accesso a eventi personalizzata che viene chiamata quando il codice client sottoscrive l'[evento](./event.md). Se si specifica una funzione di accesso `add` personalizzata, è necessario specificare anche una funzione di accesso [remove](./remove.md).  
  
## <a name="example"></a>Esempio  
L'esempio seguente mostra un evento con le funzioni di accesso `add` personalizzata e [remove](./remove.md). Per l'esempio completo, vedere [Come implementare gli eventi](../../programming-guide/events/how-to-implement-interface-events.md)di interfaccia .
  
[!code-csharp[csrefKeywordsContextual#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#15)]
  
 In genere, non è necessario fornire funzioni di accesso a eventi personalizzate. Le funzioni di accesso generate automaticamente dal compilatore quando si dichiara un evento sono sufficienti per la maggior parte degli scenari.  
  
## <a name="see-also"></a>Vedere anche

- [Events](../../programming-guide/events/index.md)
