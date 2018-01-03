---
title: Metodo ICorDebugManagedCallback::LogMessage
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback.LogMessage
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback::LogMessage
helpviewer_keywords:
- ICorDebugManagedCallback::LogMessage method [.NET Framework debugging]
- LogMessage method [.NET Framework debugging]
ms.assetid: d218554a-bf42-4d88-833d-ede30de67a53
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d62204e8fb2e1fabae4183bbcf7b4d42b832d2b8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmanagedcallbacklogmessage-method"></a><span data-ttu-id="ca749-102">Metodo ICorDebugManagedCallback::LogMessage</span><span class="sxs-lookup"><span data-stu-id="ca749-102">ICorDebugManagedCallback::LogMessage Method</span></span>
<span data-ttu-id="ca749-103">Notifica al debugger che un thread di common language runtime (CLR) gestito ha chiamato un metodo di <xref:System.Diagnostics.EventLog> classe per registrare un evento.</span><span class="sxs-lookup"><span data-stu-id="ca749-103">Notifies the debugger that a common language runtime (CLR) managed thread has called a method in the <xref:System.Diagnostics.EventLog> class to log an event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca749-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ca749-104">Syntax</span></span>  
  
```  
HRESULT LogMessage (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] LONG                 lLevel,  
    [in] WCHAR               *pLogSwitchName,  
    [in] WCHAR               *pMessage  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ca749-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ca749-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="ca749-106">[in] Un puntatore a un oggetto ICorDebugAppDomain che rappresenta il dominio applicazione che contiene il thread gestito che ha registrato l'evento.</span><span class="sxs-lookup"><span data-stu-id="ca749-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the managed thread that logged the event.</span></span>  
  
 `pThread`  
 <span data-ttu-id="ca749-107">[in] Un puntatore a un oggetto ICorDebugThread che rappresenta il thread gestito.</span><span class="sxs-lookup"><span data-stu-id="ca749-107">[in] A pointer to an ICorDebugThread object that represents the managed thread.</span></span>  
  
 `lLevel`  
 <span data-ttu-id="ca749-108">[in] Il valore di [LoggingLevelEnum](../../../../docs/framework/unmanaged-api/debugging/logginglevelenum-enumeration.md) enumerazione che indica il livello di gravità del messaggio descrittivo scritto nel registro eventi.</span><span class="sxs-lookup"><span data-stu-id="ca749-108">[in] A value of the [LoggingLevelEnum](../../../../docs/framework/unmanaged-api/debugging/logginglevelenum-enumeration.md) enumeration that indicates the severity level of the descriptive message that was written to the event log.</span></span>  
  
 `pLogSwitchName`  
 <span data-ttu-id="ca749-109">[in] Un puntatore al nome dell'opzione di analisi.</span><span class="sxs-lookup"><span data-stu-id="ca749-109">[in] A pointer to the name of the tracing switch.</span></span>  
  
 `pMessage`  
 <span data-ttu-id="ca749-110">[in] Puntatore al messaggio che è stato scritto nel registro eventi.</span><span class="sxs-lookup"><span data-stu-id="ca749-110">[in] A pointer to the message that was written to the event log.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ca749-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ca749-111">Requirements</span></span>  
 <span data-ttu-id="ca749-112">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ca749-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ca749-113">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="ca749-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ca749-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ca749-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ca749-115">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ca749-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca749-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ca749-116">See Also</span></span>  
 [<span data-ttu-id="ca749-117">Interfaccia ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="ca749-117">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
