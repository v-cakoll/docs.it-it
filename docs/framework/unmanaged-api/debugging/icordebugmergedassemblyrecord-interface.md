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
ms.openlocfilehash: 301d7d3d20b78e833101de1df8fd5c271a757144
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugmergedassemblyrecord-interface"></a><span data-ttu-id="a3cbc-102">Interfaccia ICorDebugMergedAssemblyRecord</span><span class="sxs-lookup"><span data-stu-id="a3cbc-102">ICorDebugMergedAssemblyRecord Interface</span></span>
<span data-ttu-id="a3cbc-103">Fornisce informazioni su un assembly unito.</span><span class="sxs-lookup"><span data-stu-id="a3cbc-103">Provides information about a merged assembly.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a3cbc-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="a3cbc-104">Methods</span></span>  
  
|<span data-ttu-id="a3cbc-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="a3cbc-105">Method</span></span>|<span data-ttu-id="a3cbc-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a3cbc-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a3cbc-107">Metodo GetCulture</span><span class="sxs-lookup"><span data-stu-id="a3cbc-107">GetCulture Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-getculture-method.md)|<span data-ttu-id="a3cbc-108">Ottiene la stringa del nome delle impostazioni cultura dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="a3cbc-108">Gets the culture name string of the assembly.</span></span>|  
|[<span data-ttu-id="a3cbc-109">GetIndex (metodo)</span><span class="sxs-lookup"><span data-stu-id="a3cbc-109">GetIndex Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-getindex-method.md)|<span data-ttu-id="a3cbc-110">Ottiene l'indice del prefisso dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="a3cbc-110">Gets the assembly's prefix index.</span></span>|  
|[<span data-ttu-id="a3cbc-111">Metodo GetPublicKey</span><span class="sxs-lookup"><span data-stu-id="a3cbc-111">GetPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-getpublickey-method.md)|<span data-ttu-id="a3cbc-112">Ottiene la chiave pubblica dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="a3cbc-112">Gets the assembly's public key.</span></span>|  
|[<span data-ttu-id="a3cbc-113">Metodo GetPublicKeyToken</span><span class="sxs-lookup"><span data-stu-id="a3cbc-113">GetPublicKeyToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-getpublickeytoken-method.md)|<span data-ttu-id="a3cbc-114">Ottiene il token di chiave pubblica dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="a3cbc-114">Gets the assembly's public key token.</span></span>|  
|[<span data-ttu-id="a3cbc-115">Metodo GetSimpleName</span><span class="sxs-lookup"><span data-stu-id="a3cbc-115">GetSimpleName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-getsimplename-method.md)|<span data-ttu-id="a3cbc-116">Ottiene il nome semplice dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="a3cbc-116">Gets the simple name of the assembly.</span></span>|  
|[<span data-ttu-id="a3cbc-117">GetVersion (metodo)</span><span class="sxs-lookup"><span data-stu-id="a3cbc-117">GetVersion Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-getversion-method.md)|<span data-ttu-id="a3cbc-118">Ottiene le informazioni sulla versione dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="a3cbc-118">Gets the assembly's version information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a3cbc-119">Note</span><span class="sxs-lookup"><span data-stu-id="a3cbc-119">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a3cbc-120">Questa interfaccia è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="a3cbc-120">This interface is available with .NET Native only.</span></span> <span data-ttu-id="a3cbc-121">Se questa interfaccia viene implementata per scenari ICorDebug al di fuori di .NET Native, sarà ignorata da Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="a3cbc-121">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a3cbc-122">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a3cbc-122">Requirements</span></span>  
 <span data-ttu-id="a3cbc-123">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a3cbc-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a3cbc-124">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="a3cbc-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a3cbc-125">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a3cbc-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a3cbc-126">**Versioni di .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a3cbc-126">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3cbc-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a3cbc-127">See Also</span></span>  
 [<span data-ttu-id="a3cbc-128">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="a3cbc-128">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="a3cbc-129">Debug</span><span class="sxs-lookup"><span data-stu-id="a3cbc-129">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
