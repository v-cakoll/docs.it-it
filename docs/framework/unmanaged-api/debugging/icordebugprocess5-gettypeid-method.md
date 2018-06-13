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
ms.openlocfilehash: b63c6ca8ead2a401f907ea6569e966c6470aca13
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33421951"
---
# <a name="icordebugprocess5gettypeid-method"></a><span data-ttu-id="1308a-102">Metodo ICorDebugProcess5::GetTypeID</span><span class="sxs-lookup"><span data-stu-id="1308a-102">ICorDebugProcess5::GetTypeID Method</span></span>
<span data-ttu-id="1308a-103">Converte un indirizzo di oggetto a un [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) identificatore.</span><span class="sxs-lookup"><span data-stu-id="1308a-103">Converts an object address to a [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1308a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1308a-104">Syntax</span></span>  
  
```cpp
HRESULT GetTypeID(  
    [in] CORDB_ADDRESS obj,  
    [out] COR_TYPEID *pId  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1308a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="1308a-105">Parameters</span></span>  
 `obj`  
 <span data-ttu-id="1308a-106">[in] L'indirizzo dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="1308a-106">[in] The object address.</span></span>  
  
 `pId`  
 <span data-ttu-id="1308a-107">Un puntatore al [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) valore che identifica l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="1308a-107">A pointer to the [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) value that identifies the object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1308a-108">Note</span><span class="sxs-lookup"><span data-stu-id="1308a-108">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1308a-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1308a-109">Requirements</span></span>  
 <span data-ttu-id="1308a-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1308a-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1308a-111">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="1308a-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1308a-112">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="1308a-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1308a-113">**Versioni di .NET framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1308a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1308a-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1308a-114">See Also</span></span>  
 [<span data-ttu-id="1308a-115">Interfaccia ICorDebugProcess5</span><span class="sxs-lookup"><span data-stu-id="1308a-115">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)  
 [<span data-ttu-id="1308a-116">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="1308a-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
