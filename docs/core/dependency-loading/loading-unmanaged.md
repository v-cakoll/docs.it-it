---
title: Algoritmo di caricamento della libreria non gestita-.NET Core
description: Descrizione dei dettagli dell'algoritmo di caricamento dell'assembly non gestito in .NET Core
ms.date: 10/09/2019
author: sdmaclea
ms.author: stmaclea
ms.openlocfilehash: c651aa6e0f37a968e6f8b26d1909def6fa488ccd
ms.sourcegitcommit: d7c298f6c2e3aab0c7498bfafc0a0a94ea1fe23e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/10/2019
ms.locfileid: "72250040"
---
# <a name="unmanaged-native-library-loading-algorithm"></a>Algoritmo di caricamento libreria non gestito (nativo)

Le librerie non gestite vengono individuate e caricate con un algoritmo che prevede varie fasi.

Nell'algoritmo seguente viene descritto come vengono caricate le librerie native tramite `PInvoke`.

## <a name="pinvoke-load-library-algorithm"></a>algoritmo di caricamento della libreria `PInvoke`

`PInvoke` usa l'algoritmo seguente quando si tenta di caricare un assembly non gestito:

1. Determinare il `active` <xref:System.Runtime.Loader.AssemblyLoadContext>. Per una libreria di caricamento non gestita, il AssemblyLoadContext `active` è quello con l'assembly che definisce il `PInvoke`.

2. Per la `active` <xref:System.Runtime.Loader.AssemblyLoadContext>, provare a trovare l'assembly in ordine di priorità:
    * Verifica della cache.

    * Chiamata al delegato <xref:System.Runtime.InteropServices.DllImportResolver?displayProperty=nameWithType> corrente impostato dalla funzione <xref:System.Runtime.InteropServices.NativeLibrary.SetDllImportResolver(System.Reflection.Assembly,System.Runtime.InteropServices.DllImportResolver)?displayProperty=nameWithType>.

    * Chiamata della funzione <xref:System.Runtime.Loader.AssemblyLoadContext.LoadUnmanagedDll%2A?displayProperty=nameWithType> sul AssemblyLoadContext `active`.

    * Controllo della cache dell'istanza di <xref:System.AppDomain> ed esecuzione della logica di [probe della libreria non gestita (nativa)](default-probing.md#unmanaged-native-library-probing) .

    * Generazione dell'evento <xref:System.Runtime.Loader.AssemblyLoadContext.ResolvingUnmanagedDll?displayProperty=nameWithType> per il AssemblyLoadContext `active`.
