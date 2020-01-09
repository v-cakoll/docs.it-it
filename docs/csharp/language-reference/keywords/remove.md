---
title: Parola chiave contestuale remove - Riferimenti per C#
ms.date: 07/20/2015
f1_keywords:
- remove_CSharpKeyword
helpviewer_keywords:
- remove event accessor [C#]
ms.assetid: c8223426-c17b-4fe2-8406-01564cf1dd2b
ms.openlocfilehash: 8ea3ea1910e28c03b2a894c64415cb2ccff942d0
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75713144"
---
# <a name="remove-c-reference"></a>remove (Riferimenti per C#)

La parola chiave contestuale `remove` viene usata per definire una funzione di accesso a eventi personalizzata che viene chiamata quando il codice client annulla la sottoscrizione all'[evento](event.md). Se si specifica una funzione di accesso `remove` personalizzata, è necessario specificare anche una funzione di accesso [add](add.md).

## <a name="example"></a>Esempio

L'esempio seguente mostra un evento con le funzioni di accesso [add](add.md) personalizzata e `remove`. Per l'esempio completo, vedere [come implementare eventi di interfaccia](../../programming-guide/events/how-to-implement-interface-events.md).

 [!code-csharp[csrefKeywordsContextual#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#15)]

In genere, non è necessario fornire funzioni di accesso a eventi personalizzate. Le funzioni di accesso generate automaticamente dal compilatore quando si dichiara un evento sono sufficienti per la maggior parte degli scenari.

## <a name="see-also"></a>Vedere anche

- [Eventi](../../programming-guide/events/index.md)
