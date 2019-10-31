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
ms.openlocfilehash: 47647bf0460507b4c88b47bf87bfcc3bf620aecc
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137213"
---
# <a name="icordebugprocess2getreferencevaluefromgchandle-method"></a><span data-ttu-id="a2a40-102">Metodo ICorDebugProcess2::GetReferenceValueFromGCHandle</span><span class="sxs-lookup"><span data-stu-id="a2a40-102">ICorDebugProcess2::GetReferenceValueFromGCHandle Method</span></span>
<span data-ttu-id="a2a40-103">Ottiene un puntatore di riferimento all'oggetto gestito specificato con un handle Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="a2a40-103">Gets a reference pointer to the specified managed object that has a garbage collection handle.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2a40-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a2a40-104">Syntax</span></span>  
  
```cpp  
HRESULT GetReferenceValueFromGCHandle (  
    [in]  UINT_PTR                 handle,  
    [out] ICorDebugReferenceValue  **pOutValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a2a40-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a2a40-105">Parameters</span></span>  
 `handle`  
 <span data-ttu-id="a2a40-106">in Puntatore a un oggetto gestito che dispone di un handle Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="a2a40-106">[in] A pointer to a managed object that has a garbage collection handle.</span></span> <span data-ttu-id="a2a40-107">Questo valore è un oggetto <xref:System.IntPtr> e può essere recuperato dall'<xref:System.Runtime.InteropServices.GCHandle> per l'oggetto gestito.</span><span class="sxs-lookup"><span data-stu-id="a2a40-107">This value is a <xref:System.IntPtr> object and can be retrieved from the <xref:System.Runtime.InteropServices.GCHandle> for the managed object.</span></span>  
  
 `pOutValue`  
 <span data-ttu-id="a2a40-108">out Puntatore all'indirizzo di un oggetto ICorDebugReferenceValue che rappresenta un riferimento all'oggetto gestito specificato.</span><span class="sxs-lookup"><span data-stu-id="a2a40-108">[out] A pointer to the address of an ICorDebugReferenceValue object that represents a reference to the specified managed object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a2a40-109">Note</span><span class="sxs-lookup"><span data-stu-id="a2a40-109">Remarks</span></span>  
 <span data-ttu-id="a2a40-110">Non confondere il valore di riferimento restituito con un Garbage Collection valore di riferimento.</span><span class="sxs-lookup"><span data-stu-id="a2a40-110">Do not confuse the returned reference value with a garbage collection reference value.</span></span>  
  
 <span data-ttu-id="a2a40-111">Il riferimento restituito si comporta come un riferimento normale.</span><span class="sxs-lookup"><span data-stu-id="a2a40-111">The returned reference behaves like a normal reference.</span></span> <span data-ttu-id="a2a40-112">Viene disabilitato quando l'esecuzione del codice continua dopo un punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="a2a40-112">It is disabled when code execution continues after a breakpoint.</span></span> <span data-ttu-id="a2a40-113">La durata dell'oggetto di destinazione non è influenzata dalla durata del valore di riferimento.</span><span class="sxs-lookup"><span data-stu-id="a2a40-113">The lifetime of the target object is not affected by the lifetime of the reference value.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a2a40-114">Il metodo `GetReferenceValueFromGCHandle` non convalida l'handle.</span><span class="sxs-lookup"><span data-stu-id="a2a40-114">The `GetReferenceValueFromGCHandle` method does not validate the handle.</span></span> <span data-ttu-id="a2a40-115">Pertanto, il metodo `GetReferenceValueFromGCHandle` può potenzialmente danneggiare sia il debugger che il codice sottoposto a debug se viene passato un handle non valido.</span><span class="sxs-lookup"><span data-stu-id="a2a40-115">Therefore, the `GetReferenceValueFromGCHandle` method can potentially corrupt both the debugger and the code being debugged if an invalid handle is passed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a2a40-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a2a40-116">Requirements</span></span>  
 <span data-ttu-id="a2a40-117">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a2a40-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a2a40-118">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a2a40-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a2a40-119">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a2a40-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a2a40-120">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a2a40-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
