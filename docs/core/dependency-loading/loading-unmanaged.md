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
# <a name="unmanaged-native-library-loading-algorithm"></a><span data-ttu-id="810d8-103">Algoritmo di caricamento libreria non gestito (nativo)</span><span class="sxs-lookup"><span data-stu-id="810d8-103">Unmanaged (native) library loading algorithm</span></span>

<span data-ttu-id="810d8-104">Le librerie non gestite vengono individuate e caricate con un algoritmo che prevede varie fasi.</span><span class="sxs-lookup"><span data-stu-id="810d8-104">Unmanaged libraries are located and loaded with an algorithm involving various stages.</span></span>

<span data-ttu-id="810d8-105">Nell'algoritmo seguente viene descritto il modo in `PInvoke`cui vengono caricate le librerie native.</span><span class="sxs-lookup"><span data-stu-id="810d8-105">The following algorithm describes how native libraries are loaded through `PInvoke`.</span></span>

## <a name="pinvoke-load-library-algorithm"></a><span data-ttu-id="810d8-106">`PInvoke`algoritmo Load Library</span><span class="sxs-lookup"><span data-stu-id="810d8-106">`PInvoke` load library algorithm</span></span>

<span data-ttu-id="810d8-107">`PInvoke`Usa l'algoritmo seguente quando si tenta di caricare un assembly non gestito:</span><span class="sxs-lookup"><span data-stu-id="810d8-107">`PInvoke` uses the following algorithm when attempting to load an unmanaged assembly:</span></span>

1. <span data-ttu-id="810d8-108">`active` Determinare .<xref:System.Runtime.Loader.AssemblyLoadContext></span><span class="sxs-lookup"><span data-stu-id="810d8-108">Determine the `active` <xref:System.Runtime.Loader.AssemblyLoadContext>.</span></span> <span data-ttu-id="810d8-109">Per una libreria `active` `PInvoke`di caricamento non gestita, AssemblyLoadContext è il chiamante di.</span><span class="sxs-lookup"><span data-stu-id="810d8-109">For an unmanaged load library, the `active` AssemblyLoadContext is the caller of the `PInvoke`.</span></span>

2. <span data-ttu-id="810d8-110">`active` Per,provareatrovarel'assembly<xref:System.Runtime.Loader.AssemblyLoadContext>in ordine di priorità:</span><span class="sxs-lookup"><span data-stu-id="810d8-110">For the `active` <xref:System.Runtime.Loader.AssemblyLoadContext>, try to find the assembly in priority order by:</span></span>
    * <span data-ttu-id="810d8-111">Verifica della cache.</span><span class="sxs-lookup"><span data-stu-id="810d8-111">Checking its cache.</span></span>

    * <span data-ttu-id="810d8-112">Chiamata al delegato <xref:System.Runtime.InteropServices.DllImportResolver?displayProperty=nameWithType> corrente impostato <xref:System.Runtime.InteropServices.NativeLibrary.SetDllImportResolver(System.Reflection.Assembly,System.Runtime.InteropServices.DllImportResolver)?displayProperty=nameWithType> dalla funzione.</span><span class="sxs-lookup"><span data-stu-id="810d8-112">Calling the current <xref:System.Runtime.InteropServices.DllImportResolver?displayProperty=nameWithType> delegate set by the <xref:System.Runtime.InteropServices.NativeLibrary.SetDllImportResolver(System.Reflection.Assembly,System.Runtime.InteropServices.DllImportResolver)?displayProperty=nameWithType> function.</span></span>

    * <span data-ttu-id="810d8-113">Chiamata della <xref:System.Runtime.Loader.AssemblyLoadContext.LoadUnmanagedDll%2A?displayProperty=nameWithType> funzione.</span><span class="sxs-lookup"><span data-stu-id="810d8-113">Calling the <xref:System.Runtime.Loader.AssemblyLoadContext.LoadUnmanagedDll%2A?displayProperty=nameWithType> function.</span></span>

    * <span data-ttu-id="810d8-114">Controllo della <xref:System.AppDomain> cache dell'istanza ed esecuzione della logica di [sondaggio della libreria non gestita (nativa)](default-probing.md#unmanaged-native-library-probing) .</span><span class="sxs-lookup"><span data-stu-id="810d8-114">Checking the <xref:System.AppDomain> instance's cache and running the [Unmanaged (native) library probing](default-probing.md#unmanaged-native-library-probing) logic.</span></span>

    * <span data-ttu-id="810d8-115">Generazione dell' <xref:System.Runtime.Loader.AssemblyLoadContext.ResolvingUnmanagedDll?displayProperty=nameWithType> evento `active` per AssemblyLoadContext.</span><span class="sxs-lookup"><span data-stu-id="810d8-115">Raising the <xref:System.Runtime.Loader.AssemblyLoadContext.ResolvingUnmanagedDll?displayProperty=nameWithType> event for the `active` AssemblyLoadContext.</span></span>

3. <span data-ttu-id="810d8-116">Se la libreria non gestita viene appena caricata, viene <xref:System.AppDomain.AssemblyLoad?displayProperty=nameWithType> generato l'evento.</span><span class="sxs-lookup"><span data-stu-id="810d8-116">If the unmanaged library is newly loaded, the <xref:System.AppDomain.AssemblyLoad?displayProperty=nameWithType> event is raised.</span></span>
