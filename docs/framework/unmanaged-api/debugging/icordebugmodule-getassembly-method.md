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
ms.openlocfilehash: 98d4670fc1d571d2a959b2a69ea8619bd8b40007
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugmodulegetassembly-method"></a><span data-ttu-id="9a2e7-102">Metodo ICorDebugModule::GetAssembly</span><span class="sxs-lookup"><span data-stu-id="9a2e7-102">ICorDebugModule::GetAssembly Method</span></span>
<span data-ttu-id="9a2e7-103">Ottiene l'assembly per il modulo che lo contiene.</span><span class="sxs-lookup"><span data-stu-id="9a2e7-103">Gets the containing assembly for this module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a2e7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9a2e7-104">Syntax</span></span>  
  
```  
HRESULT GetAssembly(  
    [out] ICorDebugAssembly **ppAssembly  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9a2e7-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="9a2e7-105">Parameters</span></span>  
 `ppAssembly`  
 <span data-ttu-id="9a2e7-106">[out] Un puntatore a un oggetto ICorDebugAssembly che rappresenta l'assembly contenente questo modulo.</span><span class="sxs-lookup"><span data-stu-id="9a2e7-106">[out] A pointer to an ICorDebugAssembly object that represents the assembly containing this module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9a2e7-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9a2e7-107">Requirements</span></span>  
 <span data-ttu-id="9a2e7-108">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9a2e7-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9a2e7-109">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="9a2e7-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9a2e7-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9a2e7-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9a2e7-111">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9a2e7-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
