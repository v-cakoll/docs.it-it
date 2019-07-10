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
ms.openlocfilehash: 96db1ca115ffed47b5eb8eadd9c3d2f620060c4a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67755443"
---
# <a name="icordebugprocessmodifylogswitch-method"></a><span data-ttu-id="fe22b-102">Metodo ICorDebugProcess::ModifyLogSwitch</span><span class="sxs-lookup"><span data-stu-id="fe22b-102">ICorDebugProcess::ModifyLogSwitch Method</span></span>
<span data-ttu-id="fe22b-103">Imposta il livello di gravità dell'opzione di log specificato.</span><span class="sxs-lookup"><span data-stu-id="fe22b-103">Sets the severity level of the specified log switch.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe22b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fe22b-104">Syntax</span></span>  
  
```cpp  
HRESULT ModifyLogSwitch(  
    [in] WCHAR *pLogSwitchName,  
    [in] LONG  lLevel);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fe22b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="fe22b-105">Parameters</span></span>  
 `pLogSwitchName`  
 <span data-ttu-id="fe22b-106">[in] Un puntatore a una stringa che specifica il nome dell'opzione di log.</span><span class="sxs-lookup"><span data-stu-id="fe22b-106">[in] A pointer to a string that specifies the name of the log switch.</span></span>  
  
 `lLevel`  
 <span data-ttu-id="fe22b-107">[in] Il livello di gravità da impostare per il commutatore di log specificato.</span><span class="sxs-lookup"><span data-stu-id="fe22b-107">[in] The severity level to be set for the specified log switch.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fe22b-108">Note</span><span class="sxs-lookup"><span data-stu-id="fe22b-108">Remarks</span></span>  
 <span data-ttu-id="fe22b-109">Questo metodo è valido solo dopo il [ICorDebugManagedCallback::](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) si è verificato un callback.</span><span class="sxs-lookup"><span data-stu-id="fe22b-109">This method is valid only after the [ICorDebugManagedCallback::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) callback has occurred.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fe22b-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fe22b-110">Requirements</span></span>  
 <span data-ttu-id="fe22b-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fe22b-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fe22b-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fe22b-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fe22b-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fe22b-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fe22b-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fe22b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
