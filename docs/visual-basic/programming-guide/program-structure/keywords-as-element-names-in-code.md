---
title: Parole chiave come nomi di elementi nel codice (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, naming conventions
- keywords [Visual Basic], in code
- name conflicts [Visual Basic]
- element names [Visual Basic], in code
ms.assetid: 2e4e8e02-23f7-49b9-a1c8-2b0402b6b525
ms.openlocfilehash: c247ada67f6554362f287cf252dd49856c4995da
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58841147"
---
# <a name="keywords-as-element-names-in-code-visual-basic"></a>Parole chiave come nomi di elementi nel codice (Visual Basic)
Qualsiasi elemento del programma, ad esempio una variabile, una classe o un membro, ovvero può avere lo stesso nome di una parola chiave riservata. Ad esempio, è possibile creare una variabile denominata `Loop`. Tuttavia, per fare riferimento alla propria versione della variabile, ovvero che ha lo stesso nome di area con restrizioni `Loop` parola chiave, è necessario anteporre una stringa di qualificazione completo o racchiuderlo tra parentesi quadre (`[ ]`), come illustrato nell'esempio seguente.  
  
 [!code-vb[VbVbcnConventions#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#8)]  
  
 Se si manifesta uno di questi, il Visual Basic presuppone l'uso di intrinseci `Loop` (parola chiave) e genera un errore, come nell'esempio seguente:  
  
 `' The following statement causes a compiler error.`  
  
 `Loop.Visible = True`  
  
 È possibile usare le parentesi quadre quando si fa riferimento al form e controlli e, quando si dichiara una variabile o la definizione di una routine con lo stesso nome di una parola chiave riservata. Può essere facile dimenticare di qualificare i nomi o includere le parentesi quadre, quindi introdurre errori nel codice e rendono più difficile da leggere. Per questo motivo, è consigliabile non utilizzare le parole chiave riservate come nomi di elementi del programma. Tuttavia, se una versione futura di Visual Basic definisce una nuova parola chiave in conflitto con un modulo esistente o nome del controllo, quindi è possibile utilizzare questa tecnica quando l'aggiornamento del codice per lavorare con la nuova versione.  
  
> [!NOTE]
>  Il programma potrebbe includere anche i nomi degli elementi forniti da altri assembly di riferimento. Se questi nomi sono in conflitto con le parole chiave riservate, quindi inserire le parentesi quadre attorno a esse fa sì che Visual Basic per interpretarli come elementi definiti.  
  
## <a name="see-also"></a>Vedere anche

- [Convenzioni di denominazione di Visual Basic](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)
- [Struttura del programma e convenzioni di scrittura del codice](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)
- [Parole chiave](../../../visual-basic/language-reference/keywords/index.md)
