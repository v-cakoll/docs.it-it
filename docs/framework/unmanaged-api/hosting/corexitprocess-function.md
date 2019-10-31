---
title: Funzione CorExitProcess
ms.date: 03/30/2017
api_name:
- CorExitProcess
api_location:
- mscoree.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
- mscorsvr.dll
api_type:
- DLLExport
f1_keywords:
- CorExitProcess
helpviewer_keywords:
- CorExitProcess function [.NET Framework hosting]
ms.assetid: a5cab4c6-990e-47f3-8798-cf422b791015
topic_type:
- apiref
ms.openlocfilehash: fe61503cdf46b6b2cf568deb78b96f8fa885c203
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136926"
---
# <a name="corexitprocess-function"></a><span data-ttu-id="5812a-102">Funzione CorExitProcess</span><span class="sxs-lookup"><span data-stu-id="5812a-102">CorExitProcess Function</span></span>
<span data-ttu-id="5812a-103">Arresta il processo non gestito corrente.</span><span class="sxs-lookup"><span data-stu-id="5812a-103">Shuts down the current unmanaged process.</span></span>  
  
 <span data-ttu-id="5812a-104">Questa funzione è stata deprecata nel .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="5812a-104">This function has been deprecated in the .NET Framework 4.</span></span> <span data-ttu-id="5812a-105">Usare invece il metodo [ICLRMetaHost:: ExitProcess](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-exitprocess-method.md) .</span><span class="sxs-lookup"><span data-stu-id="5812a-105">Use the [ICLRMetaHost::ExitProcess](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-exitprocess-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5812a-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5812a-106">Syntax</span></span>  
  
```cpp  
void STDMETHODCALLTYPE CorExitProcess (   
  int  exitCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5812a-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="5812a-107">Parameters</span></span>  
 `exitCode`  
 <span data-ttu-id="5812a-108">Integer che specifica il codice di uscita del processo.</span><span class="sxs-lookup"><span data-stu-id="5812a-108">An integer that specifies the process exit code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5812a-109">Note</span><span class="sxs-lookup"><span data-stu-id="5812a-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5812a-110">A partire da .NET Framework 4, `CorExitProcess` esce da ogni runtime avviato nel processo, non solo dal runtime a cui sono state associate le API legacy.</span><span class="sxs-lookup"><span data-stu-id="5812a-110">Beginning with the .NET Framework 4, `CorExitProcess` exits every started runtime in the process, not just the runtime to which the legacy APIs have been bound.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5812a-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5812a-111">Requirements</span></span>  
 <span data-ttu-id="5812a-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5812a-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5812a-113">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="5812a-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5812a-114">**Libreria:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="5812a-114">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5812a-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5812a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5812a-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5812a-116">See also</span></span>

- [<span data-ttu-id="5812a-117">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="5812a-117">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
