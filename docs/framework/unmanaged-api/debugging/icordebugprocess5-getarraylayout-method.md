---
title: Metodo ICorDebugProcess5::GetArrayLayout
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess5.GetArrayLayout
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess5::GetArrayLayout
helpviewer_keywords:
- ICorDebugProcess5::GetArrayLayout method [.NET Framework debugging]
- GetArrayLayout method, ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: 9a7393b9-9735-43c6-8616-afb103c432fd
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 608cf003d71599a141b1009ef16c7b7bf89161aa
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocess5getarraylayout-method"></a><span data-ttu-id="e7cfa-102">Metodo ICorDebugProcess5::GetArrayLayout</span><span class="sxs-lookup"><span data-stu-id="e7cfa-102">ICorDebugProcess5::GetArrayLayout Method</span></span>
<span data-ttu-id="e7cfa-103">Fornisce informazioni sul layout dei tipi di matrice.</span><span class="sxs-lookup"><span data-stu-id="e7cfa-103">Provides information about the layout of array types.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7cfa-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e7cfa-104">Syntax</span></span>  
  
```  
HRESULT GetArrayLayout(    [in] COR_TYPEID id,     [out] COR_ARRAY_LAYOUT *pLayout);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e7cfa-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e7cfa-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="e7cfa-106">[in] Oggetto [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) token che specifica la matrice il cui layout desiderato.</span><span class="sxs-lookup"><span data-stu-id="e7cfa-106">[in] A [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) token that specifies the array whose layout is desired.</span></span>  
  
 `pLayout`  
 <span data-ttu-id="e7cfa-107">[out] Un puntatore a un [COR_ARRAY_LAYOUT](../../../../docs/framework/unmanaged-api/debugging/cor-array-layout-structure.md) struttura che contiene informazioni sul layout della matrice in memoria.</span><span class="sxs-lookup"><span data-stu-id="e7cfa-107">[out] A pointer to a [COR_ARRAY_LAYOUT](../../../../docs/framework/unmanaged-api/debugging/cor-array-layout-structure.md) structure that contains information about the layout of the array in memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e7cfa-108">Note</span><span class="sxs-lookup"><span data-stu-id="e7cfa-108">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e7cfa-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e7cfa-109">Requirements</span></span>  
 <span data-ttu-id="e7cfa-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e7cfa-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e7cfa-111">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="e7cfa-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e7cfa-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e7cfa-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e7cfa-113">**Versioni di .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e7cfa-113">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7cfa-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e7cfa-114">See Also</span></span>  
 [<span data-ttu-id="e7cfa-115">Interfaccia ICorDebugProcess5</span><span class="sxs-lookup"><span data-stu-id="e7cfa-115">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)  
 [<span data-ttu-id="e7cfa-116">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="e7cfa-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
