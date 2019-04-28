---
title: Funzioni esterne
description: Scopri la F# supporto del linguaggio per chiamare le funzioni in codice nativo.
ms.date: 05/16/2016
ms.openlocfilehash: 86ea78844fb812361233f8360c377465d83be203
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61934628"
---
# <a name="external-functions"></a><span data-ttu-id="bed94-103">Funzioni esterne</span><span class="sxs-lookup"><span data-stu-id="bed94-103">External Functions</span></span>

<span data-ttu-id="bed94-104">Questo argomento viene descritto F# supporto del linguaggio per chiamare le funzioni in codice nativo.</span><span class="sxs-lookup"><span data-stu-id="bed94-104">This topic describes F# language support for calling functions in native code.</span></span>

## <a name="syntax"></a><span data-ttu-id="bed94-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bed94-105">Syntax</span></span>

```fsharp
[<DllImport( arguments )>]
extern declaration
```

## <a name="remarks"></a><span data-ttu-id="bed94-106">Note</span><span class="sxs-lookup"><span data-stu-id="bed94-106">Remarks</span></span>

<span data-ttu-id="bed94-107">Nella sintassi precedente *argomenti* rappresenta gli argomenti forniti per il `System.Runtime.InteropServices.DllImportAttribute` attributo.</span><span class="sxs-lookup"><span data-stu-id="bed94-107">In the previous syntax, *arguments* represents arguments that are supplied to the `System.Runtime.InteropServices.DllImportAttribute` attribute.</span></span> <span data-ttu-id="bed94-108">Il primo argomento è una stringa che rappresenta il nome della DLL che contiene questa funzione, senza l'estensione dll.</span><span class="sxs-lookup"><span data-stu-id="bed94-108">The first argument is a string that represents the name of the DLL that contains this function, without the .dll extension.</span></span> <span data-ttu-id="bed94-109">Argomenti aggiuntivi possono essere forniti per qualsiasi proprietà pubblica del `System.Runtime.InteropServices.DllImportAttribute` classe, ad esempio la convenzione di chiamata.</span><span class="sxs-lookup"><span data-stu-id="bed94-109">Additional arguments can be supplied for any of the public properties of the `System.Runtime.InteropServices.DllImportAttribute` class, such as the calling convention.</span></span>

<span data-ttu-id="bed94-110">Si supponga di che avere una DLL C++ che contiene la seguente funzione esportata nativa.</span><span class="sxs-lookup"><span data-stu-id="bed94-110">Assume you have a native C++ DLL that contains the following exported function.</span></span>

```cpp
#include <stdio.h>
extern "C" void __declspec(dllexport) HelloWorld()
{
    printf("Hello world, invoked by F#!\n");
}
```

<span data-ttu-id="bed94-111">È possibile chiamare questa funzione da F# usando il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="bed94-111">You can call this function from F# by using the following code.</span></span>

```fsharp
open System.Runtime.InteropServices

module InteropWithNative =
    [<DllImport(@"C:\bin\nativedll", CallingConvention = CallingConvention.Cdecl)>]
    extern void HelloWorld()

InteropWithNative.HelloWorld()
```

<span data-ttu-id="bed94-112">L'interoperabilità con codice nativo è detta *PInvoke* ed è una funzionalità di CLR.</span><span class="sxs-lookup"><span data-stu-id="bed94-112">Interoperability with native code is referred to as *platform invoke* and is a feature of the CLR.</span></span> <span data-ttu-id="bed94-113">Per altre informazioni, vedere [Interoperabilità con codice non gestito](../../../../docs/framework/interop/index.md).</span><span class="sxs-lookup"><span data-stu-id="bed94-113">For more information, see [Interoperating with Unmanaged Code](../../../../docs/framework/interop/index.md).</span></span> <span data-ttu-id="bed94-114">Le informazioni contenute in tale sezione sono applicabile a F#.</span><span class="sxs-lookup"><span data-stu-id="bed94-114">The information in that section is applicable to F#.</span></span>

## <a name="see-also"></a><span data-ttu-id="bed94-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bed94-115">See also</span></span>

- [<span data-ttu-id="bed94-116">Funzioni</span><span class="sxs-lookup"><span data-stu-id="bed94-116">Functions</span></span>](index.md)