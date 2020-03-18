---
title: Parametri di metodo - Riferimenti per C#
ms.date: 07/20/2015
helpviewer_keywords:
- methods [C#], parameters
- method parameters [C#]
- parameters [C#]
ms.assetid: 680e39ff-775b-48b0-9f47-4186a5bfc4a1
ms.openlocfilehash: 2cc7f9178fa5c1a040be9d45ba66fac292bb0e28
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75713380"
---
# <a name="method-parameters-c-reference"></a>Parametri di metodo (Riferimenti per C#)

I parametri dichiarati per un metodo senza [in](./in-parameter-modifier.md), [ref](./ref.md) o [out](./out-parameter-modifier.md), vengono passati al metodo chiamato per valore. che può essere modificato all'interno del metodo. Il valore modificato, tuttavia, non verrà mantenuto quando il controllo viene restituito alla routine chiamante. Usando una parola chiave del parametro, è possibile modificare questo comportamento.  
  
 Questa sezione descrive le parole chiave che è possibile usare quando si dichiarano i parametri dei metodi:  
  
- [params](./params.md) specifica che questo parametro può accettare un numero variabile di argomenti.
  
- [in](./in-parameter-modifier.md) specifica che questo parametro viene passato per riferimento ma viene letto solo dal metodo chiamato.
  
- [ref](./ref.md) specifica che questo parametro viene passato per riferimento e può essere letto o scritto dal metodo chiamato.
  
- [out](./out-parameter-modifier.md) specifica che questo parametro viene passato per riferimento e viene scritto dal metodo chiamato.
  
## <a name="see-also"></a>Vedere anche

- [Guida di riferimento a C](../index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [Parole chiave di C#](./index.md)
