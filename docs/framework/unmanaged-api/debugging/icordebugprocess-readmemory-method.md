---
title: Metodo ICorDebugProcess::ReadMemory
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.ReadMemory
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::ReadMemory
helpviewer_keywords:
- ReadMemory method [.NET Framework debugging]
- ICorDebugProcess::ReadMemory method [.NET Framework debugging]
ms.assetid: 28e4b2f6-9589-445c-be24-24a3306795e7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0d74da502492065dbffb5e5499581263760636c7
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67737072"
---
# <a name="icordebugprocessreadmemory-method"></a><span data-ttu-id="3136c-102">Metodo ICorDebugProcess::ReadMemory</span><span class="sxs-lookup"><span data-stu-id="3136c-102">ICorDebugProcess::ReadMemory Method</span></span>
<span data-ttu-id="3136c-103">Legge un'area specificata di memoria del processo.</span><span class="sxs-lookup"><span data-stu-id="3136c-103">Reads a specified area of memory for this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3136c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3136c-104">Syntax</span></span>  
  
```cpp  
HRESULT ReadMemory(  
    [in]  CORDB_ADDRESS address,   
    [in]  DWORD size,  
    [out, size_is(size), length_is(size)] BYTE buffer[],  
    [out] SIZE_T *read);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3136c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="3136c-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="3136c-106">[in] Oggetto `CORDB_ADDRESS` valore che specifica l'indirizzo di base della memoria da leggere.</span><span class="sxs-lookup"><span data-stu-id="3136c-106">[in] A `CORDB_ADDRESS` value that specifies the base address of the memory to be read.</span></span>  
  
 `size`  
 <span data-ttu-id="3136c-107">[in] Il numero di byte da leggere dalla memoria.</span><span class="sxs-lookup"><span data-stu-id="3136c-107">[in] The number of bytes to be read from memory.</span></span>  
  
 `buffer`  
 <span data-ttu-id="3136c-108">[out] Un buffer che riceve il contenuto della memoria.</span><span class="sxs-lookup"><span data-stu-id="3136c-108">[out] A buffer that receives the contents of the memory.</span></span>  
  
 `read`  
 <span data-ttu-id="3136c-109">[out] Un puntatore al numero di byte trasferiti nel buffer specificato.</span><span class="sxs-lookup"><span data-stu-id="3136c-109">[out] A pointer to the number of bytes transferred into the specified buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3136c-110">Note</span><span class="sxs-lookup"><span data-stu-id="3136c-110">Remarks</span></span>  
 <span data-ttu-id="3136c-111">Il `ReadMemory` metodo è principalmente destinato a essere usato per il debug di interoperabilità per controllare le aree della memoria in uso da parte dell'oggetto del debug non gestita.</span><span class="sxs-lookup"><span data-stu-id="3136c-111">The `ReadMemory` method is primarily intended to be used by interop debugging to inspect memory regions that are being used by the unmanaged portion of the debuggee.</span></span> <span data-ttu-id="3136c-112">Questo metodo può essere utilizzato anche leggere codice Microsoft intermediate language (MSIL) e codice nativo compilato tramite JIT.</span><span class="sxs-lookup"><span data-stu-id="3136c-112">This method can also be used to read Microsoft intermediate language (MSIL) code and native JIT-compiled code.</span></span>  
  
 <span data-ttu-id="3136c-113">Punti di interruzione gestite verrà rimossa dai dati che viene restituiti nel `buffer` parametro.</span><span class="sxs-lookup"><span data-stu-id="3136c-113">Any managed breakpoints will be removed from the data that is returned in the `buffer` parameter.</span></span> <span data-ttu-id="3136c-114">Non verrà eseguita alcuna modifica per impostare punti di interruzione native [ICorDebugProcess2::SetUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md).</span><span class="sxs-lookup"><span data-stu-id="3136c-114">No adjustments will be made for native breakpoints set by [ICorDebugProcess2::SetUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md).</span></span>  
  
 <span data-ttu-id="3136c-115">Nessuna memorizzazione nella cache della memoria del processo viene eseguito.</span><span class="sxs-lookup"><span data-stu-id="3136c-115">No caching of process memory is performed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3136c-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3136c-116">Requirements</span></span>  
 <span data-ttu-id="3136c-117">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3136c-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3136c-118">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3136c-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3136c-119">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3136c-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3136c-120">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3136c-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
