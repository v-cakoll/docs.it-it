---
title: Parole chiave come nomi di elementi nel codice (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Visual Basic code, naming conventions
- keywords [Visual Basic], in code
- name conflicts [Visual Basic]
- element names [Visual Basic], in code
ms.assetid: 2e4e8e02-23f7-49b9-a1c8-2b0402b6b525
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f410a0eaac0dcc034d406a89ed1d01a8f228a583
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
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
