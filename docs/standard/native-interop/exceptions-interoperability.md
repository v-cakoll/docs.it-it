---
title: Interoperabilità delle eccezioni
ms.date: 01/16/2020
ms.technology: dotnet-standard
helpviewer_keywords:
- unmanaged code, exceptions
- exceptions, unmanaged code
- interop, exceptions
- exceptions, interop
ms.openlocfilehash: 2aff71e97e1be0dbb584f4fe43c322cea86d2480
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76795175"
---
# <a name="working-with-interop-exceptions-in-unmanaged-code"></a>Utilizzo delle eccezioni di interoperabilità nel codice non gestito

L'interoperabilità delle eccezioni del codice non gestito è supportata solo nelle piattaforme Windows. I problemi di portabilità si verificano su piattaforme non Windows. Poiché l'ABI UNIX non ha alcuna definizione per la gestione delle eccezioni, il codice gestito non è in grado di capire come funzionano i meccanismi delle eccezioni. Pertanto, le eccezioni possono causare comportamenti imprevedibili e arresti anomali.

## <a name="setjmplongjmp-behaviors"></a>Comportamenti setjmp/longjmp

L'interoperabilità con `setjmp` le funzioni C e `longjmp` non è supportata. Non è possibile `longjmp` usare per ignorare i frame gestiti.

Per ulteriori informazioni, vedere la [documentazione di longjmp](https://docs.microsoft.com/cpp/c-runtime-library/reference/longjmp).

## <a name="see-also"></a>Vedi anche

- [Eccezioni](index.md)
- [Interoperabilità con librerie native](https://www.mono-project.com/docs/advanced/pinvoke/#runtime-exception-propagation)
