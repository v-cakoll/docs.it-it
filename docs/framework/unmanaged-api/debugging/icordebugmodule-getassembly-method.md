---
title: Metodo ICorDebugModule::GetAssembly
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugModule.GetAssembly
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugModule::GetAssembly
helpviewer_keywords:
- ICorDebugModule::GetAssembly method [.NET Framework debugging]
- GetAssembly method [.NET Framework debugging]
ms.assetid: 989762c4-3d15-4485-b8ee-69e0fa8ec895
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7b359b68c1bff91e1077afe8ccf52befe22c246b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmodulegetassembly-method"></a><span data-ttu-id="192b8-102">Metodo ICorDebugModule::GetAssembly</span><span class="sxs-lookup"><span data-stu-id="192b8-102">ICorDebugModule::GetAssembly Method</span></span>
<span data-ttu-id="192b8-103">Ottiene l'assembly per il modulo che lo contiene.</span><span class="sxs-lookup"><span data-stu-id="192b8-103">Gets the containing assembly for this module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="192b8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="192b8-104">Syntax</span></span>  
  
```  
HRESULT GetAssembly(  
    [out] ICorDebugAssembly **ppAssembly  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="192b8-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="192b8-105">Parameters</span></span>  
 `ppAssembly`  
 <span data-ttu-id="192b8-106">[out] Un puntatore a un oggetto ICorDebugAssembly che rappresenta l'assembly contenente questo modulo.</span><span class="sxs-lookup"><span data-stu-id="192b8-106">[out] A pointer to an ICorDebugAssembly object that represents the assembly containing this module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="192b8-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="192b8-107">Requirements</span></span>  
 <span data-ttu-id="192b8-108">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="192b8-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="192b8-109">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="192b8-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="192b8-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="192b8-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="192b8-111">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="192b8-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
