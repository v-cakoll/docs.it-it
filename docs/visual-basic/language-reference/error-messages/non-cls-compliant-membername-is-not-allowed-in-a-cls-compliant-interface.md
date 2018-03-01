---
title: "Non conforme a CLS &lt;membername&gt; non è consentita in un'interfaccia conforme a CLS"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc40033
- vbc40033
helpviewer_keywords:
- BC40033
ms.assetid: 060c4b08-798e-40f1-94cf-c05c524f1b8a
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 74744b89ad72b6fd051f83ba38354d0a277555c8
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/21/2017
---
# <a name="non-cls-compliant-ltmembernamegt-is-not-allowed-in-a-cls-compliant-interface"></a>Non conforme a CLS &lt;membername&gt; non è consentita in un'interfaccia conforme a CLS
Una proprietà, routine o evento in un'interfaccia è contrassegnata come `<CLSCompliant(True)>` quando l'interfaccia stessa viene contrassegnata come `<CLSCompliant(False)>` o non è contrassegnata.  
  
 Per un'interfaccia deve essere compatibile con il [indipendenza del linguaggio e componenti indipendenti dal linguaggio](../../../standard/language-independence-and-language-independent-components.md) (CLS), tutti i relativi membri devono essere conformi.  
  
 Quando <xref:System.CLSCompliantAttribute> viene applicato a un elemento di programmazione, il parametro `isCompliant` dell'attributo viene impostato su `True` o `False` per indicare la conformità o la non conformità. L'impostazione predefinita per questo parametro non è disponibile, quindi è necessario specificare un valore.  
  
 Se a un elemento non viene applicato <xref:System.CLSCompliantAttribute> , l'elemento non sarà considerato conforme.  
  
 Per impostazione predefinita, si tratta di un messaggio di avviso. Per informazioni su come nascondere gli avvisi o considerarli come errori, vedere [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **ID errore:** BC40033  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Se è richiesta la conformità a CLS ed è possibile il codice sorgente dell'interfaccia, contrassegnare l'interfaccia come `<CLSCompliant(True)>` se tutti i relativi membri sono conformi.  
  
-   Se è richiesta la conformità a CLS e non è possibile controllare il codice sorgente dell'interfaccia o se esso non è conforme, definire il membro all'interno di un'interfaccia diversa.  
  
-   Se è necessario mantenere il membro nell'interfaccia corrente, rimuovere il <xref:System.CLSCompliantAttribute> dalla relativa definizione o contrassegnarlo come `<CLSCompliant(False)>`.  
  
## <a name="see-also"></a>Vedere anche  
 [Istruzione Interface](../../../visual-basic/language-reference/statements/interface-statement.md)  
 
