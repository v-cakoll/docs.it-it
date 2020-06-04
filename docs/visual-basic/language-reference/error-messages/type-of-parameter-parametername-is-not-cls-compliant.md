---
title: Il tipo di parametro '<parametername>' non è conforme a CLS
ms.date: 07/20/2015
f1_keywords:
- vbc40028
- bc40028
helpviewer_keywords:
- BC40028
ms.assetid: dfa1f6f9-bb88-44ad-b85f-149144363d41
ms.openlocfilehash: edbcadf271c4ccafc11e5b64eb103a0290976179
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84413014"
---
# <a name="type-of-parameter-parametername-is-not-cls-compliant"></a>Il tipo di parametro '\<parametername>' non è conforme a CLS
Una routine è contrassegnata come `<CLSCompliant(True)>` ma dichiara un parametro con un tipo contrassegnato come `<CLSCompliant(False)>` , non contrassegnato o non qualificato perché è un tipo non conforme.  
  
 Affinché una procedura risulti compatibile con l'[indipendenza del linguaggio e i componenti indipendenti dal linguaggio](../../../standard/language-independence-and-language-independent-components.md) (CLS), deve usare solo tipi conformi a CLS. Questo scenario si applica ai tipi dei parametri, al tipo restituito e ai tipi di tutte le variabili locali.  
  
 I tipi di dati Visual Basic seguenti non sono conformi a CLS:  
  
- [Tipo di dati SByte](../data-types/sbyte-data-type.md)  
  
- [Tipo di dati UInteger](../data-types/uinteger-data-type.md)  
  
- [Tipo di dati ULong](../data-types/ulong-data-type.md)  
  
- [Tipo di dati UShort](../data-types/ushort-data-type.md)  
  
 Quando <xref:System.CLSCompliantAttribute> viene applicato a un elemento di programmazione, il parametro `isCompliant` dell'attributo viene impostato su `True` o `False` per indicare la conformità o la non conformità. L'impostazione predefinita per questo parametro non è disponibile, quindi è necessario specificare un valore.  
  
 Se a un elemento non viene applicato <xref:System.CLSCompliantAttribute> , l'elemento non sarà considerato conforme.  
  
 Per impostazione predefinita, si tratta di un messaggio di avviso. Per informazioni su come nascondere gli avvisi o considerarli come errori, vedere [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **ID errore:** BC40028  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
- Se la routine deve prendere un parametro di questo tipo specifico, rimuovere <xref:System.CLSCompliantAttribute> . La procedura non può essere compatibile con CLS.  
  
- Se la routine deve essere conforme a CLS, modificare il tipo di questo parametro sul tipo conforme a CLS più vicino. Al posto di `UInteger` ad esempio può essere possibile usare `Integer` se non è necessario l'intervallo di valore al di sopra di 2.147.483.647. Se è necessario l'intervallo esteso, è possibile sostituire `UInteger` con `Long`.  
  
- Se si interagisce con gli oggetti COM o di automazione, tenere presente che alcuni tipi hanno larghezze di dati diverse rispetto all'.NET Framework. Ad esempio, `int` è spesso a 16 bit in altri ambienti. Se si accetta un valore integer a 16 bit da tale componente, dichiararlo come `Short` anziché `Integer` nel codice Visual Basic gestito.
