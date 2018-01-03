---
title: Metodo ICorDebugAssembly::GetAppDomain
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugAssembly.GetAppDomain
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugAssembly::GetAppDomain
helpviewer_keywords:
- ICorDebugAssembly::GetAppDomain method [.NET Framework debugging]
- GetAppDomain method, ICorDebugAssembly interface [.NET Framework debugging]
ms.assetid: 14e18510-23ac-4cba-9f96-c86147a2df9d
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f97795568b9811d0dbf7852fd64d5256c29b8f30
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugassemblygetappdomain-method"></a><span data-ttu-id="b8ef2-102">Metodo ICorDebugAssembly::GetAppDomain</span><span class="sxs-lookup"><span data-stu-id="b8ef2-102">ICorDebugAssembly::GetAppDomain Method</span></span>
<span data-ttu-id="b8ef2-103">Ottiene un puntatore a interfaccia per il dominio applicazione che contiene questo `ICorDebugAssembly` istanza.</span><span class="sxs-lookup"><span data-stu-id="b8ef2-103">Gets an interface pointer to the application domain that contains this `ICorDebugAssembly` instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8ef2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b8ef2-104">Syntax</span></span>  
  
```  
HRESULT GetAppDomain (  
    [out] ICorDebugAppDomain  **ppAppDomain  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b8ef2-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b8ef2-105">Parameters</span></span>  
 `ppAppDomain`  
 <span data-ttu-id="b8ef2-106">[out] Un puntatore all'indirizzo di un'interfaccia ICorDebugAppDomain che rappresenta il dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="b8ef2-106">[out] A pointer to the address of an ICorDebugAppDomain interface that represents the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b8ef2-107">Note</span><span class="sxs-lookup"><span data-stu-id="b8ef2-107">Remarks</span></span>  
 <span data-ttu-id="b8ef2-108">Se l'assembly è l'assembly di sistema, `GetAppDomain` restituisce null.</span><span class="sxs-lookup"><span data-stu-id="b8ef2-108">If this assembly is the system assembly, `GetAppDomain` returns null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b8ef2-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b8ef2-109">Requirements</span></span>  
 <span data-ttu-id="b8ef2-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b8ef2-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b8ef2-111">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="b8ef2-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b8ef2-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b8ef2-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b8ef2-113">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b8ef2-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
