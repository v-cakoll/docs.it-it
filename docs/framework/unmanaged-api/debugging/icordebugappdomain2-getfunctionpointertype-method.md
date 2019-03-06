---
title: Metodo ICorDebugAppDomain2::GetFunctionPointerType
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain2.GetFunctionPointerType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain2::GetFunctionPointerType
helpviewer_keywords:
- ICorDebugAppDomain2::GetFunctionPointerType method [.NET Framework debugging]
- GetFunctionPointerType method [.NET Framework debugging]
ms.assetid: 0aba6096-5b38-435c-a72a-86d35db4daef
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ec1a9968dbec10783c6f1383fb523e95ff79561e
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57489748"
---
# <a name="icordebugappdomain2getfunctionpointertype-method"></a><span data-ttu-id="35baf-102">Metodo ICorDebugAppDomain2::GetFunctionPointerType</span><span class="sxs-lookup"><span data-stu-id="35baf-102">ICorDebugAppDomain2::GetFunctionPointerType Method</span></span>
<span data-ttu-id="35baf-103">Ottiene un puntatore a una funzione che dispone di una determinata firma.</span><span class="sxs-lookup"><span data-stu-id="35baf-103">Gets a pointer to a function that has a given signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35baf-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="35baf-104">Syntax</span></span>  
  
```  
HRESULT GetFunctionPointerType (  
    [in] ULONG32                             nTypeArgs,  
    [in, size_is(nTypeArgs)] ICorDebugType   *ppTypeArgs[],  
    [out] ICorDebugType                      **ppType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="35baf-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="35baf-105">Parameters</span></span>  
 `nTypeArgs`  
 <span data-ttu-id="35baf-106">[in] Il numero di argomenti tipo per la funzione.</span><span class="sxs-lookup"><span data-stu-id="35baf-106">[in] The number of type arguments for the function.</span></span>  
  
 `ppTypeArgs`  
 <span data-ttu-id="35baf-107">[in] Una matrice di puntatori, ognuno dei quali punta a un oggetto ICorDebugType che rappresenta un argomento tipo della funzione.</span><span class="sxs-lookup"><span data-stu-id="35baf-107">[in] An array of pointers, each of which points to an ICorDebugType object that represents a type argument of the function.</span></span> <span data-ttu-id="35baf-108">Il primo elemento è il tipo restituito; ognuno degli altri elementi è un tipo di parametro.</span><span class="sxs-lookup"><span data-stu-id="35baf-108">The first element is the return type; each of the other elements is a parameter type.</span></span>  
  
 `ppType`  
 <span data-ttu-id="35baf-109">[out] Un puntatore all'indirizzo di un `ICorDebugType` oggetto che rappresenta il puntatore alla funzione.</span><span class="sxs-lookup"><span data-stu-id="35baf-109">[out] A pointer to the address of an `ICorDebugType` object that represents the pointer to the function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="35baf-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="35baf-110">Requirements</span></span>  
 <span data-ttu-id="35baf-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="35baf-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="35baf-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="35baf-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="35baf-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="35baf-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="35baf-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="35baf-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
