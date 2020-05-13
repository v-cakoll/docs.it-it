---
title: Metodo ICorDebugHeapValue2::CreateHandle
ms.date: 03/30/2017
api_name:
- ICorDebugHeapValue2.CreateHandle
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapValue2::CreateHandle
helpviewer_keywords:
- CreateHandle method [.NET Framework debugging]
- ICorDebugHeapValue2::CreateHandle method [.NET Framework debugging]
ms.assetid: fbc418e8-fa22-420d-84ec-e0e1800db041
topic_type:
- apiref
ms.openlocfilehash: cbc056e9a3cc00178b32dee4011da4403dff508a
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212776"
---
# <a name="icordebugheapvalue2createhandle-method"></a><span data-ttu-id="e5bf7-102">Metodo ICorDebugHeapValue2::CreateHandle</span><span class="sxs-lookup"><span data-stu-id="e5bf7-102">ICorDebugHeapValue2::CreateHandle Method</span></span>
<span data-ttu-id="e5bf7-103">Crea un handle del tipo specificato per il valore dell'heap rappresentato da questo oggetto ICorDebugHeapValue2.</span><span class="sxs-lookup"><span data-stu-id="e5bf7-103">Creates a handle of the specified type for the heap value represented by this ICorDebugHeapValue2 object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5bf7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e5bf7-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateHandle (  
    [in] CorDebugHandleType      type,
    [out] ICorDebugHandleValue   **ppHandle  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e5bf7-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e5bf7-105">Parameters</span></span>  
 `type`  
 <span data-ttu-id="e5bf7-106">in Valore dell'enumerazione CorDebugHandleType che specifica il tipo di handle da creare.</span><span class="sxs-lookup"><span data-stu-id="e5bf7-106">[in] A value of the CorDebugHandleType enumeration that specifies the type of handle to be created.</span></span>  
  
 `ppHandle`  
 <span data-ttu-id="e5bf7-107">out Puntatore all'indirizzo di un oggetto ICorDebugHandleValue che rappresenta il nuovo handle per questo valore dell'heap.</span><span class="sxs-lookup"><span data-stu-id="e5bf7-107">[out] A pointer to the address of an ICorDebugHandleValue object that represents the new handle for this heap value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e5bf7-108">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="e5bf7-108">Remarks</span></span>  
 <span data-ttu-id="e5bf7-109">L'handle verrà creato nel dominio applicazione associato al valore dell'heap e diventerà non valido se il dominio applicazione viene scaricato.</span><span class="sxs-lookup"><span data-stu-id="e5bf7-109">The handle will be created in the application domain that is associated with the heap value, and will become invalid if the application domain gets unloaded.</span></span>  
  
 <span data-ttu-id="e5bf7-110">Più chiamate a questa funzione per lo stesso valore heap creeranno più handle.</span><span class="sxs-lookup"><span data-stu-id="e5bf7-110">Multiple calls to this function for the same heap value will create multiple handles.</span></span> <span data-ttu-id="e5bf7-111">Poiché gli handle influiscono sulle prestazioni del Garbage Collector, il debugger deve limitarsi a un numero relativamente piccolo di handle (circa 256) attivi alla volta.</span><span class="sxs-lookup"><span data-stu-id="e5bf7-111">Because handles affect the performance of the garbage collector, the debugger should limit itself to a relatively small number of handles (about 256) that are active at a time.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5bf7-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e5bf7-112">Requirements</span></span>  
 <span data-ttu-id="e5bf7-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e5bf7-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e5bf7-114">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e5bf7-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e5bf7-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e5bf7-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e5bf7-116">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e5bf7-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
