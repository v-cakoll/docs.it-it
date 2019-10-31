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
ms.openlocfilehash: 5bb41b2b49922475550997f18832b391522e2f26
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137863"
---
# <a name="icordebugfunctiongetnativecode-method"></a><span data-ttu-id="6f85e-102">Metodo ICorDebugFunction::GetNativeCode</span><span class="sxs-lookup"><span data-stu-id="6f85e-102">ICorDebugFunction::GetNativeCode Method</span></span>
<span data-ttu-id="6f85e-103">Ottiene il codice nativo per la funzione rappresentata da questa istanza di ICorDebugFunction.</span><span class="sxs-lookup"><span data-stu-id="6f85e-103">Gets the native code for the function that is represented by this ICorDebugFunction instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f85e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6f85e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNativeCode (  
    [out] ICorDebugCode **ppCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6f85e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="6f85e-105">Parameters</span></span>  
 `ppCode`  
 <span data-ttu-id="6f85e-106">out Puntatore all'istanza di ICorDebugCode che rappresenta il codice nativo per questa funzione, o null, se questa funzione è codice MSIL (Microsoft Intermediate Language) che non è stato compilato just-in-time (JIT).</span><span class="sxs-lookup"><span data-stu-id="6f85e-106">[out] A pointer to the ICorDebugCode instance that represents the native code for this function, or null, if this function is Microsoft intermediate language (MSIL) code that has not been just-in-time (JIT) compiled.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6f85e-107">Note</span><span class="sxs-lookup"><span data-stu-id="6f85e-107">Remarks</span></span>  
 <span data-ttu-id="6f85e-108">Se la funzione rappresentata da questa istanza di `ICorDebugFunction` è stata compilata tramite JIT più di una volta, come nel caso dei tipi generici, `GetNativeCode` restituisce un oggetto di codice nativo casuale.</span><span class="sxs-lookup"><span data-stu-id="6f85e-108">If the function that is represented by this `ICorDebugFunction` instance has been JIT-compiled more than once, as in the case of generic types, `GetNativeCode` returns a random native code object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6f85e-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6f85e-109">Requirements</span></span>  
 <span data-ttu-id="6f85e-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6f85e-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6f85e-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6f85e-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6f85e-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6f85e-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6f85e-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6f85e-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
