---
title: Metodo ICorDebugProcess2::GetReferenceValueFromGCHandle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess2.GetReferenceValueFromGCHandle
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess2::GetReferenceValueFromGCHandle
helpviewer_keywords:
- GetReferenceValueFromGCHandle method [.NET Framework debugging]
- ICorDebugProcess2::GetReferenceValueFromGCHandle method [.NET Framework debugging]
ms.assetid: 8bdd7f4c-19f2-4ede-875e-603773e8c128
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d40d1799a7c1572e8213fda3a163fb9a84060f92
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugprocess2getreferencevaluefromgchandle-method"></a><span data-ttu-id="c4b7b-102">Metodo ICorDebugProcess2::GetReferenceValueFromGCHandle</span><span class="sxs-lookup"><span data-stu-id="c4b7b-102">ICorDebugProcess2::GetReferenceValueFromGCHandle Method</span></span>
<span data-ttu-id="c4b7b-103">Ottiene un puntatore di riferimento all'oggetto gestito specificato dotato di gestire un'operazione di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="c4b7b-103">Gets a reference pointer to the specified managed object that has a garbage collection handle.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4b7b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c4b7b-104">Syntax</span></span>  
  
```  
HRESULT GetReferenceValueFromGCHandle (  
    [in]  UINT_PTR                 handle,  
    [out] ICorDebugReferenceValue  **pOutValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c4b7b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c4b7b-105">Parameters</span></span>  
 `handle`  
 <span data-ttu-id="c4b7b-106">[in] Puntatore a un oggetto gestito che presenta un handle di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="c4b7b-106">[in] A pointer to a managed object that has a garbage collection handle.</span></span> <span data-ttu-id="c4b7b-107">Questo valore è un <xref:System.IntPtr> dell'oggetto e può essere recuperato dal <xref:System.Runtime.InteropServices.GCHandle> per l'oggetto gestito.</span><span class="sxs-lookup"><span data-stu-id="c4b7b-107">This value is a <xref:System.IntPtr> object and can be retrieved from the <xref:System.Runtime.InteropServices.GCHandle> for the managed object.</span></span>  
  
 `pOutValue`  
 <span data-ttu-id="c4b7b-108">[out] Un puntatore all'indirizzo di un oggetto ICorDebugReferenceValue che rappresenta un riferimento all'oggetto gestito specificato.</span><span class="sxs-lookup"><span data-stu-id="c4b7b-108">[out] A pointer to the address of an ICorDebugReferenceValue object that represents a reference to the specified managed object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c4b7b-109">Note</span><span class="sxs-lookup"><span data-stu-id="c4b7b-109">Remarks</span></span>  
 <span data-ttu-id="c4b7b-110">Non confondere il valore restituito di riferimento con un valore di riferimento di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="c4b7b-110">Do not confuse the returned reference value with a garbage collection reference value.</span></span>  
  
 <span data-ttu-id="c4b7b-111">Il riferimento restituito si comporta come un normale riferimento.</span><span class="sxs-lookup"><span data-stu-id="c4b7b-111">The returned reference behaves like a normal reference.</span></span> <span data-ttu-id="c4b7b-112">Viene disabilitato quando l'esecuzione del codice continua dopo un punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="c4b7b-112">It is disabled when code execution continues after a breakpoint.</span></span> <span data-ttu-id="c4b7b-113">La durata dell'oggetto di destinazione non è interessata dalla durata del valore di riferimento.</span><span class="sxs-lookup"><span data-stu-id="c4b7b-113">The lifetime of the target object is not affected by the lifetime of the reference value.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c4b7b-114">Il `GetReferenceValueFromGCHandle` metodo non convalida l'handle.</span><span class="sxs-lookup"><span data-stu-id="c4b7b-114">The `GetReferenceValueFromGCHandle` method does not validate the handle.</span></span> <span data-ttu-id="c4b7b-115">Pertanto, il `GetReferenceValueFromGCHandle` metodo può potenzialmente danneggiare il debugger sia il codice sottoposto a debug se viene passato un handle non valido.</span><span class="sxs-lookup"><span data-stu-id="c4b7b-115">Therefore, the `GetReferenceValueFromGCHandle` method can potentially corrupt both the debugger and the code being debugged if an invalid handle is passed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c4b7b-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c4b7b-116">Requirements</span></span>  
 <span data-ttu-id="c4b7b-117">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c4b7b-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c4b7b-118">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="c4b7b-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c4b7b-119">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c4b7b-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c4b7b-120">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c4b7b-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
