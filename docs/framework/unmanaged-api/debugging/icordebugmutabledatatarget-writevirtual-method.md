---
title: 'Metodo ICorDebugMutableDataTarget:: WriteVirtual'
ms.date: 03/30/2017
ms.assetid: 80833648-58a7-491a-8dc8-9a48e9bb3adc
ms.openlocfilehash: 5947caa8dfb97574bb4b3c5634d962df153211c7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132685"
---
# <a name="icordebugmutabledatatargetwritevirtual-method"></a><span data-ttu-id="08934-102">Metodo ICorDebugMutableDataTarget:: WriteVirtual</span><span class="sxs-lookup"><span data-stu-id="08934-102">ICorDebugMutableDataTarget::WriteVirtual Method</span></span>
<span data-ttu-id="08934-103">Scrive dalla memoria nello spazio degli indirizzi del processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="08934-103">Writes memory into the target process address space.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08934-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="08934-104">Syntax</span></span>  
  
```cpp  
HRESULT WriteVirtual(  
   [in] CORDB_ADDRESS address,  
   [in, size_is(bytesRequested)] const BYTE * pBuffer,  
   [in] ULONG32 bytesRequested);  
```  
  
## <a name="parameters"></a><span data-ttu-id="08934-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="08934-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="08934-106">[in] Indirizzo in cui scrivere il contenuto di `pBuffer`.</span><span class="sxs-lookup"><span data-stu-id="08934-106">[in] The address at which to write the contents of `pBuffer`.</span></span>  
  
 `pBuffer`  
 <span data-ttu-id="08934-107">[in] Puntatore a una matrice di byte che contiene i byte da scrivere.</span><span class="sxs-lookup"><span data-stu-id="08934-107">[in] A pointer to a byte array that contains the bytes to be written.</span></span>  
  
 `address`  
 <span data-ttu-id="08934-108">[in] Numero di byte in `pBuffer`.</span><span class="sxs-lookup"><span data-stu-id="08934-108">[in] The number of bytes in `pBuffer`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="08934-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="08934-109">Return Value</span></span>  
 <span data-ttu-id="08934-110">`S_OK` in caso di esito positivo o qualsiasi altro `HRESULT` in caso di errore.</span><span class="sxs-lookup"><span data-stu-id="08934-110">`S_OK` on success, or any other `HRESULT` on failure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="08934-111">Note</span><span class="sxs-lookup"><span data-stu-id="08934-111">Remarks</span></span>  
 <span data-ttu-id="08934-112">Se non è possibile scrivere dei byte, la chiamata al metodo non riesce e non modifica i byte nello spazio degli indirizzi di destinazione</span><span class="sxs-lookup"><span data-stu-id="08934-112">If any bytes cannot be written, the method call fails without changing any bytes in the target address space.</span></span> <span data-ttu-id="08934-113">(altrimenti la destinazione potrebbe trovarsi in uno stato incoerente che renderebbe il debug successivo inaffidabile).</span><span class="sxs-lookup"><span data-stu-id="08934-113">(Otherwise, the target would be in an inconsistent state that makes further debugging unreliable.)</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="08934-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="08934-114">Requirements</span></span>  
 <span data-ttu-id="08934-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="08934-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="08934-116">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="08934-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="08934-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="08934-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="08934-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="08934-118">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08934-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="08934-119">See also</span></span>

- [<span data-ttu-id="08934-120">Interfaccia ICorDebugMutableDataTarget</span><span class="sxs-lookup"><span data-stu-id="08934-120">ICorDebugMutableDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmutabledatatarget-interface.md)
- [<span data-ttu-id="08934-121">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="08934-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
