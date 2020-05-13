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
ms.openlocfilehash: a33b6ff308f3444496e5a1cb2e04f28e80305db5
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212581"
---
# <a name="icordebugmodulegetfunctionfromtoken-method"></a><span data-ttu-id="48daf-102">Metodo ICorDebugModule::GetFunctionFromToken</span><span class="sxs-lookup"><span data-stu-id="48daf-102">ICorDebugModule::GetFunctionFromToken Method</span></span>
<span data-ttu-id="48daf-103">Ottiene la funzione specificata dal token di metadati.</span><span class="sxs-lookup"><span data-stu-id="48daf-103">Gets the function that is specified by the metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48daf-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="48daf-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionFromToken(  
    [in] mdMethodDef methodDef,  
    [out] ICorDebugFunction **ppFunction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="48daf-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="48daf-105">Parameters</span></span>  
 `methodDef`  
 <span data-ttu-id="48daf-106">in `mdMethodDef`Token di metadati che fa riferimento ai metadati della funzione.</span><span class="sxs-lookup"><span data-stu-id="48daf-106">[in] A `mdMethodDef` metadata token that references the function's metadata.</span></span>  
  
 `ppFunction`  
 <span data-ttu-id="48daf-107">out Puntatore all'indirizzo di un oggetto interfaccia ICorDebugFunction che rappresenta la funzione.</span><span class="sxs-lookup"><span data-stu-id="48daf-107">[out] A pointer to the address of a ICorDebugFunction interface object that represents the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="48daf-108">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="48daf-108">Remarks</span></span>  
 <span data-ttu-id="48daf-109">Il `GetFunctionFromToken` metodo restituisce un CORDBG_E_FUNCTION_NOT_IL HRESULT se il valore passato non `methodDef` fa riferimento a un metodo MSIL (Microsoft Intermediate Language).</span><span class="sxs-lookup"><span data-stu-id="48daf-109">The `GetFunctionFromToken` method returns a CORDBG_E_FUNCTION_NOT_IL HRESULT if the value passed in `methodDef` does not refer to a Microsoft intermediate language (MSIL) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="48daf-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="48daf-110">Requirements</span></span>  
 <span data-ttu-id="48daf-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="48daf-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="48daf-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="48daf-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="48daf-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="48daf-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="48daf-114">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="48daf-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
