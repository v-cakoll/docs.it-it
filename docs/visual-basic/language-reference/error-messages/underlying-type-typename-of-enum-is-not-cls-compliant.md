---
title: Il tipo sottostante <typename> di Enum non è conforme a CLS
ms.date: 07/20/2015
f1_keywords:
- vbc40032
- bc40032
helpviewer_keywords:
- BC40032
ms.assetid: 32bf1949-fd73-456c-a323-bf1ffe1320ed
ms.openlocfilehash: 636fcc36e7bac52467998dc9c59f14ba1bedead3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61774881"
---
# <a name="underlying-type-typename-of-enum-is-not-cls-compliant"></a>Il tipo sottostante \<typename > dell'enumerazione non è conforme a CLS
Il tipo di dati specificato per questa enumerazione non è in parte i [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS). Non si tratta di un errore all'interno del componente, perché il [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] e Visual Basic supporta questo tipo di dati. Tuttavia, un altro componente scritto in codice strettamente conforme a CLS potrebbe non supportare questo tipo di dati. Un componente di questo tipo potrebbe non essere in grado di interagire correttamente con il componente.  
  
 I seguenti tipi di dati di Visual Basic non sono conformi a CLS:  
  
- [Tipo di dati SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
- [Tipo di dati UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
- [Tipo di dati ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
- [Tipo di dati UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 Per impostazione predefinita, si tratta di un messaggio di avviso. Per altre informazioni su come nascondere gli avvisi o considerarli come errori, vedere [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **ID errore:** BC40032  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
- Se il componente interagisce solo con altri [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] componenti o non si interfaccia con altri componenti, non è necessario apportare alcuna modifica.  
  
- Se si prevede l'interazione con un componente non scritto per il [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)], potrebbe essere in grado di determinare, tramite reflection o nella documentazione, che supporta questo tipo di dati. In caso affermativo, non occorre apportare alcuna modifica.  
  
- Se si prevede l'interazione con un componente che non supporta questo tipo di dati, è necessario sostituirlo con il tipo compatibile con CLS più vicino. Al posto di `UInteger` ad esempio può essere possibile usare `Integer` se non è necessario l'intervallo di valore al di sopra di 2.147.483.647. Se è necessario l'intervallo esteso, è possibile sostituire `UInteger` con `Long`.  
  
- Se si prevede l'interazione con gli oggetti COM o di automazione, tenere presente che alcuni tipi hanno un'ampiezza di dati diversa da [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]. Ad esempio, `uint` è spesso a 16 bit in altri ambienti. Se si passa un argomento a 16 bit a un componente, dichiararlo come `UShort` invece di `UInteger` nel codice gestito di Visual Basic.  
  
## <a name="see-also"></a>Vedere anche

- [Reflection (Visual Basic)](../../programming-guide/concepts/reflection.md)
- [Reflection](../../../framework/reflection-and-codedom/reflection.md)
