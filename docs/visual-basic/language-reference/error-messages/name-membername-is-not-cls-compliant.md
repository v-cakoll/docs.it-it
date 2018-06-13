---
title: Nome &lt;membername&gt; non è conforme a CLS
ms.date: 07/20/2015
f1_keywords:
- bc40031
- vbc40031
helpviewer_keywords:
- BC40031
ms.assetid: e2b885dc-cbf9-49ff-bbbe-531657ea99f7
ms.openlocfilehash: 26ff13de461d5a96724868b7928129a326cdf1d0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33593342"
---
# <a name="name-ltmembernamegt-is-not-cls-compliant"></a>Nome &lt;membername&gt; non è conforme a CLS
Un assembly è contrassegnato come `<CLSCompliant(True)>` ma espone un membro con un nome che inizia con un carattere di sottolineatura (`_`).  
  
 Un elemento di programmazione può contenere uno o più caratteri di sottolineatura, ma to deve essere compatibile con il [indipendenza del linguaggio e componenti indipendenti dal linguaggio](../../../standard/language-independence-and-language-independent-components.md) (CLS), non può iniziare con un carattere di sottolineatura. Vedere [nomi di elementi dichiarati](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
 Quando <xref:System.CLSCompliantAttribute> viene applicato a un elemento di programmazione, il parametro `isCompliant` dell'attributo viene impostato su `True` o `False` per indicare la conformità o la non conformità. L'impostazione predefinita per questo parametro non è disponibile, quindi è necessario specificare un valore.  
  
 Se a un elemento non viene applicato <xref:System.CLSCompliantAttribute> , l'elemento non sarà considerato conforme.  
  
 Per impostazione predefinita, si tratta di un messaggio di avviso. Per informazioni su come nascondere gli avvisi o considerarli come errori, vedere [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **ID errore:** BC40031  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Se si dispone di codice sorgente, modificare il nome del membro in modo che non inizia con un carattere di sottolineatura.  
  
-   Se è necessario che il nome del membro rimangono invariati, rimuovere il <xref:System.CLSCompliantAttribute> dalla relativa definizione o contrassegnarlo come `<CLSCompliant(False)>`. È comunque possibile contrassegnare l'assembly come `<CLSCompliant(True)>`.  
  
## <a name="see-also"></a>Vedere anche  
 [Nomi di elementi dichiarati](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)  
 [Convenzioni di denominazione di Visual Basic](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)  

