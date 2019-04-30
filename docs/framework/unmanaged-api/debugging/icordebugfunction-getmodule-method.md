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
ms.openlocfilehash: 1cefe84c482df3b20b5939e031ad76647f295d3e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61995613"
---
# <a name="icordebugfunctiongetmodule-method"></a><span data-ttu-id="79ae0-102">Metodo ICorDebugFunction::GetModule</span><span class="sxs-lookup"><span data-stu-id="79ae0-102">ICorDebugFunction::GetModule Method</span></span>
<span data-ttu-id="79ae0-103">Ottiene il modulo in cui questa funzione è definita.</span><span class="sxs-lookup"><span data-stu-id="79ae0-103">Gets the module in which this function is defined.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="79ae0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="79ae0-104">Syntax</span></span>  
  
```  
HRESULT GetModule (  
    [out] ICorDebugModule **ppModule  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="79ae0-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="79ae0-105">Parameters</span></span>  
 `ppModule`  
 <span data-ttu-id="79ae0-106">[out] Un puntatore all'indirizzo di un oggetto ICorDebugModule che rappresenta il modulo in cui questa funzione è definita.</span><span class="sxs-lookup"><span data-stu-id="79ae0-106">[out] A pointer to the address of an ICorDebugModule object that represents the module in which this function is defined.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="79ae0-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="79ae0-107">Requirements</span></span>  
 <span data-ttu-id="79ae0-108">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="79ae0-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="79ae0-109">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="79ae0-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="79ae0-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="79ae0-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="79ae0-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="79ae0-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
