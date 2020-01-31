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
ms.openlocfilehash: dca2a4e5ee869346108137a8ba01ab8855756725
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792562"
---
# <a name="icordebugprocessreadmemory-method"></a><span data-ttu-id="2bde5-102">Metodo ICorDebugProcess::ReadMemory</span><span class="sxs-lookup"><span data-stu-id="2bde5-102">ICorDebugProcess::ReadMemory Method</span></span>
<span data-ttu-id="2bde5-103">Legge un'area di memoria specificata per questo processo.</span><span class="sxs-lookup"><span data-stu-id="2bde5-103">Reads a specified area of memory for this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2bde5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2bde5-104">Syntax</span></span>  
  
```cpp  
HRESULT ReadMemory(  
    [in]  CORDB_ADDRESS address,   
    [in]  DWORD size,  
    [out, size_is(size), length_is(size)] BYTE buffer[],  
    [out] SIZE_T *read);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2bde5-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="2bde5-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="2bde5-106">in Valore `CORDB_ADDRESS` che specifica l'indirizzo di base della memoria da leggere.</span><span class="sxs-lookup"><span data-stu-id="2bde5-106">[in] A `CORDB_ADDRESS` value that specifies the base address of the memory to be read.</span></span>  
  
 `size`  
 <span data-ttu-id="2bde5-107">in Numero di byte da leggere dalla memoria.</span><span class="sxs-lookup"><span data-stu-id="2bde5-107">[in] The number of bytes to be read from memory.</span></span>  
  
 `buffer`  
 <span data-ttu-id="2bde5-108">out Buffer che riceve il contenuto della memoria.</span><span class="sxs-lookup"><span data-stu-id="2bde5-108">[out] A buffer that receives the contents of the memory.</span></span>  
  
 `read`  
 <span data-ttu-id="2bde5-109">out Puntatore al numero di byte trasferiti nel buffer specificato.</span><span class="sxs-lookup"><span data-stu-id="2bde5-109">[out] A pointer to the number of bytes transferred into the specified buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2bde5-110">Note</span><span class="sxs-lookup"><span data-stu-id="2bde5-110">Remarks</span></span>  
 <span data-ttu-id="2bde5-111">Il metodo `ReadMemory` è destinato principalmente a essere utilizzato dal debug di interoperabilità per esaminare le aree di memoria utilizzate dalla parte non gestita dell'oggetto del debug.</span><span class="sxs-lookup"><span data-stu-id="2bde5-111">The `ReadMemory` method is primarily intended to be used by interop debugging to inspect memory regions that are being used by the unmanaged portion of the debuggee.</span></span> <span data-ttu-id="2bde5-112">Questo metodo può essere utilizzato anche per leggere codice MSIL (Microsoft Intermediate Language) e codice nativo compilato tramite JIT.</span><span class="sxs-lookup"><span data-stu-id="2bde5-112">This method can also be used to read Microsoft intermediate language (MSIL) code and native JIT-compiled code.</span></span>  
  
 <span data-ttu-id="2bde5-113">Eventuali punti di interruzione gestiti verranno rimossi dai dati restituiti nel parametro `buffer`.</span><span class="sxs-lookup"><span data-stu-id="2bde5-113">Any managed breakpoints will be removed from the data that is returned in the `buffer` parameter.</span></span> <span data-ttu-id="2bde5-114">Non verranno apportate modifiche per i punti di interruzione nativi impostati da [ICorDebugProcess2:: SetUnmanagedBreakpoint](icordebugprocess2-setunmanagedbreakpoint-method.md).</span><span class="sxs-lookup"><span data-stu-id="2bde5-114">No adjustments will be made for native breakpoints set by [ICorDebugProcess2::SetUnmanagedBreakpoint](icordebugprocess2-setunmanagedbreakpoint-method.md).</span></span>  
  
 <span data-ttu-id="2bde5-115">Non viene eseguita la memorizzazione nella cache della memoria del processo.</span><span class="sxs-lookup"><span data-stu-id="2bde5-115">No caching of process memory is performed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2bde5-116">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="2bde5-116">Requirements</span></span>  
 <span data-ttu-id="2bde5-117">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2bde5-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2bde5-118">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2bde5-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2bde5-119">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2bde5-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2bde5-120">**Versioni .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2bde5-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
