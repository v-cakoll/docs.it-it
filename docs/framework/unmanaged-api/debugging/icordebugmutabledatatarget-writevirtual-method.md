---
title: Metodo ICorDebugMutableDataTarget::WriteVirtual
ms.date: 03/30/2017
ms.assetid: 80833648-58a7-491a-8dc8-9a48e9bb3adc
ms.openlocfilehash: 2b4bd1dc97f37f5a514ab54f9e4d778fe3b91736
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792825"
---
# <a name="icordebugmutabledatatargetwritevirtual-method"></a><span data-ttu-id="511c2-102">Metodo ICorDebugMutableDataTarget::WriteVirtual</span><span class="sxs-lookup"><span data-stu-id="511c2-102">ICorDebugMutableDataTarget::WriteVirtual Method</span></span>
<span data-ttu-id="511c2-103">Scrive dalla memoria nello spazio degli indirizzi del processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="511c2-103">Writes memory into the target process address space.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="511c2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="511c2-104">Syntax</span></span>  
  
```cpp  
HRESULT WriteVirtual(  
   [in] CORDB_ADDRESS address,  
   [in, size_is(bytesRequested)] const BYTE * pBuffer,  
   [in] ULONG32 bytesRequested);  
```  
  
## <a name="parameters"></a><span data-ttu-id="511c2-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="511c2-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="511c2-106">[in] Indirizzo in cui scrivere il contenuto di `pBuffer`.</span><span class="sxs-lookup"><span data-stu-id="511c2-106">[in] The address at which to write the contents of `pBuffer`.</span></span>  
  
 `pBuffer`  
 <span data-ttu-id="511c2-107">[in] Puntatore a una matrice di byte che contiene i byte da scrivere.</span><span class="sxs-lookup"><span data-stu-id="511c2-107">[in] A pointer to a byte array that contains the bytes to be written.</span></span>  
  
 `address`  
 <span data-ttu-id="511c2-108">[in] Numero di byte in `pBuffer`.</span><span class="sxs-lookup"><span data-stu-id="511c2-108">[in] The number of bytes in `pBuffer`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="511c2-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="511c2-109">Return Value</span></span>  
 <span data-ttu-id="511c2-110">`S_OK` in caso di esito positivo o qualsiasi altro `HRESULT` in caso di errore.</span><span class="sxs-lookup"><span data-stu-id="511c2-110">`S_OK` on success, or any other `HRESULT` on failure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="511c2-111">Note</span><span class="sxs-lookup"><span data-stu-id="511c2-111">Remarks</span></span>  
 <span data-ttu-id="511c2-112">Se non è possibile scrivere dei byte, la chiamata al metodo non riesce e non modifica i byte nello spazio degli indirizzi di destinazione</span><span class="sxs-lookup"><span data-stu-id="511c2-112">If any bytes cannot be written, the method call fails without changing any bytes in the target address space.</span></span> <span data-ttu-id="511c2-113">(altrimenti la destinazione potrebbe trovarsi in uno stato incoerente che renderebbe il debug successivo inaffidabile).</span><span class="sxs-lookup"><span data-stu-id="511c2-113">(Otherwise, the target would be in an inconsistent state that makes further debugging unreliable.)</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="511c2-114">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="511c2-114">Requirements</span></span>  
 <span data-ttu-id="511c2-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="511c2-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="511c2-116">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="511c2-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="511c2-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="511c2-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="511c2-118">**Versioni .NET Framework:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="511c2-118">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="511c2-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="511c2-119">See also</span></span>

- [<span data-ttu-id="511c2-120">Interfaccia ICorDebugMutableDataTarget</span><span class="sxs-lookup"><span data-stu-id="511c2-120">ICorDebugMutableDataTarget Interface</span></span>](icordebugmutabledatatarget-interface.md)
- [<span data-ttu-id="511c2-121">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="511c2-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
