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
ms.openlocfilehash: 0a433ccb81ef62ac92a4553a838a2c98a04fc7c1
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212815"
---
# <a name="icordebugprocesswritememory-method"></a><span data-ttu-id="2ed26-102">Metodo ICorDebugProcess::WriteMemory</span><span class="sxs-lookup"><span data-stu-id="2ed26-102">ICorDebugProcess::WriteMemory Method</span></span>
<span data-ttu-id="2ed26-103">Scrive i dati in un'area di memoria in questo processo.</span><span class="sxs-lookup"><span data-stu-id="2ed26-103">Writes data to an area of memory in this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ed26-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2ed26-104">Syntax</span></span>  
  
```cpp  
HRESULT WriteMemory(  
    [in]  CORDB_ADDRESS address,  
    [in]  DWORD size,  
    [in, size_is(size)] BYTE buffer[],  
    [out] SIZE_T *written);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2ed26-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="2ed26-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="2ed26-106">in `CORDB_ADDRESS`Valore che rappresenta l'indirizzo di base dell'area di memoria in cui vengono scritti i dati.</span><span class="sxs-lookup"><span data-stu-id="2ed26-106">[in] A `CORDB_ADDRESS` value that is the base address of the memory area to which data is written.</span></span> <span data-ttu-id="2ed26-107">Prima che si verifichi il trasferimento dei dati, il sistema verifica che l'area di memoria della dimensione specificata, a partire dall'indirizzo di base, sia accessibile per la scrittura.</span><span class="sxs-lookup"><span data-stu-id="2ed26-107">Before data transfer occurs, the system verifies that the memory area of the specified size, beginning at the base address, is accessible for writing.</span></span> <span data-ttu-id="2ed26-108">Se non è accessibile, il metodo ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="2ed26-108">If it is not accessible, the method fails.</span></span>  
  
 `size`  
 <span data-ttu-id="2ed26-109">in Numero di byte da scrivere nell'area di memoria.</span><span class="sxs-lookup"><span data-stu-id="2ed26-109">[in] The number of bytes to be written to the memory area.</span></span>  
  
 `buffer`  
 <span data-ttu-id="2ed26-110">in Buffer contenente i dati da scrivere.</span><span class="sxs-lookup"><span data-stu-id="2ed26-110">[in] A buffer that contains data to be written.</span></span>  
  
 `written`  
 <span data-ttu-id="2ed26-111">out Puntatore a una variabile che riceve il numero di byte scritti nell'area di memoria del processo.</span><span class="sxs-lookup"><span data-stu-id="2ed26-111">[out] A pointer to a variable that receives the number of bytes written to the memory area in this process.</span></span> <span data-ttu-id="2ed26-112">Se `written` è null, questo parametro viene ignorato.</span><span class="sxs-lookup"><span data-stu-id="2ed26-112">If `written` is NULL, this parameter is ignored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2ed26-113">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="2ed26-113">Remarks</span></span>  
 <span data-ttu-id="2ed26-114">I dati vengono scritti automaticamente dietro i punti di interruzione.</span><span class="sxs-lookup"><span data-stu-id="2ed26-114">Data is automatically written behind any breakpoints.</span></span> <span data-ttu-id="2ed26-115">In .NET Framework versione 2,0 i debugger nativi non devono usare questo metodo per inserire i punti di interruzione nel flusso di istruzioni.</span><span class="sxs-lookup"><span data-stu-id="2ed26-115">In the .NET Framework version 2.0, native debuggers should not use this method to inject breakpoints into the instruction stream.</span></span> <span data-ttu-id="2ed26-116">Usare invece [ICorDebugProcess2:: SetUnmanagedBreakpoint](icordebugprocess2-setunmanagedbreakpoint-method.md) .</span><span class="sxs-lookup"><span data-stu-id="2ed26-116">Use [ICorDebugProcess2::SetUnmanagedBreakpoint](icordebugprocess2-setunmanagedbreakpoint-method.md) instead.</span></span>  
  
 <span data-ttu-id="2ed26-117">Il `WriteMemory` metodo deve essere utilizzato solo all'esterno del codice gestito.</span><span class="sxs-lookup"><span data-stu-id="2ed26-117">The `WriteMemory` method should be used only outside of managed code.</span></span> <span data-ttu-id="2ed26-118">Questo metodo può danneggiare il runtime se usato in modo errato.</span><span class="sxs-lookup"><span data-stu-id="2ed26-118">This method can corrupt the runtime if used improperly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2ed26-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2ed26-119">Requirements</span></span>  
 <span data-ttu-id="2ed26-120">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2ed26-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2ed26-121">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2ed26-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2ed26-122">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2ed26-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2ed26-123">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2ed26-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
