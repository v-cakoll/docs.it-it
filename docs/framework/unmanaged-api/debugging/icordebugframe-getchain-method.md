---
title: Metodo ICorDebugFrame::GetChain
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugFrame.GetChain
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugFrame::GetChain
helpviewer_keywords:
- ICorDebugFrame::GetChain method [.NET Framework debugging]
- GetChain method [.NET Framework debugging]
ms.assetid: e28e51d3-8f73-494f-bcd4-48bac239fbe1
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3fbde18a15b08b8921c6d31f0fb3c19c85c26cfe
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugframegetchain-method"></a><span data-ttu-id="ed047-102">Metodo ICorDebugFrame::GetChain</span><span class="sxs-lookup"><span data-stu-id="ed047-102">ICorDebugFrame::GetChain Method</span></span>
<span data-ttu-id="ed047-103">Ottiene un puntatore alla catena di di che questo fotogramma fa parte.</span><span class="sxs-lookup"><span data-stu-id="ed047-103">Gets a pointer to the chain this frame is a part of.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed047-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ed047-104">Syntax</span></span>  
  
```  
HRESULT GetChain (  
    [out] ICorDebugChain     **ppChain  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ed047-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ed047-105">Parameters</span></span>  
 `ppChain`  
 <span data-ttu-id="ed047-106">[out] Un puntatore all'indirizzo di un oggetto ICorDebugChain che rappresenta la catena che contiene il frame.</span><span class="sxs-lookup"><span data-stu-id="ed047-106">[out] A pointer to the address of an ICorDebugChain object that represents the chain containing this frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ed047-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ed047-107">Requirements</span></span>  
 <span data-ttu-id="ed047-108">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ed047-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ed047-109">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="ed047-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ed047-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ed047-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ed047-111">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ed047-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
