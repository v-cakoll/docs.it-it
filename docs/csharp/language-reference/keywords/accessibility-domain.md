---
title: Dominio di accessibilità - Riferimenti per C#
ms.date: 07/20/2015
helpviewer_keywords:
- accessibility domain [C#]
ms.assetid: 8af779c1-275b-44be-a864-9edfbca71bcc
ms.openlocfilehash: 4a4319b03f3e0d7f9ec721e611b78c124a8a8ee5
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75713827"
---
# <a name="accessibility-domain-c-reference"></a>Dominio di accessibilità (Riferimenti per C#)
Il dominio di accessibilità di un membro specifica in quali sezioni del programma è possibile fare riferimento a un membro. Se il membro è annidato all'interno di un altro tipo, il suo dominio di accessibilità viene determinato dal [livello di accessibilità](./accessibility-levels.md) del membro e dal dominio di accessibilità del tipo contenitore.  
  
 Il dominio di accessibilità di un tipo di primo livello è minimo il testo di programma del progetto in cui è dichiarato. Vale a dire che il dominio include tutti i file di origine di questo progetto. Il dominio di accessibilità di un tipo annidato è minimo il testo del programma del tipo in cui è dichiarato. Vale a dire che il dominio è il corpo tipo che include tutti i tipi annidati. Il dominio di accessibilità di un tipo annidato non è mai superiore a quello del tipo contenitore. Questi concetti vengono illustrati nell'esempio seguente.  
  
## <a name="example"></a>Esempio  
 Questo esempio include un tipo di primo livello, `T1`, e due classi annidate, `M1` e `M2`. Le classi contengono campi diversi con accessibilità dichiarate. Nel metodo `Main` un commento segue ogni istruzione per indicare il dominio di accessibilità di ogni membro. Si noti che le istruzioni che tentano di fare riferimento ai membri inaccessibili sono impostate come commento. Se si desidera visualizzare gli errori del compilatore causati da un riferimento a un membro inaccessibile, rimuovere i commenti uno alla volta.  
  
[!code-csharp[csrefKeywordsModifiers#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#4)]
  
## <a name="c-language-specification"></a>Specifica del linguaggio C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [Parole chiave di C#](./index.md)
- [Modificatori di accesso](./access-modifiers.md)
- [Livelli di accessibilità](./accessibility-levels.md)
- [Restrizioni relative all'uso dei livelli di accessibilità](./restrictions-on-using-accessibility-levels.md)
- [Modificatori di accesso](../../programming-guide/classes-and-structs/access-modifiers.md)
- [public](./public.md)
- [private](./private.md)
- [protected](./protected.md)
- [internal](./internal.md)
