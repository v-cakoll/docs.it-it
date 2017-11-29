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
ms.openlocfilehash: 4f525b2b750c2ce42230c61aa0e72f957739b206
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="external-functions"></a><span data-ttu-id="798e2-104">Funzioni esterne</span><span class="sxs-lookup"><span data-stu-id="798e2-104">External Functions</span></span>

<span data-ttu-id="798e2-105">In questo argomento viene descritto il supporto del linguaggio F # per chiamare le funzioni in codice nativo.</span><span class="sxs-lookup"><span data-stu-id="798e2-105">This topic describes F# language support for calling functions in native code.</span></span>

## <a name="syntax"></a><span data-ttu-id="798e2-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="798e2-106">Syntax</span></span>

```fsharp
[<DllImport( arguments )>]
extern declaration
```

## <a name="remarks"></a><span data-ttu-id="798e2-107">Note</span><span class="sxs-lookup"><span data-stu-id="798e2-107">Remarks</span></span>

<span data-ttu-id="798e2-108">Nella sintassi precedente, *argomenti* rappresenta gli argomenti forniti per il `System.Runtime.InteropServices.DllImportAttribute` attributo.</span><span class="sxs-lookup"><span data-stu-id="798e2-108">In the previous syntax, *arguments* represents arguments that are supplied to the `System.Runtime.InteropServices.DllImportAttribute` attribute.</span></span> <span data-ttu-id="798e2-109">Il primo argomento è una stringa che rappresenta il nome della DLL che contiene questa funzione, senza l'estensione. dll.</span><span class="sxs-lookup"><span data-stu-id="798e2-109">The first argument is a string that represents the name of the DLL that contains this function, without the .dll extension.</span></span> <span data-ttu-id="798e2-110">È possibile fornire argomenti aggiuntivi per le proprietà pubbliche del `System.Runtime.InteropServices.DllImportAttribute` classe, ad esempio la convenzione di chiamata.</span><span class="sxs-lookup"><span data-stu-id="798e2-110">Additional arguments can be supplied for any of the public properties of the `System.Runtime.InteropServices.DllImportAttribute` class, such as the calling convention.</span></span>

<span data-ttu-id="798e2-111">Si supponga di che disporre di una DLL di C++ che contiene la seguente funzione esportata nativa.</span><span class="sxs-lookup"><span data-stu-id="798e2-111">Assume you have a native C++ DLL that contains the following exported function.</span></span>

```cpp
#include <stdio.h>
extern "C" void __declspec(dllexport) HelloWorld()
{
    printf("Hello world, invoked by F#!\n");
}
```

<span data-ttu-id="798e2-112">È possibile chiamare questa funzione da F # utilizzando il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="798e2-112">You can call this function from F# by using the following code.</span></span>

```fsharp
open System.Runtime.InteropServices

module InteropWithNative =
    [<DllImport(@"C:\bin\nativedll", CallingConvention = CallingConvention.Cdecl)>]
    extern void HelloWorld()

InteropWithNative.HelloWorld()
```

<span data-ttu-id="798e2-113">Interoperabilità con codice nativo è detto *PInvoke* ed è una funzionalità di Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="798e2-113">Interoperability with native code is referred to as *platform invoke* and is a feature of the CLR.</span></span> <span data-ttu-id="798e2-114">Per altre informazioni, vedere [Interoperabilità con codice non gestito](https://msdn.microsoft.com/library/sd10k43k.aspx).</span><span class="sxs-lookup"><span data-stu-id="798e2-114">For more information, see [Interoperating with Unmanaged Code](https://msdn.microsoft.com/library/sd10k43k.aspx).</span></span> <span data-ttu-id="798e2-115">Le informazioni contenute in tale sezione sono applicabile a F #.</span><span class="sxs-lookup"><span data-stu-id="798e2-115">The information in that section is applicable to F#.</span></span>


## <a name="see-also"></a><span data-ttu-id="798e2-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="798e2-116">See Also</span></span>

[<span data-ttu-id="798e2-117">Funzioni</span><span class="sxs-lookup"><span data-stu-id="798e2-117">Functions</span></span>](index.md)
