---
title: Metodo ICorDebugProcess::ModifyLogSwitch
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.ModifyLogSwitch
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::ModifyLogSwitch
helpviewer_keywords:
- ICorDebugProcess::ModifyLogSwitch method [.NET Framework debugging]
- ModifyLogSwitch method [.NET Framework debugging]
ms.assetid: 5fd30875-555e-4e96-877b-5dd266cde7c4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4b1c85499e5269027da2c2a01ab67aab2c5da626
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61775546"
---
# <a name="icordebugprocessmodifylogswitch-method"></a><span data-ttu-id="9c333-102">Metodo ICorDebugProcess::ModifyLogSwitch</span><span class="sxs-lookup"><span data-stu-id="9c333-102">ICorDebugProcess::ModifyLogSwitch Method</span></span>
<span data-ttu-id="9c333-103">Imposta il livello di gravità dell'opzione di log specificato.</span><span class="sxs-lookup"><span data-stu-id="9c333-103">Sets the severity level of the specified log switch.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c333-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9c333-104">Syntax</span></span>  
  
```  
HRESULT ModifyLogSwitch(  
    [in] WCHAR *pLogSwitchName,  
    [in] LONG  lLevel);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9c333-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="9c333-105">Parameters</span></span>  
 `pLogSwitchName`  
 <span data-ttu-id="9c333-106">[in] Un puntatore a una stringa che specifica il nome dell'opzione di log.</span><span class="sxs-lookup"><span data-stu-id="9c333-106">[in] A pointer to a string that specifies the name of the log switch.</span></span>  
  
 `lLevel`  
 <span data-ttu-id="9c333-107">[in] Il livello di gravità da impostare per il commutatore di log specificato.</span><span class="sxs-lookup"><span data-stu-id="9c333-107">[in] The severity level to be set for the specified log switch.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9c333-108">Note</span><span class="sxs-lookup"><span data-stu-id="9c333-108">Remarks</span></span>  
 <span data-ttu-id="9c333-109">Questo metodo è valido solo dopo il [ICorDebugManagedCallback::](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) si è verificato un callback.</span><span class="sxs-lookup"><span data-stu-id="9c333-109">This method is valid only after the [ICorDebugManagedCallback::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) callback has occurred.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9c333-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9c333-110">Requirements</span></span>  
 <span data-ttu-id="9c333-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9c333-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9c333-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9c333-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9c333-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9c333-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9c333-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9c333-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
