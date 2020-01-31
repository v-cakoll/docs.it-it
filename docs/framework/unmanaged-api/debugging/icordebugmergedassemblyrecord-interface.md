---
title: Interfaccia ICorDebugMergedAssemblyRecord
ms.date: 03/30/2017
ms.assetid: fe280b11-9479-4e34-a07c-0d1ea8088422
ms.openlocfilehash: 6d5d862110cd91e8ac81c96e50486be10c579903
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793066"
---
# <a name="icordebugmergedassemblyrecord-interface"></a><span data-ttu-id="dc6dc-102">Interfaccia ICorDebugMergedAssemblyRecord</span><span class="sxs-lookup"><span data-stu-id="dc6dc-102">ICorDebugMergedAssemblyRecord Interface</span></span>
<span data-ttu-id="dc6dc-103">Fornisce informazioni su un assembly unito.</span><span class="sxs-lookup"><span data-stu-id="dc6dc-103">Provides information about a merged assembly.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="dc6dc-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="dc6dc-104">Methods</span></span>  
  
|<span data-ttu-id="dc6dc-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="dc6dc-105">Method</span></span>|<span data-ttu-id="dc6dc-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dc6dc-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="dc6dc-107">Metodo GetCulture</span><span class="sxs-lookup"><span data-stu-id="dc6dc-107">GetCulture Method</span></span>](icordebugmergedassemblyrecord-getculture-method.md)|<span data-ttu-id="dc6dc-108">Ottiene la stringa del nome delle impostazioni cultura dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="dc6dc-108">Gets the culture name string of the assembly.</span></span>|  
|[<span data-ttu-id="dc6dc-109">Metodo GetIndex</span><span class="sxs-lookup"><span data-stu-id="dc6dc-109">GetIndex Method</span></span>](icordebugmergedassemblyrecord-getindex-method.md)|<span data-ttu-id="dc6dc-110">Ottiene l'indice del prefisso dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="dc6dc-110">Gets the assembly's prefix index.</span></span>|  
|[<span data-ttu-id="dc6dc-111">Metodo GetPublicKey</span><span class="sxs-lookup"><span data-stu-id="dc6dc-111">GetPublicKey Method</span></span>](icordebugmergedassemblyrecord-getpublickey-method.md)|<span data-ttu-id="dc6dc-112">Ottiene la chiave pubblica dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="dc6dc-112">Gets the assembly's public key.</span></span>|  
|[<span data-ttu-id="dc6dc-113">Metodo GetPublicKeyToken</span><span class="sxs-lookup"><span data-stu-id="dc6dc-113">GetPublicKeyToken Method</span></span>](icordebugmergedassemblyrecord-getpublickeytoken-method.md)|<span data-ttu-id="dc6dc-114">Ottiene il token di chiave pubblica dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="dc6dc-114">Gets the assembly's public key token.</span></span>|  
|[<span data-ttu-id="dc6dc-115">Metodo GetSimpleName</span><span class="sxs-lookup"><span data-stu-id="dc6dc-115">GetSimpleName Method</span></span>](icordebugmergedassemblyrecord-getsimplename-method.md)|<span data-ttu-id="dc6dc-116">Ottiene il nome semplice dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="dc6dc-116">Gets the simple name of the assembly.</span></span>|  
|[<span data-ttu-id="dc6dc-117">Metodo GetVersion</span><span class="sxs-lookup"><span data-stu-id="dc6dc-117">GetVersion Method</span></span>](icordebugmergedassemblyrecord-getversion-method.md)|<span data-ttu-id="dc6dc-118">Ottiene le informazioni sulla versione dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="dc6dc-118">Gets the assembly's version information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dc6dc-119">Note</span><span class="sxs-lookup"><span data-stu-id="dc6dc-119">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="dc6dc-120">Questa interfaccia è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="dc6dc-120">This interface is available with .NET Native only.</span></span> <span data-ttu-id="dc6dc-121">Se questa interfaccia viene implementata per scenari ICorDebug al di fuori di .NET Native, sarà ignorata da Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="dc6dc-121">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dc6dc-122">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="dc6dc-122">Requirements</span></span>  
 <span data-ttu-id="dc6dc-123">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dc6dc-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dc6dc-124">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dc6dc-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dc6dc-125">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dc6dc-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dc6dc-126">**Versioni .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dc6dc-126">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc6dc-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dc6dc-127">See also</span></span>

- [<span data-ttu-id="dc6dc-128">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="dc6dc-128">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="dc6dc-129">Debug</span><span class="sxs-lookup"><span data-stu-id="dc6dc-129">Debugging</span></span>](index.md)
