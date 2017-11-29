---
title: Metodo ICorDebugFunction::GetModule
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugFunction.GetModule
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugFunction::GetModule
helpviewer_keywords:
- ICorDebugFunction::GetModule method [.NET Framework debugging]
- GetModule method, ICorDebugFunction interface [.NET Framework debugging]
ms.assetid: 5031a5d3-2564-412a-9007-e36d4631308a
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 23c1cb74742f5ae2bc6bae22b2f94966f7dbc2f8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugfunctiongetmodule-method"></a><span data-ttu-id="70bd3-102">Metodo ICorDebugFunction::GetModule</span><span class="sxs-lookup"><span data-stu-id="70bd3-102">ICorDebugFunction::GetModule Method</span></span>
<span data-ttu-id="70bd3-103">Ottiene il modulo in cui questa funzione è definita.</span><span class="sxs-lookup"><span data-stu-id="70bd3-103">Gets the module in which this function is defined.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70bd3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="70bd3-104">Syntax</span></span>  
  
```  
HRESULT GetModule (  
    [out] ICorDebugModule **ppModule  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="70bd3-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="70bd3-105">Parameters</span></span>  
 `ppModule`  
 <span data-ttu-id="70bd3-106">[out] Un puntatore all'indirizzo di un oggetto ICorDebugModule che rappresenta il modulo in cui questa funzione è definita.</span><span class="sxs-lookup"><span data-stu-id="70bd3-106">[out] A pointer to the address of an ICorDebugModule object that represents the module in which this function is defined.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="70bd3-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="70bd3-107">Requirements</span></span>  
 <span data-ttu-id="70bd3-108">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="70bd3-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="70bd3-109">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="70bd3-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="70bd3-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="70bd3-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="70bd3-111">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="70bd3-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
