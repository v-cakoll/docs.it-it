---
title: Parametri di metodo (Riferimenti per C#)
ms.date: 07/20/2015
helpviewer_keywords:
- methods [C#], parameters
- method parameters [C#]
- parameters [C#]
ms.assetid: 680e39ff-775b-48b0-9f47-4186a5bfc4a1
ms.openlocfilehash: 446a5239fa1de8559dea50f7e8b8869aed0297c5
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2018
ms.locfileid: "43390000"
---
# <a name="method-parameters-c-reference"></a>Parametri di metodo (Riferimenti per C#)

I parametri dichiarati per un metodo senza [in](../../../csharp/language-reference/keywords/in-parameter-modifier.md), [ref](../../../csharp/language-reference/keywords/ref.md) o [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md), vengono passati al metodo chiamato per valore. che può essere modificato all'interno del metodo. Il valore modificato, tuttavia, non verrà mantenuto quando il controllo viene restituito alla routine chiamante. Usando una parola chiave del parametro, è possibile modificare questo comportamento.  
  
 Questa sezione descrive le parole chiave che è possibile usare quando si dichiarano i parametri dei metodi:  
  
-   [params](../../../csharp/language-reference/keywords/params.md) specifica che questo parametro può accettare un numero variabile di argomenti.
  
-   [in](../../../csharp/language-reference/keywords/in-parameter-modifier.md) specifica che questo parametro viene passato per riferimento ma viene letto solo dal metodo chiamato.
  
-   [ref](../../../csharp/language-reference/keywords/ref.md) specifica che questo parametro viene passato per riferimento e può essere letto o scritto dal metodo chiamato.
  
-   [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md) specifica che questo parametro viene passato per riferimento e viene scritto dal metodo chiamato.
  
## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../../../csharp/language-reference/index.md)  
- [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
- [Parole chiave di C#](../../../csharp/language-reference/keywords/index.md)
