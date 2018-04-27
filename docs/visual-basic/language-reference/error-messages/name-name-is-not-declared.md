---
title: Nome &#39; &lt;nome&gt; &#39; non è dichiarato
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30451
- vbc30451
helpviewer_keywords:
- BC30451
ms.assetid: 765f099b-e21e-47c6-a906-a065444e56b3
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 26245952a2dc5341dedba6c497c47773b882b49b
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="name-39ltnamegt39-is-not-declared"></a>Nome &#39; &lt;nome&gt; &#39; non è dichiarato
Un'istruzione fa riferimento a un elemento di programmazione, ma il compilatore non trova un elemento con quel nome esatto.  
  
 **ID errore:** BC30451  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1.  Controllare l'ortografia del nome nell'istruzione di riferimento. Visual Basic è tra maiuscole e minuscole, ma qualsiasi altra variazione nell'ortografia verrà considerata come un nome completamente diverso. Si noti che il carattere di sottolineatura (`_`) fa parte del nome e quindi dell'ortografia.  
  
2.  Verificare di avere l'operatore di accesso ai membri (`.`) tra un oggetto e il relativo membro. Ad esempio, se è presente un controllo <xref:System.Windows.Forms.TextBox> denominato `TextBox1`, per accedere alla relativa proprietà <xref:System.Windows.Forms.TextBoxBase.Text%2A> occorre digitare `TextBox1.Text`. Se invece si digita `TextBox1Text`, viene creato un nome diverso.  
  
3.  Se l'ortografia e la sintassi di accesso ai membri qualsiasi oggetto sia corretta, verificare che l'elemento è stato dichiarato. Per ulteriori informazioni, vedere [elementi dichiarati](../../../visual-basic/programming-guide/language-features/declared-elements/index.md).  
  
4.  Se è stato dichiarato l'elemento di programmazione, controllare che si trova nell'ambito. Se l'istruzione che fa riferimento è di fuori dell'area di dichiarazione di elemento di programmazione, è necessario qualificare il nome dell'elemento. Per ulteriori informazioni, vedere [ambito in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/scope.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Riepilogo delle dichiarazioni e delle costanti](../../../visual-basic/language-reference/keywords/declarations-and-constants-summary.md)  
 [Convenzioni di denominazione di Visual Basic](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)  
 [Nomi di elementi dichiarati](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)  
 [Riferimenti a elementi dichiarati](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
