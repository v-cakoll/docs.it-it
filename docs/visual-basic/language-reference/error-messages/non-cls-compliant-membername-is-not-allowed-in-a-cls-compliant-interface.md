---
title: <membername> non conforme a CLS non consentito in un'interfaccia conforme a CLS
ms.date: 07/20/2015
f1_keywords:
- bc40033
- vbc40033
helpviewer_keywords:
- BC40033
ms.assetid: 060c4b08-798e-40f1-94cf-c05c524f1b8a
ms.openlocfilehash: e572189b958612bf9527c82ce702df3ab929a23f
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409400"
---
# <a name="non-cls-compliant-membername-is-not-allowed-in-a-cls-compliant-interface"></a>\<membername> non conforme a CLS non consentito in un'interfaccia conforme a CLS
Una proprietà, una routine o un evento in un'interfaccia è contrassegnato come `<CLSCompliant(True)>` quando l'interfaccia stessa è contrassegnata come `<CLSCompliant(False)>` o non è contrassegnata.  
  
 Affinché un'interfaccia sia conforme all'indipendenza del [linguaggio e ai componenti indipendenti dal linguaggio](../../../standard/language-independence-and-language-independent-components.md) , tutti i relativi membri devono essere conformi.  
  
 Quando <xref:System.CLSCompliantAttribute> viene applicato a un elemento di programmazione, il parametro `isCompliant` dell'attributo viene impostato su `True` o `False` per indicare la conformità o la non conformità. L'impostazione predefinita per questo parametro non è disponibile, quindi è necessario specificare un valore.  
  
 Se a un elemento non viene applicato <xref:System.CLSCompliantAttribute> , l'elemento non sarà considerato conforme.  
  
 Per impostazione predefinita, si tratta di un messaggio di avviso. Per informazioni su come nascondere gli avvisi o considerarli come errori, vedere [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **ID errore:** BC40033  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
- Se è necessaria la conformità a CLS e si ha il controllo sul codice sorgente dell'interfaccia, contrassegnare l'interfaccia come `<CLSCompliant(True)>` se tutti i relativi membri fossero conformi.  
  
- Se è necessaria la conformità a CLS e non si ha il controllo sul codice sorgente dell'interfaccia o se non si è idonei per essere conforme, definire questo membro all'interno di un'interfaccia diversa.  
  
- Se è necessario che il membro rimanga all'interno dell'interfaccia corrente, rimuovere <xref:System.CLSCompliantAttribute> dalla relativa definizione o contrassegnarlo come `<CLSCompliant(False)>` .  
  
## <a name="see-also"></a>Vedere anche

- [Istruzione Interface](../statements/interface-statement.md)
