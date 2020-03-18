---
title: Algoritmo di caricamento della libreria non gestita - .NET CoreUnmanaged library loading algorithm - .NET Core
description: Descrizione dei dettagli dell'algoritmo di caricamento di assembly non gestito in .NET Core
ms.date: 10/09/2019
author: sdmaclea
ms.author: stmaclea
ms.openlocfilehash: c651aa6e0f37a968e6f8b26d1909def6fa488ccd
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "72250040"
---
# <a name="unmanaged-native-library-loading-algorithm"></a>Algoritmo di caricamento della libreria non gestita (nativa) Unmanaged (native) library loading algorithm

Le librerie non gestite vengono individuate e caricate con un algoritmo che coinvolge varie fasi.

L'algoritmo seguente descrive il `PInvoke`modo in cui le librerie native vengono caricate tramite .

## <a name="pinvoke-load-library-algorithm"></a>`PInvoke`algoritmo della libreria di caricamento

`PInvoke`utilizza il seguente algoritmo quando si tenta di caricare un assembly non gestito:

1. Determinare `active` <xref:System.Runtime.Loader.AssemblyLoadContext>il file . Per una libreria di `active` caricamento non gestita, AssemblyLoadContext è `PInvoke`quello con l'assembly che definisce l'oggetto .

2. Per `active` <xref:System.Runtime.Loader.AssemblyLoadContext>, provare a trovare l'assieme in ordine di priorità per:
    * Controllo della cache.

    * Chiamata del <xref:System.Runtime.InteropServices.DllImportResolver?displayProperty=nameWithType> delegato corrente <xref:System.Runtime.InteropServices.NativeLibrary.SetDllImportResolver(System.Reflection.Assembly,System.Runtime.InteropServices.DllImportResolver)?displayProperty=nameWithType> impostato dalla funzione.

    * Chiamata <xref:System.Runtime.Loader.AssemblyLoadContext.LoadUnmanagedDll%2A?displayProperty=nameWithType> della funzione `active` su AssemblyLoadContext.

    * Controllo <xref:System.AppDomain> della cache dell'istanza e esecuzione della logica di [probe della libreria Unmanaged (nativa).](default-probing.md#unmanaged-native-library-probing)

    * Generazione <xref:System.Runtime.Loader.AssemblyLoadContext.ResolvingUnmanagedDll?displayProperty=nameWithType> dell'evento `active` per AssemblyLoadContext.
