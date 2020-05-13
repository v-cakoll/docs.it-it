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
ms.openlocfilehash: de570507c4312f09def0908b9d56e5371c63527e
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83207285"
---
# <a name="icordebugprocess5getobject-method"></a><span data-ttu-id="983e0-102">Metodo ICorDebugProcess5::GetObject</span><span class="sxs-lookup"><span data-stu-id="983e0-102">ICorDebugProcess5::GetObject Method</span></span>
<span data-ttu-id="983e0-103">Converte un indirizzo di oggetto in un oggetto "ICorDebugObjectValue".</span><span class="sxs-lookup"><span data-stu-id="983e0-103">Converts an object address to an "ICorDebugObjectValue" object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="983e0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="983e0-104">Syntax</span></span>  
  
```cpp  
HRESULT GetObject(  
    [in] CORDB_ADDRESS addr,
    [out] ICorDebugObjectValue **ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="983e0-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="983e0-105">Parameters</span></span>  
 `addr`  
 <span data-ttu-id="983e0-106">in Indirizzo dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="983e0-106">[in] The object address.</span></span>  
  
 `ppObject`  
 <span data-ttu-id="983e0-107">out Puntatore all'indirizzo di un oggetto "ICorDebugObjectValue".</span><span class="sxs-lookup"><span data-stu-id="983e0-107">[out] A pointer to the address of an  "ICorDebugObjectValue" object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="983e0-108">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="983e0-108">Remarks</span></span>  
 <span data-ttu-id="983e0-109">Se `addr` non punta a un oggetto gestito valido, il `GetObject` metodo restituisce `E_FAIL` .</span><span class="sxs-lookup"><span data-stu-id="983e0-109">If `addr` does not point to a valid managed object, the `GetObject` method returns `E_FAIL`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="983e0-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="983e0-110">Requirements</span></span>  
 <span data-ttu-id="983e0-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="983e0-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="983e0-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="983e0-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="983e0-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="983e0-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="983e0-114">**Versioni .NET Framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="983e0-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="983e0-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="983e0-115">See also</span></span>

- [<span data-ttu-id="983e0-116">Interfaccia ICorDebugProcess5</span><span class="sxs-lookup"><span data-stu-id="983e0-116">ICorDebugProcess5 Interface</span></span>](icordebugprocess5-interface.md)
- [<span data-ttu-id="983e0-117">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="983e0-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
