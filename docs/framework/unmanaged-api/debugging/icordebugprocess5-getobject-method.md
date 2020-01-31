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
ms.openlocfilehash: 540ca78c5548d4fbdd3338671ea02314736f15cd
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792358"
---
# <a name="icordebugprocess5getobject-method"></a><span data-ttu-id="25405-102">Metodo ICorDebugProcess5::GetObject</span><span class="sxs-lookup"><span data-stu-id="25405-102">ICorDebugProcess5::GetObject Method</span></span>
<span data-ttu-id="25405-103">Converte un indirizzo di oggetto in un oggetto "ICorDebugObjectValue".</span><span class="sxs-lookup"><span data-stu-id="25405-103">Converts an object address to an "ICorDebugObjectValue" object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25405-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="25405-104">Syntax</span></span>  
  
```cpp  
HRESULT GetObject(  
    [in] CORDB_ADDRESS addr,   
    [out] ICorDebugObjectValue **ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="25405-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="25405-105">Parameters</span></span>  
 `addr`  
 <span data-ttu-id="25405-106">in Indirizzo dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="25405-106">[in] The object address.</span></span>  
  
 `ppObject`  
 <span data-ttu-id="25405-107">out Puntatore all'indirizzo di un oggetto "ICorDebugObjectValue".</span><span class="sxs-lookup"><span data-stu-id="25405-107">[out] A pointer to the address of an  "ICorDebugObjectValue" object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="25405-108">Note</span><span class="sxs-lookup"><span data-stu-id="25405-108">Remarks</span></span>  
 <span data-ttu-id="25405-109">Se `addr` non punta a un oggetto gestito valido, il metodo `GetObject` restituisce `E_FAIL`.</span><span class="sxs-lookup"><span data-stu-id="25405-109">If `addr` does not point to a valid managed object, the `GetObject` method returns `E_FAIL`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="25405-110">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="25405-110">Requirements</span></span>  
 <span data-ttu-id="25405-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="25405-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="25405-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="25405-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="25405-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="25405-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="25405-114">**Versioni .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="25405-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25405-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="25405-115">See also</span></span>

- [<span data-ttu-id="25405-116">Interfaccia ICorDebugProcess5</span><span class="sxs-lookup"><span data-stu-id="25405-116">ICorDebugProcess5 Interface</span></span>](icordebugprocess5-interface.md)
- [<span data-ttu-id="25405-117">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="25405-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
