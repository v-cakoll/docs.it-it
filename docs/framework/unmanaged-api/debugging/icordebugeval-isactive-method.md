---
title: Metodo ICorDebugEval::IsActive
ms.date: 03/30/2017
api_name:
- ICorDebugEval.IsActive
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::IsActive
helpviewer_keywords:
- IsActive method, ICorDebugEval interface [.NET Framework debugging]
- ICorDebugEval::IsActive method [.NET Framework debugging]
ms.assetid: bf2bba24-d278-43bd-b1c5-35680e748d3e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2fe29b3e35d2fbd42fac2d9ec1d1c594abe1239c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33411158"
---
# <a name="icordebugevalisactive-method"></a><span data-ttu-id="5009c-102">Metodo ICorDebugEval::IsActive</span><span class="sxs-lookup"><span data-stu-id="5009c-102">ICorDebugEval::IsActive Method</span></span>
<span data-ttu-id="5009c-103">Ottiene un valore che indica se l'oggetto ICorDebugEval è attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="5009c-103">Gets a value that indicates whether this ICorDebugEval object is currently executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5009c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5009c-104">Syntax</span></span>  
  
```  
HRESULT IsActive (  
    [out] BOOL              *pbActive  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5009c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="5009c-105">Parameters</span></span>  
 `pbActive`  
 <span data-ttu-id="5009c-106">[out] Puntatore a un valore che indica se questa valutazione è attiva.</span><span class="sxs-lookup"><span data-stu-id="5009c-106">[out] Pointer to a value that indicates whether this evaluation is active.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5009c-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5009c-107">Requirements</span></span>  
 <span data-ttu-id="5009c-108">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5009c-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5009c-109">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="5009c-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5009c-110">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="5009c-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5009c-111">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5009c-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
