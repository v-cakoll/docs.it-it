---
title: Le costanti devono essere di tipo intrinseco o enumerato, non di tipo classe, struttura, parametro di tipo o matrice
ms.date: 07/20/2015
f1_keywords:
- vbc30424
- bc30424
helpviewer_keywords:
- BC30424
ms.assetid: 2d402c2f-27ad-428b-b699-d45cd62f7196
ms.openlocfilehash: 88bbab2005b464ee97d647f2b4b9be6ff81e2d82
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59299111"
---
# <a name="constants-must-be-of-an-intrinsic-or-enumerated-type-not-a-class-structure-type-parameter-or-array-type"></a>Le costanti devono essere di tipo intrinseco o enumerato, non di tipo classe, struttura, parametro di tipo o matrice
Si è provato a dichiarare una costante come una classe, struttura o tipo di matrice o come un parametro di tipo definito da un tipo generico che lo contiene.  
  
 Le costanti devono essere di tipo intrinseco (`Boolean`, `Byte`, `Date`, `Decimal`, `Double`, `Integer`, `Long`, `Object`, `SByte`, `Short`, `Single`, `String`, `UInteger`, `ULong`, o `UShort`), o un `Enum` tipo basato su uno dei tipi integrali.  
  
 **ID errore:** BC30424  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1. Dichiarare la costante come funzione intrinseca o `Enum` tipo.  
  
2. Una costante può anche essere, ad esempio un valore speciale `True`, `False`, o `Nothing`. Il compilatore considera i valori predefiniti di tipo intrinseco appropriato.  
  
## <a name="see-also"></a>Vedere anche

- [Costanti ed enumerazioni](../../../visual-basic/language-reference/constants-and-enumerations.md)
- [Tipi di dati](../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [Tipi di dati](../../../visual-basic/language-reference/data-types/index.md)
