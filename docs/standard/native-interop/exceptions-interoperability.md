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
# <a name="working-with-interop-exceptions-in-unmanaged-code"></a><span data-ttu-id="3b87d-102">Utilizzo delle eccezioni di interoperabilità nel codice non gestito</span><span class="sxs-lookup"><span data-stu-id="3b87d-102">Working with Interop Exceptions in Unmanaged Code</span></span>

<span data-ttu-id="3b87d-103">L'interoperabilità delle eccezioni del codice non gestito è supportata solo nelle piattaforme Windows.</span><span class="sxs-lookup"><span data-stu-id="3b87d-103">Unmanaged code exception interop is supported on Windows platforms only.</span></span> <span data-ttu-id="3b87d-104">I problemi di portabilità si verificano su piattaforme non Windows.</span><span class="sxs-lookup"><span data-stu-id="3b87d-104">Portability issues arise on non-Windows platforms.</span></span> <span data-ttu-id="3b87d-105">Poiché l'ABI UNIX non ha alcuna definizione per la gestione delle eccezioni, il codice gestito non è in grado di capire come funzionano i meccanismi delle eccezioni.</span><span class="sxs-lookup"><span data-stu-id="3b87d-105">Since the Unix ABI has no definition for exception handling, managed code can't know how exception mechanisms work under the covers.</span></span> <span data-ttu-id="3b87d-106">Pertanto, le eccezioni possono causare comportamenti imprevedibili e arresti anomali.</span><span class="sxs-lookup"><span data-stu-id="3b87d-106">Therefore, exceptions can end up resulting in unpredictable behaviors and crashes.</span></span>

## <a name="setjmplongjmp-behaviors"></a><span data-ttu-id="3b87d-107">Comportamenti setjmp/longjmp</span><span class="sxs-lookup"><span data-stu-id="3b87d-107">Setjmp/Longjmp Behaviors</span></span>

<span data-ttu-id="3b87d-108">L'interoperabilità con funzioni `setjmp` e `longjmp` C non è supportato.</span><span class="sxs-lookup"><span data-stu-id="3b87d-108">Interop with `setjmp` and `longjmp` C functions is not supported.</span></span> <span data-ttu-id="3b87d-109">Non è possibile usare `longjmp` per ignorare i frame gestiti.</span><span class="sxs-lookup"><span data-stu-id="3b87d-109">You can't use `longjmp` to skip over managed frames.</span></span>

<span data-ttu-id="3b87d-110">Per ulteriori informazioni, vedere la [documentazione di longjmp](https://docs.microsoft.com/cpp/c-runtime-library/reference/longjmp).</span><span class="sxs-lookup"><span data-stu-id="3b87d-110">For more information, see [longjmp documentation](https://docs.microsoft.com/cpp/c-runtime-library/reference/longjmp).</span></span>

## <a name="see-also"></a><span data-ttu-id="3b87d-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3b87d-111">See also</span></span>

- [<span data-ttu-id="3b87d-112">Eccezioni</span><span class="sxs-lookup"><span data-stu-id="3b87d-112">Exceptions</span></span>](index.md)
- [<span data-ttu-id="3b87d-113">Interoperabilità con librerie native</span><span class="sxs-lookup"><span data-stu-id="3b87d-113">Interop with Native Libraries</span></span>](https://www.mono-project.com/docs/advanced/pinvoke/#runtime-exception-propagation)
