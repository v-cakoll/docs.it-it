---
title: Parametri di metodo (Riferimenti per C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- methods [C#], parameters
- method parameters [C#]
- parameters [C#]
ms.assetid: 680e39ff-775b-48b0-9f47-4186a5bfc4a1
caps.latest.revision: 8
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 35d96066deb866e02f6bf624121376fe3ae94373
ms.sourcegitcommit: 935d5267c44f9bce801468ef95f44572f1417e8c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/28/2018
---
# <a name="method-parameters-c-reference"></a>Parametri di metodo (Riferimenti per C#)

I parametri dichiarati per un metodo senza [in](../../../csharp/language-reference/keywords/in-parameter-modifier.md), [ref](../../../csharp/language-reference/keywords/ref.md) o [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md), vengono passati al metodo chiamato per valore. che può essere modificato all'interno del metodo. Il valore modificato, tuttavia, non verrà mantenuto quando il controllo viene restituito alla routine chiamante. Usando una parola chiave del parametro, è possibile modificare questo comportamento.  
  
 Questa sezione descrive le parole chiave che è possibile usare quando si dichiarano i parametri dei metodi:  
  
-   [params](../../../csharp/language-reference/keywords/params.md) specifica che questo parametro può accettare un numero variabile di argomenti.
  
-   [in](../../../csharp/language-reference/keywords/in-parameter-modifier.md) specifica che questo parametro viene passato per riferimento ma viene letto solo dal metodo chiamato.
  
-   [ref](../../../csharp/language-reference/keywords/ref.md) specifica che questo parametro viene passato per riferimento e può essere letto o scritto dal metodo chiamato.
  
-   [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md) specifica che questo parametro viene passato per riferimento e viene scritto dal metodo chiamato.
  
## <a name="see-also"></a>Vedere anche  
 [Riferimenti per C#](../../../csharp/language-reference/index.md)  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
 [Parole chiave di C#](../../../csharp/language-reference/keywords/index.md)
