---
title: Differenze tra shadowing e override (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- shadowing, vs. overriding
- overriding, vs. shadowing
ms.assetid: 2d014a0b-7630-407d-8f4e-24bd87987923
ms.openlocfilehash: b935184f0e4d0378bfea69811aa4e6c068a9776f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58827926"
---
# <a name="differences-between-shadowing-and-overriding-visual-basic"></a>Differenze tra shadowing e override (Visual Basic)
Quando si definisce una classe che eredita da una classe base, a volte si desidera ridefinire uno o più degli elementi nella classe derivata della classe base. Shadowing e override sono entrambi disponibili per questo scopo.  
  
## <a name="comparison"></a>Confronto  
 Shadowing e override vengono entrambi utilizzati quando una classe derivata eredita da una classe di base ed entrambi consentono di ridefinire un elemento dichiarato con un altro. Ma esistono differenze significative tra i due.  
  
 La tabella seguente confronta shadowing e override.  
  
||||  
|---|---|---|  
|Punto di confronto|Shadowing|Si esegue l'override|  
|Scopo|Consente di proteggere una successiva modifica della classe di base che introduce un membro che già definito nella classe derivata|Applica il polimorfismo definendo un'implementazione diversa di una routine o proprietà con la stessa sequenza di chiamata<sup>1</sup>|  
|Elemento ridefinito|Qualsiasi tipo di elemento dichiarato|Solo una routine (`Function`, `Sub`, o `Operator`) o una proprietà|  
|La ridefinizione di elemento|Qualsiasi tipo di elemento dichiarato|Solo una routine o proprietà con la sequenza di chiamata identica<sup>1</sup>|  
|Livello di accesso dell'elemento di ridefinizione|Qualsiasi livello di accesso|Non è possibile modificare il livello di accesso dell'elemento sottoposto a override|  
|Lettura e scrittura dell'elemento di ridefinizione|Qualsiasi combinazione|Non è possibile modificare la leggibilità o la scrittura della proprietà sottoposta a override|  
|Controllo sulla ridefinizione|Elemento della classe base non è possibile applicare o vietare shadowing|Elemento della classe base specificabile `MustOverride`, `NotOverridable`, o `Overridable`|  
|Utilizzo di parole chiave|`Shadows` scelta consigliata nella classe derivata. `Shadows` presuppone che se nessuno dei due `Shadows` né `Overrides` specificato<sup>2</sup>|`Overridable` o `MustOverride` necessario nella classe base. `Overrides` necessario nella classe derivata|  
|Ereditarietà dell'elemento di ridefinizione dalle classi che derivano dalla classe derivata|Elemento di shadowing ereditata da altre classi derivate; elemento nascosto ancora nascosta<sup>3</sup>|Elemento viene sottoposto a override ereditata da altre classi derivate; elemento sottoposto a override comunque sottoposto a override|  
  
 <sup>1</sup> il *sequenza di chiamata* costituita dal tipo di elemento (`Function`, `Sub`, `Operator`, o `Property`), nome, l'elenco dei parametri e il tipo restituito. È possibile eseguire l'override di una procedura con una proprietà o viceversa. È possibile eseguire l'override di un tipo di routine (`Function`, `Sub`, o `Operator`) con un altro tipo.  
  
 <sup>2</sup> se non si specificano né `Shadows` o `Overrides`, il compilatore genera un messaggio di avviso che consentono di verificare che il tipo di ridefinizione si desidera utilizzare. Se si ignora l'avviso, viene utilizzato il meccanismo di shadowing.  
  
 <sup>3</sup> se l'elemento di shadowing non è accessibile in una classe derivata ulteriormente, shadowing non è ereditato. Ad esempio, se si dichiara l'elemento di shadowing come `Private`, una classe che deriva dalla classe derivata eredita l'elemento originale anziché l'elemento di shadowing.  
  
## <a name="guidelines"></a>Indicazioni  
 Si usano normalmente viene sottoposto a override nei casi seguenti:  
  
-   Si siano definendo le classi derivate polimorfiche.  
  
-   Quando si desidera che il compilatore di imporre il tipo di elemento identico e una sequenza di chiamata.  
  
 In genere si usano shadowing nei casi seguenti:  
  
-   Si prevede che la classe di base potrebbe essere stata modificata e definisce un elemento con lo stesso nome come quelle in uso.  
  
-   Si desidera che la libertà di modifica del tipo di elemento o sequenza di chiamata.  
  
## <a name="see-also"></a>Vedere anche

- [Riferimenti a elementi dichiarati](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [Shadowing in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
- [Procedura: Nascondere una variabile con lo stesso nome di variabile](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md)
- [Procedura: Nascondere una variabile ereditata](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md)
- [Procedura: Accedere a una variabile nascosta da una classe derivata](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md)
- [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md)
- [Overrides](../../../../visual-basic/language-reference/modifiers/overrides.md)
