---
title: Metodo ICorDebugReferenceValue::SetValue
ms.date: 03/30/2017
api_name:
- ICorDebugReferenceValue.SetValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugReferenceValue::SetValue
helpviewer_keywords:
- SetValue method, ICorDebugReferenceValue interface [.NET Framework debugging]
- ICorDebugReferenceValue::SetValue method [.NET Framework debugging]
ms.assetid: 3d3f6eec-d772-401f-a028-1a2ecdc31e95
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2f0c06f9b04c5f15171464b93dc93765625d6f19
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33418142"
---
# <a name="icordebugreferencevaluesetvalue-method"></a><span data-ttu-id="696a0-102">Metodo ICorDebugReferenceValue::SetValue</span><span class="sxs-lookup"><span data-stu-id="696a0-102">ICorDebugReferenceValue::SetValue Method</span></span>
<span data-ttu-id="696a0-103">Imposta l'indirizzo di memoria specificata.</span><span class="sxs-lookup"><span data-stu-id="696a0-103">Sets the specified memory address.</span></span> <span data-ttu-id="696a0-104">Ovvero, questo metodo imposta ICorDebugReferenceValue in modo che punti a un oggetto.</span><span class="sxs-lookup"><span data-stu-id="696a0-104">That is, this method sets this ICorDebugReferenceValue to point to an object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="696a0-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="696a0-105">Syntax</span></span>  
  
```  
HRESULT SetValue (  
    [in] CORDB_ADDRESS    value  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="696a0-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="696a0-106">Parameters</span></span>  
 `value`  
 <span data-ttu-id="696a0-107">[in] Oggetto `CORDB_ADDRESS` valore che specifica l'indirizzo dell'oggetto a cui `ICorDebugReferenceValue` punti.</span><span class="sxs-lookup"><span data-stu-id="696a0-107">[in] A `CORDB_ADDRESS` value that specifies the address of the object to which this `ICorDebugReferenceValue` points.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="696a0-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="696a0-108">Requirements</span></span>  
 <span data-ttu-id="696a0-109">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="696a0-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="696a0-110">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="696a0-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="696a0-111">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="696a0-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="696a0-112">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="696a0-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
