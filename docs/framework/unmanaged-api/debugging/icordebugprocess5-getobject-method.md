---
title: Metodo ICorDebugProcess5::GetObject
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.GetObject
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::GetObject
helpviewer_keywords:
- GetObject method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::GetObject method [.NET Framework debugging]
ms.assetid: c8111502-5a20-447f-9dc2-76e8acd7ed5a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4fa6a8c4989b6bc7027a585f098e0aedf17fee01
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33417284"
---
# <a name="icordebugprocess5getobject-method"></a><span data-ttu-id="673ed-102">Metodo ICorDebugProcess5::GetObject</span><span class="sxs-lookup"><span data-stu-id="673ed-102">ICorDebugProcess5::GetObject Method</span></span>
<span data-ttu-id="673ed-103">Converte un indirizzo di oggetto in un oggetto "ICorDebugObjectValue".</span><span class="sxs-lookup"><span data-stu-id="673ed-103">Converts an object address to an "ICorDebugObjectValue" object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="673ed-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="673ed-104">Syntax</span></span>  
  
```  
HRESULT GetObject(  
    [in] CORDB_ADDRESS addr,   
    [out] ICorDebugObjectValue **ppObject  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="673ed-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="673ed-105">Parameters</span></span>  
 `addr`  
 <span data-ttu-id="673ed-106">[in] L'indirizzo dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="673ed-106">[in] The object address.</span></span>  
  
 `ppObject`  
 <span data-ttu-id="673ed-107">[out] Un puntatore all'indirizzo di un oggetto "ICorDebugObjectValue".</span><span class="sxs-lookup"><span data-stu-id="673ed-107">[out] A pointer to the address of an  "ICorDebugObjectValue" object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="673ed-108">Note</span><span class="sxs-lookup"><span data-stu-id="673ed-108">Remarks</span></span>  
 <span data-ttu-id="673ed-109">Se `addr` non punta a un oggetto gestito valido, il `GetObject` restituisce `E_FAIL`.</span><span class="sxs-lookup"><span data-stu-id="673ed-109">If `addr` does not point to a valid managed object, the `GetObject` method returns `E_FAIL`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="673ed-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="673ed-110">Requirements</span></span>  
 <span data-ttu-id="673ed-111">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="673ed-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="673ed-112">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="673ed-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="673ed-113">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="673ed-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="673ed-114">**Versioni di .NET framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="673ed-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="673ed-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="673ed-115">See Also</span></span>  
 [<span data-ttu-id="673ed-116">Interfaccia ICorDebugProcess5</span><span class="sxs-lookup"><span data-stu-id="673ed-116">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)  
 [<span data-ttu-id="673ed-117">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="673ed-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
