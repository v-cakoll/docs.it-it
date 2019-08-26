---
title: Parametri di metodo - Riferimenti per C#
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- methods [C#], parameters
- method parameters [C#]
- parameters [C#]
ms.assetid: 680e39ff-775b-48b0-9f47-4186a5bfc4a1
ms.openlocfilehash: 4011cbd3bc9306b64df87b1fcde48f1f41df8240
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/19/2019
ms.locfileid: "69602033"
---
# <a name="method-parameters-c-reference"></a>Parametri di metodo (Riferimenti per C#)

I parametri dichiarati per un metodo senza [in](./in-parameter-modifier.md), [ref](./ref.md) o [out](./out-parameter-modifier.md), vengono passati al metodo chiamato per valore. che può essere modificato all'interno del metodo. Il valore modificato, tuttavia, non verrà mantenuto quando il controllo viene restituito alla routine chiamante. Usando una parola chiave del parametro, è possibile modificare questo comportamento.  
  
 Questa sezione descrive le parole chiave che è possibile usare quando si dichiarano i parametri dei metodi:  
  
- [params](./params.md) specifica che questo parametro può accettare un numero variabile di argomenti.
  
- [in](./in-parameter-modifier.md) specifica che questo parametro viene passato per riferimento ma viene letto solo dal metodo chiamato.
  
- [ref](./ref.md) specifica che questo parametro viene passato per riferimento e può essere letto o scritto dal metodo chiamato.
  
- [out](./out-parameter-modifier.md) specifica che questo parametro viene passato per riferimento e viene scritto dal metodo chiamato.
  
## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [Parole chiave di C#](./index.md)
