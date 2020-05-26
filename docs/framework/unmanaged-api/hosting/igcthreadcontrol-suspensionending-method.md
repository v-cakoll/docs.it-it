---
title: Metodo IGCThreadControl::SuspensionEnding
ms.date: 03/30/2017
api_name:
- IGCThreadControl.SuspensionEnding
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SuspensionEnding
helpviewer_keywords:
- IGCThreadControl::SuspensionEnding method [.NET Framework hosting]
- SuspensionEnding method, IGCThreadControl interface [.NET Framework hosting]
ms.assetid: 70814265-c734-4ddc-9502-fe8b28d2b414
topic_type:
- apiref
ms.openlocfilehash: 8300daf0d39745ceda80f6c56da7e3c459a97468
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/22/2020
ms.locfileid: "83805108"
---
# <a name="igcthreadcontrolsuspensionending-method"></a><span data-ttu-id="58f8f-102">Metodo IGCThreadControl::SuspensionEnding</span><span class="sxs-lookup"><span data-stu-id="58f8f-102">IGCThreadControl::SuspensionEnding Method</span></span>
<span data-ttu-id="58f8f-103">Notifica all'host che il Runtime sta riprendendo i thread dopo una Garbage Collection o un'altra sospensione.</span><span class="sxs-lookup"><span data-stu-id="58f8f-103">Notifies the host that the runtime is resuming threads after a garbage collection or other suspension.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58f8f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="58f8f-104">Syntax</span></span>  
  
```cpp  
HRESULT SuspensionEnding (  
    [in] DWORD Generation  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="58f8f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="58f8f-105">Parameters</span></span>  
 `Generation`  
 <span data-ttu-id="58f8f-106">in Generazione in cui è stata eseguita una Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="58f8f-106">[in] The generation on which a garbage collection has been performed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="58f8f-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="58f8f-107">Remarks</span></span>  
 <span data-ttu-id="58f8f-108">Non ripianificare alcun thread durante il `SuspensionEnding` callback.</span><span class="sxs-lookup"><span data-stu-id="58f8f-108">Do not reschedule any threads during the `SuspensionEnding` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="58f8f-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="58f8f-109">Requirements</span></span>  
 <span data-ttu-id="58f8f-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="58f8f-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="58f8f-111">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="58f8f-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="58f8f-112">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="58f8f-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="58f8f-113">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="58f8f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58f8f-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="58f8f-114">See also</span></span>

- [<span data-ttu-id="58f8f-115">Interfaccia IGCThreadControl</span><span class="sxs-lookup"><span data-stu-id="58f8f-115">IGCThreadControl Interface</span></span>](igcthreadcontrol-interface.md)
