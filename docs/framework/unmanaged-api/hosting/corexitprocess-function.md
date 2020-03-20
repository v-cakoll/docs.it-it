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
ms.openlocfilehash: 44578595b3cb790570c5359e714bd39c109cf1f8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176461"
---
# <a name="corexitprocess-function"></a><span data-ttu-id="1c3b9-102">Funzione CorExitProcess</span><span class="sxs-lookup"><span data-stu-id="1c3b9-102">CorExitProcess Function</span></span>
<span data-ttu-id="1c3b9-103">Arresta il processo non gestito corrente.</span><span class="sxs-lookup"><span data-stu-id="1c3b9-103">Shuts down the current unmanaged process.</span></span>  
  
 <span data-ttu-id="1c3b9-104">Questa funzione è stata deprecata in .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="1c3b9-104">This function has been deprecated in the .NET Framework 4.</span></span> <span data-ttu-id="1c3b9-105">Utilizzare invece il metodo [ICLRMetaHost::ExitProcess](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-exitprocess-method.md) .</span><span class="sxs-lookup"><span data-stu-id="1c3b9-105">Use the [ICLRMetaHost::ExitProcess](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-exitprocess-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c3b9-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1c3b9-106">Syntax</span></span>  
  
```cpp  
void STDMETHODCALLTYPE CorExitProcess (
  int  exitCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1c3b9-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="1c3b9-107">Parameters</span></span>  
 `exitCode`  
 <span data-ttu-id="1c3b9-108">Un numero intero che specifica il codice di uscita del processo.</span><span class="sxs-lookup"><span data-stu-id="1c3b9-108">An integer that specifies the process exit code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1c3b9-109">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="1c3b9-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1c3b9-110">A partire da .NET `CorExitProcess` Framework 4.NET Framework 4, esce da ogni runtime avviato nel processo, non solo dal runtime a cui sono state associate le API legacy.</span><span class="sxs-lookup"><span data-stu-id="1c3b9-110">Beginning with the .NET Framework 4, `CorExitProcess` exits every started runtime in the process, not just the runtime to which the legacy APIs have been bound.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1c3b9-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1c3b9-111">Requirements</span></span>  
 <span data-ttu-id="1c3b9-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1c3b9-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1c3b9-113">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="1c3b9-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1c3b9-114">**Biblioteca:** Mscoree</span><span class="sxs-lookup"><span data-stu-id="1c3b9-114">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1c3b9-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1c3b9-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c3b9-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1c3b9-116">See also</span></span>

- [<span data-ttu-id="1c3b9-117">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="1c3b9-117">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
