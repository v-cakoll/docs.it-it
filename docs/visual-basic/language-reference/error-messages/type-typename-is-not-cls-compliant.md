---
title: Il tipo <typename> non è conforme a CLS
ms.date: 07/20/2015
f1_keywords:
- bc40041
- vbc40041
helpviewer_keywords:
- BC40041
ms.assetid: 634132c2-5646-44aa-98c6-f773e2e63882
ms.openlocfilehash: 243f51b3e6c798c82fdbe7b28557c4f96c728bf2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61764374"
---
# <a name="type-typename-is-not-cls-compliant"></a>Tipo \<typename > non è conforme a CLS
Una variabile, proprietà o restituito dalla funzione è dichiarato con un tipo di dati che non è conforme a CLS.  
  
 Per un'applicazione è compatibile con il [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS), è necessario utilizzare solo tipi conformi a CLS.  
  
 I seguenti tipi di dati di Visual Basic non sono conformi a CLS:  
  
- [Tipo di dati SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
- [Tipo di dati UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
- [Tipo di dati ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
- [Tipo di dati UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 **ID errore:** BC40041  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
- Se l'applicazione deve essere conforme a CLS, modificare il tipo di dati di questo elemento di tipo conforme a CLS più vicina. Al posto di `UInteger` ad esempio può essere possibile usare `Integer` se non è necessario l'intervallo di valore al di sopra di 2.147.483.647. Se è necessario l'intervallo esteso, è possibile sostituire `UInteger` con `Long`.  
  
- Se l'applicazione non deve essere conforme a CLS, non occorre apportare alcuna modifica. È consigliabile tenere la non conformità, tuttavia.