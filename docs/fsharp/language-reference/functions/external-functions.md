---
title: Funzioni esterne (F#)
description: 'Informazioni sul supporto del linguaggio F # per chiamare le funzioni in codice nativo.'
ms.date: 05/16/2016
ms.openlocfilehash: 398697c5e0deab7f8d81ec5198ab1918bd865e13
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33564482"
---
# <a name="external-functions"></a><span data-ttu-id="082cc-103">Funzioni esterne</span><span class="sxs-lookup"><span data-stu-id="082cc-103">External Functions</span></span>

<span data-ttu-id="082cc-104">In questo argomento viene descritto il supporto del linguaggio F # per chiamare le funzioni in codice nativo.</span><span class="sxs-lookup"><span data-stu-id="082cc-104">This topic describes F# language support for calling functions in native code.</span></span>

## <a name="syntax"></a><span data-ttu-id="082cc-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="082cc-105">Syntax</span></span>

```fsharp
[<DllImport( arguments )>]
extern declaration
```

## <a name="remarks"></a><span data-ttu-id="082cc-106">Note</span><span class="sxs-lookup"><span data-stu-id="082cc-106">Remarks</span></span>

<span data-ttu-id="082cc-107">Nella sintassi precedente, *argomenti* rappresenta gli argomenti forniti per il `System.Runtime.InteropServices.DllImportAttribute` attributo.</span><span class="sxs-lookup"><span data-stu-id="082cc-107">In the previous syntax, *arguments* represents arguments that are supplied to the `System.Runtime.InteropServices.DllImportAttribute` attribute.</span></span> <span data-ttu-id="082cc-108">Il primo argomento è una stringa che rappresenta il nome della DLL che contiene questa funzione, senza l'estensione. dll.</span><span class="sxs-lookup"><span data-stu-id="082cc-108">The first argument is a string that represents the name of the DLL that contains this function, without the .dll extension.</span></span> <span data-ttu-id="082cc-109">È possibile fornire argomenti aggiuntivi per le proprietà pubbliche del `System.Runtime.InteropServices.DllImportAttribute` classe, ad esempio la convenzione di chiamata.</span><span class="sxs-lookup"><span data-stu-id="082cc-109">Additional arguments can be supplied for any of the public properties of the `System.Runtime.InteropServices.DllImportAttribute` class, such as the calling convention.</span></span>

<span data-ttu-id="082cc-110">Si supponga di che disporre di una DLL di C++ che contiene la seguente funzione esportata nativa.</span><span class="sxs-lookup"><span data-stu-id="082cc-110">Assume you have a native C++ DLL that contains the following exported function.</span></span>

```cpp
#include <stdio.h>
extern "C" void __declspec(dllexport) HelloWorld()
{
    printf("Hello world, invoked by F#!\n");
}
```

<span data-ttu-id="082cc-111">È possibile chiamare questa funzione da F # utilizzando il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="082cc-111">You can call this function from F# by using the following code.</span></span>

```fsharp
open System.Runtime.InteropServices

module InteropWithNative =
    [<DllImport(@"C:\bin\nativedll", CallingConvention = CallingConvention.Cdecl)>]
    extern void HelloWorld()

InteropWithNative.HelloWorld()
```

<span data-ttu-id="082cc-112">Interoperabilità con codice nativo è detto *PInvoke* ed è una funzionalità di Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="082cc-112">Interoperability with native code is referred to as *platform invoke* and is a feature of the CLR.</span></span> <span data-ttu-id="082cc-113">Per altre informazioni, vedere [Interoperabilità con codice non gestito](../../../../docs/framework/interop/index.md).</span><span class="sxs-lookup"><span data-stu-id="082cc-113">For more information, see [Interoperating with Unmanaged Code](../../../../docs/framework/interop/index.md).</span></span> <span data-ttu-id="082cc-114">Le informazioni contenute in tale sezione sono applicabile a F #.</span><span class="sxs-lookup"><span data-stu-id="082cc-114">The information in that section is applicable to F#.</span></span>


## <a name="see-also"></a><span data-ttu-id="082cc-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="082cc-115">See Also</span></span>

[<span data-ttu-id="082cc-116">Funzioni</span><span class="sxs-lookup"><span data-stu-id="082cc-116">Functions</span></span>](index.md)
