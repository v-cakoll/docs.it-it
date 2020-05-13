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
ms.openlocfilehash: c5fa55a84ed8907a5072f6099c3bf02cd6d78683
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213127"
---
# <a name="icordebugmoduleisinmemory-method"></a><span data-ttu-id="cbccf-102">Metodo ICorDebugModule::IsInMemory</span><span class="sxs-lookup"><span data-stu-id="cbccf-102">ICorDebugModule::IsInMemory Method</span></span>
<span data-ttu-id="cbccf-103">Ottiene un valore che indica se questo modulo esiste solo in memoria.</span><span class="sxs-lookup"><span data-stu-id="cbccf-103">Gets a value that indicates whether this module exists only in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cbccf-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cbccf-104">Syntax</span></span>  
  
```cpp  
HRESULT IsInMemory(  
    [out] BOOL *pInMemory  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cbccf-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="cbccf-105">Parameters</span></span>  
 `pInMemory`  
 <span data-ttu-id="cbccf-106">[out] `true` Se il modulo esiste solo in memoria; in caso contrario, `false` .</span><span class="sxs-lookup"><span data-stu-id="cbccf-106">[out] `true` if this module exists only in memory; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cbccf-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="cbccf-107">Remarks</span></span>  
 <span data-ttu-id="cbccf-108">Il Common Language Runtime (CLR) supporta il caricamento di moduli da flussi di byte non elaborati.</span><span class="sxs-lookup"><span data-stu-id="cbccf-108">The common language runtime (CLR) supports the loading of modules from raw streams of bytes.</span></span> <span data-ttu-id="cbccf-109">Tali moduli sono denominati *moduli in memoria* e non esistono sul disco.</span><span class="sxs-lookup"><span data-stu-id="cbccf-109">Such modules are called *in-memory modules* and do not exist on disk.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cbccf-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="cbccf-110">Requirements</span></span>  
 <span data-ttu-id="cbccf-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cbccf-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cbccf-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cbccf-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cbccf-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cbccf-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cbccf-114">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cbccf-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbccf-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cbccf-115">See also</span></span>
