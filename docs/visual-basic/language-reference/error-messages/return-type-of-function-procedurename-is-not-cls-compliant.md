---
title: Tipo restituito della funzione &#39; &lt;nomeroutine&gt; &#39; non è conforme a CLS
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc40027
- vbc40027
helpviewer_keywords:
- BC40027
ms.assetid: 33c088c7-48e7-400c-920e-6d8967e1f3fc
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3b3aa178ec3a33d7edb64190d7c83d3b51483feb
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="return-type-of-function-39ltprocedurenamegt39-is-not-cls-compliant"></a>Tipo restituito della funzione &#39; &lt;nomeroutine&gt; &#39; non è conforme a CLS
Oggetto `Function` routine contrassegnata come `<CLSCompliant(True)>` ma restituisce un tipo contrassegnato come `<CLSCompliant(False)>`, non è contrassegnata o non si qualifica in quanto è un tipo non conforme.  
  
 Affinché una procedura risulti compatibile con l'[indipendenza del linguaggio e i componenti indipendenti dal linguaggio](../../../standard/language-independence-and-language-independent-components.md) (CLS), deve usare solo tipi conformi a CLS. Questo scenario si applica ai tipi dei parametri, al tipo restituito e ai tipi di tutte le variabili locali.  
  
 I seguenti tipi di dati Visual Basic non sono conformi a CLS:  
  
-   [Tipo di dati SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
-   [Tipo di dati UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
-   [Tipo di dati ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
-   [Tipo di dati UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 Quando <xref:System.CLSCompliantAttribute> viene applicato a un elemento di programmazione, il parametro `isCompliant` dell'attributo viene impostato su `True` o `False` per indicare la conformità o la non conformità. L'impostazione predefinita per questo parametro non è disponibile, quindi è necessario specificare un valore.  
  
 Se a un elemento non viene applicato <xref:System.CLSCompliantAttribute> , l'elemento non sarà considerato conforme.  
  
 Per impostazione predefinita, si tratta di un messaggio di avviso. Per informazioni su come nascondere gli avvisi o considerarli come errori, vedere [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **ID errore:** BC40027  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Se il `Function` procedure deve restituire questo particolare tipo, rimuovere il <xref:System.CLSCompliantAttribute>. La procedura non può essere compatibile con CLS.  
  
-   Se il `Function` procedura deve essere conforme a CLS, modificare il tipo restituito per il tipo conforme a CLS più vicino. Al posto di `UInteger` ad esempio può essere possibile usare `Integer` se non è necessario l'intervallo di valore al di sopra di 2.147.483.647. Se è necessario l'intervallo esteso, è possibile sostituire `UInteger` con `Long`.  
  
-   Se si prevede l'interazione con gli oggetti COM o di automazione, tenere presente che alcuni tipi hanno un'ampiezza di dati diversa da [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]. Ad esempio, `int` è spesso a 16 bit in altri ambienti. Se viene restituito un integer a 16 bit a un componente di questo tipo, dichiararla `Short` invece di `Integer` nel codice gestito di Visual Basic.