---
title: Interfaccia ICorDebugMergedAssemblyRecord
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: fe280b11-9479-4e34-a07c-0d1ea8088422
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6086d1a82b5f086d857ac612a9d454a6ed77ba1f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmergedassemblyrecord-interface"></a><span data-ttu-id="4a095-102">Interfaccia ICorDebugMergedAssemblyRecord</span><span class="sxs-lookup"><span data-stu-id="4a095-102">ICorDebugMergedAssemblyRecord Interface</span></span>
<span data-ttu-id="4a095-103">Fornisce informazioni su un assembly unito.</span><span class="sxs-lookup"><span data-stu-id="4a095-103">Provides information about a merged assembly.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4a095-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="4a095-104">Methods</span></span>  
  
|<span data-ttu-id="4a095-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="4a095-105">Method</span></span>|<span data-ttu-id="4a095-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4a095-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4a095-107">Metodo GetCulture</span><span class="sxs-lookup"><span data-stu-id="4a095-107">GetCulture Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-getculture-method.md)|<span data-ttu-id="4a095-108">Ottiene la stringa del nome delle impostazioni cultura dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="4a095-108">Gets the culture name string of the assembly.</span></span>|  
|[<span data-ttu-id="4a095-109">Metodo GetIndex</span><span class="sxs-lookup"><span data-stu-id="4a095-109">GetIndex Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-getindex-method.md)|<span data-ttu-id="4a095-110">Ottiene l'indice del prefisso dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="4a095-110">Gets the assembly's prefix index.</span></span>|  
|[<span data-ttu-id="4a095-111">Metodo GetPublicKey</span><span class="sxs-lookup"><span data-stu-id="4a095-111">GetPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-getpublickey-method.md)|<span data-ttu-id="4a095-112">Ottiene la chiave pubblica dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="4a095-112">Gets the assembly's public key.</span></span>|  
|[<span data-ttu-id="4a095-113">Metodo GetPublicKeyToken</span><span class="sxs-lookup"><span data-stu-id="4a095-113">GetPublicKeyToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-getpublickeytoken-method.md)|<span data-ttu-id="4a095-114">Ottiene il token di chiave pubblica dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="4a095-114">Gets the assembly's public key token.</span></span>|  
|[<span data-ttu-id="4a095-115">Metodo GetSimpleName</span><span class="sxs-lookup"><span data-stu-id="4a095-115">GetSimpleName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-getsimplename-method.md)|<span data-ttu-id="4a095-116">Ottiene il nome semplice dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="4a095-116">Gets the simple name of the assembly.</span></span>|  
|[<span data-ttu-id="4a095-117">Metodo GetVersion</span><span class="sxs-lookup"><span data-stu-id="4a095-117">GetVersion Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-getversion-method.md)|<span data-ttu-id="4a095-118">Ottiene le informazioni sulla versione dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="4a095-118">Gets the assembly's version information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4a095-119">Note</span><span class="sxs-lookup"><span data-stu-id="4a095-119">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4a095-120">Questa interfaccia è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="4a095-120">This interface is available with .NET Native only.</span></span> <span data-ttu-id="4a095-121">Se questa interfaccia viene implementata per scenari ICorDebug al di fuori di .NET Native, sarà ignorata da Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="4a095-121">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4a095-122">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4a095-122">Requirements</span></span>  
 <span data-ttu-id="4a095-123">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4a095-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4a095-124">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="4a095-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4a095-125">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4a095-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4a095-126">**Versioni di .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4a095-126">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a095-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4a095-127">See Also</span></span>  
 [<span data-ttu-id="4a095-128">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="4a095-128">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="4a095-129">Debug</span><span class="sxs-lookup"><span data-stu-id="4a095-129">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
