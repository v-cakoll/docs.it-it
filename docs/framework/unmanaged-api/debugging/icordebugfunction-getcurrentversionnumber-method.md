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
ms.openlocfilehash: 61b2de0595ac9330d9bb4e8e2dcbe4591928eb91
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33413884"
---
# <a name="icordebugfunctiongetcurrentversionnumber-method"></a><span data-ttu-id="8b21a-102">Metodo ICorDebugFunction::GetCurrentVersionNumber</span><span class="sxs-lookup"><span data-stu-id="8b21a-102">ICorDebugFunction::GetCurrentVersionNumber Method</span></span>
<span data-ttu-id="8b21a-103">Ottiene il numero di versione dell'ultima modifica apportata alla funzione rappresentata da questo oggetto ICorDebugFunction.</span><span class="sxs-lookup"><span data-stu-id="8b21a-103">Gets the version number of the latest edit made to the function represented by this ICorDebugFunction object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b21a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8b21a-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentVersionNumber (  
    [out] ULONG32 *pnCurrentVersion  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8b21a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="8b21a-105">Parameters</span></span>  
 `pnCurrentVersion`  
 <span data-ttu-id="8b21a-106">[out] Puntatore a un valore intero che rappresenta il numero di versione dell'ultima modifica apportata a questa funzione.</span><span class="sxs-lookup"><span data-stu-id="8b21a-106">[out] A pointer to an integer value that is the version number of the latest edit made to this function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8b21a-107">Note</span><span class="sxs-lookup"><span data-stu-id="8b21a-107">Remarks</span></span>  
 <span data-ttu-id="8b21a-108">Il numero di versione dell'ultima modifica apportata a questa funzione può essere maggiore del numero di versione della funzione stessa.</span><span class="sxs-lookup"><span data-stu-id="8b21a-108">The version number of the latest edit made to this function may be greater than the version number of the function itself.</span></span> <span data-ttu-id="8b21a-109">Utilizzare il [ICorDebugFunction2:: GetVersionNumber](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-getversionnumber-method.md) metodo o [GetVersionNumber](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getversionnumber-method.md) metodo per recuperare il numero di versione della funzione.</span><span class="sxs-lookup"><span data-stu-id="8b21a-109">Use either the [ICorDebugFunction2::GetVersionNumber](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-getversionnumber-method.md) method or the [ICorDebugCode::GetVersionNumber](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getversionnumber-method.md) method to retrieve the version number of the function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8b21a-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8b21a-110">Requirements</span></span>  
 <span data-ttu-id="8b21a-111">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8b21a-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8b21a-112">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="8b21a-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8b21a-113">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="8b21a-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8b21a-114">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8b21a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
