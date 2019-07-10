---
title: Metodo ICorDebugProcess::EnableLogMessages
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.EnableLogMessages
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::EnableLogMessages
helpviewer_keywords:
- ICorDebugProcess::EnableLogMessages method [.NET Framework debugging]
- EnableLogMessages method [.NET Framework debugging]
ms.assetid: 14a4e5a3-3eaf-4f53-9dd1-762726963a23
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b199d3226ec391fadc356b5efacdbf10a3e25adf
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67766167"
---
# <a name="icordebugprocessenablelogmessages-method"></a><span data-ttu-id="f56a9-102">Metodo ICorDebugProcess::EnableLogMessages</span><span class="sxs-lookup"><span data-stu-id="f56a9-102">ICorDebugProcess::EnableLogMessages Method</span></span>
<span data-ttu-id="f56a9-103">Abilita e disabilita la trasmissione di messaggi di log per il debugger.</span><span class="sxs-lookup"><span data-stu-id="f56a9-103">Enables and disables the transmission of log messages to the debugger.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f56a9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f56a9-104">Syntax</span></span>  
  
```cpp  
HRESULT EnableLogMessages([in]BOOL fOnOff);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f56a9-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f56a9-105">Parameters</span></span>  
 `fOnOff`  
 <span data-ttu-id="f56a9-106">[in] `true` consente la trasmissione dei messaggi di log. `false` disabilita la trasmissione.</span><span class="sxs-lookup"><span data-stu-id="f56a9-106">[in] `true` enables the transmission of log messages; `false` disables the transmission.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f56a9-107">Note</span><span class="sxs-lookup"><span data-stu-id="f56a9-107">Remarks</span></span>  
 <span data-ttu-id="f56a9-108">Questo metodo è valido solo dopo il [ICorDebugManagedCallback::](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) callback si verifica.</span><span class="sxs-lookup"><span data-stu-id="f56a9-108">This method is valid only after the [ICorDebugManagedCallback::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) callback occurs.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f56a9-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f56a9-109">Requirements</span></span>  
 <span data-ttu-id="f56a9-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f56a9-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f56a9-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f56a9-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f56a9-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f56a9-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f56a9-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f56a9-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
