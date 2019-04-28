---
title: Metodo IDebuggerInfo::IsDebuggerAttached
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0708a3b501a99b5f71be5ba4c6cc4ea2b754d12a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61699890"
---
# <a name="idebuggerinfoisdebuggerattached-method"></a><span data-ttu-id="01790-102">Metodo IDebuggerInfo::IsDebuggerAttached</span><span class="sxs-lookup"><span data-stu-id="01790-102">IDebuggerInfo::IsDebuggerAttached Method</span></span>
<span data-ttu-id="01790-103">Ottiene un valore che indica se un debugger gestito viene collegato al processo.</span><span class="sxs-lookup"><span data-stu-id="01790-103">Gets a value that indicates whether a managed debugger is attached to this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01790-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="01790-104">Syntax</span></span>  
  
```  
HRESULT IsDebuggerAttached (  
    [out] BOOL *pbAttached  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="01790-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="01790-105">Parameters</span></span>  
 `pbAttached`  
 <span data-ttu-id="01790-106">[out] Un puntatore a un valore che rappresenta `true` se un debugger gestito viene collegato al processo; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="01790-106">[out] A pointer to a value that is `true` if a managed debugger is attached to the process; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="01790-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="01790-107">Requirements</span></span>  
 <span data-ttu-id="01790-108">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="01790-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="01790-109">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="01790-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="01790-110">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="01790-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="01790-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="01790-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01790-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="01790-112">See also</span></span>

- [<span data-ttu-id="01790-113">Interfaccia IDebuggerInfo</span><span class="sxs-lookup"><span data-stu-id="01790-113">IDebuggerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerinfo-interface.md)
