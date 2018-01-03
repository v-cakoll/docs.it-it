---
title: "Tipo &lt;typename&gt; non è conforme a CLS"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc40041
- vbc40041
helpviewer_keywords: BC40041
ms.assetid: 634132c2-5646-44aa-98c6-f773e2e63882
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 36a49ccf7d2185c26ef8d23eebea216cc193d951
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/21/2017
---
# <a name="type-lttypenamegt-is-not-cls-compliant"></a>Tipo &lt;typename&gt; non è conforme a CLS
Una funzione, una proprietà o una variabile viene dichiarata con un tipo di dati che non è conforme a CLS.  
  
 Per un'applicazione sia compatibile con il [indipendenza del linguaggio e componenti indipendenti dal linguaggio](../../../standard/language-independence-and-language-independent-components.md) (CLS), è necessario utilizzare solo tipi conformi a CLS.  
  
 I tipi di dati di [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] seguenti non sono compatibili con CLS:  
  
-   [Tipo di dati SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
-   [Tipo di dati UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
-   [Tipo di dati ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
-   [Tipo di dati UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 **ID errore:** BC40041  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Se l'applicazione deve essere conforme a CLS, modificare il tipo di dati di questo elemento per il tipo conforme a CLS più vicino. Al posto di `UInteger` ad esempio può essere possibile usare `Integer` se non è necessario l'intervallo di valore al di sopra di 2.147.483.647. Se è necessario l'intervallo esteso, è possibile sostituire `UInteger` con `Long`.  
  
-   Se l'applicazione non deve essere conforme a CLS, non è necessario apportare alcuna modifica. È necessario essere consapevoli di conformità, tuttavia.