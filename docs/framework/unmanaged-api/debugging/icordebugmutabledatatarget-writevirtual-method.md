---
title: Metodo ICorDebugMutableDataTarget::WriteVirtual
ms.date: 03/30/2017
ms.assetid: 80833648-58a7-491a-8dc8-9a48e9bb3adc
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 11fc4bf6feb2a90c0b54c4410ed807c5b7e3eb5b
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57501734"
---
# <a name="icordebugmutabledatatargetwritevirtual-method"></a><span data-ttu-id="96280-102">Metodo ICorDebugMutableDataTarget::WriteVirtual</span><span class="sxs-lookup"><span data-stu-id="96280-102">ICorDebugMutableDataTarget::WriteVirtual Method</span></span>
<span data-ttu-id="96280-103">Scrive dalla memoria nello spazio degli indirizzi del processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="96280-103">Writes memory into the target process address space.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96280-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="96280-104">Syntax</span></span>  
  
```  
HRESULT WriteVirtual(  
   [in] CORDB_ADDRESS address,  
   [in, size_is(bytesRequested)] const BYTE * pBuffer,  
   [in] ULONG32 bytesRequested);  
```  
  
## <a name="parameters"></a><span data-ttu-id="96280-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="96280-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="96280-106">[in] Indirizzo in cui scrivere il contenuto di `pBuffer`.</span><span class="sxs-lookup"><span data-stu-id="96280-106">[in] The address at which to write the contents of `pBuffer`.</span></span>  
  
 `pBuffer`  
 <span data-ttu-id="96280-107">[in] Puntatore a una matrice di byte che contiene i byte da scrivere.</span><span class="sxs-lookup"><span data-stu-id="96280-107">[in] A pointer to a byte array that contains the bytes to be written.</span></span>  
  
 `address`  
 <span data-ttu-id="96280-108">[in] Numero di byte in `pBuffer`.</span><span class="sxs-lookup"><span data-stu-id="96280-108">[in] The number of bytes in `pBuffer`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="96280-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="96280-109">Return Value</span></span>  
 <span data-ttu-id="96280-110">`S_OK` in caso di esito positivo o qualsiasi altro `HRESULT` in caso di errore.</span><span class="sxs-lookup"><span data-stu-id="96280-110">`S_OK` on success, or any other `HRESULT` on failure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="96280-111">Note</span><span class="sxs-lookup"><span data-stu-id="96280-111">Remarks</span></span>  
 <span data-ttu-id="96280-112">Se non è possibile scrivere dei byte, la chiamata al metodo non riesce e non modifica i byte nello spazio degli indirizzi di destinazione</span><span class="sxs-lookup"><span data-stu-id="96280-112">If any bytes cannot be written, the method call fails without changing any bytes in the target address space.</span></span> <span data-ttu-id="96280-113">(altrimenti la destinazione potrebbe trovarsi in uno stato incoerente che renderebbe il debug successivo inaffidabile).</span><span class="sxs-lookup"><span data-stu-id="96280-113">(Otherwise, the target would be in an inconsistent state that makes further debugging unreliable.)</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="96280-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="96280-114">Requirements</span></span>  
 <span data-ttu-id="96280-115">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="96280-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="96280-116">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="96280-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="96280-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="96280-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="96280-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="96280-118">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96280-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="96280-119">See also</span></span>
- [<span data-ttu-id="96280-120">Interfaccia ICorDebugMutableDataTarget</span><span class="sxs-lookup"><span data-stu-id="96280-120">ICorDebugMutableDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmutabledatatarget-interface.md)
- [<span data-ttu-id="96280-121">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="96280-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
