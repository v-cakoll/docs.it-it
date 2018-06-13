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
ms.openlocfilehash: 13498c58c7625edfa4954b8da8837f1bd60c976d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33423416"
---
# <a name="icordebugprocess5gettypefortypeid-method"></a><span data-ttu-id="a00b7-102">Metodo ICorDebugProcess5::GetTypeForTypeID</span><span class="sxs-lookup"><span data-stu-id="a00b7-102">ICorDebugProcess5::GetTypeForTypeID Method</span></span>
<span data-ttu-id="a00b7-103">Converte un identificatore di tipo in un valore ICorDebugType.</span><span class="sxs-lookup"><span data-stu-id="a00b7-103">Converts a type identifier to an ICorDebugType value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a00b7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a00b7-104">Syntax</span></span>  
  
```  
HRESULT GetTypeForTypeID(  
    [in] COR_TYPEID id, [  
    out] ICorDebugType **ppType  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a00b7-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a00b7-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="a00b7-106">[in] L'identificatore del tipo.</span><span class="sxs-lookup"><span data-stu-id="a00b7-106">[in] The type identifier.</span></span>  
  
 `ppType`  
 <span data-ttu-id="a00b7-107">[out] Un puntatore all'indirizzo di un oggetto ICorDebugType.</span><span class="sxs-lookup"><span data-stu-id="a00b7-107">[out] A pointer to the address of an ICorDebugType object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a00b7-108">Note</span><span class="sxs-lookup"><span data-stu-id="a00b7-108">Remarks</span></span>  
 <span data-ttu-id="a00b7-109">In alcuni casi, i metodi che restituiscono un identificatore di tipo possono restituire un valore null `COR_TYPEID` valore.</span><span class="sxs-lookup"><span data-stu-id="a00b7-109">In some cases, methods that return a type identifier may return a null `COR_TYPEID` value.</span></span> <span data-ttu-id="a00b7-110">Se questo valore viene passato come il `id` argomento, la `GetTypeForTypeID` metodo avrà esito negativo e restituire `E_FAIL`.</span><span class="sxs-lookup"><span data-stu-id="a00b7-110">If this value is passed as the `id` argument, the `GetTypeForTypeID` method will fail and return `E_FAIL`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a00b7-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a00b7-111">Requirements</span></span>  
 <span data-ttu-id="a00b7-112">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a00b7-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a00b7-113">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="a00b7-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a00b7-114">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="a00b7-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a00b7-115">**Versioni di .NET framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a00b7-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a00b7-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a00b7-116">See Also</span></span>  
 [<span data-ttu-id="a00b7-117">Interfaccia ICorDebugProcess5</span><span class="sxs-lookup"><span data-stu-id="a00b7-117">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)  
 [<span data-ttu-id="a00b7-118">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="a00b7-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
