---
title: <membername> non conforme a CLS non consentito in un'interfaccia conforme a CLS
ms.date: 07/20/2015
f1_keywords:
- bc40033
- vbc40033
helpviewer_keywords:
- BC40033
ms.assetid: 060c4b08-798e-40f1-94cf-c05c524f1b8a
ms.openlocfilehash: dbffe2bd196e798b90104aebb74269387660c794
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58840458"
---
# <a name="non-cls-compliant-membername-is-not-allowed-in-a-cls-compliant-interface"></a>Non conforme a CLS \<membername > non è consentita in un'interfaccia conforme a CLS
Una proprietà, routine o evento in un'interfaccia è contrassegnata come `<CLSCompliant(True)>` quando l'interfaccia stessa viene contrassegnata come `<CLSCompliant(False)>` o non è contrassegnata.  
  
 Per un'interfaccia è conforme con la [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS), tutti i relativi membri devono essere conformi.  
  
 Quando <xref:System.CLSCompliantAttribute> viene applicato a un elemento di programmazione, il parametro `isCompliant` dell'attributo viene impostato su `True` o `False` per indicare la conformità o la non conformità. L'impostazione predefinita per questo parametro non è disponibile, quindi è necessario specificare un valore.  
  
 Se a un elemento non viene applicato <xref:System.CLSCompliantAttribute> , l'elemento non sarà considerato conforme.  
  
 Per impostazione predefinita, si tratta di un messaggio di avviso. Per informazioni su come nascondere gli avvisi o considerarli come errori, vedere [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **ID errore:** BC40033  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Se si Richiedi la conformità a CLS ed è possibile accedere al codice sorgente di interfaccia, contrassegnare l'interfaccia come `<CLSCompliant(True)>` se tutti i relativi membri sono conformi.  
  
-   Se necessaria la conformità a CLS e non è possibile controllare il codice sorgente dell'interfaccia, o se non è idonea essere conforme, definire il membro all'interno di un'interfaccia diversa.  
  
-   Se è necessario che il membro rimanga nell'interfaccia corrente, rimuovere il <xref:System.CLSCompliantAttribute> dalla relativa definizione o contrassegnarlo come `<CLSCompliant(False)>`.  
  
## <a name="see-also"></a>Vedere anche

- [Istruzione Interface](../../../visual-basic/language-reference/statements/interface-statement.md)
