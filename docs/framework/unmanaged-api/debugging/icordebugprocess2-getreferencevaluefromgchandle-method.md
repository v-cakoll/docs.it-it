---
title: Metodo ICorDebugProcess2::GetReferenceValueFromGCHandle
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2.GetReferenceValueFromGCHandle
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2::GetReferenceValueFromGCHandle
helpviewer_keywords:
- GetReferenceValueFromGCHandle method [.NET Framework debugging]
- ICorDebugProcess2::GetReferenceValueFromGCHandle method [.NET Framework debugging]
ms.assetid: 8bdd7f4c-19f2-4ede-875e-603773e8c128
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 21da325ee58df65ac449464f8292f2ba94d99338
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69943289"
---
# <a name="icordebugprocess2getreferencevaluefromgchandle-method"></a><span data-ttu-id="596e9-102">Metodo ICorDebugProcess2::GetReferenceValueFromGCHandle</span><span class="sxs-lookup"><span data-stu-id="596e9-102">ICorDebugProcess2::GetReferenceValueFromGCHandle Method</span></span>
<span data-ttu-id="596e9-103">Ottiene un puntatore di riferimento all'oggetto gestito specificato con un handle Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="596e9-103">Gets a reference pointer to the specified managed object that has a garbage collection handle.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="596e9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="596e9-104">Syntax</span></span>  
  
```cpp  
HRESULT GetReferenceValueFromGCHandle (  
    [in]  UINT_PTR                 handle,  
    [out] ICorDebugReferenceValue  **pOutValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="596e9-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="596e9-105">Parameters</span></span>  
 `handle`  
 <span data-ttu-id="596e9-106">in Puntatore a un oggetto gestito che dispone di un handle Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="596e9-106">[in] A pointer to a managed object that has a garbage collection handle.</span></span> <span data-ttu-id="596e9-107">Questo valore è un <xref:System.IntPtr> oggetto e può essere recuperato <xref:System.Runtime.InteropServices.GCHandle> da per l'oggetto gestito.</span><span class="sxs-lookup"><span data-stu-id="596e9-107">This value is a <xref:System.IntPtr> object and can be retrieved from the <xref:System.Runtime.InteropServices.GCHandle> for the managed object.</span></span>  
  
 `pOutValue`  
 <span data-ttu-id="596e9-108">out Puntatore all'indirizzo di un oggetto ICorDebugReferenceValue che rappresenta un riferimento all'oggetto gestito specificato.</span><span class="sxs-lookup"><span data-stu-id="596e9-108">[out] A pointer to the address of an ICorDebugReferenceValue object that represents a reference to the specified managed object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="596e9-109">Note</span><span class="sxs-lookup"><span data-stu-id="596e9-109">Remarks</span></span>  
 <span data-ttu-id="596e9-110">Non confondere il valore di riferimento restituito con un Garbage Collection valore di riferimento.</span><span class="sxs-lookup"><span data-stu-id="596e9-110">Do not confuse the returned reference value with a garbage collection reference value.</span></span>  
  
 <span data-ttu-id="596e9-111">Il riferimento restituito si comporta come un riferimento normale.</span><span class="sxs-lookup"><span data-stu-id="596e9-111">The returned reference behaves like a normal reference.</span></span> <span data-ttu-id="596e9-112">Viene disabilitato quando l'esecuzione del codice continua dopo un punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="596e9-112">It is disabled when code execution continues after a breakpoint.</span></span> <span data-ttu-id="596e9-113">La durata dell'oggetto di destinazione non è influenzata dalla durata del valore di riferimento.</span><span class="sxs-lookup"><span data-stu-id="596e9-113">The lifetime of the target object is not affected by the lifetime of the reference value.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="596e9-114">Il `GetReferenceValueFromGCHandle` metodo non convalida l'handle.</span><span class="sxs-lookup"><span data-stu-id="596e9-114">The `GetReferenceValueFromGCHandle` method does not validate the handle.</span></span> <span data-ttu-id="596e9-115">Pertanto, il `GetReferenceValueFromGCHandle` metodo può potenzialmente danneggiare sia il debugger che il codice sottoposto a debug se viene passato un handle non valido.</span><span class="sxs-lookup"><span data-stu-id="596e9-115">Therefore, the `GetReferenceValueFromGCHandle` method can potentially corrupt both the debugger and the code being debugged if an invalid handle is passed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="596e9-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="596e9-116">Requirements</span></span>  
 <span data-ttu-id="596e9-117">**Piattaforme** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="596e9-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="596e9-118">**Intestazione:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="596e9-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="596e9-119">**Libreria** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="596e9-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="596e9-120">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="596e9-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
