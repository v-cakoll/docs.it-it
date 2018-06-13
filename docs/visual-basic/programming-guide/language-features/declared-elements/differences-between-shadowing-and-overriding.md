---
title: Differenze tra shadowing e override (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- shadowing, vs. overriding
- overriding, vs. shadowing
ms.assetid: 2d014a0b-7630-407d-8f4e-24bd87987923
ms.openlocfilehash: 94ce3e7fe25b7942730e6e89a53654b03d91c42b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33649633"
---
# <a name="differences-between-shadowing-and-overriding-visual-basic"></a>Differenze tra shadowing e override (Visual Basic)
Quando si definisce una classe che eredita da una classe base, a volte si desidera ridefinire uno o più degli elementi nella classe derivata della classe base. Shadowing e override sono entrambi disponibili per questo scopo.  
  
## <a name="comparison"></a>Confronto  
 Shadowing e override vengono entrambi utilizzati quando una classe derivata eredita da una classe di base ed entrambi consentono di ridefinire un elemento dichiarato con un altro. Ma esistono differenze significative tra i due.  
  
 Nella tabella seguente confronta shadowing e override.  
  
||||  
|---|---|---|  
|Punto di confronto|Shadowing|Viene sottoposto a override|  
|Scopo|Consente di proteggere una modifica della classe base successivi che introduce un membro che già definito nella classe derivata|Applica il polimorfismo definendo un'implementazione diversa di una routine o proprietà con la stessa sequenza di chiamata<sup>1</sup>|  
|Elemento ridefinito|Qualsiasi tipo di elemento dichiarato|Solo una routine (`Function`, `Sub`, o `Operator`) o una proprietà|  
|Ridefinizione di elemento|Qualsiasi tipo di elemento dichiarato|Solo una routine o proprietà con la sequenza di chiamata identica<sup>1</sup>|  
|Livello di accesso dell'elemento di ridefinizione|Livello di accesso|Non è possibile modificare il livello di accesso dell'elemento sottoposto a override|  
|Lettura e scrittura dell'elemento di ridefinizione|Qualsiasi combinazione|Non è possibile modificare la lettura o scrittura della proprietà sottoposta a override|  
|Controllare la ridefinizione|Elemento della classe base non può applicare o impedire lo shadowing|Elemento della classe base specificabile `MustOverride`, `NotOverridable`, o `Overridable`|  
|Utilizzo della parola chiave|`Shadows` consigliata nella classe derivata; `Shadows` presuppone che se nessuno dei due `Shadows` né `Overrides` specificato<sup>2</sup>|`Overridable` o `MustOverride` necessario nella classe base. `Overrides` obbligatoria nella classe derivata|  
|Ereditarietà dell'elemento di ridefinizione per le classi che derivano dalla classe derivata|Elemento di shadowing ereditato da altre classi derivate; elemento nascosto rimangono nascosto<sup>3</sup>|Elemento di override ereditato da altre classi derivate; elemento sottoposto a override ancora sottoposto a override|  
  
 <sup>1</sup> il *sequenza di chiamata* costituita dal tipo di elemento (`Function`, `Sub`, `Operator`, o `Property`), nome, l'elenco dei parametri e tipo restituito. È possibile eseguire l'override di una routine con una proprietà o viceversa. È possibile eseguire l'override di un tipo di routine (`Function`, `Sub`, o `Operator`) con un altro tipo.  
  
 <sup>2</sup> se non si specifica `Shadows` o `Overrides`, il compilatore genera un messaggio di avviso che consentono di assicurarsi che il tipo di ridefinizione si desidera utilizzare. Se si ignora il messaggio di avviso, viene utilizzato il meccanismo di shadowing.  
  
 <sup>3</sup> se l'elemento di shadowing sia inaccessibile in una classe derivata ulteriormente, lo shadowing non è ereditato. Ad esempio, se si dichiara l'elemento di shadowing come `Private`, una classe che deriva dalla classe derivata eredita l'elemento originale anziché l'elemento di shadowing.  
  
## <a name="guidelines"></a>Indicazioni  
 È in genere utilizzare viene sottoposto a override nei casi seguenti:  
  
-   Si siano definendo le classi derivate polimorfiche.  
  
-   Quando si desidera applicare il tipo di elemento identici e una sequenza di chiamata del compilatore.  
  
 È in genere utilizzare shadowing nei casi seguenti:  
  
-   Si prevede che la classe di base potrebbe essere stata modificata e definisce un elemento con lo stesso nome come quelle in uso.  
  
-   Si desidera la libertà di modifica del tipo di elemento o sequenza di chiamata.  
  
## <a name="see-also"></a>Vedere anche  
 [Riferimenti a elementi dichiarati](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)  
 [Shadowing in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)  
 [Procedura: nascondere una variabile con lo stesso nome di un'altra variabile](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md)  
 [Procedura: nascondere una variabile ereditata](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md)  
 [Procedura: accedere a una variabile nascosta da una classe derivata](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md)  
 [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md)  
 [Overrides](../../../../visual-basic/language-reference/modifiers/overrides.md)
