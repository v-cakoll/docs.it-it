---
title: Metodo ICorDebugManagedCallback::LoadClass
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.LoadClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::LoadClass
helpviewer_keywords:
- ICorDebugManagedCallback::LoadClass method [.NET Framework debugging]
- LoadClass method [.NET Framework debugging]
ms.assetid: e58dac7b-85c3-41ca-b9aa-3a7fc9ae6680
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f1d920a97338bba3e90ec8f0c440f6dd2a93e722
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33416205"
---
# <a name="icordebugmanagedcallbackloadclass-method"></a><span data-ttu-id="0fb10-102">Metodo ICorDebugManagedCallback::LoadClass</span><span class="sxs-lookup"><span data-stu-id="0fb10-102">ICorDebugManagedCallback::LoadClass Method</span></span>
<span data-ttu-id="0fb10-103">Notifica al debugger che è stata caricata una classe.</span><span class="sxs-lookup"><span data-stu-id="0fb10-103">Notifies the debugger that a class has been loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0fb10-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0fb10-104">Syntax</span></span>  
  
```  
HRESULT LoadClass (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugClass     *c  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0fb10-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="0fb10-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="0fb10-106">[in] Un puntatore a un oggetto ICorDebugAppDomain che rappresenta il dominio applicazione in cui è stata caricata la classe.</span><span class="sxs-lookup"><span data-stu-id="0fb10-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain into which the class has been loaded.</span></span>  
  
 `c`  
 <span data-ttu-id="0fb10-107">[in] Un puntatore a un oggetto ICorDebugClass che rappresenta la classe.</span><span class="sxs-lookup"><span data-stu-id="0fb10-107">[in] A pointer to an ICorDebugClass object that represents the class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0fb10-108">Note</span><span class="sxs-lookup"><span data-stu-id="0fb10-108">Remarks</span></span>  
 <span data-ttu-id="0fb10-109">Questo callback si verifica solo se il caricamento delle classi è stato abilitato per il modulo che contiene la classe.</span><span class="sxs-lookup"><span data-stu-id="0fb10-109">This callback occurs only if class loading has been enabled for the module that contains the class.</span></span> <span data-ttu-id="0fb10-110">Caricamento di classe è sempre abilitato per i moduli dinamici.</span><span class="sxs-lookup"><span data-stu-id="0fb10-110">Class loading is always enabled for dynamic modules.</span></span>  
  
 <span data-ttu-id="0fb10-111">Il `LoadClass` callback fornisce un momento appropriato per associare i punti di interruzione a classi appena generate nei moduli dinamici.</span><span class="sxs-lookup"><span data-stu-id="0fb10-111">The `LoadClass` callback provides an appropriate time to bind breakpoints to newly generated classes in dynamic modules.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0fb10-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0fb10-112">Requirements</span></span>  
 <span data-ttu-id="0fb10-113">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0fb10-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0fb10-114">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="0fb10-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0fb10-115">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="0fb10-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0fb10-116">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0fb10-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0fb10-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0fb10-117">See Also</span></span>  
 [<span data-ttu-id="0fb10-118">Metodo UnloadClass</span><span class="sxs-lookup"><span data-stu-id="0fb10-118">UnloadClass Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md)  
 [<span data-ttu-id="0fb10-119">Interfaccia ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="0fb10-119">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
