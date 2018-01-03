---
title: Metodo ICorDebugEval::IsActive
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugEval.IsActive
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugEval::IsActive
helpviewer_keywords:
- IsActive method, ICorDebugEval interface [.NET Framework debugging]
- ICorDebugEval::IsActive method [.NET Framework debugging]
ms.assetid: bf2bba24-d278-43bd-b1c5-35680e748d3e
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b574d74de1e042ab50e52eb3bb2fe217801bf1eb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugevalisactive-method"></a><span data-ttu-id="4aed8-102">Metodo ICorDebugEval::IsActive</span><span class="sxs-lookup"><span data-stu-id="4aed8-102">ICorDebugEval::IsActive Method</span></span>
<span data-ttu-id="4aed8-103">Ottiene un valore che indica se l'oggetto ICorDebugEval è attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="4aed8-103">Gets a value that indicates whether this ICorDebugEval object is currently executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4aed8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4aed8-104">Syntax</span></span>  
  
```  
HRESULT IsActive (  
    [out] BOOL              *pbActive  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4aed8-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="4aed8-105">Parameters</span></span>  
 `pbActive`  
 <span data-ttu-id="4aed8-106">[out] Puntatore a un valore che indica se questa valutazione è attiva.</span><span class="sxs-lookup"><span data-stu-id="4aed8-106">[out] Pointer to a value that indicates whether this evaluation is active.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4aed8-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4aed8-107">Requirements</span></span>  
 <span data-ttu-id="4aed8-108">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4aed8-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4aed8-109">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="4aed8-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4aed8-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4aed8-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4aed8-111">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4aed8-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
