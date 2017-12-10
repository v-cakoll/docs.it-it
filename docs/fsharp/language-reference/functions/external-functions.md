---
title: Funzioni esterne (F#)
description: 'Informazioni sul supporto del linguaggio F # per chiamare le funzioni in codice nativo.'
keywords: visual f#, f#, programmazione funzionale
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: c26b6124-ceaa-471c-9dc9-861b4dfa332a
ms.openlocfilehash: 69b73983a91bc6c7cc38fa34484a3c89fc01858f
ms.sourcegitcommit: 685143b62385500f59bc36274b8adb191f573a16
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2017
---
# <a name="external-functions"></a><span data-ttu-id="4326c-104">Funzioni esterne</span><span class="sxs-lookup"><span data-stu-id="4326c-104">External Functions</span></span>

<span data-ttu-id="4326c-105">In questo argomento viene descritto il supporto del linguaggio F # per chiamare le funzioni in codice nativo.</span><span class="sxs-lookup"><span data-stu-id="4326c-105">This topic describes F# language support for calling functions in native code.</span></span>

## <a name="syntax"></a><span data-ttu-id="4326c-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4326c-106">Syntax</span></span>

```fsharp
[<DllImport( arguments )>]
extern declaration
```

## <a name="remarks"></a><span data-ttu-id="4326c-107">Note</span><span class="sxs-lookup"><span data-stu-id="4326c-107">Remarks</span></span>

<span data-ttu-id="4326c-108">Nella sintassi precedente, *argomenti* rappresenta gli argomenti forniti per il `System.Runtime.InteropServices.DllImportAttribute` attributo.</span><span class="sxs-lookup"><span data-stu-id="4326c-108">In the previous syntax, *arguments* represents arguments that are supplied to the `System.Runtime.InteropServices.DllImportAttribute` attribute.</span></span> <span data-ttu-id="4326c-109">Il primo argomento è una stringa che rappresenta il nome della DLL che contiene questa funzione, senza l'estensione. dll.</span><span class="sxs-lookup"><span data-stu-id="4326c-109">The first argument is a string that represents the name of the DLL that contains this function, without the .dll extension.</span></span> <span data-ttu-id="4326c-110">È possibile fornire argomenti aggiuntivi per le proprietà pubbliche del `System.Runtime.InteropServices.DllImportAttribute` classe, ad esempio la convenzione di chiamata.</span><span class="sxs-lookup"><span data-stu-id="4326c-110">Additional arguments can be supplied for any of the public properties of the `System.Runtime.InteropServices.DllImportAttribute` class, such as the calling convention.</span></span>

<span data-ttu-id="4326c-111">Si supponga di che disporre di una DLL di C++ che contiene la seguente funzione esportata nativa.</span><span class="sxs-lookup"><span data-stu-id="4326c-111">Assume you have a native C++ DLL that contains the following exported function.</span></span>

```cpp
#include <stdio.h>
extern "C" void __declspec(dllexport) HelloWorld()
{
    printf("Hello world, invoked by F#!\n");
}
```

<span data-ttu-id="4326c-112">È possibile chiamare questa funzione da F # utilizzando il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="4326c-112">You can call this function from F# by using the following code.</span></span>

```fsharp
open System.Runtime.InteropServices

module InteropWithNative =
    [<DllImport(@"C:\bin\nativedll", CallingConvention = CallingConvention.Cdecl)>]
    extern void HelloWorld()

InteropWithNative.HelloWorld()
```

<span data-ttu-id="4326c-113">Interoperabilità con codice nativo è detto *PInvoke* ed è una funzionalità di Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="4326c-113">Interoperability with native code is referred to as *platform invoke* and is a feature of the CLR.</span></span> <span data-ttu-id="4326c-114">Per altre informazioni, vedere [Interoperabilità con codice non gestito](../../../../docs/framework/interop/index.md).</span><span class="sxs-lookup"><span data-stu-id="4326c-114">For more information, see [Interoperating with Unmanaged Code](../../../../docs/framework/interop/index.md).</span></span> <span data-ttu-id="4326c-115">Le informazioni contenute in tale sezione sono applicabile a F #.</span><span class="sxs-lookup"><span data-stu-id="4326c-115">The information in that section is applicable to F#.</span></span>


## <a name="see-also"></a><span data-ttu-id="4326c-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4326c-116">See Also</span></span>

[<span data-ttu-id="4326c-117">Funzioni</span><span class="sxs-lookup"><span data-stu-id="4326c-117">Functions</span></span>](index.md)
