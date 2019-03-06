---
title: Metodo ICorDebugFunction::GetCurrentVersionNumber
ms.date: 03/30/2017
api_name:
- ICorDebugFunction.GetCurrentVersionNumber
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction::GetCurrentVersionNumber
helpviewer_keywords:
- GetCurrentVersionNumber method [.NET Framework debugging]
- ICorDebugFunction::GetCurrentVersionNumber method [.NET Framework debugging]
ms.assetid: c3af1575-cbe6-457a-bc08-c53460edcbc8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ea615eacb30fd4e7a0fd7d730094c2ab4f9dc285
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57478479"
---
# <a name="icordebugfunctiongetcurrentversionnumber-method"></a><span data-ttu-id="29a81-102">Metodo ICorDebugFunction::GetCurrentVersionNumber</span><span class="sxs-lookup"><span data-stu-id="29a81-102">ICorDebugFunction::GetCurrentVersionNumber Method</span></span>
<span data-ttu-id="29a81-103">Ottiene il numero di versione dell'ultima modifica apportata alla funzione rappresentata da questo oggetto ICorDebugFunction.</span><span class="sxs-lookup"><span data-stu-id="29a81-103">Gets the version number of the latest edit made to the function represented by this ICorDebugFunction object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="29a81-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="29a81-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentVersionNumber (  
    [out] ULONG32 *pnCurrentVersion  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="29a81-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="29a81-105">Parameters</span></span>  
 `pnCurrentVersion`  
 <span data-ttu-id="29a81-106">[out] Un puntatore a un valore intero che indica il numero di versione dell'ultima modifica apportata a questa funzione.</span><span class="sxs-lookup"><span data-stu-id="29a81-106">[out] A pointer to an integer value that is the version number of the latest edit made to this function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="29a81-107">Note</span><span class="sxs-lookup"><span data-stu-id="29a81-107">Remarks</span></span>  
 <span data-ttu-id="29a81-108">Il numero di versione dell'ultima modifica apportata a questa funzione può essere maggiore del numero di versione della funzione stessa.</span><span class="sxs-lookup"><span data-stu-id="29a81-108">The version number of the latest edit made to this function may be greater than the version number of the function itself.</span></span> <span data-ttu-id="29a81-109">Usare la [ICorDebugFunction2::GetVersionNumber](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-getversionnumber-method.md) metodo o il [GetVersionNumber](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getversionnumber-method.md) metodo per recuperare il numero di versione della funzione.</span><span class="sxs-lookup"><span data-stu-id="29a81-109">Use either the [ICorDebugFunction2::GetVersionNumber](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-getversionnumber-method.md) method or the [ICorDebugCode::GetVersionNumber](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getversionnumber-method.md) method to retrieve the version number of the function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="29a81-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="29a81-110">Requirements</span></span>  
 <span data-ttu-id="29a81-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="29a81-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="29a81-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="29a81-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="29a81-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="29a81-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="29a81-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="29a81-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
