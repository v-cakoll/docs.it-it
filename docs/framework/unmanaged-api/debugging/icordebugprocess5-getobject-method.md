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
ms.openlocfilehash: 4b48132ee60bcaebb218d8f583de6558372f5055
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178600"
---
# <a name="icordebugprocess5getobject-method"></a><span data-ttu-id="a27c8-102">Metodo ICorDebugProcess5::GetObject</span><span class="sxs-lookup"><span data-stu-id="a27c8-102">ICorDebugProcess5::GetObject Method</span></span>
<span data-ttu-id="a27c8-103">Converte un indirizzo di oggetto in un oggetto "ICorDebugObjectValue".</span><span class="sxs-lookup"><span data-stu-id="a27c8-103">Converts an object address to an "ICorDebugObjectValue" object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a27c8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a27c8-104">Syntax</span></span>  
  
```cpp  
HRESULT GetObject(  
    [in] CORDB_ADDRESS addr,
    [out] ICorDebugObjectValue **ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a27c8-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a27c8-105">Parameters</span></span>  
 `addr`  
 <span data-ttu-id="a27c8-106">[in] Indirizzo dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="a27c8-106">[in] The object address.</span></span>  
  
 `ppObject`  
 <span data-ttu-id="a27c8-107">[fuori] Puntatore all'indirizzo di un oggetto "ICorDebugObjectValue".</span><span class="sxs-lookup"><span data-stu-id="a27c8-107">[out] A pointer to the address of an  "ICorDebugObjectValue" object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a27c8-108">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="a27c8-108">Remarks</span></span>  
 <span data-ttu-id="a27c8-109">Se `addr` non punta a un oggetto `GetObject` gestito `E_FAIL`valido, il metodo restituisce .</span><span class="sxs-lookup"><span data-stu-id="a27c8-109">If `addr` does not point to a valid managed object, the `GetObject` method returns `E_FAIL`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a27c8-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a27c8-110">Requirements</span></span>  
 <span data-ttu-id="a27c8-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a27c8-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a27c8-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a27c8-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a27c8-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a27c8-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a27c8-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a27c8-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a27c8-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a27c8-115">See also</span></span>

- [<span data-ttu-id="a27c8-116">Interfaccia ICorDebugProcess5</span><span class="sxs-lookup"><span data-stu-id="a27c8-116">ICorDebugProcess5 Interface</span></span>](icordebugprocess5-interface.md)
- [<span data-ttu-id="a27c8-117">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="a27c8-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
