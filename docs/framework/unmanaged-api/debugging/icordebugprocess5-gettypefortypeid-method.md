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
ms.openlocfilehash: 39f5c1813b08f4d72c610820b1434e29eb4aec8e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121280"
---
# <a name="icordebugprocess5gettypefortypeid-method"></a><span data-ttu-id="0d7a9-102">Metodo ICorDebugProcess5::GetTypeForTypeID</span><span class="sxs-lookup"><span data-stu-id="0d7a9-102">ICorDebugProcess5::GetTypeForTypeID Method</span></span>
<span data-ttu-id="0d7a9-103">Converte un identificatore di tipo in un valore ICorDebugType.</span><span class="sxs-lookup"><span data-stu-id="0d7a9-103">Converts a type identifier to an ICorDebugType value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d7a9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0d7a9-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeForTypeID(  
    [in] COR_TYPEID id, [  
    out] ICorDebugType **ppType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0d7a9-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="0d7a9-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="0d7a9-106">in Identificatore del tipo.</span><span class="sxs-lookup"><span data-stu-id="0d7a9-106">[in] The type identifier.</span></span>  
  
 `ppType`  
 <span data-ttu-id="0d7a9-107">out Puntatore all'indirizzo di un oggetto ICorDebugType.</span><span class="sxs-lookup"><span data-stu-id="0d7a9-107">[out] A pointer to the address of an ICorDebugType object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0d7a9-108">Note</span><span class="sxs-lookup"><span data-stu-id="0d7a9-108">Remarks</span></span>  
 <span data-ttu-id="0d7a9-109">In alcuni casi, i metodi che restituiscono un identificatore di tipo possono restituire un valore null `COR_TYPEID`.</span><span class="sxs-lookup"><span data-stu-id="0d7a9-109">In some cases, methods that return a type identifier may return a null `COR_TYPEID` value.</span></span> <span data-ttu-id="0d7a9-110">Se questo valore viene passato come argomento `id`, il `GetTypeForTypeID` metodo avrà esito negativo e restituirà `E_FAIL`.</span><span class="sxs-lookup"><span data-stu-id="0d7a9-110">If this value is passed as the `id` argument, the `GetTypeForTypeID` method will fail and return `E_FAIL`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0d7a9-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0d7a9-111">Requirements</span></span>  
 <span data-ttu-id="0d7a9-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0d7a9-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0d7a9-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0d7a9-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0d7a9-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0d7a9-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0d7a9-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0d7a9-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d7a9-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0d7a9-116">See also</span></span>

- [<span data-ttu-id="0d7a9-117">Interfaccia ICorDebugProcess5</span><span class="sxs-lookup"><span data-stu-id="0d7a9-117">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [<span data-ttu-id="0d7a9-118">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="0d7a9-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
