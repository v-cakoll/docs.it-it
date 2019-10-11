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
# <a name="unmanaged-native-library-loading-algorithm"></a><span data-ttu-id="81cc4-103">Algoritmo di caricamento libreria non gestito (nativo)</span><span class="sxs-lookup"><span data-stu-id="81cc4-103">Unmanaged (native) library loading algorithm</span></span>

<span data-ttu-id="81cc4-104">Le librerie non gestite vengono individuate e caricate con un algoritmo che prevede varie fasi.</span><span class="sxs-lookup"><span data-stu-id="81cc4-104">Unmanaged libraries are located and loaded with an algorithm involving various stages.</span></span>

<span data-ttu-id="81cc4-105">Nell'algoritmo seguente viene descritto come vengono caricate le librerie native tramite `PInvoke`.</span><span class="sxs-lookup"><span data-stu-id="81cc4-105">The following algorithm describes how native libraries are loaded through `PInvoke`.</span></span>

## <a name="pinvoke-load-library-algorithm"></a><span data-ttu-id="81cc4-106">algoritmo di caricamento della libreria `PInvoke`</span><span class="sxs-lookup"><span data-stu-id="81cc4-106">`PInvoke` load library algorithm</span></span>

<span data-ttu-id="81cc4-107">`PInvoke` usa l'algoritmo seguente quando si tenta di caricare un assembly non gestito:</span><span class="sxs-lookup"><span data-stu-id="81cc4-107">`PInvoke` uses the following algorithm when attempting to load an unmanaged assembly:</span></span>

1. <span data-ttu-id="81cc4-108">Determinare il `active` <xref:System.Runtime.Loader.AssemblyLoadContext>.</span><span class="sxs-lookup"><span data-stu-id="81cc4-108">Determine the `active` <xref:System.Runtime.Loader.AssemblyLoadContext>.</span></span> <span data-ttu-id="81cc4-109">Per una libreria di caricamento non gestita, il AssemblyLoadContext `active` è quello con l'assembly che definisce il `PInvoke`.</span><span class="sxs-lookup"><span data-stu-id="81cc4-109">For an unmanaged load library, the `active` AssemblyLoadContext is the one with the assembly that defines the `PInvoke`.</span></span>

2. <span data-ttu-id="81cc4-110">Per la `active` <xref:System.Runtime.Loader.AssemblyLoadContext>, provare a trovare l'assembly in ordine di priorità:</span><span class="sxs-lookup"><span data-stu-id="81cc4-110">For the `active` <xref:System.Runtime.Loader.AssemblyLoadContext>, try to find the assembly in priority order by:</span></span>
    * <span data-ttu-id="81cc4-111">Verifica della cache.</span><span class="sxs-lookup"><span data-stu-id="81cc4-111">Checking its cache.</span></span>

    * <span data-ttu-id="81cc4-112">Chiamata al delegato <xref:System.Runtime.InteropServices.DllImportResolver?displayProperty=nameWithType> corrente impostato dalla funzione <xref:System.Runtime.InteropServices.NativeLibrary.SetDllImportResolver(System.Reflection.Assembly,System.Runtime.InteropServices.DllImportResolver)?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="81cc4-112">Calling the current <xref:System.Runtime.InteropServices.DllImportResolver?displayProperty=nameWithType> delegate set by the <xref:System.Runtime.InteropServices.NativeLibrary.SetDllImportResolver(System.Reflection.Assembly,System.Runtime.InteropServices.DllImportResolver)?displayProperty=nameWithType> function.</span></span>

    * <span data-ttu-id="81cc4-113">Chiamata della funzione <xref:System.Runtime.Loader.AssemblyLoadContext.LoadUnmanagedDll%2A?displayProperty=nameWithType> sul AssemblyLoadContext `active`.</span><span class="sxs-lookup"><span data-stu-id="81cc4-113">Calling the <xref:System.Runtime.Loader.AssemblyLoadContext.LoadUnmanagedDll%2A?displayProperty=nameWithType> function on the `active` AssemblyLoadContext.</span></span>

    * <span data-ttu-id="81cc4-114">Controllo della cache dell'istanza di <xref:System.AppDomain> ed esecuzione della logica di [probe della libreria non gestita (nativa)](default-probing.md#unmanaged-native-library-probing) .</span><span class="sxs-lookup"><span data-stu-id="81cc4-114">Checking the <xref:System.AppDomain> instance's cache and running the [Unmanaged (native) library probing](default-probing.md#unmanaged-native-library-probing) logic.</span></span>

    * <span data-ttu-id="81cc4-115">Generazione dell'evento <xref:System.Runtime.Loader.AssemblyLoadContext.ResolvingUnmanagedDll?displayProperty=nameWithType> per il AssemblyLoadContext `active`.</span><span class="sxs-lookup"><span data-stu-id="81cc4-115">Raising the <xref:System.Runtime.Loader.AssemblyLoadContext.ResolvingUnmanagedDll?displayProperty=nameWithType> event for the `active` AssemblyLoadContext.</span></span>
