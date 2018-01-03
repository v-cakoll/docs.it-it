---
title: Metodo ICorDebugProcess::GetID
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess.GetID
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess::GetID
helpviewer_keywords:
- GetID method, ICorDebugProcess interface [.NET Framework debugging]
- ICorDebugProcess::GetID method [.NET Framework debugging]
ms.assetid: b0ba8453-fa7e-4c14-93e5-335409cd4a47
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d09888434048c312bd78dddf29d39a45f023695e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocessgetid-method"></a><span data-ttu-id="4cee4-102">Metodo ICorDebugProcess::GetID</span><span class="sxs-lookup"><span data-stu-id="4cee4-102">ICorDebugProcess::GetID Method</span></span>
<span data-ttu-id="4cee4-103">Ottiene l'ID del sistema operativo () del processo.</span><span class="sxs-lookup"><span data-stu-id="4cee4-103">Gets the operating system (OS) ID of the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4cee4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4cee4-104">Syntax</span></span>  
  
```  
HRESULT GetID([out] DWORD *pdwProcessId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4cee4-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="4cee4-105">Parameters</span></span>  
 `pdwProcessId`  
 <span data-ttu-id="4cee4-106">[out] ID univoco del processo.</span><span class="sxs-lookup"><span data-stu-id="4cee4-106">[out] The unique ID of the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4cee4-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4cee4-107">Requirements</span></span>  
 <span data-ttu-id="4cee4-108">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4cee4-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4cee4-109">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="4cee4-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4cee4-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4cee4-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4cee4-111">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4cee4-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
