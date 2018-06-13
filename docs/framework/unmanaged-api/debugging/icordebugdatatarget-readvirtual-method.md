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
ms.openlocfilehash: 2d9e619e4176633074242521133d42f191f140ca
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33412191"
---
# <a name="icordebugdatatargetreadvirtual-method"></a><span data-ttu-id="54d6f-102">Metodo ICorDebugDataTarget::ReadVirtual</span><span class="sxs-lookup"><span data-stu-id="54d6f-102">ICorDebugDataTarget::ReadVirtual Method</span></span>
<span data-ttu-id="54d6f-103">Ottiene un blocco di memoria contigua a partire dall'indirizzo specificato e lo restituisce nel buffer fornito.</span><span class="sxs-lookup"><span data-stu-id="54d6f-103">Gets a block of contiguous memory starting at the specified address, and returns it in the supplied buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54d6f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="54d6f-104">Syntax</span></span>  
  
```  
HRESULT ReadVirtual(  
    [in] CORDB_ADDRESS   address,  
    [out, size_is(bytesRequested), length_is(*pBytesRead)]  
          BYTE *     pBuffer,  
    [in]  ULONG32    bytesRequested,  
    [out] ULONG32 *  pBytesRead);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="54d6f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="54d6f-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="54d6f-106">[in] Indirizzo iniziale di memoria richiesta.</span><span class="sxs-lookup"><span data-stu-id="54d6f-106">[in] The start address of requested memory.</span></span>  
  
 `pbuffer`  
 <span data-ttu-id="54d6f-107">[out] Buffer in cui verrà archiviata la memoria.</span><span class="sxs-lookup"><span data-stu-id="54d6f-107">[out] The buffer where the memory will be stored.</span></span>  
  
 `bytesRequested`  
 <span data-ttu-id="54d6f-108">[in] Il numero di byte da ottenere dall'indirizzo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="54d6f-108">[in] The number of bytes to get from the target address.</span></span>  
  
 `pBytesRead`  
 <span data-ttu-id="54d6f-109">[out] Il numero di byte effettivamente letti dall'indirizzo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="54d6f-109">[out] The number of bytes actually read from the target address.</span></span> <span data-ttu-id="54d6f-110">Può trattarsi di un valore minore di `bytesRequested`.</span><span class="sxs-lookup"><span data-stu-id="54d6f-110">This can be fewer than `bytesRequested`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="54d6f-111">Note</span><span class="sxs-lookup"><span data-stu-id="54d6f-111">Remarks</span></span>  
 <span data-ttu-id="54d6f-112">Se è possibile leggere il primo byte (in corrispondenza dell'indirizzo di inizio specificato), la chiamata deve restituire l'esito positivo (per supportare la lettura efficiente di strutture di dati con autodescrittivi lunghezza, come le stringhe con terminazione null).</span><span class="sxs-lookup"><span data-stu-id="54d6f-112">If the first byte (at the specified start address) can be read, the call should return success (to support efficient reading of data structures with self-describing length, like null-terminated strings).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="54d6f-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="54d6f-113">Requirements</span></span>  
 <span data-ttu-id="54d6f-114">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="54d6f-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="54d6f-115">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="54d6f-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="54d6f-116">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="54d6f-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="54d6f-117">**Versioni di .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="54d6f-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54d6f-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="54d6f-118">See Also</span></span>  
 [<span data-ttu-id="54d6f-119">Interfaccia ICorDebugDataTarget</span><span class="sxs-lookup"><span data-stu-id="54d6f-119">ICorDebugDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)  
 [<span data-ttu-id="54d6f-120">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="54d6f-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="54d6f-121">Debug</span><span class="sxs-lookup"><span data-stu-id="54d6f-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
