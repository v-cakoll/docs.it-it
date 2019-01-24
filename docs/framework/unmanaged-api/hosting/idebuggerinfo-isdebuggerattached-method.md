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
ms.openlocfilehash: 7d471ac13061cfb3a0320801445fb5c931718691
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54562924"
---
# <a name="idebuggerinfoisdebuggerattached-method"></a><span data-ttu-id="384ac-102">Metodo IDebuggerInfo::IsDebuggerAttached</span><span class="sxs-lookup"><span data-stu-id="384ac-102">IDebuggerInfo::IsDebuggerAttached Method</span></span>
<span data-ttu-id="384ac-103">Ottiene un valore che indica se un debugger gestito viene collegato al processo.</span><span class="sxs-lookup"><span data-stu-id="384ac-103">Gets a value that indicates whether a managed debugger is attached to this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="384ac-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="384ac-104">Syntax</span></span>  
  
```  
HRESULT IsDebuggerAttached (  
    [out] BOOL *pbAttached  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="384ac-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="384ac-105">Parameters</span></span>  
 `pbAttached`  
 <span data-ttu-id="384ac-106">[out] Un puntatore a un valore che rappresenta `true` se un debugger gestito viene collegato al processo; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="384ac-106">[out] A pointer to a value that is `true` if a managed debugger is attached to the process; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="384ac-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="384ac-107">Requirements</span></span>  
 <span data-ttu-id="384ac-108">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="384ac-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="384ac-109">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="384ac-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="384ac-110">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="384ac-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="384ac-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="384ac-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="384ac-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="384ac-112">See also</span></span>
- [<span data-ttu-id="384ac-113">Interfaccia IDebuggerInfo</span><span class="sxs-lookup"><span data-stu-id="384ac-113">IDebuggerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerinfo-interface.md)
