---
title: Metodo ICorDebugAppDomain::GetProcess
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.GetProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::GetProcess
helpviewer_keywords:
- GetProcess method, ICorDebugAppDomain interface [.NET Framework debugging]
- ICorDebugAppDomain::GetProcess method [.NET Framework debugging]
ms.assetid: 9d0b9628-a91c-40d0-b9bc-00b34a396b8f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d172af14aba418d6e97fe77724bf91b0eaf1c56a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33403114"
---
# <a name="icordebugappdomaingetprocess-method"></a><span data-ttu-id="35b4f-102">Metodo ICorDebugAppDomain::GetProcess</span><span class="sxs-lookup"><span data-stu-id="35b4f-102">ICorDebugAppDomain::GetProcess Method</span></span>
<span data-ttu-id="35b4f-103">Ottiene il processo che contiene il dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="35b4f-103">Gets the process containing the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35b4f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="35b4f-104">Syntax</span></span>  
  
```  
HRESULT GetProcess (  
    [out] ICorDebugProcess   **ppProcess  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="35b4f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="35b4f-105">Parameters</span></span>  
 `ppProcess`  
 <span data-ttu-id="35b4f-106">[out] Un puntatore all'indirizzo di un oggetto ICorDebugProcess che rappresenta il processo.</span><span class="sxs-lookup"><span data-stu-id="35b4f-106">[out] A pointer to the address of an ICorDebugProcess object that represents the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="35b4f-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="35b4f-107">Requirements</span></span>  
 <span data-ttu-id="35b4f-108">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="35b4f-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="35b4f-109">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="35b4f-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="35b4f-110">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="35b4f-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="35b4f-111">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="35b4f-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
