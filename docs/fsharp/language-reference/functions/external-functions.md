---
title: Funzioni esterne (F#)
description: 'Scopri il supporto del linguaggio F # per chiamare le funzioni in codice nativo.'
ms.date: 05/16/2016
ms.openlocfilehash: db0d3362d867b07b333951f3380c6735ff471d5e
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/14/2018
ms.locfileid: "45609162"
---
# <a name="external-functions"></a><span data-ttu-id="ce5e0-103">Funzioni esterne</span><span class="sxs-lookup"><span data-stu-id="ce5e0-103">External Functions</span></span>

<span data-ttu-id="ce5e0-104">In questo argomento viene descritto il supporto del linguaggio F # per chiamare le funzioni in codice nativo.</span><span class="sxs-lookup"><span data-stu-id="ce5e0-104">This topic describes F# language support for calling functions in native code.</span></span>

## <a name="syntax"></a><span data-ttu-id="ce5e0-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ce5e0-105">Syntax</span></span>

```fsharp
[<DllImport( arguments )>]
extern declaration
```

## <a name="remarks"></a><span data-ttu-id="ce5e0-106">Note</span><span class="sxs-lookup"><span data-stu-id="ce5e0-106">Remarks</span></span>

<span data-ttu-id="ce5e0-107">Nella sintassi precedente *argomenti* rappresenta gli argomenti forniti per il `System.Runtime.InteropServices.DllImportAttribute` attributo.</span><span class="sxs-lookup"><span data-stu-id="ce5e0-107">In the previous syntax, *arguments* represents arguments that are supplied to the `System.Runtime.InteropServices.DllImportAttribute` attribute.</span></span> <span data-ttu-id="ce5e0-108">Il primo argomento è una stringa che rappresenta il nome della DLL che contiene questa funzione, senza l'estensione dll.</span><span class="sxs-lookup"><span data-stu-id="ce5e0-108">The first argument is a string that represents the name of the DLL that contains this function, without the .dll extension.</span></span> <span data-ttu-id="ce5e0-109">Argomenti aggiuntivi possono essere forniti per qualsiasi proprietà pubblica del `System.Runtime.InteropServices.DllImportAttribute` classe, ad esempio la convenzione di chiamata.</span><span class="sxs-lookup"><span data-stu-id="ce5e0-109">Additional arguments can be supplied for any of the public properties of the `System.Runtime.InteropServices.DllImportAttribute` class, such as the calling convention.</span></span>

<span data-ttu-id="ce5e0-110">Si supponga di che avere una DLL C++ che contiene la seguente funzione esportata nativa.</span><span class="sxs-lookup"><span data-stu-id="ce5e0-110">Assume you have a native C++ DLL that contains the following exported function.</span></span>

```cpp
#include <stdio.h>
extern "C" void __declspec(dllexport) HelloWorld()
{
    printf("Hello world, invoked by F#!\n");
}
```

<span data-ttu-id="ce5e0-111">È possibile chiamare questa funzione da F # usando il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="ce5e0-111">You can call this function from F# by using the following code.</span></span>

```fsharp
open System.Runtime.InteropServices

module InteropWithNative =
    [<DllImport(@"C:\bin\nativedll", CallingConvention = CallingConvention.Cdecl)>]
    extern void HelloWorld()

InteropWithNative.HelloWorld()
```

<span data-ttu-id="ce5e0-112">L'interoperabilità con codice nativo è detta *PInvoke* ed è una funzionalità di CLR.</span><span class="sxs-lookup"><span data-stu-id="ce5e0-112">Interoperability with native code is referred to as *platform invoke* and is a feature of the CLR.</span></span> <span data-ttu-id="ce5e0-113">Per altre informazioni, vedere [Interoperabilità con codice non gestito](../../../../docs/framework/interop/index.md).</span><span class="sxs-lookup"><span data-stu-id="ce5e0-113">For more information, see [Interoperating with Unmanaged Code](../../../../docs/framework/interop/index.md).</span></span> <span data-ttu-id="ce5e0-114">Le informazioni contenute in tale sezione sono applicabile a F #.</span><span class="sxs-lookup"><span data-stu-id="ce5e0-114">The information in that section is applicable to F#.</span></span>

## <a name="see-also"></a><span data-ttu-id="ce5e0-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ce5e0-115">See also</span></span>

- [<span data-ttu-id="ce5e0-116">Funzioni</span><span class="sxs-lookup"><span data-stu-id="ce5e0-116">Functions</span></span>](index.md)
