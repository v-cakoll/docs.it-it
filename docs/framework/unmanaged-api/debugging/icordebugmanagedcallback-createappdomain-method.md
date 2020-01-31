---
title: Metodo ICorDebugManagedCallback::CreateAppDomain
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.CreateAppDomain
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::CreateAppDomain
helpviewer_keywords:
- CreateAppDomain method [.NET Framework debugging]
- ICorDebugManagedCallback::CreateAppDomain method [.NET Framework debugging]
ms.assetid: 48d410d7-6749-4125-a8fd-f9562c7088e9
topic_type:
- apiref
ms.openlocfilehash: 35ea69d32ee9b994cc0bf91339c798edcd472f44
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788419"
---
# <a name="icordebugmanagedcallbackcreateappdomain-method"></a><span data-ttu-id="ebc3c-102">Metodo ICorDebugManagedCallback::CreateAppDomain</span><span class="sxs-lookup"><span data-stu-id="ebc3c-102">ICorDebugManagedCallback::CreateAppDomain Method</span></span>
<span data-ttu-id="ebc3c-103">Notifica al debugger che è stato creato un dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="ebc3c-103">Notifies the debugger that an application domain has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ebc3c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ebc3c-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateAppDomain (  
    [in] ICorDebugProcess   *pProcess,  
    [in] ICorDebugAppDomain *pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ebc3c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ebc3c-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="ebc3c-106">in Puntatore a un oggetto ICorDebugProcess che rappresenta il processo in cui è stato creato il dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="ebc3c-106">[in] A pointer to an ICorDebugProcess object that represents the process in which the application domain was created.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="ebc3c-107">in Puntatore a un oggetto ICorDebugAppDomain che rappresenta il dominio applicazione creato.</span><span class="sxs-lookup"><span data-stu-id="ebc3c-107">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that has been created.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ebc3c-108">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="ebc3c-108">Requirements</span></span>  
 <span data-ttu-id="ebc3c-109">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ebc3c-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ebc3c-110">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ebc3c-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ebc3c-111">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ebc3c-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ebc3c-112">**Versioni .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ebc3c-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ebc3c-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ebc3c-113">See also</span></span>

- [<span data-ttu-id="ebc3c-114">Interfaccia ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="ebc3c-114">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
