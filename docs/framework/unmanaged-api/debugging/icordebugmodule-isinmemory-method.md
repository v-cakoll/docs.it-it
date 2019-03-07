---
title: Metodo ICorDebugModule::IsInMemory
ms.date: 03/30/2017
api_name:
- ICorDebugModule.IsInMemory
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::IsInMemory
helpviewer_keywords:
- IsInMemory method [.NET Framework debugging]
- ICorDebugModule::IsInMemory method [.NET Framework debugging]
ms.assetid: 89940711-98e7-4aa6-bffc-5e39e91e1b7d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0f057896d9dd65a850c0b07e4084bc263e804d20
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57497366"
---
# <a name="icordebugmoduleisinmemory-method"></a><span data-ttu-id="06018-102">Metodo ICorDebugModule::IsInMemory</span><span class="sxs-lookup"><span data-stu-id="06018-102">ICorDebugModule::IsInMemory Method</span></span>
<span data-ttu-id="06018-103">Ottiene un valore che indica se questo modulo esiste solo in memoria.</span><span class="sxs-lookup"><span data-stu-id="06018-103">Gets a value that indicates whether this module exists only in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06018-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="06018-104">Syntax</span></span>  
  
```  
HRESULT IsInMemory(  
    [out] BOOL *pInMemory  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="06018-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="06018-105">Parameters</span></span>  
 `pInMemory`  
 <span data-ttu-id="06018-106">[out] `true` se questo modulo esiste solo in memoria; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="06018-106">[out] `true` if this module exists only in memory; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="06018-107">Note</span><span class="sxs-lookup"><span data-stu-id="06018-107">Remarks</span></span>  
 <span data-ttu-id="06018-108">Common language runtime (CLR) supporta il caricamento dei moduli da flussi di byte non elaborati.</span><span class="sxs-lookup"><span data-stu-id="06018-108">The common language runtime (CLR) supports the loading of modules from raw streams of bytes.</span></span> <span data-ttu-id="06018-109">Questi moduli sono denominati *i moduli in memoria* e non esistono sul disco.</span><span class="sxs-lookup"><span data-stu-id="06018-109">Such modules are called *in-memory modules* and do not exist on disk.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="06018-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="06018-110">Requirements</span></span>  
 <span data-ttu-id="06018-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="06018-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="06018-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="06018-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="06018-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="06018-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="06018-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="06018-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06018-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="06018-115">See also</span></span>


