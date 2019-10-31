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
ms.openlocfilehash: 86b8737577bdb5f61f1061cb217620fae03ebd0c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139380"
---
# <a name="icordebugprocessmodifylogswitch-method"></a><span data-ttu-id="3d1d5-102">Metodo ICorDebugProcess::ModifyLogSwitch</span><span class="sxs-lookup"><span data-stu-id="3d1d5-102">ICorDebugProcess::ModifyLogSwitch Method</span></span>
<span data-ttu-id="3d1d5-103">Imposta il livello di gravità dell'opzione di log specificata.</span><span class="sxs-lookup"><span data-stu-id="3d1d5-103">Sets the severity level of the specified log switch.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d1d5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3d1d5-104">Syntax</span></span>  
  
```cpp  
HRESULT ModifyLogSwitch(  
    [in] WCHAR *pLogSwitchName,  
    [in] LONG  lLevel);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3d1d5-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="3d1d5-105">Parameters</span></span>  
 `pLogSwitchName`  
 <span data-ttu-id="3d1d5-106">in Puntatore a una stringa che specifica il nome dell'opzione di log.</span><span class="sxs-lookup"><span data-stu-id="3d1d5-106">[in] A pointer to a string that specifies the name of the log switch.</span></span>  
  
 `lLevel`  
 <span data-ttu-id="3d1d5-107">in Livello di gravità da impostare per l'opzione di log specificata.</span><span class="sxs-lookup"><span data-stu-id="3d1d5-107">[in] The severity level to be set for the specified log switch.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3d1d5-108">Note</span><span class="sxs-lookup"><span data-stu-id="3d1d5-108">Remarks</span></span>  
 <span data-ttu-id="3d1d5-109">Questo metodo è valido solo dopo che si è verificato il callback [ICorDebugManagedCallback:: CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) .</span><span class="sxs-lookup"><span data-stu-id="3d1d5-109">This method is valid only after the [ICorDebugManagedCallback::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) callback has occurred.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3d1d5-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3d1d5-110">Requirements</span></span>  
 <span data-ttu-id="3d1d5-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3d1d5-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3d1d5-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3d1d5-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3d1d5-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3d1d5-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3d1d5-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3d1d5-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
