---
title: Le costanti devono essere di tipo intrinseco o enumerato, non di tipo classe, struttura, parametro di tipo o matrice
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30424
- bc30424
helpviewer_keywords: BC30424
ms.assetid: 2d402c2f-27ad-428b-b699-d45cd62f7196
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 702472751810c2d2bd08ece944ef0ffafc2049b5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="constants-must-be-of-an-intrinsic-or-enumerated-type-not-a-class-structure-type-parameter-or-array-type"></a>Le costanti devono essere di tipo intrinseco o enumerato, non di tipo classe, struttura, parametro di tipo o matrice
Si è provato a dichiarare una costante come una classe, struttura o tipo di matrice o come un parametro di tipo definito da un tipo generico contenitore.  
  
 Le costanti devono essere di tipo intrinseco (`Boolean`, `Byte`, `Date`, `Decimal`, `Double`, `Integer`, `Long`, `Object`, `SByte`, `Short`, `Single`, `String`, `UInteger`, `ULong`, o `UShort`), o un `Enum` tipo basato su uno dei tipi integrali.  
  
 **ID errore:** BC30424  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1.  Dichiarare la costante come funzione intrinseca o `Enum` tipo.  
  
2.  Una costante può anche essere un valore speciale, ad esempio `True`, `False`, o `Nothing`. Il compilatore considera questi valori predefiniti per essere di tipo intrinseco appropriato.  
  
## <a name="see-also"></a>Vedere anche  
 [Costanti ed enumerazioni](../../../visual-basic/language-reference/constants-and-enumerations.md)  
 [Tipi di dati](../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [Tipi di dati](../../../visual-basic/language-reference/data-types/data-type-summary.md)
