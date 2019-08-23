---
title: Funzioni esterne
description: Informazioni sul supporto F# del linguaggio per la chiamata di funzioni in codice nativo.
ms.date: 05/16/2016
ms.openlocfilehash: 3c8edaba25e07b6ca2c44a58c4b55dc98a13b4fc
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69968725"
---
# <a name="external-functions"></a><span data-ttu-id="28da1-103">Funzioni esterne</span><span class="sxs-lookup"><span data-stu-id="28da1-103">External Functions</span></span>

<span data-ttu-id="28da1-104">Questo argomento descrive F# il supporto del linguaggio per chiamare le funzioni in codice nativo.</span><span class="sxs-lookup"><span data-stu-id="28da1-104">This topic describes F# language support for calling functions in native code.</span></span>

## <a name="syntax"></a><span data-ttu-id="28da1-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="28da1-105">Syntax</span></span>

```fsharp
[<DllImport( arguments )>]
extern declaration
```

## <a name="remarks"></a><span data-ttu-id="28da1-106">Note</span><span class="sxs-lookup"><span data-stu-id="28da1-106">Remarks</span></span>

<span data-ttu-id="28da1-107">Nella sintassi precedente gli *argomenti* rappresentano gli argomenti forniti all' `System.Runtime.InteropServices.DllImportAttribute` attributo.</span><span class="sxs-lookup"><span data-stu-id="28da1-107">In the previous syntax, *arguments* represents arguments that are supplied to the `System.Runtime.InteropServices.DllImportAttribute` attribute.</span></span> <span data-ttu-id="28da1-108">Il primo argomento è una stringa che rappresenta il nome della DLL che contiene questa funzione, senza l'estensione dll.</span><span class="sxs-lookup"><span data-stu-id="28da1-108">The first argument is a string that represents the name of the DLL that contains this function, without the .dll extension.</span></span> <span data-ttu-id="28da1-109">È possibile specificare argomenti aggiuntivi per qualsiasi proprietà pubblica della `System.Runtime.InteropServices.DllImportAttribute` classe, ad esempio la convenzione di chiamata.</span><span class="sxs-lookup"><span data-stu-id="28da1-109">Additional arguments can be supplied for any of the public properties of the `System.Runtime.InteropServices.DllImportAttribute` class, such as the calling convention.</span></span>

<span data-ttu-id="28da1-110">Si supponga di disporre di C++ una DLL nativa contenente la seguente funzione esportata.</span><span class="sxs-lookup"><span data-stu-id="28da1-110">Assume you have a native C++ DLL that contains the following exported function.</span></span>

```cpp
#include <stdio.h>
extern "C" void __declspec(dllexport) HelloWorld()
{
    printf("Hello world, invoked by F#!\n");
}
```

<span data-ttu-id="28da1-111">È possibile chiamare questa funzione da F# usando il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="28da1-111">You can call this function from F# by using the following code.</span></span>

```fsharp
open System.Runtime.InteropServices

module InteropWithNative =
    [<DllImport(@"C:\bin\nativedll", CallingConvention = CallingConvention.Cdecl)>]
    extern void HelloWorld()

InteropWithNative.HelloWorld()
```

<span data-ttu-id="28da1-112">L'interoperabilità con il codice nativo viene definito *Platform Invoke* ed è una funzionalità di CLR.</span><span class="sxs-lookup"><span data-stu-id="28da1-112">Interoperability with native code is referred to as *platform invoke* and is a feature of the CLR.</span></span> <span data-ttu-id="28da1-113">Per altre informazioni, vedere [Interoperabilità con codice non gestito](../../../framework/interop/index.md).</span><span class="sxs-lookup"><span data-stu-id="28da1-113">For more information, see [Interoperating with Unmanaged Code](../../../framework/interop/index.md).</span></span> <span data-ttu-id="28da1-114">Le informazioni contenute in questa sezione sono applicabili F#a.</span><span class="sxs-lookup"><span data-stu-id="28da1-114">The information in that section is applicable to F#.</span></span>

## <a name="see-also"></a><span data-ttu-id="28da1-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="28da1-115">See also</span></span>

- [<span data-ttu-id="28da1-116">Funzioni</span><span class="sxs-lookup"><span data-stu-id="28da1-116">Functions</span></span>](index.md)
