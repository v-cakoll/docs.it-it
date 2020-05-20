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
ms.openlocfilehash: a60805e1fd78cb14835957a7afc14fe279cb20fb
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616567"
---
# <a name="corexitprocess-function"></a><span data-ttu-id="9c0c1-102">Funzione CorExitProcess</span><span class="sxs-lookup"><span data-stu-id="9c0c1-102">CorExitProcess Function</span></span>
<span data-ttu-id="9c0c1-103">Arresta il processo non gestito corrente.</span><span class="sxs-lookup"><span data-stu-id="9c0c1-103">Shuts down the current unmanaged process.</span></span>  
  
 <span data-ttu-id="9c0c1-104">Questa funzione è stata deprecata nel .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="9c0c1-104">This function has been deprecated in the .NET Framework 4.</span></span> <span data-ttu-id="9c0c1-105">Usare invece il metodo [ICLRMetaHost:: ExitProcess](iclrmetahost-exitprocess-method.md) .</span><span class="sxs-lookup"><span data-stu-id="9c0c1-105">Use the [ICLRMetaHost::ExitProcess](iclrmetahost-exitprocess-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c0c1-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9c0c1-106">Syntax</span></span>  
  
```cpp  
void STDMETHODCALLTYPE CorExitProcess (
  int  exitCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9c0c1-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="9c0c1-107">Parameters</span></span>  
 `exitCode`  
 <span data-ttu-id="9c0c1-108">Integer che specifica il codice di uscita del processo.</span><span class="sxs-lookup"><span data-stu-id="9c0c1-108">An integer that specifies the process exit code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9c0c1-109">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="9c0c1-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9c0c1-110">A partire da .NET Framework 4, `CorExitProcess` chiude ogni runtime avviato nel processo, non solo il runtime a cui sono state associate le API legacy.</span><span class="sxs-lookup"><span data-stu-id="9c0c1-110">Beginning with the .NET Framework 4, `CorExitProcess` exits every started runtime in the process, not just the runtime to which the legacy APIs have been bound.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9c0c1-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9c0c1-111">Requirements</span></span>  
 <span data-ttu-id="9c0c1-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9c0c1-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9c0c1-113">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="9c0c1-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9c0c1-114">**Libreria:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="9c0c1-114">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9c0c1-115">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9c0c1-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c0c1-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9c0c1-116">See also</span></span>

- [<span data-ttu-id="9c0c1-117">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="9c0c1-117">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
