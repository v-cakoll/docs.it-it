---
title: Funzioni esterne (F#)
description: 'Informazioni sul supporto del linguaggio F # per chiamare le funzioni in codice nativo.'
ms.date: 05/16/2016
ms.openlocfilehash: 398697c5e0deab7f8d81ec5198ab1918bd865e13
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="external-functions"></a>Funzioni esterne

In questo argomento viene descritto il supporto del linguaggio F # per chiamare le funzioni in codice nativo.

## <a name="syntax"></a>Sintassi

```fsharp
[<DllImport( arguments )>]
extern declaration
```

## <a name="remarks"></a>Note

Nella sintassi precedente, *argomenti* rappresenta gli argomenti forniti per il `System.Runtime.InteropServices.DllImportAttribute` attributo. Il primo argomento è una stringa che rappresenta il nome della DLL che contiene questa funzione, senza l'estensione. dll. È possibile fornire argomenti aggiuntivi per le proprietà pubbliche del `System.Runtime.InteropServices.DllImportAttribute` classe, ad esempio la convenzione di chiamata.

Si supponga di che disporre di una DLL di C++ che contiene la seguente funzione esportata nativa.

```cpp
#include <stdio.h>
extern "C" void __declspec(dllexport) HelloWorld()
{
    printf("Hello world, invoked by F#!\n");
}
```

È possibile chiamare questa funzione da F # utilizzando il codice seguente.

```fsharp
open System.Runtime.InteropServices

module InteropWithNative =
    [<DllImport(@"C:\bin\nativedll", CallingConvention = CallingConvention.Cdecl)>]
    extern void HelloWorld()

InteropWithNative.HelloWorld()
```

Interoperabilità con codice nativo è detto *PInvoke* ed è una funzionalità di Common Language Runtime. Per altre informazioni, vedere [Interoperabilità con codice non gestito](../../../../docs/framework/interop/index.md). Le informazioni contenute in tale sezione sono applicabile a F #.


## <a name="see-also"></a>Vedere anche

[Funzioni](index.md)
