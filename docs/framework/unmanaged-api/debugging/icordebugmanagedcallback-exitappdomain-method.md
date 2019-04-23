---
title: Metodo ICorDebugManagedCallback::ExitAppDomain
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.ExitAppDomain
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::ExitAppDomain
helpviewer_keywords:
- ICorDebugManagedCallback::ExitAppDomain method [.NET Framework debugging]
- ExitAppDomain method [.NET Framework debugging]
ms.assetid: d815486e-b3bd-4fe8-ba28-02abdb4d67ba
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: aed6ccd938761385aafd21802829bd741847b4ba
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59110240"
---
# <a name="icordebugmanagedcallbackexitappdomain-method"></a><span data-ttu-id="17302-102">Metodo ICorDebugManagedCallback::ExitAppDomain</span><span class="sxs-lookup"><span data-stu-id="17302-102">ICorDebugManagedCallback::ExitAppDomain Method</span></span>
<span data-ttu-id="17302-103">Notifica al debugger che è stato chiuso un dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="17302-103">Notifies the debugger that an application domain has exited.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="17302-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="17302-104">Syntax</span></span>  
  
```  
HRESULT ExitAppDomain (  
    [in] ICorDebugProcess   *pProcess,  
    [in] ICorDebugAppDomain *pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="17302-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="17302-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="17302-106">[in] Un puntatore a un oggetto ICorDebugProcess che rappresenta il processo che contiene il dominio applicazione specificato.</span><span class="sxs-lookup"><span data-stu-id="17302-106">[in] A pointer to an ICorDebugProcess object that represents the process that contains the given application domain.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="17302-107">[in] Un puntatore a un oggetto ICorDebugAppDomain che rappresenta il dominio dell'applicazione che è stato terminato.</span><span class="sxs-lookup"><span data-stu-id="17302-107">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that has exited.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="17302-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="17302-108">Requirements</span></span>  
 <span data-ttu-id="17302-109">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="17302-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="17302-110">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="17302-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="17302-111">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="17302-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="17302-112">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="17302-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17302-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="17302-113">See also</span></span>

- [<span data-ttu-id="17302-114">Interfaccia ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="17302-114">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
