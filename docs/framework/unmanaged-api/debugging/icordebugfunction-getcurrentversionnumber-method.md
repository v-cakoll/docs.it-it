---
title: Metodo ICorDebugFunction::GetCurrentVersionNumber
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugFunction.GetCurrentVersionNumber
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugFunction::GetCurrentVersionNumber
helpviewer_keywords:
- GetCurrentVersionNumber method [.NET Framework debugging]
- ICorDebugFunction::GetCurrentVersionNumber method [.NET Framework debugging]
ms.assetid: c3af1575-cbe6-457a-bc08-c53460edcbc8
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0b4e26be7e50f7746caeb793bef6d6dbcfed7eef
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugfunctiongetcurrentversionnumber-method"></a><span data-ttu-id="b5276-102">Metodo ICorDebugFunction::GetCurrentVersionNumber</span><span class="sxs-lookup"><span data-stu-id="b5276-102">ICorDebugFunction::GetCurrentVersionNumber Method</span></span>
<span data-ttu-id="b5276-103">Ottiene il numero di versione dell'ultima modifica apportata alla funzione rappresentata da questo oggetto ICorDebugFunction.</span><span class="sxs-lookup"><span data-stu-id="b5276-103">Gets the version number of the latest edit made to the function represented by this ICorDebugFunction object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5276-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b5276-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentVersionNumber (  
    [out] ULONG32 *pnCurrentVersion  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b5276-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b5276-105">Parameters</span></span>  
 `pnCurrentVersion`  
 <span data-ttu-id="b5276-106">[out] Puntatore a un valore intero che rappresenta il numero di versione dell'ultima modifica apportata a questa funzione.</span><span class="sxs-lookup"><span data-stu-id="b5276-106">[out] A pointer to an integer value that is the version number of the latest edit made to this function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b5276-107">Note</span><span class="sxs-lookup"><span data-stu-id="b5276-107">Remarks</span></span>  
 <span data-ttu-id="b5276-108">Il numero di versione dell'ultima modifica apportata a questa funzione può essere maggiore del numero di versione della funzione stessa.</span><span class="sxs-lookup"><span data-stu-id="b5276-108">The version number of the latest edit made to this function may be greater than the version number of the function itself.</span></span> <span data-ttu-id="b5276-109">Utilizzare il [ICorDebugFunction2:: GetVersionNumber](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-getversionnumber-method.md) metodo o [GetVersionNumber](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getversionnumber-method.md) metodo per recuperare il numero di versione della funzione.</span><span class="sxs-lookup"><span data-stu-id="b5276-109">Use either the [ICorDebugFunction2::GetVersionNumber](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-getversionnumber-method.md) method or the [ICorDebugCode::GetVersionNumber](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getversionnumber-method.md) method to retrieve the version number of the function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b5276-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b5276-110">Requirements</span></span>  
 <span data-ttu-id="b5276-111">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b5276-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b5276-112">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="b5276-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b5276-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b5276-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b5276-114">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b5276-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
