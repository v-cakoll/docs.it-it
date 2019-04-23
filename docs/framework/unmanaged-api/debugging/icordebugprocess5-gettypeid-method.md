---
title: Metodo ICorDebugProcess5::GetTypeID
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugProcess5.GetTypeID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::GetTypeID
helpviewer_keywords:
- ICorDebugProcess5::GetTypeID method [.NET Framework debugging]
- GetTypeID method, ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: 47dbaea4-8857-462e-93ba-fff880fc9e50
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 07c23a32037e83a878bb3136c48176f19249b207
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59173188"
---
# <a name="icordebugprocess5gettypeid-method"></a><span data-ttu-id="3080c-102">Metodo ICorDebugProcess5::GetTypeID</span><span class="sxs-lookup"><span data-stu-id="3080c-102">ICorDebugProcess5::GetTypeID Method</span></span>
<span data-ttu-id="3080c-103">Converte un indirizzo di oggetto a un [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) identificatore.</span><span class="sxs-lookup"><span data-stu-id="3080c-103">Converts an object address to a [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3080c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3080c-104">Syntax</span></span>  
  
```cpp
HRESULT GetTypeID(  
    [in] CORDB_ADDRESS obj,  
    [out] COR_TYPEID *pId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3080c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="3080c-105">Parameters</span></span>  
 `obj`  
 <span data-ttu-id="3080c-106">[in] L'indirizzo dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="3080c-106">[in] The object address.</span></span>  
  
 `pId`  
 <span data-ttu-id="3080c-107">Un puntatore per il [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) valore che identifica l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="3080c-107">A pointer to the [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) value that identifies the object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3080c-108">Note</span><span class="sxs-lookup"><span data-stu-id="3080c-108">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3080c-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3080c-109">Requirements</span></span>  
 <span data-ttu-id="3080c-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3080c-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3080c-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3080c-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3080c-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3080c-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3080c-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3080c-113">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3080c-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3080c-114">See also</span></span>

- [<span data-ttu-id="3080c-115">Interfaccia ICorDebugProcess5</span><span class="sxs-lookup"><span data-stu-id="3080c-115">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [<span data-ttu-id="3080c-116">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="3080c-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
