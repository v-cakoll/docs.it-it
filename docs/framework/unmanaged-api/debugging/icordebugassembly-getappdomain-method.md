---
title: Metodo ICorDebugAssembly::GetAppDomain
ms.date: 03/30/2017
api_name:
- ICorDebugAssembly.GetAppDomain
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAssembly::GetAppDomain
helpviewer_keywords:
- ICorDebugAssembly::GetAppDomain method [.NET Framework debugging]
- GetAppDomain method, ICorDebugAssembly interface [.NET Framework debugging]
ms.assetid: 14e18510-23ac-4cba-9f96-c86147a2df9d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a9ba09b80d7118b0ccd9b1647011a7fc7cd74e22
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57485109"
---
# <a name="icordebugassemblygetappdomain-method"></a><span data-ttu-id="adf61-102">Metodo ICorDebugAssembly::GetAppDomain</span><span class="sxs-lookup"><span data-stu-id="adf61-102">ICorDebugAssembly::GetAppDomain Method</span></span>
<span data-ttu-id="adf61-103">Ottiene un puntatore a interfaccia per il dominio dell'applicazione che contiene questo `ICorDebugAssembly` istanza.</span><span class="sxs-lookup"><span data-stu-id="adf61-103">Gets an interface pointer to the application domain that contains this `ICorDebugAssembly` instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="adf61-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="adf61-104">Syntax</span></span>  
  
```  
HRESULT GetAppDomain (  
    [out] ICorDebugAppDomain  **ppAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="adf61-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="adf61-105">Parameters</span></span>  
 `ppAppDomain`  
 <span data-ttu-id="adf61-106">[out] Un puntatore all'indirizzo di un'interfaccia ICorDebugAppDomain che rappresenta il dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="adf61-106">[out] A pointer to the address of an ICorDebugAppDomain interface that represents the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="adf61-107">Note</span><span class="sxs-lookup"><span data-stu-id="adf61-107">Remarks</span></span>  
 <span data-ttu-id="adf61-108">Se l'assembly è l'assembly di sistema, `GetAppDomain` restituisce null.</span><span class="sxs-lookup"><span data-stu-id="adf61-108">If this assembly is the system assembly, `GetAppDomain` returns null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="adf61-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="adf61-109">Requirements</span></span>  
 <span data-ttu-id="adf61-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="adf61-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="adf61-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="adf61-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="adf61-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="adf61-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="adf61-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="adf61-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
