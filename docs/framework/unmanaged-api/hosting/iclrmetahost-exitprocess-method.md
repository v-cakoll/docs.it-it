---
title: Metodo ICLRMetaHost::ExitProcess
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 64c212d064ad658678926690d1e680afe27c7c99
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61993252"
---
# <a name="iclrmetahostexitprocess-method"></a><span data-ttu-id="ce821-102">Metodo ICLRMetaHost::ExitProcess</span><span class="sxs-lookup"><span data-stu-id="ce821-102">ICLRMetaHost::ExitProcess Method</span></span>
<span data-ttu-id="ce821-103">Tenta di arresto normale runtime caricati tutti e quindi termina il processo.</span><span class="sxs-lookup"><span data-stu-id="ce821-103">Attempts to shut down all loaded runtimes gracefully and then terminates the process.</span></span> <span data-ttu-id="ce821-104">Sostituisce il [CorExitProcess](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md) (funzione).</span><span class="sxs-lookup"><span data-stu-id="ce821-104">Supersedes the [CorExitProcess](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce821-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ce821-105">Syntax</span></span>  
  
```  
HRESULT ExitProcess (  
    [in] INT32 iExitCode);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ce821-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="ce821-106">Parameters</span></span>  
 `iExitCode`  
 <span data-ttu-id="ce821-107">[in] Il codice di uscita del processo.</span><span class="sxs-lookup"><span data-stu-id="ce821-107">[in] The exit code for the process.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ce821-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="ce821-108">Return Value</span></span>  
 <span data-ttu-id="ce821-109">Questo metodo non restituisce mai, pertanto il relativo valore restituito è indefinito.</span><span class="sxs-lookup"><span data-stu-id="ce821-109">This method never returns, so its return value is undefined.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ce821-110">Note</span><span class="sxs-lookup"><span data-stu-id="ce821-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ce821-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ce821-111">Requirements</span></span>  
 <span data-ttu-id="ce821-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ce821-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ce821-113">**Intestazione:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="ce821-113">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="ce821-114">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="ce821-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ce821-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ce821-115">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce821-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ce821-116">See also</span></span>

- [<span data-ttu-id="ce821-117">Interfaccia ICLRMetaHost</span><span class="sxs-lookup"><span data-stu-id="ce821-117">ICLRMetaHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)
- [<span data-ttu-id="ce821-118">Hosting</span><span class="sxs-lookup"><span data-stu-id="ce821-118">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
