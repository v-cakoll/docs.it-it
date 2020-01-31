---
title: Metodo ICorDebugManagedCallback::Exception
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.Exception
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::Exception
helpviewer_keywords:
- Exception method, ICorDebugManagedCallback interface [.NET Framework debugging]
- ICorDebugManagedCallback::Exception method [.NET Framework debugging]
ms.assetid: ab18a509-dff3-4930-b585-bd15e0414176
topic_type:
- apiref
ms.openlocfilehash: 328c10c1895f65b43dc365b1be6b4ec5ef01e720
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76777353"
---
# <a name="icordebugmanagedcallbackexception-method"></a><span data-ttu-id="bc4ad-102">Metodo ICorDebugManagedCallback::Exception</span><span class="sxs-lookup"><span data-stu-id="bc4ad-102">ICorDebugManagedCallback::Exception Method</span></span>
<span data-ttu-id="bc4ad-103">Notifica al debugger che è stata generata un'eccezione dal codice gestito.</span><span class="sxs-lookup"><span data-stu-id="bc4ad-103">Notifies the debugger that an exception has been thrown from managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc4ad-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bc4ad-104">Syntax</span></span>  
  
```cpp  
HRESULT Exception (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *pThread,  
    [in] BOOL                unhandled  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bc4ad-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="bc4ad-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="bc4ad-106">in Puntatore a un oggetto ICorDebugAppDomain che rappresenta il dominio applicazione in cui è stata generata l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="bc4ad-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain in which the exception was thrown.</span></span>  
  
 `pThread`  
 <span data-ttu-id="bc4ad-107">in Puntatore a un oggetto ICorDebugThread che rappresenta il thread in cui è stata generata l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="bc4ad-107">[in] A pointer to an ICorDebugThread object that represents the thread in which the exception was thrown.</span></span>  
  
 `unhandled`  
 <span data-ttu-id="bc4ad-108">in Se questo valore è `false`, l'eccezione non è ancora stata elaborata dall'applicazione. in caso contrario, l'eccezione non viene gestita e terminerà il processo.</span><span class="sxs-lookup"><span data-stu-id="bc4ad-108">[in] If this value is `false`, the exception has not yet been processed by the application; otherwise, the exception is unhandled and will terminate the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bc4ad-109">Note</span><span class="sxs-lookup"><span data-stu-id="bc4ad-109">Remarks</span></span>  
 <span data-ttu-id="bc4ad-110">L'eccezione specifica può essere recuperata dall'oggetto thread.</span><span class="sxs-lookup"><span data-stu-id="bc4ad-110">The specific exception can be retrieved from the thread object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bc4ad-111">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="bc4ad-111">Requirements</span></span>  
 <span data-ttu-id="bc4ad-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bc4ad-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bc4ad-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bc4ad-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bc4ad-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bc4ad-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bc4ad-115">**Versioni .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bc4ad-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc4ad-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bc4ad-116">See also</span></span>

- [<span data-ttu-id="bc4ad-117">Interfaccia ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="bc4ad-117">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
