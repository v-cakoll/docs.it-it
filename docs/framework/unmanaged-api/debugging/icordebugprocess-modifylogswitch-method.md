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
ms.openlocfilehash: c9375854b45432eafb6cc706a1a62f5424e0fee8
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210488"
---
# <a name="icordebugprocessmodifylogswitch-method"></a><span data-ttu-id="58768-102">Metodo ICorDebugProcess::ModifyLogSwitch</span><span class="sxs-lookup"><span data-stu-id="58768-102">ICorDebugProcess::ModifyLogSwitch Method</span></span>
<span data-ttu-id="58768-103">Imposta il livello di gravità dell'opzione di log specificata.</span><span class="sxs-lookup"><span data-stu-id="58768-103">Sets the severity level of the specified log switch.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58768-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="58768-104">Syntax</span></span>  
  
```cpp  
HRESULT ModifyLogSwitch(  
    [in] WCHAR *pLogSwitchName,  
    [in] LONG  lLevel);  
```  
  
## <a name="parameters"></a><span data-ttu-id="58768-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="58768-105">Parameters</span></span>  
 `pLogSwitchName`  
 <span data-ttu-id="58768-106">in Puntatore a una stringa che specifica il nome dell'opzione di log.</span><span class="sxs-lookup"><span data-stu-id="58768-106">[in] A pointer to a string that specifies the name of the log switch.</span></span>  
  
 `lLevel`  
 <span data-ttu-id="58768-107">in Livello di gravità da impostare per l'opzione di log specificata.</span><span class="sxs-lookup"><span data-stu-id="58768-107">[in] The severity level to be set for the specified log switch.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="58768-108">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="58768-108">Remarks</span></span>  
 <span data-ttu-id="58768-109">Questo metodo è valido solo dopo che si è verificato il callback [ICorDebugManagedCallback:: CreateProcess](icordebugmanagedcallback-createprocess-method.md) .</span><span class="sxs-lookup"><span data-stu-id="58768-109">This method is valid only after the [ICorDebugManagedCallback::CreateProcess](icordebugmanagedcallback-createprocess-method.md) callback has occurred.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="58768-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="58768-110">Requirements</span></span>  
 <span data-ttu-id="58768-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="58768-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="58768-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="58768-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="58768-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="58768-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="58768-114">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="58768-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
