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
ms.openlocfilehash: 786582c7118fbed394de7c414a10243616cf4ee1
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209799"
---
# <a name="icordebugmanagedcallbackexitappdomain-method"></a><span data-ttu-id="de8de-102">Metodo ICorDebugManagedCallback::ExitAppDomain</span><span class="sxs-lookup"><span data-stu-id="de8de-102">ICorDebugManagedCallback::ExitAppDomain Method</span></span>
<span data-ttu-id="de8de-103">Notifica al debugger che un dominio applicazione è stato terminato.</span><span class="sxs-lookup"><span data-stu-id="de8de-103">Notifies the debugger that an application domain has exited.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de8de-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="de8de-104">Syntax</span></span>  
  
```cpp  
HRESULT ExitAppDomain (  
    [in] ICorDebugProcess   *pProcess,  
    [in] ICorDebugAppDomain *pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="de8de-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="de8de-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="de8de-106">in Puntatore a un oggetto ICorDebugProcess che rappresenta il processo che contiene il dominio applicazione specificato.</span><span class="sxs-lookup"><span data-stu-id="de8de-106">[in] A pointer to an ICorDebugProcess object that represents the process that contains the given application domain.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="de8de-107">in Puntatore a un oggetto ICorDebugAppDomain che rappresenta il dominio applicazione terminato.</span><span class="sxs-lookup"><span data-stu-id="de8de-107">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that has exited.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="de8de-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="de8de-108">Requirements</span></span>  
 <span data-ttu-id="de8de-109">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="de8de-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="de8de-110">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="de8de-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="de8de-111">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="de8de-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="de8de-112">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="de8de-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de8de-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="de8de-113">See also</span></span>

- [<span data-ttu-id="de8de-114">Interfaccia ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="de8de-114">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
