---
title: Il tipo di parametro '<parametername>' non è conforme a CLS
ms.date: 07/20/2015
f1_keywords:
- vbc40028
- bc40028
helpviewer_keywords:
- BC40028
ms.assetid: dfa1f6f9-bb88-44ad-b85f-149144363d41
ms.openlocfilehash: 1f671b75972642670e28b9e761a8174d02d39c4e
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "65642168"
---
# <a name="type-of-parameter-parametername-is-not-cls-compliant"></a>Tipo del parametro '\<nomeparametro >' non è conforme a CLS
Una procedura è contrassegnata come `<CLSCompliant(True)>` ma viene dichiarato un parametro con un tipo contrassegnato come `<CLSCompliant(False)>`, non è contrassegnata o non può essere utilizzato perché è un tipo non conforme.  
  
 Affinché una procedura risulti compatibile con l'[indipendenza del linguaggio e i componenti indipendenti dal linguaggio](../../../standard/language-independence-and-language-independent-components.md) (CLS), deve usare solo tipi conformi a CLS. Questo scenario si applica ai tipi dei parametri, al tipo restituito e ai tipi di tutte le variabili locali.  
  
 I seguenti tipi di dati di Visual Basic non sono conformi a CLS:  
  
- [Tipo di dati SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
- [Tipo di dati UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
- [Tipo di dati ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
- [Tipo di dati UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 Quando <xref:System.CLSCompliantAttribute> viene applicato a un elemento di programmazione, il parametro `isCompliant` dell'attributo viene impostato su `True` o `False` per indicare la conformità o la non conformità. L'impostazione predefinita per questo parametro non è disponibile, quindi è necessario specificare un valore.  
  
 Se a un elemento non viene applicato <xref:System.CLSCompliantAttribute> , l'elemento non sarà considerato conforme.  
  
 Per impostazione predefinita, si tratta di un messaggio di avviso. Per informazioni su come nascondere gli avvisi o considerarli come errori, vedere [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **ID errore:** BC40028  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
- Se la routine deve accettare un parametro di questo tipo specifico, rimuovere il <xref:System.CLSCompliantAttribute>. La procedura non può essere compatibile con CLS.  
  
- Se la procedura deve essere conforme a CLS, modificare il tipo di questo parametro di tipo conforme a CLS più vicina. Al posto di `UInteger` ad esempio può essere possibile usare `Integer` se non è necessario l'intervallo di valore al di sopra di 2.147.483.647. Se è necessario l'intervallo esteso, è possibile sostituire `UInteger` con `Long`.  
  
- Se si prevede l'interazione con oggetti COM o di automazione, tenere presente che alcuni tipi hanno un'ampiezza di dati diversi in .NET Framework. Ad esempio, `int` è spesso a 16 bit in altri ambienti. Se si accetta un intero a 16 bit da tale componente, dichiararlo come `Short` invece di `Integer` nel codice gestito di Visual Basic.
