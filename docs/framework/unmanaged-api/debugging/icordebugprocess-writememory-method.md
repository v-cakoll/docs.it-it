---
title: Metodo ICorDebugProcess::WriteMemory
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.WriteMemory
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::WriteMemory
helpviewer_keywords:
- ICorDebugProcess::WriteMemory method [.NET Framework debugging]
- WriteMemory method [.NET Framework debugging]
ms.assetid: d5c07d86-045d-4391-893b-0bcd2959f90e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2e9d640fb1c9dae5bb195baa504e560ba8e45821
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61930299"
---
# <a name="icordebugprocesswritememory-method"></a><span data-ttu-id="2a5f6-102">Metodo ICorDebugProcess::WriteMemory</span><span class="sxs-lookup"><span data-stu-id="2a5f6-102">ICorDebugProcess::WriteMemory Method</span></span>
<span data-ttu-id="2a5f6-103">Scrive dati in un'area di memoria di questo processo.</span><span class="sxs-lookup"><span data-stu-id="2a5f6-103">Writes data to an area of memory in this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a5f6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2a5f6-104">Syntax</span></span>  
  
```  
HRESULT WriteMemory(  
    [in]  CORDB_ADDRESS address,  
    [in]  DWORD size,  
    [in, size_is(size)] BYTE buffer[],  
    [out] SIZE_T *written);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2a5f6-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="2a5f6-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="2a5f6-106">[in] Oggetto `CORDB_ADDRESS` valore, ovvero l'indirizzo di base dell'area di memoria a dati che viene scritto.</span><span class="sxs-lookup"><span data-stu-id="2a5f6-106">[in] A `CORDB_ADDRESS` value that is the base address of the memory area to which data is written.</span></span> <span data-ttu-id="2a5f6-107">Prima che si verifichi il trasferimento dei dati, il sistema verifica che l'area di memoria della dimensione specificata, iniziando in corrispondenza l'indirizzo di base, sia accessibile in scrittura.</span><span class="sxs-lookup"><span data-stu-id="2a5f6-107">Before data transfer occurs, the system verifies that the memory area of the specified size, beginning at the base address, is accessible for writing.</span></span> <span data-ttu-id="2a5f6-108">Se non è accessibile, il metodo ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="2a5f6-108">If it is not accessible, the method fails.</span></span>  
  
 `size`  
 <span data-ttu-id="2a5f6-109">[in] Il numero di byte da scrivere nell'area di memoria.</span><span class="sxs-lookup"><span data-stu-id="2a5f6-109">[in] The number of bytes to be written to the memory area.</span></span>  
  
 `buffer`  
 <span data-ttu-id="2a5f6-110">[in] Un buffer contenente dati da scrivere.</span><span class="sxs-lookup"><span data-stu-id="2a5f6-110">[in] A buffer that contains data to be written.</span></span>  
  
 `written`  
 <span data-ttu-id="2a5f6-111">[out] Un puntatore a una variabile che riceve il numero di byte scritti nell'area di memoria di questo processo.</span><span class="sxs-lookup"><span data-stu-id="2a5f6-111">[out] A pointer to a variable that receives the number of bytes written to the memory area in this process.</span></span> <span data-ttu-id="2a5f6-112">Se `written` è NULL, questo parametro viene ignorato.</span><span class="sxs-lookup"><span data-stu-id="2a5f6-112">If `written` is NULL, this parameter is ignored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2a5f6-113">Note</span><span class="sxs-lookup"><span data-stu-id="2a5f6-113">Remarks</span></span>  
 <span data-ttu-id="2a5f6-114">Dati vengono scritti automaticamente protetti da qualsiasi punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="2a5f6-114">Data is automatically written behind any breakpoints.</span></span> <span data-ttu-id="2a5f6-115">In .NET Framework versione 2.0, debugger nativo non devono usare questo metodo per inserire i punti di interruzione nel flusso di istruzioni.</span><span class="sxs-lookup"><span data-stu-id="2a5f6-115">In the .NET Framework version 2.0, native debuggers should not use this method to inject breakpoints into the instruction stream.</span></span> <span data-ttu-id="2a5f6-116">Uso [ICorDebugProcess2::SetUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md) invece.</span><span class="sxs-lookup"><span data-stu-id="2a5f6-116">Use [ICorDebugProcess2::SetUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md) instead.</span></span>  
  
 <span data-ttu-id="2a5f6-117">Il `WriteMemory` metodo deve essere usato solo all'esterno di codice gestito.</span><span class="sxs-lookup"><span data-stu-id="2a5f6-117">The `WriteMemory` method should be used only outside of managed code.</span></span> <span data-ttu-id="2a5f6-118">Questo metodo può danneggiare il runtime se utilizzato in modo non corretto.</span><span class="sxs-lookup"><span data-stu-id="2a5f6-118">This method can corrupt the runtime if used improperly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2a5f6-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2a5f6-119">Requirements</span></span>  
 <span data-ttu-id="2a5f6-120">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2a5f6-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2a5f6-121">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2a5f6-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2a5f6-122">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2a5f6-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2a5f6-123">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2a5f6-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
