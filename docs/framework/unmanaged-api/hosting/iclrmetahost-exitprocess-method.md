---
title: Metodo ICLRMetaHost::ExitProcess
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
- ICLRMetaHost.ExitProcess
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost::ExitProcess
helpviewer_keywords:
- ICLRMetaHost::ExitProcess method [.NET Framework hosting]
- ExitProcess method, ICLRMetaHost interface [.NET Framework hosting]
ms.assetid: b4df98cc-4e4e-407b-b8f4-e0076afef3a4
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2407dd8fb4911bd7e6d46c973ebbab836da4f8fa
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="iclrmetahostexitprocess-method"></a><span data-ttu-id="6f39b-102">Metodo ICLRMetaHost::ExitProcess</span><span class="sxs-lookup"><span data-stu-id="6f39b-102">ICLRMetaHost::ExitProcess Method</span></span>
<span data-ttu-id="6f39b-103">Tenta di arrestare normalmente caricati tutti i Runtime e quindi termina il processo.</span><span class="sxs-lookup"><span data-stu-id="6f39b-103">Attempts to shut down all loaded runtimes gracefully and then terminates the process.</span></span> <span data-ttu-id="6f39b-104">Sostituisce il [CorExitProcess](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md) (funzione).</span><span class="sxs-lookup"><span data-stu-id="6f39b-104">Supersedes the [CorExitProcess](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f39b-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6f39b-105">Syntax</span></span>  
  
```  
HRESULT ExitProcess (  
    [in] INT32 iExitCode);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6f39b-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="6f39b-106">Parameters</span></span>  
 `iExitCode`  
 <span data-ttu-id="6f39b-107">[in] Il codice di uscita per il processo.</span><span class="sxs-lookup"><span data-stu-id="6f39b-107">[in] The exit code for the process.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6f39b-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="6f39b-108">Return Value</span></span>  
 <span data-ttu-id="6f39b-109">Questo metodo non restituisce mai, pertanto il relativo valore restituito è indefinito.</span><span class="sxs-lookup"><span data-stu-id="6f39b-109">This method never returns, so its return value is undefined.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6f39b-110">Note</span><span class="sxs-lookup"><span data-stu-id="6f39b-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6f39b-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6f39b-111">Requirements</span></span>  
 <span data-ttu-id="6f39b-112">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6f39b-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6f39b-113">**Intestazione:** Metahost. H</span><span class="sxs-lookup"><span data-stu-id="6f39b-113">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="6f39b-114">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6f39b-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6f39b-115">**Versioni di .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6f39b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f39b-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6f39b-116">See Also</span></span>  
 [<span data-ttu-id="6f39b-117">Interfaccia ICLRMetaHost</span><span class="sxs-lookup"><span data-stu-id="6f39b-117">ICLRMetaHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)  
 [<span data-ttu-id="6f39b-118">Hosting</span><span class="sxs-lookup"><span data-stu-id="6f39b-118">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
