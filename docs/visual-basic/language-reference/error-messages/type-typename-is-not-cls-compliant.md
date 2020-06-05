---
title: Il tipo <typename> non è conforme a CLS
ms.date: 07/20/2015
f1_keywords:
- bc40041
- vbc40041
helpviewer_keywords:
- BC40041
ms.assetid: 634132c2-5646-44aa-98c6-f773e2e63882
ms.openlocfilehash: eacf5036ebc6fc31dfa0e8de39c4fb574c9072b3
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84386958"
---
# <a name="type-typename-is-not-cls-compliant"></a>Il tipo \<typename> non è conforme a CLS
Una variabile, una proprietà o una funzione restituita è dichiarata con un tipo di dati che non è conforme a CLS.  
  
 Affinché un'applicazione sia compatibile con l'indipendenza del [linguaggio e i componenti indipendenti dal linguaggio](../../../standard/language-independence-and-language-independent-components.md) (CLS), deve utilizzare solo tipi conformi a CLS.  
  
 I tipi di dati Visual Basic seguenti non sono conformi a CLS:  
  
- [Tipo di dati SByte](../data-types/sbyte-data-type.md)  
  
- [Tipo di dati UInteger](../data-types/uinteger-data-type.md)  
  
- [Tipo di dati ULong](../data-types/ulong-data-type.md)  
  
- [Tipo di dati UShort](../data-types/ushort-data-type.md)  
  
 **ID errore:** BC40041  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
- Se l'applicazione deve essere conforme a CLS, modificare il tipo di dati di questo elemento sul tipo conforme a CLS più vicino. Al posto di `UInteger` ad esempio può essere possibile usare `Integer` se non è necessario l'intervallo di valore al di sopra di 2.147.483.647. Se è necessario l'intervallo esteso, è possibile sostituire `UInteger` con `Long`.  
  
- Se non è necessario che l'applicazione sia conforme a CLS, non è necessario apportare alcuna modifica. È tuttavia necessario tenere presente la relativa non conformità.
