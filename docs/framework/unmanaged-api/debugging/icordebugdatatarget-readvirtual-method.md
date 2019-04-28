---
title: Metodo ICorDebugDataTarget::ReadVirtual
ms.date: 03/30/2017
api_name:
- ICorDebugDataTarget.ReadVirtual Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugDataTarget::ReadVirtual
helpviewer_keywords:
- ICorDebugDataTarget::ReadVirtual method [.NET Framework debugging]
- ReadVirtual method, ICorDebugDataTarget interface [.NET Framework debugging]
ms.assetid: 55e57640-b3d2-413d-b4f4-fbc27fb8e37c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4749bfee22e58ad7c3ca29ec992da88493ca2c5c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61763841"
---
# <a name="icordebugdatatargetreadvirtual-method"></a><span data-ttu-id="3ca28-102">Metodo ICorDebugDataTarget::ReadVirtual</span><span class="sxs-lookup"><span data-stu-id="3ca28-102">ICorDebugDataTarget::ReadVirtual Method</span></span>
<span data-ttu-id="3ca28-103">Ottiene un blocco di memoria contigua a partire dall'indirizzo specificato e lo restituisce nel buffer fornito.</span><span class="sxs-lookup"><span data-stu-id="3ca28-103">Gets a block of contiguous memory starting at the specified address, and returns it in the supplied buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ca28-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3ca28-104">Syntax</span></span>  
  
```  
HRESULT ReadVirtual(  
    [in] CORDB_ADDRESS   address,  
    [out, size_is(bytesRequested), length_is(*pBytesRead)]  
          BYTE *     pBuffer,  
    [in]  ULONG32    bytesRequested,  
    [out] ULONG32 *  pBytesRead);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3ca28-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="3ca28-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="3ca28-106">[in] L'indirizzo iniziale di memoria richiesta.</span><span class="sxs-lookup"><span data-stu-id="3ca28-106">[in] The start address of requested memory.</span></span>  
  
 `pbuffer`  
 <span data-ttu-id="3ca28-107">[out] Buffer in cui verrà archiviata la memoria.</span><span class="sxs-lookup"><span data-stu-id="3ca28-107">[out] The buffer where the memory will be stored.</span></span>  
  
 `bytesRequested`  
 <span data-ttu-id="3ca28-108">[in] Il numero di byte da ottenere dall'indirizzo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="3ca28-108">[in] The number of bytes to get from the target address.</span></span>  
  
 `pBytesRead`  
 <span data-ttu-id="3ca28-109">[out] Il numero di byte effettivamente letti dall'indirizzo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="3ca28-109">[out] The number of bytes actually read from the target address.</span></span> <span data-ttu-id="3ca28-110">Questo può essere minore `bytesRequested`.</span><span class="sxs-lookup"><span data-stu-id="3ca28-110">This can be fewer than `bytesRequested`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3ca28-111">Note</span><span class="sxs-lookup"><span data-stu-id="3ca28-111">Remarks</span></span>  
 <span data-ttu-id="3ca28-112">Se è possibile leggere il primo byte (in corrispondenza dell'indirizzo iniziale specificato), la chiamata deve restituire esito positivo (per supportare la lettura efficiente di strutture di dati con lunghezza autodescrittiva, come le stringhe con terminazione null).</span><span class="sxs-lookup"><span data-stu-id="3ca28-112">If the first byte (at the specified start address) can be read, the call should return success (to support efficient reading of data structures with self-describing length, like null-terminated strings).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3ca28-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3ca28-113">Requirements</span></span>  
 <span data-ttu-id="3ca28-114">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3ca28-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3ca28-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3ca28-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3ca28-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3ca28-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3ca28-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3ca28-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ca28-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3ca28-118">See also</span></span>

- [<span data-ttu-id="3ca28-119">Interfaccia ICorDebugDataTarget</span><span class="sxs-lookup"><span data-stu-id="3ca28-119">ICorDebugDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)
- [<span data-ttu-id="3ca28-120">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="3ca28-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="3ca28-121">Debug</span><span class="sxs-lookup"><span data-stu-id="3ca28-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
