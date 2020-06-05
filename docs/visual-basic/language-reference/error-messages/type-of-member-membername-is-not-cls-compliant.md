---
title: Il tipo di membro "<membername>" non è conforme a CLS
ms.date: 07/20/2015
f1_keywords:
- bc40025
- vbc40025
helpviewer_keywords:
- BC40025
ms.assetid: adbd34bb-43d2-4266-90e7-cd1afaf49b4e
ms.openlocfilehash: 030cb31b8f1ba0e8eaa82eeb8e37153411a53404
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400305"
---
# <a name="type-of-member-membername-is-not-cls-compliant"></a>Il tipo di membro "\<membername>" non è conforme a CLS
Il tipo di dati specificato per questo membro non fa parte dell' [indipendenza del linguaggio e dei componenti indipendenti dal linguaggio](../../../standard/language-independence-and-language-independent-components.md) (CLS). Non si tratta di un errore all'interno del componente, perché il .NET Framework e Visual Basic supportano questo tipo di dati. Tuttavia, un altro componente scritto in codice strettamente conforme a CLS potrebbe non supportare questo tipo di dati. Un componente di questo tipo potrebbe non essere in grado di interagire correttamente con il componente.  
  
 I tipi di dati Visual Basic seguenti non sono conformi a CLS:  
  
- [Tipo di dati SByte](../data-types/sbyte-data-type.md)  
  
- [Tipo di dati UInteger](../data-types/uinteger-data-type.md)  
  
- [Tipo di dati ULong](../data-types/ulong-data-type.md)  
  
- [Tipo di dati UShort](../data-types/ushort-data-type.md)  
  
 Per impostazione predefinita, si tratta di un messaggio di avviso. Per altre informazioni su come nascondere gli avvisi o considerarli come errori, vedere [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **ID errore:** BC40025  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
- Se il componente si interfaccia solo con altri componenti .NET Framework o non si interfaccia con altri componenti, non è necessario apportare alcuna modifica.  
  
- Se si esegue l'interazione con un componente non scritto per il .NET Framework, potrebbe essere possibile determinare, tramite reflection o dalla documentazione, se supporta questo tipo di dati. In tal caso, non è necessario apportare alcuna modifica.  
  
- Se si esegue l'interazione con un componente che non supporta questo tipo di dati, è necessario sostituirlo con il tipo più vicino conforme a CLS. Al posto di `UInteger` ad esempio può essere possibile usare `Integer` se non è necessario l'intervallo di valore al di sopra di 2.147.483.647. Se è necessario l'intervallo esteso, è possibile sostituire `UInteger` con `Long`.  
  
- Se si interagisce con gli oggetti COM o di automazione, tenere presente che alcuni tipi hanno larghezze di dati diverse rispetto all'.NET Framework. Ad esempio, `uint` è spesso a 16 bit in altri ambienti. Se si passa un argomento a 16 bit a tale componente, dichiararlo come `UShort` anziché `UInteger` nel codice gestito del Visual Basic.  
  
## <a name="see-also"></a>Vedere anche

- [Reflection](../../../framework/reflection-and-codedom/reflection.md)
