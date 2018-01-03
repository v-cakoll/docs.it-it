---
title: Metodo ICorDebugAssembly::EnumerateModules
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugAssembly.EnumerateModules
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugAssembly::EnumerateModules
helpviewer_keywords:
- ICorDebugAssembly::EnumerateModules method [.NET Framework debugging]
- EnumerateModules method [.NET Framework debugging]
ms.assetid: c7ba51a1-0dd5-4452-b471-232febe0f897
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e5bc6aced78d1d7ffc6521bca52bed1b2e232bbe
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugassemblyenumeratemodules-method"></a><span data-ttu-id="3fd7f-102">Metodo ICorDebugAssembly::EnumerateModules</span><span class="sxs-lookup"><span data-stu-id="3fd7f-102">ICorDebugAssembly::EnumerateModules Method</span></span>
<span data-ttu-id="3fd7f-103">Ottiene un enumeratore per i moduli inclusi nel `ICorDebugAssembly`.</span><span class="sxs-lookup"><span data-stu-id="3fd7f-103">Gets an enumerator for the modules contained in the `ICorDebugAssembly`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3fd7f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3fd7f-104">Syntax</span></span>  
  
```  
HRESULT EnumerateModules (  
    [out] ICorDebugModuleEnum **ppModules  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3fd7f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="3fd7f-105">Parameters</span></span>  
 `ppModules`  
 <span data-ttu-id="3fd7f-106">[out] Un puntatore all'indirizzo dell'interfaccia ICorDebugModuleEnum che è l'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="3fd7f-106">[out] A pointer to the address of the ICorDebugModuleEnum interface that is the enumerator.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3fd7f-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3fd7f-107">Requirements</span></span>  
 <span data-ttu-id="3fd7f-108">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3fd7f-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3fd7f-109">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="3fd7f-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3fd7f-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3fd7f-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3fd7f-111">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3fd7f-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
