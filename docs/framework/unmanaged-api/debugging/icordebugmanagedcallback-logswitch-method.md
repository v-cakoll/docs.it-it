---
title: Metodo ICorDebugManagedCallback::LogSwitch
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.LogSwitch
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::LogSwitch
helpviewer_keywords:
- LogSwitch method [.NET Framework debugging]
- ICorDebugManagedCallback::LogSwitch method [.NET Framework debugging]
ms.assetid: 0ac59d27-783f-4a87-b7a8-baa3ccc54582
topic_type:
- apiref
ms.openlocfilehash: a72eabb1b405c67f5603164e56a589a237603d2f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130687"
---
# <a name="icordebugmanagedcallbacklogswitch-method"></a><span data-ttu-id="e56c3-102">Metodo ICorDebugManagedCallback::LogSwitch</span><span class="sxs-lookup"><span data-stu-id="e56c3-102">ICorDebugManagedCallback::LogSwitch Method</span></span>
<span data-ttu-id="e56c3-103">Notifica al debugger che un thread gestito di Common Language Runtime (CLR) ha chiamato un metodo nella classe <xref:System.Diagnostics.Switch> per creare, modificare o eliminare un'opzione di debug/traccia.</span><span class="sxs-lookup"><span data-stu-id="e56c3-103">Notifies the debugger that a common language runtime (CLR) managed thread has called a method in the <xref:System.Diagnostics.Switch> class to create, modify, or delete a debugging/tracing switch.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e56c3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e56c3-104">Syntax</span></span>  
  
```cpp  
HRESULT LogSwitch (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] LONG                 lLevel,  
    [in] ULONG                ulReason,  
    [in] WCHAR               *pLogSwitchName,  
    [in] WCHAR               *pParentName);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e56c3-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e56c3-105">Parameters</span></span>  
 `PAppDomain`  
 <span data-ttu-id="e56c3-106">in Puntatore a un oggetto ICorDebugAppDomain che rappresenta il dominio applicazione contenente il thread gestito che ha creato, modificato o eliminato un'opzione di debug/traccia.</span><span class="sxs-lookup"><span data-stu-id="e56c3-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the managed thread that created, modified, or deleted a debugging/tracing switch.</span></span>  
  
 `pThread`  
 <span data-ttu-id="e56c3-107">in Puntatore a un oggetto ICorDebugThread che rappresenta il thread gestito.</span><span class="sxs-lookup"><span data-stu-id="e56c3-107">[in] A pointer to an ICorDebugThread object that represents the managed thread.</span></span>  
  
 `lLevel`  
 <span data-ttu-id="e56c3-108">in Valore che indica il livello di gravità del messaggio descrittivo che è stato scritto nel log eventi.</span><span class="sxs-lookup"><span data-stu-id="e56c3-108">[in] A value that indicates the severity level of the descriptive message that was written to the event log.</span></span>  
  
 `ulReason`  
 <span data-ttu-id="e56c3-109">in Valore dell'enumerazione [LogSwitchCallReason](../../../../docs/framework/unmanaged-api/debugging/logswitchcallreason-enumeration.md) che indica l'operazione eseguita sull'opzione di debug/traccia.</span><span class="sxs-lookup"><span data-stu-id="e56c3-109">[in] A value of the [LogSwitchCallReason](../../../../docs/framework/unmanaged-api/debugging/logswitchcallreason-enumeration.md) enumeration that indicates the operation performed on the debugging/tracing switch.</span></span>  
  
 `pLogSwitchName`  
 <span data-ttu-id="e56c3-110">in Puntatore al nome dell'opzione di debug/traccia.</span><span class="sxs-lookup"><span data-stu-id="e56c3-110">[in] A pointer to the name of the debugging/tracing switch.</span></span>  
  
 `pParentName`  
 <span data-ttu-id="e56c3-111">in Puntatore al nome dell'elemento padre dell'opzione di debug/traccia.</span><span class="sxs-lookup"><span data-stu-id="e56c3-111">[in] A pointer to the name of the parent of the debugging/tracing switch.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e56c3-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e56c3-112">Requirements</span></span>  
 <span data-ttu-id="e56c3-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e56c3-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e56c3-114">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e56c3-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e56c3-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e56c3-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e56c3-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e56c3-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e56c3-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e56c3-117">See also</span></span>

- [<span data-ttu-id="e56c3-118">Interfaccia ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="e56c3-118">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
