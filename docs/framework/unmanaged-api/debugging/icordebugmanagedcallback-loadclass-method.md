---
title: Metodo ICorDebugManagedCallback::LoadClass
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback.LoadClass
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback::LoadClass
helpviewer_keywords:
- ICorDebugManagedCallback::LoadClass method [.NET Framework debugging]
- LoadClass method [.NET Framework debugging]
ms.assetid: e58dac7b-85c3-41ca-b9aa-3a7fc9ae6680
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3518a20567cdac8ed6587aa3dc06408ae6bf7b06
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugmanagedcallbackloadclass-method"></a><span data-ttu-id="546d7-102">Metodo ICorDebugManagedCallback::LoadClass</span><span class="sxs-lookup"><span data-stu-id="546d7-102">ICorDebugManagedCallback::LoadClass Method</span></span>
<span data-ttu-id="546d7-103">Notifica al debugger che è stata caricata una classe.</span><span class="sxs-lookup"><span data-stu-id="546d7-103">Notifies the debugger that a class has been loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="546d7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="546d7-104">Syntax</span></span>  
  
```  
HRESULT LoadClass (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugClass     *c  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="546d7-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="546d7-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="546d7-106">[in] Un puntatore a un oggetto ICorDebugAppDomain che rappresenta il dominio applicazione in cui è stata caricata la classe.</span><span class="sxs-lookup"><span data-stu-id="546d7-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain into which the class has been loaded.</span></span>  
  
 `c`  
 <span data-ttu-id="546d7-107">[in] Un puntatore a un oggetto ICorDebugClass che rappresenta la classe.</span><span class="sxs-lookup"><span data-stu-id="546d7-107">[in] A pointer to an ICorDebugClass object that represents the class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="546d7-108">Note</span><span class="sxs-lookup"><span data-stu-id="546d7-108">Remarks</span></span>  
 <span data-ttu-id="546d7-109">Questo callback si verifica solo se il caricamento delle classi è stato abilitato per il modulo che contiene la classe.</span><span class="sxs-lookup"><span data-stu-id="546d7-109">This callback occurs only if class loading has been enabled for the module that contains the class.</span></span> <span data-ttu-id="546d7-110">Caricamento di classe è sempre abilitato per i moduli dinamici.</span><span class="sxs-lookup"><span data-stu-id="546d7-110">Class loading is always enabled for dynamic modules.</span></span>  
  
 <span data-ttu-id="546d7-111">Il `LoadClass` callback fornisce un momento appropriato per associare i punti di interruzione a classi appena generate nei moduli dinamici.</span><span class="sxs-lookup"><span data-stu-id="546d7-111">The `LoadClass` callback provides an appropriate time to bind breakpoints to newly generated classes in dynamic modules.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="546d7-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="546d7-112">Requirements</span></span>  
 <span data-ttu-id="546d7-113">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="546d7-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="546d7-114">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="546d7-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="546d7-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="546d7-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="546d7-116">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="546d7-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="546d7-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="546d7-117">See Also</span></span>  
 [<span data-ttu-id="546d7-118">UnloadClass (metodo)</span><span class="sxs-lookup"><span data-stu-id="546d7-118">UnloadClass Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md)  
 [<span data-ttu-id="546d7-119">ICorDebugManagedCallback (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="546d7-119">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
