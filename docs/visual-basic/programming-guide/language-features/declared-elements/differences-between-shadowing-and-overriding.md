---
title: Differenze tra shadowing e override
ms.date: 07/20/2015
helpviewer_keywords:
- shadowing, vs. overriding
- overriding, vs. shadowing
ms.assetid: 2d014a0b-7630-407d-8f4e-24bd87987923
ms.openlocfilehash: a6ea83fadf18ef3be778e6de31c0eb4e65e74824
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84392870"
---
# <a name="differences-between-shadowing-and-overriding-visual-basic"></a>Differenze tra shadowing e override (Visual Basic)
Quando si definisce una classe che eredita da una classe base, è talvolta necessario ridefinire uno o più elementi della classe di base nella classe derivata. Lo shadowing e l'override sono entrambi disponibili a questo scopo.  
  
## <a name="comparison"></a>Confronto  
 Lo shadowing e l'override vengono entrambi usati quando una classe derivata eredita da una classe di base ed entrambi ridefiniscono un elemento dichiarato con un altro. Tuttavia, esistono differenze significative tra i due.  
  
 La tabella seguente confronta lo shadowing con l'override di.  
  
||||  
|---|---|---|  
|Punto di confronto|Shadowing|Override|  
|Scopo|Protegge da una successiva modifica della classe di base che introduce un membro già definito nella classe derivata|Ottiene il polimorfismo definendo una diversa implementazione di una routine o di una proprietà con la stessa sequenza di chiamata<sup>1</sup>|  
|Elemento ridefinito|Qualsiasi tipo di elemento dichiarato|Solo una routine ( `Function` , `Sub` o `Operator` ) o una proprietà|  
|Ridefinizione dell'elemento|Qualsiasi tipo di elemento dichiarato|Solo una routine o una proprietà con la sequenza di chiamata identica<sup>1</sup>|  
|Livello di accesso dell'elemento di ridefinizione|Qualsiasi livello di accesso|Impossibile modificare il livello di accesso dell'elemento sottoposto a override|  
|Leggibilità e leggibilità dell'elemento di ridefinizione|Qualsiasi combinazione|Impossibile modificare la leggibilità o la leggibilità della proprietà sottoposta a override|  
|Controllo sulla ridefinizione|L'elemento della classe base non può applicare o impedire lo shadowing|L'elemento della classe base può specificare `MustOverride` , `NotOverridable` o`Overridable`|  
|Utilizzo parole chiave|`Shadows`consigliato nella classe derivata; si `Shadows` presuppone se né `Shadows` né `Overrides` specificato<sup>2</sup>|`Overridable`o `MustOverride` obbligatorio nella classe di base; `Overrides` obbligatorio nella classe derivata|  
|Ereditarietà della ridefinizione dell'elemento per classi che derivano dalla classe derivata|Elemento shadowing ereditato da ulteriori classi derivate. elemento ombreggiato ancora nascosto<sup>3</sup>|Override dell'elemento ereditato da ulteriori classi derivate. elemento sottoposto a override ancora sottoposto a override|  
  
 <sup>1</sup> la *sequenza chiamante* è costituita dal tipo di elemento ( `Function` ,, `Sub` `Operator` o `Property` ), dal nome, dall'elenco di parametri e dal tipo restituito. Non è possibile eseguire l'override di una routine con una proprietà o viceversa. Non è possibile eseguire l'override di un tipo di routine ( `Function` , `Sub` o `Operator` ) con un altro tipo.  
  
 <sup>2</sup> se non si specifica né `Shadows` `Overrides` , il compilatore genera un messaggio di avviso che consente di verificare il tipo di ridefinizione che si desidera utilizzare. Se si ignora l'avviso, viene utilizzato il meccanismo di ombreggiatura.  
  
 <sup>3</sup> se l'elemento shadowing non è accessibile in un'altra classe derivata, l'ombreggiatura non viene ereditata. Se, ad esempio, si dichiara l'elemento shadowing come `Private` , una classe che deriva dalla classe derivata eredita l'elemento originale anziché l'elemento shadowing.  
  
## <a name="guidelines"></a>Linee guida  
 Normalmente si usa l'override nei casi seguenti:  
  
- Si definiscono classi derivate polimorfiche.  
  
- Si desidera che il compilatore applichi il tipo di elemento e la sequenza chiamante identici.  
  
 In genere si usa lo shadowing nei casi seguenti:  
  
- Si prevede che la classe di base potrebbe essere modificata e definire un elemento usando lo stesso nome.  
  
- Si desidera la libertà di modificare il tipo di elemento o la sequenza chiamante.  
  
## <a name="see-also"></a>Vedere anche

- [References to Declared Elements](references-to-declared-elements.md)
- [Shadowing in Visual Basic](shadowing.md)
- [Procedura: nascondere una variabile con lo stesso nome di un'altra variabile](how-to-hide-a-variable-with-the-same-name-as-your-variable.md)
- [Procedura: nascondere una variabile ereditata](how-to-hide-an-inherited-variable.md)
- [Procedura: accedere a una variabile nascosta da una classe derivata](how-to-access-a-variable-hidden-by-a-derived-class.md)
- [Shadows](../../../language-reference/modifiers/shadows.md)
- [Override](../../../language-reference/modifiers/overrides.md)
