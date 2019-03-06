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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a93e73fa8345b48e604d6f63d16170d850ead451
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57484576"
---
# <a name="corexitprocess-function"></a><span data-ttu-id="2f0e8-102">Funzione CorExitProcess</span><span class="sxs-lookup"><span data-stu-id="2f0e8-102">CorExitProcess Function</span></span>
<span data-ttu-id="2f0e8-103">Arresta il processo non gestito corrente.</span><span class="sxs-lookup"><span data-stu-id="2f0e8-103">Shuts down the current unmanaged process.</span></span>  
  
 <span data-ttu-id="2f0e8-104">Questa funzione è stata deprecata nel [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2f0e8-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span> <span data-ttu-id="2f0e8-105">Usare la [ICLRMetaHost](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-exitprocess-method.md) metodo invece.</span><span class="sxs-lookup"><span data-stu-id="2f0e8-105">Use the [ICLRMetaHost::ExitProcess](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-exitprocess-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f0e8-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2f0e8-106">Syntax</span></span>  
  
```  
void STDMETHODCALLTYPE CorExitProcess (   
  int  exitCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2f0e8-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="2f0e8-107">Parameters</span></span>  
 `exitCode`  
 <span data-ttu-id="2f0e8-108">Valore intero che specifica il codice di uscita del processo.</span><span class="sxs-lookup"><span data-stu-id="2f0e8-108">An integer that specifies the process exit code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2f0e8-109">Note</span><span class="sxs-lookup"><span data-stu-id="2f0e8-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2f0e8-110">Inizia con la [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)], `CorExitProcess` chiude ogni runtime avviato il processo, non solo il runtime a cui sono state associate le API legacy.</span><span class="sxs-lookup"><span data-stu-id="2f0e8-110">Beginning with the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)], `CorExitProcess` exits every started runtime in the process, not just the runtime to which the legacy APIs have been bound.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2f0e8-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2f0e8-111">Requirements</span></span>  
 <span data-ttu-id="2f0e8-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2f0e8-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2f0e8-113">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2f0e8-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2f0e8-114">**Libreria:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2f0e8-114">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2f0e8-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2f0e8-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f0e8-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2f0e8-116">See also</span></span>
- [<span data-ttu-id="2f0e8-117">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="2f0e8-117">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
