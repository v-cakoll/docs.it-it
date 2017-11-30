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
ms.openlocfilehash: b4c5d07e1645bc3736de2f8a298ad5b80e2cb26d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugprocess5getarraylayout-method"></a><span data-ttu-id="2f78a-102">Metodo ICorDebugProcess5::GetArrayLayout</span><span class="sxs-lookup"><span data-stu-id="2f78a-102">ICorDebugProcess5::GetArrayLayout Method</span></span>
<span data-ttu-id="2f78a-103">Fornisce informazioni sul layout dei tipi di matrice.</span><span class="sxs-lookup"><span data-stu-id="2f78a-103">Provides information about the layout of array types.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f78a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2f78a-104">Syntax</span></span>  
  
```  
HRESULT GetArrayLayout(    [in] COR_TYPEID id,     [out] COR_ARRAY_LAYOUT *pLayout);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2f78a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="2f78a-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="2f78a-106">[in] Oggetto [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) token che specifica la matrice il cui layout desiderato.</span><span class="sxs-lookup"><span data-stu-id="2f78a-106">[in] A [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) token that specifies the array whose layout is desired.</span></span>  
  
 `pLayout`  
 <span data-ttu-id="2f78a-107">[out] Un puntatore a un [COR_ARRAY_LAYOUT](../../../../docs/framework/unmanaged-api/debugging/cor-array-layout-structure.md) struttura che contiene informazioni sul layout della matrice in memoria.</span><span class="sxs-lookup"><span data-stu-id="2f78a-107">[out] A pointer to a [COR_ARRAY_LAYOUT](../../../../docs/framework/unmanaged-api/debugging/cor-array-layout-structure.md) structure that contains information about the layout of the array in memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2f78a-108">Note</span><span class="sxs-lookup"><span data-stu-id="2f78a-108">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2f78a-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2f78a-109">Requirements</span></span>  
 <span data-ttu-id="2f78a-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2f78a-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2f78a-111">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="2f78a-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2f78a-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2f78a-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2f78a-113">**Versioni di .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2f78a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f78a-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2f78a-114">See Also</span></span>  
 [<span data-ttu-id="2f78a-115">ICorDebugProcess5 (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="2f78a-115">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)  
 [<span data-ttu-id="2f78a-116">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="2f78a-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
