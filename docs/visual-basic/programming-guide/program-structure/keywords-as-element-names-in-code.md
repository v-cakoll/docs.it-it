---
title: Parole chiave come nomi di elementi nel codice (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, naming conventions
- keywords [Visual Basic], in code
- name conflicts [Visual Basic]
- element names [Visual Basic], in code
ms.assetid: 2e4e8e02-23f7-49b9-a1c8-2b0402b6b525
ms.openlocfilehash: 53c3172e8518115d001c23be2430fbc87ae1b60f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="keywords-as-element-names-in-code-visual-basic"></a>Parole chiave come nomi di elementi nel codice (Visual Basic)
Qualsiasi elemento del programma, ad esempio una variabile, una classe o membro, può avere lo stesso nome di una parola chiave riservata. Ad esempio, è possibile creare una variabile denominata `Loop`. Tuttavia, per fare riferimento alla versione di esso, che ha lo stesso nome con restrizioni `Loop` (parola chiave), è necessario farlo precedere da una stringa di qualificazione completo o racchiuderlo tra parentesi quadre (`[ ]`), come illustrato nell'esempio seguente.  
  
 [!code-vb[VbVbcnConventions#8](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/keywords-as-element-names-in-code_1.vb)]  
  
 Se questa non uno di questi, Visual Basic si presuppone l'uso dell'intrinseco `Loop` (parola chiave) e genera un errore, come nell'esempio seguente:  
  
 `' The following statement causes a compiler error.`  
  
 `Loop.Visible = True`  
  
 È possibile utilizzare le parentesi quadre quando si fa riferimento al form e controlli e quando si dichiara una variabile o la definizione di una routine con lo stesso nome di una parola chiave riservata. Può essere facile dimenticare di qualificare i nomi o includere le parentesi quadre e pertanto introdurre errori nel codice e rendere più difficile la lettura. Per questo motivo, è consigliabile non utilizzare parole chiave riservate come nomi di elementi del programma. Tuttavia, se una versione futura di Visual Basic definisce una nuova parola chiave in conflitto con un nome di controllo o un modulo esistente, quindi è possibile utilizzare questa tecnica quando si aggiorna il codice per funzionare con la nuova versione.  
  
> [!NOTE]
>  Il programma, inoltre, può includere nomi di elementi forniti da altri assembly a cui viene fatto riferimento. Se questi nomi in conflitto con le parole chiave riservate, quindi se le parentesi quadre attorno a esse, Visual Basic e interpretati come elementi definiti.  
  
## <a name="see-also"></a>Vedere anche  
 [Convenzioni di denominazione di Visual Basic](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)  
 [Struttura del programma e convenzioni di scrittura del codice](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)  
 [Parole chiave](../../../visual-basic/language-reference/keywords/index.md)
