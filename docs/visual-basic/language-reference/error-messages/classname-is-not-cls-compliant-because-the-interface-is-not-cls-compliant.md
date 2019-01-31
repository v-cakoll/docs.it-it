---
title: "'<classname>' non è conforme a CLS perché l'interfaccia '<interfacename>' implementata non è conforme a CLS"
ms.date: 07/20/2015
f1_keywords:
- bc40029
- vbc40029
helpviewer_keywords:
- BC40029
ms.assetid: 178452f3-5575-4da0-9d6c-53bcddb6a338
ms.openlocfilehash: 6743a0decebb9711a4e44d09b03fe32f88ff2f72
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55283478"
---
# <a name="classname-is-not-cls-compliant-because-the-interface-interfacename-it-implements-is-not-cls-compliant"></a>'\<NomeClasse >' non è conforme a CLS perché l'interfaccia '\<nomeinterfaccia >' viene implementata non è conforme a CLS
Una classe o interfaccia è contrassegnata come `<CLSCompliant(True)>` quando deriva da o implementa un tipo contrassegnato come `<CLSCompliant(False)>` o non è contrassegnata.  
  
 Per una classe o interfaccia è conforme con la [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS), la gerarchia di ereditarietà deve essere conforme. Ciò significa che ogni tipo da cui eredita, direttamente o indirettamente, deve essere conforme. Analogamente, se una classe implementa una o più interfacce, esse devono essere tutte conformi nelle relative gerarchie di ereditarietà.  
  
 Quando <xref:System.CLSCompliantAttribute> viene applicato a un elemento di programmazione, il parametro `isCompliant` dell'attributo viene impostato su `True` o `False` per indicare la conformità o la non conformità. L'impostazione predefinita per questo parametro non è disponibile, quindi è necessario specificare un valore.  
  
 Se a un elemento non viene applicato <xref:System.CLSCompliantAttribute> , l'elemento non sarà considerato conforme.  
  
 Per impostazione predefinita, si tratta di un messaggio di avviso. Per informazioni su come nascondere gli avvisi o considerarli come errori, vedere [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **ID errore:** BC40029  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Se è necessaria la conformità a CLS, definire il tipo all'interno di uno schema di implementazione o una gerarchia di ereditarietà diversi.  
  
-   Se è necessario che questo tipo resti all'interno dello schema di implementazione o della gerarchia di ereditarietà corrente, rimuovere <xref:System.CLSCompliantAttribute> dalla relativa definizione o contrassegnarlo come `<CLSCompliant(False)>`.  
  
 
