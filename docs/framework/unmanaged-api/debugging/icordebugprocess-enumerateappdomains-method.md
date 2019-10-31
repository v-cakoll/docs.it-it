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
ms.openlocfilehash: e09e25503ad00ab3542f0c4f50221b6014b25561
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128891"
---
# <a name="icordebugprocessenumerateappdomains-method"></a><span data-ttu-id="a204b-102">Metodo ICorDebugProcess::EnumerateAppDomains</span><span class="sxs-lookup"><span data-stu-id="a204b-102">ICorDebugProcess::EnumerateAppDomains Method</span></span>
<span data-ttu-id="a204b-103">Enumera tutti i domini applicazione in questo processo.</span><span class="sxs-lookup"><span data-stu-id="a204b-103">Enumerates all the application domains in this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a204b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a204b-104">Syntax</span></span>  
  
``` cpp 
HRESULT EnumerateAppDomains(  
    [out] ICorDebugAppDomainEnum **ppAppDomains);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a204b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a204b-105">Parameters</span></span>  
 `ppAppDomains`  
 <span data-ttu-id="a204b-106">out Puntatore all'indirizzo di un [ICorDebugAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomainenum-interface.md) che rappresenta un enumeratore per i domini applicazione in questo processo.</span><span class="sxs-lookup"><span data-stu-id="a204b-106">[out] A pointer to the address of an [ICorDebugAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomainenum-interface.md) that is an enumerator for the application domains in this process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a204b-107">Note</span><span class="sxs-lookup"><span data-stu-id="a204b-107">Remarks</span></span>  
 <span data-ttu-id="a204b-108">Questo metodo può essere utilizzato prima del callback [ICorDebugManagedCallback:: CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) .</span><span class="sxs-lookup"><span data-stu-id="a204b-108">This method can be used before the [ICorDebugManagedCallback::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a204b-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a204b-109">Requirements</span></span>  
 <span data-ttu-id="a204b-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a204b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a204b-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a204b-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a204b-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a204b-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a204b-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a204b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
