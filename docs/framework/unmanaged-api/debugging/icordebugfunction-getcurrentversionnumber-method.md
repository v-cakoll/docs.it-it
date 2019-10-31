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
ms.openlocfilehash: 0530ba742a739003bfa33079ad75cb1e6f5f5e59
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124013"
---
# <a name="icordebugfunctiongetcurrentversionnumber-method"></a><span data-ttu-id="81f88-102">Metodo ICorDebugFunction::GetCurrentVersionNumber</span><span class="sxs-lookup"><span data-stu-id="81f88-102">ICorDebugFunction::GetCurrentVersionNumber Method</span></span>
<span data-ttu-id="81f88-103">Ottiene il numero di versione dell'Ultima modifica apportata alla funzione rappresentata da questo oggetto ICorDebugFunction.</span><span class="sxs-lookup"><span data-stu-id="81f88-103">Gets the version number of the latest edit made to the function represented by this ICorDebugFunction object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81f88-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="81f88-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentVersionNumber (  
    [out] ULONG32 *pnCurrentVersion  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="81f88-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="81f88-105">Parameters</span></span>  
 `pnCurrentVersion`  
 <span data-ttu-id="81f88-106">out Puntatore a un valore integer che rappresenta il numero di versione dell'Ultima modifica apportata a questa funzione.</span><span class="sxs-lookup"><span data-stu-id="81f88-106">[out] A pointer to an integer value that is the version number of the latest edit made to this function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="81f88-107">Note</span><span class="sxs-lookup"><span data-stu-id="81f88-107">Remarks</span></span>  
 <span data-ttu-id="81f88-108">Il numero di versione dell'Ultima modifica apportata a questa funzione potrebbe essere maggiore del numero di versione della funzione stessa.</span><span class="sxs-lookup"><span data-stu-id="81f88-108">The version number of the latest edit made to this function may be greater than the version number of the function itself.</span></span> <span data-ttu-id="81f88-109">Usare il metodo [ICorDebugFunction2:: GetVersionNumber](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-getversionnumber-method.md) o [ICorDebugCode:: GetVersionNumber](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getversionnumber-method.md) per recuperare il numero di versione della funzione.</span><span class="sxs-lookup"><span data-stu-id="81f88-109">Use either the [ICorDebugFunction2::GetVersionNumber](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-getversionnumber-method.md) method or the [ICorDebugCode::GetVersionNumber](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getversionnumber-method.md) method to retrieve the version number of the function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="81f88-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="81f88-110">Requirements</span></span>  
 <span data-ttu-id="81f88-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="81f88-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="81f88-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="81f88-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="81f88-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="81f88-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="81f88-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="81f88-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
