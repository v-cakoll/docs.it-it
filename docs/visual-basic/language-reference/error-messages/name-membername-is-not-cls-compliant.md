---
title: Il nome <membername> non è conforme a CLS
ms.date: 07/20/2015
f1_keywords:
- bc40031
- vbc40031
helpviewer_keywords:
- BC40031
ms.assetid: e2b885dc-cbf9-49ff-bbbe-531657ea99f7
ms.openlocfilehash: 45c9332237dffc7311daeedaf36035d9e9958415
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84397181"
---
# <a name="name-membername-is-not-cls-compliant"></a>Il nome \<membername> non è conforme a CLS
Un assembly è contrassegnato come `<CLSCompliant(True)>` ma espone un membro con un nome che inizia con un carattere di sottolineatura ( `_` ).  
  
 Un elemento di programmazione può contenere uno o più caratteri di sottolineatura, ma deve essere conforme all' [indipendenza del linguaggio e ai componenti indipendenti dal linguaggio](../../../standard/language-independence-and-language-independent-components.md) (CLS), non deve iniziare con un carattere di sottolineatura. Vedere [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).  
  
 Quando <xref:System.CLSCompliantAttribute> viene applicato a un elemento di programmazione, il parametro `isCompliant` dell'attributo viene impostato su `True` o `False` per indicare la conformità o la non conformità. L'impostazione predefinita per questo parametro non è disponibile, quindi è necessario specificare un valore.  
  
 Se a un elemento non viene applicato <xref:System.CLSCompliantAttribute> , l'elemento non sarà considerato conforme.  
  
 Per impostazione predefinita, si tratta di un messaggio di avviso. Per informazioni su come nascondere gli avvisi o considerarli come errori, vedere [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **ID errore:** BC40031  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
- Se si ha il controllo sul codice sorgente, modificare il nome del membro in modo che non inizi con un carattere di sottolineatura.  
  
- Se è necessario che il nome del membro rimanga invariato, rimuovere <xref:System.CLSCompliantAttribute> dalla relativa definizione o contrassegnarlo come `<CLSCompliant(False)>` . È comunque possibile contrassegnare l'assembly come `<CLSCompliant(True)>` .  
  
## <a name="see-also"></a>Vedere anche

- [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md)
- [Convenzioni di denominazione di Visual Basic](../../programming-guide/program-structure/naming-conventions.md)
