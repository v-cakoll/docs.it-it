---
title: Funzioni esterne (F#)
description: 'Scopri il supporto del linguaggio F # per chiamare le funzioni in codice nativo.'
ms.date: 05/16/2016
ms.openlocfilehash: db0d3362d867b07b333951f3380c6735ff471d5e
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/05/2018
ms.locfileid: "43747382"
---
# <a name="external-functions"></a>Funzioni esterne

In questo argomento viene descritto il supporto del linguaggio F # per chiamare le funzioni in codice nativo.

## <a name="syntax"></a>Sintassi

```fsharp
[<DllImport( arguments )>]
extern declaration
```

## <a name="remarks"></a>Note

Nella sintassi precedente *argomenti* rappresenta gli argomenti forniti per il `System.Runtime.InteropServices.DllImportAttribute` attributo. Il primo argomento è una stringa che rappresenta il nome della DLL che contiene questa funzione, senza l'estensione dll. Argomenti aggiuntivi possono essere forniti per qualsiasi proprietà pubblica del `System.Runtime.InteropServices.DllImportAttribute` classe, ad esempio la convenzione di chiamata.

Si supponga di che avere una DLL C++ che contiene la seguente funzione esportata nativa.

```cpp
#include <stdio.h>
extern "C" void __declspec(dllexport) HelloWorld()
{
    printf("Hello world, invoked by F#!\n");
}
```

È possibile chiamare questa funzione da F # usando il codice seguente.

```fsharp
open System.Runtime.InteropServices

module InteropWithNative =
    [<DllImport(@"C:\bin\nativedll", CallingConvention = CallingConvention.Cdecl)>]
    extern void HelloWorld()

InteropWithNative.HelloWorld()
```

L'interoperabilità con codice nativo è detta *PInvoke* ed è una funzionalità di CLR. Per altre informazioni, vedere [Interoperabilità con codice non gestito](../../../../docs/framework/interop/index.md). Le informazioni contenute in tale sezione sono applicabile a F #.

## <a name="see-also"></a>Vedere anche

- [Funzioni](index.md)
