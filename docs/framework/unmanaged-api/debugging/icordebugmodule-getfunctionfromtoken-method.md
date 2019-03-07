---
title: Metodo ICorDebugModule::GetFunctionFromToken
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetFunctionFromToken
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetFunctionFromToken
helpviewer_keywords:
- GetFunctionFromToken method, ICorDebugModule interface [.NET Framework debugging]
- ICorDebugModule::GetFunctionFromToken method [.NET Framework debugging]
ms.assetid: 6fe12194-4ef7-43c1-9570-ade35ccf127a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c1af0f8f792c856c0b27b4d3d9ff557bcc5fce82
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57500070"
---
# <a name="icordebugmodulegetfunctionfromtoken-method"></a><span data-ttu-id="74f01-102">Metodo ICorDebugModule::GetFunctionFromToken</span><span class="sxs-lookup"><span data-stu-id="74f01-102">ICorDebugModule::GetFunctionFromToken Method</span></span>
<span data-ttu-id="74f01-103">Ottiene la funzione specificata dal token di metadati.</span><span class="sxs-lookup"><span data-stu-id="74f01-103">Gets the function that is specified by the metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74f01-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="74f01-104">Syntax</span></span>  
  
```  
HRESULT GetFunctionFromToken(  
    [in] mdMethodDef methodDef,  
    [out] ICorDebugFunction **ppFunction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="74f01-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="74f01-105">Parameters</span></span>  
 `methodDef`  
 <span data-ttu-id="74f01-106">[in] Oggetto `mdMethodDef` token di metadati che fa riferimento ai metadati della funzione.</span><span class="sxs-lookup"><span data-stu-id="74f01-106">[in] A `mdMethodDef` metadata token that references the function's metadata.</span></span>  
  
 `ppFunction`  
 <span data-ttu-id="74f01-107">[out] Un puntatore all'indirizzo di un oggetto di interfaccia ICorDebugFunction che rappresenta la funzione.</span><span class="sxs-lookup"><span data-stu-id="74f01-107">[out] A pointer to the address of a ICorDebugFunction interface object that represents the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="74f01-108">Note</span><span class="sxs-lookup"><span data-stu-id="74f01-108">Remarks</span></span>  
 <span data-ttu-id="74f01-109">Il `GetFunctionFromToken` metodo restituisce un HRESULT CORDBG_E_FUNCTION_NOT_IL se il valore passato in `methodDef` non fa riferimento a un metodo di Microsoft intermediate language (MSIL).</span><span class="sxs-lookup"><span data-stu-id="74f01-109">The `GetFunctionFromToken` method returns a CORDBG_E_FUNCTION_NOT_IL HRESULT if the value passed in `methodDef` does not refer to a Microsoft intermediate language (MSIL) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="74f01-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="74f01-110">Requirements</span></span>  
 <span data-ttu-id="74f01-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="74f01-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="74f01-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="74f01-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="74f01-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="74f01-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="74f01-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="74f01-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
