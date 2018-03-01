---
title: Metodo IDebuggerInfo::IsDebuggerAttached
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IDebuggerInfo.IsDebuggerAttached
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IsDebuggerAttached
helpviewer_keywords:
- IDebuggerInfo::IsDebuggerAttached method [.NET Framework hosting]
- IsDebuggerAttached method, IDebuggerInfo interface [.NET Framework hosting]
ms.assetid: 6e21872f-602f-411a-a423-bff5cdf27000
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 7c241af6b71591374d8ce8cc8d1610a8dce91b2e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="idebuggerinfoisdebuggerattached-method"></a><span data-ttu-id="f7b63-102">Metodo IDebuggerInfo::IsDebuggerAttached</span><span class="sxs-lookup"><span data-stu-id="f7b63-102">IDebuggerInfo::IsDebuggerAttached Method</span></span>
<span data-ttu-id="f7b63-103">Ottiene un valore che indica se un debugger gestito è collegato a questo processo.</span><span class="sxs-lookup"><span data-stu-id="f7b63-103">Gets a value that indicates whether a managed debugger is attached to this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7b63-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f7b63-104">Syntax</span></span>  
  
```  
HRESULT IsDebuggerAttached (  
    [out] BOOL *pbAttached  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f7b63-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f7b63-105">Parameters</span></span>  
 `pbAttached`  
 <span data-ttu-id="f7b63-106">[out] Un puntatore a un valore che è `true` se un debugger gestito è collegato al processo; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="f7b63-106">[out] A pointer to a value that is `true` if a managed debugger is attached to the process; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f7b63-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f7b63-107">Requirements</span></span>  
 <span data-ttu-id="f7b63-108">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f7b63-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f7b63-109">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="f7b63-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f7b63-110">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f7b63-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f7b63-111">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f7b63-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7b63-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f7b63-112">See Also</span></span>  
 [<span data-ttu-id="f7b63-113">Interfaccia IDebuggerInfo</span><span class="sxs-lookup"><span data-stu-id="f7b63-113">IDebuggerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerinfo-interface.md)
