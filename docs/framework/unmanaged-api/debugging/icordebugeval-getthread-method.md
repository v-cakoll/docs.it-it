---
title: Metodo ICorDebugEval::GetThread
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugEval.GetThread
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugEval::GetThread
helpviewer_keywords:
- GetThread method, ICorDebugEval interface [.NET Framework debugging]
- ICorDebugEval::GetThread method [.NET Framework debugging]
ms.assetid: 57163b0d-c8a7-44af-9078-e7a895d29f9a
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: cde844d0664f7dc7643ef60b65befa95f2d039e5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugevalgetthread-method"></a><span data-ttu-id="51489-102">Metodo ICorDebugEval::GetThread</span><span class="sxs-lookup"><span data-stu-id="51489-102">ICorDebugEval::GetThread Method</span></span>
<span data-ttu-id="51489-103">Ottiene il thread in cui questa valutazione è in esecuzione o verrà eseguito.</span><span class="sxs-lookup"><span data-stu-id="51489-103">Gets the thread in which this evaluation is executing or will execute.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51489-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="51489-104">Syntax</span></span>  
  
```  
HRESULT GetThread (  
    [out] ICorDebugThread   **ppThread  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="51489-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="51489-105">Parameters</span></span>  
 `ppThread`  
 <span data-ttu-id="51489-106">[out] Un puntatore all'indirizzo di un oggetto ICorDebugThread che rappresenta il thread.</span><span class="sxs-lookup"><span data-stu-id="51489-106">[out] A pointer to the address of an ICorDebugThread object that represents the thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="51489-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="51489-107">Requirements</span></span>  
 <span data-ttu-id="51489-108">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="51489-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="51489-109">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="51489-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="51489-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="51489-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="51489-111">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="51489-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
