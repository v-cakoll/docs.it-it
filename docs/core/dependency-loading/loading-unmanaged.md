---
title: Algoritmo di caricamento della libreria non gestita-.NET Core
description: Descrizione dei dettagli dell'algoritmo di caricamento dell'assembly non gestito in .NET Core
ms.date: 08/09/2019
author: sdmaclea
ms.author: stmaclea
ms.openlocfilehash: 8240cb730180637393e2545f8013d3f1439be719
ms.sourcegitcommit: 121ab70c1ebedba41d276e436dd2b1502748a49f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/24/2019
ms.locfileid: "70234660"
---
# <a name="unmanaged-native-library-loading-algorithm"></a>Algoritmo di caricamento libreria non gestito (nativo)

Le librerie non gestite vengono individuate e caricate con un algoritmo che prevede varie fasi.

Nell'algoritmo seguente viene descritto il modo in `PInvoke`cui vengono caricate le librerie native.

## <a name="pinvoke-load-library-algorithm"></a>`PInvoke`algoritmo Load Library

`PInvoke`Usa l'algoritmo seguente quando si tenta di caricare un assembly non gestito:

1. `active` Determinare .<xref:System.Runtime.Loader.AssemblyLoadContext> Per una libreria `active` `PInvoke`di caricamento non gestita, AssemblyLoadContext è il chiamante di.

2. `active` Per,provareatrovarel'assembly<xref:System.Runtime.Loader.AssemblyLoadContext>in ordine di priorità:
    * Verifica della cache.

    * Chiamata al delegato <xref:System.Runtime.InteropServices.DllImportResolver?displayProperty=nameWithType> corrente impostato <xref:System.Runtime.InteropServices.NativeLibrary.SetDllImportResolver(System.Reflection.Assembly,System.Runtime.InteropServices.DllImportResolver)?displayProperty=nameWithType> dalla funzione.

    * Chiamata della <xref:System.Runtime.Loader.AssemblyLoadContext.LoadUnmanagedDll%2A?displayProperty=nameWithType> funzione.

    * Controllo della <xref:System.AppDomain> cache dell'istanza ed esecuzione della logica di [sondaggio della libreria non gestita (nativa)](default-probing.md#unmanaged-native-library-probing) .

    * Generazione dell' <xref:System.Runtime.Loader.AssemblyLoadContext.ResolvingUnmanagedDll?displayProperty=nameWithType> evento `active` per AssemblyLoadContext.

3. Se la libreria non gestita viene appena caricata, viene <xref:System.AppDomain.AssemblyLoad?displayProperty=nameWithType> generato l'evento.
