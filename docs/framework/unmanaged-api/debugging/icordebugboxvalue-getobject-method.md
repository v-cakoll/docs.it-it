---
title: Metodo ICorDebugBoxValue::GetObject
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugBoxValue.GetObject
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBoxValue::GetObject
helpviewer_keywords:
- ICorDebugBoxValue::GetObject method [.NET Framework debugging]
- GetObject method, ICorDebugBoxValue interface [.NET Framework debugging]
ms.assetid: 3a867a5b-bf94-493f-a4f5-b28685cf5325
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 0e71da40af57d00e4651c094ddad9c86fc6fe636
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugboxvaluegetobject-method"></a><span data-ttu-id="ea8d2-102">Metodo ICorDebugBoxValue::GetObject</span><span class="sxs-lookup"><span data-stu-id="ea8d2-102">ICorDebugBoxValue::GetObject Method</span></span>
<span data-ttu-id="ea8d2-103">Ottiene il valore boxed.</span><span class="sxs-lookup"><span data-stu-id="ea8d2-103">Gets the boxed value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea8d2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ea8d2-104">Syntax</span></span>  
  
```  
HRESULT GetObject (  
    [out] ICorDebugObjectValue **ppObject  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ea8d2-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ea8d2-105">Parameters</span></span>  
 `ppObject`  
 <span data-ttu-id="ea8d2-106">[out] Un puntatore all'indirizzo di un oggetto ICorDebugObjectValue che rappresenta il valore boxed.</span><span class="sxs-lookup"><span data-stu-id="ea8d2-106">[out] A pointer to the address of an ICorDebugObjectValue object that represents the boxed value.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ea8d2-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ea8d2-107">Requirements</span></span>  
 <span data-ttu-id="ea8d2-108">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ea8d2-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ea8d2-109">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="ea8d2-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ea8d2-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ea8d2-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ea8d2-111">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ea8d2-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
