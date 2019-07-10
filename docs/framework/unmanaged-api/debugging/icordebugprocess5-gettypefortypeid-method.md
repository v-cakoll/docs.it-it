---
title: Metodo ICorDebugProcess5::GetTypeForTypeID
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.GetTypeForTypeID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::GetTypeForTypeID
helpviewer_keywords:
- GetTypeForTypeID method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::GetTypeForTypeID method [.NET Framework debugging]
ms.assetid: e0eed5a8-fa6d-4818-bd00-7babcea30325
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f37fab4d877ae804996f46290e3576cecc5a25ca
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67767621"
---
# <a name="icordebugprocess5gettypefortypeid-method"></a><span data-ttu-id="56f62-102">Metodo ICorDebugProcess5::GetTypeForTypeID</span><span class="sxs-lookup"><span data-stu-id="56f62-102">ICorDebugProcess5::GetTypeForTypeID Method</span></span>
<span data-ttu-id="56f62-103">Converte un identificatore di tipo in un valore di ICorDebugType.</span><span class="sxs-lookup"><span data-stu-id="56f62-103">Converts a type identifier to an ICorDebugType value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="56f62-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="56f62-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeForTypeID(  
    [in] COR_TYPEID id, [  
    out] ICorDebugType **ppType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="56f62-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="56f62-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="56f62-106">[in] L'identificatore del tipo.</span><span class="sxs-lookup"><span data-stu-id="56f62-106">[in] The type identifier.</span></span>  
  
 `ppType`  
 <span data-ttu-id="56f62-107">[out] Un puntatore all'indirizzo di un oggetto di ICorDebugType.</span><span class="sxs-lookup"><span data-stu-id="56f62-107">[out] A pointer to the address of an ICorDebugType object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="56f62-108">Note</span><span class="sxs-lookup"><span data-stu-id="56f62-108">Remarks</span></span>  
 <span data-ttu-id="56f62-109">In alcuni casi, i metodi che restituiscono un identificatore di tipo possono restituire un valore null `COR_TYPEID` valore.</span><span class="sxs-lookup"><span data-stu-id="56f62-109">In some cases, methods that return a type identifier may return a null `COR_TYPEID` value.</span></span> <span data-ttu-id="56f62-110">Se questo valore viene passato come il `id` argomento, la `GetTypeForTypeID` metodo avrà esito negativo e restituire `E_FAIL`.</span><span class="sxs-lookup"><span data-stu-id="56f62-110">If this value is passed as the `id` argument, the `GetTypeForTypeID` method will fail and return `E_FAIL`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="56f62-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="56f62-111">Requirements</span></span>  
 <span data-ttu-id="56f62-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="56f62-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="56f62-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="56f62-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="56f62-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="56f62-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="56f62-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="56f62-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56f62-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="56f62-116">See also</span></span>

- [<span data-ttu-id="56f62-117">Interfaccia ICorDebugProcess5</span><span class="sxs-lookup"><span data-stu-id="56f62-117">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [<span data-ttu-id="56f62-118">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="56f62-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
