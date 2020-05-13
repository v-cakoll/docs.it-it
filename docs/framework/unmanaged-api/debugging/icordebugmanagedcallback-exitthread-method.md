---
title: Metodo ICorDebugManagedCallback::ExitThread
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.ExitThread
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::ExitThread
helpviewer_keywords:
- ExitThread method [.NET Framework debugging]
- ICorDebugManagedCallback::ExitThread method [.NET Framework debugging]
ms.assetid: 62db708b-6cf0-45c5-b897-4b5c75bd2505
topic_type:
- apiref
ms.openlocfilehash: 3ba1280aa44a9445f6af7fe9a8769b7cdc7edb66
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83205251"
---
# <a name="icordebugmanagedcallbackexitthread-method"></a><span data-ttu-id="98153-102">Metodo ICorDebugManagedCallback::ExitThread</span><span class="sxs-lookup"><span data-stu-id="98153-102">ICorDebugManagedCallback::ExitThread Method</span></span>
<span data-ttu-id="98153-103">Notifica al debugger che un thread che stava eseguendo il codice gestito è stato terminato.</span><span class="sxs-lookup"><span data-stu-id="98153-103">Notifies the debugger that a thread that was executing managed code has exited.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98153-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="98153-104">Syntax</span></span>  
  
```cpp  
HRESULT ExitThread (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *thread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="98153-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="98153-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="98153-106">in Puntatore a un oggetto ICorDebugAppDomain che rappresenta il dominio applicazione contenente il thread gestito.</span><span class="sxs-lookup"><span data-stu-id="98153-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the managed thread.</span></span>  
  
 `thread`  
 <span data-ttu-id="98153-107">in Puntatore a un oggetto ICorDebugThread che rappresenta il thread gestito.</span><span class="sxs-lookup"><span data-stu-id="98153-107">[in] A pointer to an ICorDebugThread object that represents the managed thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="98153-108">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="98153-108">Remarks</span></span>  
 <span data-ttu-id="98153-109">Una volta `ExitThread` generato il callback, il thread non verrà più visualizzato nelle enumerazioni dei thread.</span><span class="sxs-lookup"><span data-stu-id="98153-109">Once the `ExitThread` callback is fired, the thread will no longer appear in thread enumerations.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="98153-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="98153-110">Requirements</span></span>  
 <span data-ttu-id="98153-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="98153-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="98153-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="98153-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="98153-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="98153-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="98153-114">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="98153-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98153-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="98153-115">See also</span></span>

- [<span data-ttu-id="98153-116">Interfaccia ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="98153-116">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
