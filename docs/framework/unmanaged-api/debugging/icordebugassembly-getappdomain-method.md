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
ms.openlocfilehash: e22d112d1414b13033f73723821e5e4b5764e1c8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33401979"
---
# <a name="icordebugassemblygetappdomain-method"></a><span data-ttu-id="14fd6-102">Metodo ICorDebugAssembly::GetAppDomain</span><span class="sxs-lookup"><span data-stu-id="14fd6-102">ICorDebugAssembly::GetAppDomain Method</span></span>
<span data-ttu-id="14fd6-103">Ottiene un puntatore a interfaccia per il dominio applicazione che contiene questo `ICorDebugAssembly` istanza.</span><span class="sxs-lookup"><span data-stu-id="14fd6-103">Gets an interface pointer to the application domain that contains this `ICorDebugAssembly` instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14fd6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="14fd6-104">Syntax</span></span>  
  
```  
HRESULT GetAppDomain (  
    [out] ICorDebugAppDomain  **ppAppDomain  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="14fd6-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="14fd6-105">Parameters</span></span>  
 `ppAppDomain`  
 <span data-ttu-id="14fd6-106">[out] Un puntatore all'indirizzo di un'interfaccia ICorDebugAppDomain che rappresenta il dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="14fd6-106">[out] A pointer to the address of an ICorDebugAppDomain interface that represents the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="14fd6-107">Note</span><span class="sxs-lookup"><span data-stu-id="14fd6-107">Remarks</span></span>  
 <span data-ttu-id="14fd6-108">Se l'assembly è l'assembly di sistema, `GetAppDomain` restituisce null.</span><span class="sxs-lookup"><span data-stu-id="14fd6-108">If this assembly is the system assembly, `GetAppDomain` returns null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="14fd6-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="14fd6-109">Requirements</span></span>  
 <span data-ttu-id="14fd6-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="14fd6-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="14fd6-111">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="14fd6-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="14fd6-112">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="14fd6-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="14fd6-113">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="14fd6-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
