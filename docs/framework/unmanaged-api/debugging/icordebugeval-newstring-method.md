---
title: Metodo ICorDebugEval::NewString
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugEval.NewString
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugEval::NewString
helpviewer_keywords:
- NewString method [.NET Framework debugging]
- ICorDebugEval::NewString method [.NET Framework debugging]
ms.assetid: 29e7a14b-d50e-4852-bfda-011b76c0c9ee
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6cc45d766801391fcd157c39357058be17759f8d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugevalnewstring-method"></a><span data-ttu-id="30a15-102">Metodo ICorDebugEval::NewString</span><span class="sxs-lookup"><span data-stu-id="30a15-102">ICorDebugEval::NewString Method</span></span>
<span data-ttu-id="30a15-103">Alloca una nuova istanza di stringa con il contenuto specificato.</span><span class="sxs-lookup"><span data-stu-id="30a15-103">Allocates a new string instance with the specified contents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30a15-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="30a15-104">Syntax</span></span>  
  
```  
HRESULT NewString (  
    [in] LPCWSTR   string  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="30a15-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="30a15-105">Parameters</span></span>  
 `string`  
 <span data-ttu-id="30a15-106">[in] Puntatore al contenuto per la stringa.</span><span class="sxs-lookup"><span data-stu-id="30a15-106">[in] Pointer to the contents for the string.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="30a15-107">Note</span><span class="sxs-lookup"><span data-stu-id="30a15-107">Remarks</span></span>  
 <span data-ttu-id="30a15-108">La stringa viene sempre creata nel dominio dell'applicazione in cui il thread è in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="30a15-108">The string is always created in the application domain in which the thread is currently executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="30a15-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="30a15-109">Requirements</span></span>  
 <span data-ttu-id="30a15-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="30a15-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="30a15-111">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="30a15-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="30a15-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="30a15-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="30a15-113">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="30a15-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
