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
# <a name="unmanaged-native-library-loading-algorithm"></a><span data-ttu-id="83234-103">Algoritmo di caricamento della libreria non gestita (nativa) Unmanaged (native) library loading algorithm</span><span class="sxs-lookup"><span data-stu-id="83234-103">Unmanaged (native) library loading algorithm</span></span>

<span data-ttu-id="83234-104">Le librerie non gestite vengono individuate e caricate con un algoritmo che coinvolge varie fasi.</span><span class="sxs-lookup"><span data-stu-id="83234-104">Unmanaged libraries are located and loaded with an algorithm involving various stages.</span></span>

<span data-ttu-id="83234-105">L'algoritmo seguente descrive il `PInvoke`modo in cui le librerie native vengono caricate tramite .</span><span class="sxs-lookup"><span data-stu-id="83234-105">The following algorithm describes how native libraries are loaded through `PInvoke`.</span></span>

## <a name="pinvoke-load-library-algorithm"></a><span data-ttu-id="83234-106">`PInvoke`algoritmo della libreria di caricamento</span><span class="sxs-lookup"><span data-stu-id="83234-106">`PInvoke` load library algorithm</span></span>

<span data-ttu-id="83234-107">`PInvoke`utilizza il seguente algoritmo quando si tenta di caricare un assembly non gestito:</span><span class="sxs-lookup"><span data-stu-id="83234-107">`PInvoke` uses the following algorithm when attempting to load an unmanaged assembly:</span></span>

1. <span data-ttu-id="83234-108">Determinare `active` <xref:System.Runtime.Loader.AssemblyLoadContext>il file .</span><span class="sxs-lookup"><span data-stu-id="83234-108">Determine the `active` <xref:System.Runtime.Loader.AssemblyLoadContext>.</span></span> <span data-ttu-id="83234-109">Per una libreria di `active` caricamento non gestita, AssemblyLoadContext è `PInvoke`quello con l'assembly che definisce l'oggetto .</span><span class="sxs-lookup"><span data-stu-id="83234-109">For an unmanaged load library, the `active` AssemblyLoadContext is the one with the assembly that defines the `PInvoke`.</span></span>

2. <span data-ttu-id="83234-110">Per `active` <xref:System.Runtime.Loader.AssemblyLoadContext>, provare a trovare l'assieme in ordine di priorità per:</span><span class="sxs-lookup"><span data-stu-id="83234-110">For the `active` <xref:System.Runtime.Loader.AssemblyLoadContext>, try to find the assembly in priority order by:</span></span>
    * <span data-ttu-id="83234-111">Controllo della cache.</span><span class="sxs-lookup"><span data-stu-id="83234-111">Checking its cache.</span></span>

    * <span data-ttu-id="83234-112">Chiamata del <xref:System.Runtime.InteropServices.DllImportResolver?displayProperty=nameWithType> delegato corrente <xref:System.Runtime.InteropServices.NativeLibrary.SetDllImportResolver(System.Reflection.Assembly,System.Runtime.InteropServices.DllImportResolver)?displayProperty=nameWithType> impostato dalla funzione.</span><span class="sxs-lookup"><span data-stu-id="83234-112">Calling the current <xref:System.Runtime.InteropServices.DllImportResolver?displayProperty=nameWithType> delegate set by the <xref:System.Runtime.InteropServices.NativeLibrary.SetDllImportResolver(System.Reflection.Assembly,System.Runtime.InteropServices.DllImportResolver)?displayProperty=nameWithType> function.</span></span>

    * <span data-ttu-id="83234-113">Chiamata <xref:System.Runtime.Loader.AssemblyLoadContext.LoadUnmanagedDll%2A?displayProperty=nameWithType> della funzione `active` su AssemblyLoadContext.</span><span class="sxs-lookup"><span data-stu-id="83234-113">Calling the <xref:System.Runtime.Loader.AssemblyLoadContext.LoadUnmanagedDll%2A?displayProperty=nameWithType> function on the `active` AssemblyLoadContext.</span></span>

    * <span data-ttu-id="83234-114">Controllo <xref:System.AppDomain> della cache dell'istanza e esecuzione della logica di [probe della libreria Unmanaged (nativa).](default-probing.md#unmanaged-native-library-probing)</span><span class="sxs-lookup"><span data-stu-id="83234-114">Checking the <xref:System.AppDomain> instance's cache and running the [Unmanaged (native) library probing](default-probing.md#unmanaged-native-library-probing) logic.</span></span>

    * <span data-ttu-id="83234-115">Generazione <xref:System.Runtime.Loader.AssemblyLoadContext.ResolvingUnmanagedDll?displayProperty=nameWithType> dell'evento `active` per AssemblyLoadContext.</span><span class="sxs-lookup"><span data-stu-id="83234-115">Raising the <xref:System.Runtime.Loader.AssemblyLoadContext.ResolvingUnmanagedDll?displayProperty=nameWithType> event for the `active` AssemblyLoadContext.</span></span>
