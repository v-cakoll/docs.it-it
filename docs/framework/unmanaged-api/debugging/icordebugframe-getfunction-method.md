---
title: Metodo ICorDebugFrame::GetFunction
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugFrame.GetFunction
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugFrame::GetFunction
helpviewer_keywords:
- GetFunction method, ICorDebugFrame interface [.NET Framework debugging]
- ICorDebugFrame::GetFunction method [.NET Framework debugging]
ms.assetid: 879d2311-0ff1-4616-a8b3-959ea5868b2e
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d3bd671d90ff924bce32b6d67c33b90b4fa042f3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugframegetfunction-method"></a><span data-ttu-id="82fc6-102">Metodo ICorDebugFrame::GetFunction</span><span class="sxs-lookup"><span data-stu-id="82fc6-102">ICorDebugFrame::GetFunction Method</span></span>
<span data-ttu-id="82fc6-103">Ottiene la funzione che contiene il codice associato a questo stack frame.</span><span class="sxs-lookup"><span data-stu-id="82fc6-103">Gets the function that contains the code associated with this stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82fc6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="82fc6-104">Syntax</span></span>  
  
```  
HRESULT GetFunction (  
    [out] ICorDebugFunction  **ppFunction  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="82fc6-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="82fc6-105">Parameters</span></span>  
 `ppFunction`  
 <span data-ttu-id="82fc6-106">[out] Un puntatore all'indirizzo di un oggetto ICorDebugFunction che rappresenta la funzione contenente il codice associato a questo stack frame.</span><span class="sxs-lookup"><span data-stu-id="82fc6-106">[out] A pointer to the address of an ICorDebugFunction object that represents the function containing the code associated with this stack frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="82fc6-107">Note</span><span class="sxs-lookup"><span data-stu-id="82fc6-107">Remarks</span></span>  
 <span data-ttu-id="82fc6-108">Il `GetFunction` metodo potrebbe non riuscire se il frame non è associato ad alcuna funzione particolare.</span><span class="sxs-lookup"><span data-stu-id="82fc6-108">The `GetFunction` method may fail if the frame is not associated with any particular function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="82fc6-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="82fc6-109">Requirements</span></span>  
 <span data-ttu-id="82fc6-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="82fc6-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="82fc6-111">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="82fc6-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="82fc6-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="82fc6-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="82fc6-113">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="82fc6-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
