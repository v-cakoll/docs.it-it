---
title: Il tipo restituito della funzione '<procedurename>' non è conforme a CLS
ms.date: 07/20/2015
f1_keywords:
- bc40027
- vbc40027
helpviewer_keywords:
- BC40027
ms.assetid: 33c088c7-48e7-400c-920e-6d8967e1f3fc
ms.openlocfilehash: 9cc7e25ef1be21ff2f6a71dcb61bc29ec92da30f
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400357"
---
# <a name="return-type-of-function-procedurename-is-not-cls-compliant"></a>Il tipo restituito della funzione '\<procedurename>' non è conforme a CLS
Una `Function` routine è contrassegnata come `<CLSCompliant(True)>` , ma restituisce un tipo contrassegnato come `<CLSCompliant(False)>` , non contrassegnato o non qualificato perché è un tipo non conforme.  
  
 Affinché una procedura risulti compatibile con l'[indipendenza del linguaggio e i componenti indipendenti dal linguaggio](../../../standard/language-independence-and-language-independent-components.md) (CLS), deve usare solo tipi conformi a CLS. Questo scenario si applica ai tipi dei parametri, al tipo restituito e ai tipi di tutte le variabili locali.  
  
 I tipi di dati Visual Basic seguenti non sono conformi a CLS:  
  
- [Tipo di dati SByte](../data-types/sbyte-data-type.md)  
  
- [Tipo di dati UInteger](../data-types/uinteger-data-type.md)  
  
- [Tipo di dati ULong](../data-types/ulong-data-type.md)  
  
- [Tipo di dati UShort](../data-types/ushort-data-type.md)  
  
 Quando <xref:System.CLSCompliantAttribute> viene applicato a un elemento di programmazione, il parametro `isCompliant` dell'attributo viene impostato su `True` o `False` per indicare la conformità o la non conformità. L'impostazione predefinita per questo parametro non è disponibile, quindi è necessario specificare un valore.  
  
 Se a un elemento non viene applicato <xref:System.CLSCompliantAttribute> , l'elemento non sarà considerato conforme.  
  
 Per impostazione predefinita, si tratta di un messaggio di avviso. Per informazioni su come nascondere gli avvisi o considerarli come errori, vedere [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **ID errore:** BC40027  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
- Se la `Function` routine deve restituire questo particolare tipo, rimuovere <xref:System.CLSCompliantAttribute> . La procedura non può essere compatibile con CLS.  
  
- Se la `Function` routine deve essere conforme a CLS, impostare il tipo restituito sul tipo conforme a CLS più vicino. Al posto di `UInteger` ad esempio può essere possibile usare `Integer` se non è necessario l'intervallo di valore al di sopra di 2.147.483.647. Se è necessario l'intervallo esteso, è possibile sostituire `UInteger` con `Long`.  
  
- Se si interagisce con gli oggetti COM o di automazione, tenere presente che alcuni tipi hanno larghezze di dati diverse rispetto all'.NET Framework. Ad esempio, `int` è spesso a 16 bit in altri ambienti. Se si sta restituendo un intero a 16 bit a tale componente, dichiararlo come `Short` anziché `Integer` nel codice Visual Basic gestito.
