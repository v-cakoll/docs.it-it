---
title: Metodo ICorDebugFunction::GetModule
ms.date: 03/30/2017
api_name:
- ICorDebugFunction.GetModule
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction::GetModule
helpviewer_keywords:
- ICorDebugFunction::GetModule method [.NET Framework debugging]
- GetModule method, ICorDebugFunction interface [.NET Framework debugging]
ms.assetid: 5031a5d3-2564-412a-9007-e36d4631308a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: aef12634da477e72757e98e520b600ec1ee0f1b5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33412165"
---
# <a name="icordebugfunctiongetmodule-method"></a><span data-ttu-id="7eb31-102">Metodo ICorDebugFunction::GetModule</span><span class="sxs-lookup"><span data-stu-id="7eb31-102">ICorDebugFunction::GetModule Method</span></span>
<span data-ttu-id="7eb31-103">Ottiene il modulo in cui questa funzione è definita.</span><span class="sxs-lookup"><span data-stu-id="7eb31-103">Gets the module in which this function is defined.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7eb31-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7eb31-104">Syntax</span></span>  
  
```  
HRESULT GetModule (  
    [out] ICorDebugModule **ppModule  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7eb31-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="7eb31-105">Parameters</span></span>  
 `ppModule`  
 <span data-ttu-id="7eb31-106">[out] Un puntatore all'indirizzo di un oggetto ICorDebugModule che rappresenta il modulo in cui questa funzione è definita.</span><span class="sxs-lookup"><span data-stu-id="7eb31-106">[out] A pointer to the address of an ICorDebugModule object that represents the module in which this function is defined.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7eb31-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7eb31-107">Requirements</span></span>  
 <span data-ttu-id="7eb31-108">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7eb31-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7eb31-109">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="7eb31-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7eb31-110">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="7eb31-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7eb31-111">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7eb31-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
