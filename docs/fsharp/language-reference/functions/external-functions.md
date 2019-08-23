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
# <a name="external-functions"></a>Funzioni esterne

Questo argomento descrive F# il supporto del linguaggio per chiamare le funzioni in codice nativo.

## <a name="syntax"></a>Sintassi

```fsharp
[<DllImport( arguments )>]
extern declaration
```

## <a name="remarks"></a>Note

Nella sintassi precedente gli *argomenti* rappresentano gli argomenti forniti all' `System.Runtime.InteropServices.DllImportAttribute` attributo. Il primo argomento è una stringa che rappresenta il nome della DLL che contiene questa funzione, senza l'estensione dll. È possibile specificare argomenti aggiuntivi per qualsiasi proprietà pubblica della `System.Runtime.InteropServices.DllImportAttribute` classe, ad esempio la convenzione di chiamata.

Si supponga di disporre di C++ una DLL nativa contenente la seguente funzione esportata.

```cpp
#include <stdio.h>
extern "C" void __declspec(dllexport) HelloWorld()
{
    printf("Hello world, invoked by F#!\n");
}
```

È possibile chiamare questa funzione da F# usando il codice seguente.

```fsharp
open System.Runtime.InteropServices

module InteropWithNative =
    [<DllImport(@"C:\bin\nativedll", CallingConvention = CallingConvention.Cdecl)>]
    extern void HelloWorld()

InteropWithNative.HelloWorld()
```

L'interoperabilità con il codice nativo viene definito *Platform Invoke* ed è una funzionalità di CLR. Per altre informazioni, vedere [Interoperabilità con codice non gestito](../../../framework/interop/index.md). Le informazioni contenute in questa sezione sono applicabili F#a.

## <a name="see-also"></a>Vedere anche

- [Funzioni](index.md)
