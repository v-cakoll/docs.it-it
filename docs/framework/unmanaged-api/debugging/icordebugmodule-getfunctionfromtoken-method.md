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
ms.openlocfilehash: cb966a918c63b4fbc00dcf52819b9384427dfdaa
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129583"
---
# <a name="icordebugmodulegetfunctionfromtoken-method"></a><span data-ttu-id="d2718-102">Metodo ICorDebugModule::GetFunctionFromToken</span><span class="sxs-lookup"><span data-stu-id="d2718-102">ICorDebugModule::GetFunctionFromToken Method</span></span>
<span data-ttu-id="d2718-103">Ottiene la funzione specificata dal token di metadati.</span><span class="sxs-lookup"><span data-stu-id="d2718-103">Gets the function that is specified by the metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2718-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d2718-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionFromToken(  
    [in] mdMethodDef methodDef,  
    [out] ICorDebugFunction **ppFunction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d2718-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d2718-105">Parameters</span></span>  
 `methodDef`  
 <span data-ttu-id="d2718-106">in Token di metadati `mdMethodDef` che fa riferimento ai metadati della funzione.</span><span class="sxs-lookup"><span data-stu-id="d2718-106">[in] A `mdMethodDef` metadata token that references the function's metadata.</span></span>  
  
 `ppFunction`  
 <span data-ttu-id="d2718-107">out Puntatore all'indirizzo di un oggetto interfaccia ICorDebugFunction che rappresenta la funzione.</span><span class="sxs-lookup"><span data-stu-id="d2718-107">[out] A pointer to the address of a ICorDebugFunction interface object that represents the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d2718-108">Note</span><span class="sxs-lookup"><span data-stu-id="d2718-108">Remarks</span></span>  
 <span data-ttu-id="d2718-109">Il metodo `GetFunctionFromToken` restituisce un HRESULT CORDBG_E_FUNCTION_NOT_IL se il valore passato in `methodDef` non fa riferimento a un metodo MSIL (Microsoft Intermediate Language).</span><span class="sxs-lookup"><span data-stu-id="d2718-109">The `GetFunctionFromToken` method returns a CORDBG_E_FUNCTION_NOT_IL HRESULT if the value passed in `methodDef` does not refer to a Microsoft intermediate language (MSIL) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d2718-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d2718-110">Requirements</span></span>  
 <span data-ttu-id="d2718-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d2718-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d2718-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d2718-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d2718-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d2718-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d2718-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d2718-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
