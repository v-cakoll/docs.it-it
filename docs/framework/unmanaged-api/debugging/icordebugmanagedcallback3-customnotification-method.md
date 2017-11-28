---
title: Metodo ICorDebugManagedCallback3::CustomNotification
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback3.CustomNotification Method
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback3::CustomNotification
helpviewer_keywords:
- ICorDebugManagedCallback3::CustomNotification method [.NET Framework debugging]
- CustomNotification method [.NET Framework debugging]
ms.assetid: 5e5422ac-afa1-403d-a894-2d7348673e38
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: edff9c4b19131fcdfd4510c4020612acb43b6305
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugmanagedcallback3customnotification-method"></a><span data-ttu-id="027aa-102">Metodo ICorDebugManagedCallback3::CustomNotification</span><span class="sxs-lookup"><span data-stu-id="027aa-102">ICorDebugManagedCallback3::CustomNotification Method</span></span>
<span data-ttu-id="027aa-103">Indica che è stata generata una notifica di debugger personalizzate.</span><span class="sxs-lookup"><span data-stu-id="027aa-103">Indicates that a custom debugger notification has been raised.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="027aa-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="027aa-104">Syntax</span></span>  
  
```  
HRESULT CustomNotification(ICorDebugThread *    pThread,  
                           ICorDebugAppDomain * pAppDomain);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="027aa-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="027aa-105">Parameters</span></span>  
 `pThread`  
 <span data-ttu-id="027aa-106">[in] Puntatore al thread che ha generato la notifica.</span><span class="sxs-lookup"><span data-stu-id="027aa-106">[in] A pointer to the thread that raised the notification.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="027aa-107">[in] Puntatore al dominio applicazione che contiene il thread che ha generato la notifica.</span><span class="sxs-lookup"><span data-stu-id="027aa-107">[in] A pointer to the application domain that contains the thread that raised the notification.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="027aa-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="027aa-108">Return Value</span></span>  
 <span data-ttu-id="027aa-109">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="027aa-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="027aa-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="027aa-110">HRESULT</span></span>|<span data-ttu-id="027aa-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="027aa-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="027aa-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="027aa-112">S_OK</span></span>|<span data-ttu-id="027aa-113">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="027aa-113">The method completed successfully.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="027aa-114">Eccezioni</span><span class="sxs-lookup"><span data-stu-id="027aa-114">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="027aa-115">Note</span><span class="sxs-lookup"><span data-stu-id="027aa-115">Remarks</span></span>  
 <span data-ttu-id="027aa-116">Una chiamata successiva al [ICorDebugThread4:: GetCurrentCustomDebuggerNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-getcurrentcustomdebuggernotification-method.md) che consente di recuperare l'oggetto thread che è stato passato il <xref:System.Diagnostics.Debugger.NotifyOfCrossThreadDependency%2A?displayProperty=nameWithType> metodo.</span><span class="sxs-lookup"><span data-stu-id="027aa-116">A subsequent call to the [ICorDebugThread4::GetCurrentCustomDebuggerNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-getcurrentcustomdebuggernotification-method.md) method retrieves the thread object that was passed to the <xref:System.Diagnostics.Debugger.NotifyOfCrossThreadDependency%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="027aa-117">Tipo dell'oggetto thread deve avere stato abilitato in precedenza chiamando il [ICorDebugProcess3:: SetEnableCustomNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess3-setenablecustomnotification-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="027aa-117">The thread object's type must have been previously enabled by calling the [ICorDebugProcess3::SetEnableCustomNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess3-setenablecustomnotification-method.md) method.</span></span> <span data-ttu-id="027aa-118">Il debugger può leggere i parametri specifici del tipo rispetto ai campi dell'oggetto thread e può archiviare le risposte nei campi.</span><span class="sxs-lookup"><span data-stu-id="027aa-118">The debugger can read type-specific parameters from the fields of the thread object, and can store responses into fields.</span></span>  
  
 <span data-ttu-id="027aa-119">Il [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) interfaccia non impone criteri sui tipi di notifiche o il relativo contenuto e la semantica delle notifiche è rigorosamente un contratto tra debugger, applicazioni e .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="027aa-119">The [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) interface imposes no policy on the types of notifications or their contents, and the semantics of the notifications are strictly a contract between debuggers, applications, and the .NET Framework.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="027aa-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="027aa-120">Requirements</span></span>  
 <span data-ttu-id="027aa-121">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="027aa-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="027aa-122">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="027aa-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="027aa-123">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="027aa-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="027aa-124">**Versioni di .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="027aa-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="027aa-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="027aa-125">See Also</span></span>  
 [<span data-ttu-id="027aa-126">ICorDebugManagedCallback3 (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="027aa-126">ICorDebugManagedCallback3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-interface.md)  
 [<span data-ttu-id="027aa-127">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="027aa-127">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="027aa-128">Debug</span><span class="sxs-lookup"><span data-stu-id="027aa-128">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
