---
title: Metodo ICorDebugMergedAssemblyRecord::GetPublicKeyToken
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 72020b72-9611-4bc3-b1e7-5a16b023bfa3
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a1871e6060303ad496e4edb7bed47b9d91ecf71f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmergedassemblyrecordgetpublickeytoken-method"></a><span data-ttu-id="c00fa-102">Metodo ICorDebugMergedAssemblyRecord::GetPublicKeyToken</span><span class="sxs-lookup"><span data-stu-id="c00fa-102">ICorDebugMergedAssemblyRecord::GetPublicKeyToken Method</span></span>
<span data-ttu-id="c00fa-103">Ottiene il token di chiave pubblica dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="c00fa-103">Gets the assembly's public key token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c00fa-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c00fa-104">Syntax</span></span>  
  
```  
HRESULT GetPublicKeyToken(  
   [in] ULONG32 cbPublicKeyToken,   
   [out] ULONG32 *pcbPublicKeyToken,   
   [out, size_is(cbPublicKeyToken), length_is(*pcbPublicKeyToken)] BYTE pbPublicKeyToken[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c00fa-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c00fa-105">Parameters</span></span>  
 `cbPublicKeyToken`  
 <span data-ttu-id="c00fa-106">[in] Numero massimo di byte nella matrice di `pbPublicKeyToken`.</span><span class="sxs-lookup"><span data-stu-id="c00fa-106">[in] The maximum number of bytes in the `pbPublicKeyToken` array.</span></span>  
  
 `pcbPublicKeyToken`  
 <span data-ttu-id="c00fa-107">[out] Puntatore al numero effettivo di byte scritti nella matrice di `pbPublicKeyToken`.</span><span class="sxs-lookup"><span data-stu-id="c00fa-107">[out] A pointer to the actual number of bytes written to the `pbPublicKeyToken` array.</span></span>  
  
 `pbPublicKeyToken`  
 <span data-ttu-id="c00fa-108">[out] Puntatore a una matrice di byte che contiene il token di chiave pubblica dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="c00fa-108">[out] A pointer to a byte array that contains the assembly's public key token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c00fa-109">Note</span><span class="sxs-lookup"><span data-stu-id="c00fa-109">Remarks</span></span>  
 <span data-ttu-id="c00fa-110">Il token di chiave pubblica di un assembly corrisponde agli ultimi otto byte di un hash SHA1 della relativa chiave pubblica.</span><span class="sxs-lookup"><span data-stu-id="c00fa-110">An assembly's public key token is the last eight bytes of a SHA1 hash of its public key.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c00fa-111">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="c00fa-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c00fa-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c00fa-112">Requirements</span></span>  
 <span data-ttu-id="c00fa-113">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c00fa-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c00fa-114">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="c00fa-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c00fa-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c00fa-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c00fa-116">**Versioni di .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c00fa-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c00fa-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c00fa-117">See Also</span></span>  
 [<span data-ttu-id="c00fa-118">Interfaccia ICorDebugMergedAssemblyRecord</span><span class="sxs-lookup"><span data-stu-id="c00fa-118">ICorDebugMergedAssemblyRecord Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)  
 [<span data-ttu-id="c00fa-119">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="c00fa-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
