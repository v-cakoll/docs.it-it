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
ms.openlocfilehash: 36a18d92f05db55957bba55de84490c0da1a1f86
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976512"
---
# <a name="icordebugdatatargetreadvirtual-method"></a><span data-ttu-id="49e02-102">Metodo ICorDebugDataTarget::ReadVirtual</span><span class="sxs-lookup"><span data-stu-id="49e02-102">ICorDebugDataTarget::ReadVirtual Method</span></span>
<span data-ttu-id="49e02-103">Ottiene un blocco di memoria contigua a partire dall'indirizzo specificato e lo restituisce nel buffer fornito.</span><span class="sxs-lookup"><span data-stu-id="49e02-103">Gets a block of contiguous memory starting at the specified address, and returns it in the supplied buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49e02-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="49e02-104">Syntax</span></span>  
  
```cpp  
HRESULT ReadVirtual(  
    [in] CORDB_ADDRESS   address,  
    [out, size_is(bytesRequested), length_is(*pBytesRead)]  
          BYTE *     pBuffer,  
    [in]  ULONG32    bytesRequested,  
    [out] ULONG32 *  pBytesRead);  
```  
  
## <a name="parameters"></a><span data-ttu-id="49e02-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="49e02-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="49e02-106">in Indirizzo iniziale della memoria richiesta.</span><span class="sxs-lookup"><span data-stu-id="49e02-106">[in] The start address of requested memory.</span></span>  
  
 `pbuffer`  
 <span data-ttu-id="49e02-107">out Buffer in cui verrà archiviata la memoria.</span><span class="sxs-lookup"><span data-stu-id="49e02-107">[out] The buffer where the memory will be stored.</span></span>  
  
 `bytesRequested`  
 <span data-ttu-id="49e02-108">in Numero di byte da ottenere dall'indirizzo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="49e02-108">[in] The number of bytes to get from the target address.</span></span>  
  
 `pBytesRead`  
 <span data-ttu-id="49e02-109">out Numero di byte effettivamente letti dall'indirizzo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="49e02-109">[out] The number of bytes actually read from the target address.</span></span> <span data-ttu-id="49e02-110">Questo può essere minore di `bytesRequested`.</span><span class="sxs-lookup"><span data-stu-id="49e02-110">This can be fewer than `bytesRequested`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="49e02-111">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="49e02-111">Remarks</span></span>  
 <span data-ttu-id="49e02-112">Se è possibile leggere il primo byte (all'indirizzo iniziale specificato), la chiamata dovrebbe restituire esito positivo (per supportare una lettura efficiente delle strutture di dati con lunghezza autodescrittiva, ad esempio stringhe con terminazione null).</span><span class="sxs-lookup"><span data-stu-id="49e02-112">If the first byte (at the specified start address) can be read, the call should return success (to support efficient reading of data structures with self-describing length, like null-terminated strings).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="49e02-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="49e02-113">Requirements</span></span>  
 <span data-ttu-id="49e02-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="49e02-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="49e02-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="49e02-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="49e02-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="49e02-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="49e02-117">**Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="49e02-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49e02-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="49e02-118">See also</span></span>

- [<span data-ttu-id="49e02-119">Interfaccia ICorDebugDataTarget</span><span class="sxs-lookup"><span data-stu-id="49e02-119">ICorDebugDataTarget Interface</span></span>](icordebugdatatarget-interface.md)
- [<span data-ttu-id="49e02-120">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="49e02-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="49e02-121">Debug</span><span class="sxs-lookup"><span data-stu-id="49e02-121">Debugging</span></span>](index.md)
