---
title: Metodo ICorDebugProcess::EnableLogMessages
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess.EnableLogMessages
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess::EnableLogMessages
helpviewer_keywords:
- ICorDebugProcess::EnableLogMessages method [.NET Framework debugging]
- EnableLogMessages method [.NET Framework debugging]
ms.assetid: 14a4e5a3-3eaf-4f53-9dd1-762726963a23
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4c67d211e9408cec54d069c4d9bad963aeabb09d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocessenablelogmessages-method"></a><span data-ttu-id="3dd70-102">Metodo ICorDebugProcess::EnableLogMessages</span><span class="sxs-lookup"><span data-stu-id="3dd70-102">ICorDebugProcess::EnableLogMessages Method</span></span>
<span data-ttu-id="3dd70-103">Abilita e disabilita la trasmissione dei messaggi di log al debugger.</span><span class="sxs-lookup"><span data-stu-id="3dd70-103">Enables and disables the transmission of log messages to the debugger.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3dd70-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3dd70-104">Syntax</span></span>  
  
```  
HRESULT EnableLogMessages([in]BOOL fOnOff);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3dd70-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="3dd70-105">Parameters</span></span>  
 `fOnOff`  
 <span data-ttu-id="3dd70-106">[in] `true` consente la trasmissione di messaggi di log. `false` disabilita la trasmissione.</span><span class="sxs-lookup"><span data-stu-id="3dd70-106">[in] `true` enables the transmission of log messages; `false` disables the transmission.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3dd70-107">Note</span><span class="sxs-lookup"><span data-stu-id="3dd70-107">Remarks</span></span>  
 <span data-ttu-id="3dd70-108">Questo metodo è valido solo dopo il [ICorDebugManagedCallback::](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) callback si verifica.</span><span class="sxs-lookup"><span data-stu-id="3dd70-108">This method is valid only after the [ICorDebugManagedCallback::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) callback occurs.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3dd70-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3dd70-109">Requirements</span></span>  
 <span data-ttu-id="3dd70-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3dd70-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3dd70-111">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="3dd70-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3dd70-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3dd70-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3dd70-113">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3dd70-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
