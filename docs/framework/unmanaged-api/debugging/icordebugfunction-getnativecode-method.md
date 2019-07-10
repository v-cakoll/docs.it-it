---
title: Metodo ICorDebugFunction::GetNativeCode
ms.date: 03/30/2017
api_name:
- ICorDebugFunction.GetNativeCode
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction::GetNativeCode
helpviewer_keywords:
- GetNativeCode method [.NET Framework debugging]
- ICorDebugFunction::GetNativeCode method [.NET Framework debugging]
ms.assetid: c8a34916-0eef-4987-8d29-c8bcb4be9cf6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c0507d59011f6b584ecb1ae11c35c456c80793af
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67754591"
---
# <a name="icordebugfunctiongetnativecode-method"></a><span data-ttu-id="03348-102">Metodo ICorDebugFunction::GetNativeCode</span><span class="sxs-lookup"><span data-stu-id="03348-102">ICorDebugFunction::GetNativeCode Method</span></span>
<span data-ttu-id="03348-103">Ottiene il codice nativo per la funzione rappresentata da questa istanza ICorDebugFunction.</span><span class="sxs-lookup"><span data-stu-id="03348-103">Gets the native code for the function that is represented by this ICorDebugFunction instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03348-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="03348-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNativeCode (  
    [out] ICorDebugCode **ppCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="03348-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="03348-105">Parameters</span></span>  
 `ppCode`  
 <span data-ttu-id="03348-106">[out] Un puntatore all'istanza ICorDebugCode che rappresenta il codice nativo per questa funzione, o null, se questa funzione è codice Microsoft intermediate language (MSIL) che non è stato just-in-time (JIT) compilato.</span><span class="sxs-lookup"><span data-stu-id="03348-106">[out] A pointer to the ICorDebugCode instance that represents the native code for this function, or null, if this function is Microsoft intermediate language (MSIL) code that has not been just-in-time (JIT) compiled.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="03348-107">Note</span><span class="sxs-lookup"><span data-stu-id="03348-107">Remarks</span></span>  
 <span data-ttu-id="03348-108">Se la funzione rappresentata da questo `ICorDebugFunction` istanza è stata compilata tramite JIT più di una volta, come nel caso di tipi generici, `GetNativeCode` restituisce un oggetto di codice nativa casuale.</span><span class="sxs-lookup"><span data-stu-id="03348-108">If the function that is represented by this `ICorDebugFunction` instance has been JIT-compiled more than once, as in the case of generic types, `GetNativeCode` returns a random native code object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="03348-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="03348-109">Requirements</span></span>  
 <span data-ttu-id="03348-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="03348-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="03348-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="03348-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="03348-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="03348-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="03348-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="03348-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
