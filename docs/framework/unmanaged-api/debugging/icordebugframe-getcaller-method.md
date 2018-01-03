---
title: Metodo ICorDebugFrame::GetCaller
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugFrame.GetCaller
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugFrame::GetCaller
helpviewer_keywords:
- GetCaller method, ICorDebugFrame interface [.NET Framework debugging]
- ICorDebugFrame::GetCaller method [.NET Framework debugging]
ms.assetid: bfdc946b-8238-4eb9-8a85-884049fb0fd4
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f465dd123b517b347a29118f3092f244c2212cd9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugframegetcaller-method"></a><span data-ttu-id="75793-102">Metodo ICorDebugFrame::GetCaller</span><span class="sxs-lookup"><span data-stu-id="75793-102">ICorDebugFrame::GetCaller Method</span></span>
<span data-ttu-id="75793-103">Ottiene un puntatore all'oggetto ICorDebugFrame nella catena che ha chiamato il frame corrente.</span><span class="sxs-lookup"><span data-stu-id="75793-103">Gets a pointer to the ICorDebugFrame object in the current chain that called this frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75793-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="75793-104">Syntax</span></span>  
  
```  
HRESULT GetCaller (  
    [out] ICorDebugFrame     **ppFrame  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="75793-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="75793-105">Parameters</span></span>  
 `ppFrame`  
 <span data-ttu-id="75793-106">[out] Un puntatore all'indirizzo di un `ICorDebugFrame` oggetto che rappresenta il frame del chiamante.</span><span class="sxs-lookup"><span data-stu-id="75793-106">[out] A pointer to the address of an `ICorDebugFrame` object that represents the calling frame.</span></span> <span data-ttu-id="75793-107">Questo valore è null se il frame chiamato cornice più esterna della catena corrente.</span><span class="sxs-lookup"><span data-stu-id="75793-107">This value is null if the called frame is the outermost frame in the current chain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="75793-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="75793-108">Requirements</span></span>  
 <span data-ttu-id="75793-109">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="75793-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="75793-110">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="75793-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="75793-111">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="75793-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="75793-112">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="75793-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
