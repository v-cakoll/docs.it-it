---
title: Metodo ICorDebugProcess::EnumerateAppDomains
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.EnumerateAppDomains
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::EnumerateAppDomains
helpviewer_keywords:
- ICorDebugProcess::EnumerateAppDomains method [.NET Framework debugging]
- EnumerateAppDomains method [.NET Framework debugging]
ms.assetid: d508981f-e2b2-445b-a649-69951c22702d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d3c0f20cc93b02e048c9d1952188af3d21d37221
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67766127"
---
# <a name="icordebugprocessenumerateappdomains-method"></a><span data-ttu-id="ff24e-102">Metodo ICorDebugProcess::EnumerateAppDomains</span><span class="sxs-lookup"><span data-stu-id="ff24e-102">ICorDebugProcess::EnumerateAppDomains Method</span></span>
<span data-ttu-id="ff24e-103">Enumera tutti i domini applicazione in questo processo.</span><span class="sxs-lookup"><span data-stu-id="ff24e-103">Enumerates all the application domains in this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff24e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ff24e-104">Syntax</span></span>  
  
``` cpp 
HRESULT EnumerateAppDomains(  
    [out] ICorDebugAppDomainEnum **ppAppDomains);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ff24e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ff24e-105">Parameters</span></span>  
 `ppAppDomains`  
 <span data-ttu-id="ff24e-106">[out] Un puntatore all'indirizzo di un [ICorDebugAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomainenum-interface.md) vale a dire un enumeratore per i domini applicazione in questo processo.</span><span class="sxs-lookup"><span data-stu-id="ff24e-106">[out] A pointer to the address of an [ICorDebugAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomainenum-interface.md) that is an enumerator for the application domains in this process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ff24e-107">Note</span><span class="sxs-lookup"><span data-stu-id="ff24e-107">Remarks</span></span>  
 <span data-ttu-id="ff24e-108">Questo metodo può essere usato prima la [ICorDebugManagedCallback::](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) callback.</span><span class="sxs-lookup"><span data-stu-id="ff24e-108">This method can be used before the [ICorDebugManagedCallback::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ff24e-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ff24e-109">Requirements</span></span>  
 <span data-ttu-id="ff24e-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ff24e-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ff24e-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ff24e-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ff24e-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ff24e-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ff24e-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ff24e-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
