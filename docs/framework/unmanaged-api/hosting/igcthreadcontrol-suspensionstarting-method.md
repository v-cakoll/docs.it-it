---
title: Metodo IGCThreadControl::SuspensionStarting
ms.date: 03/30/2017
api_name:
- IGCThreadControl.SuspensionStarting
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SuspensionStarting
helpviewer_keywords:
- IGCThreadControl::SuspensionStarting method [.NET Framework hosting]
- SuspensionStarting method, IGCThreadControl interface [.NET Framework hosting]
ms.assetid: 0af312af-98e9-415e-b182-42e80a1aee51
topic_type:
- apiref
ms.openlocfilehash: 1e1d63ab28276f69e5b3a762520db8f8300d05bc
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134767"
---
# <a name="igcthreadcontrolsuspensionstarting-method"></a><span data-ttu-id="10fbc-102">Metodo IGCThreadControl::SuspensionStarting</span><span class="sxs-lookup"><span data-stu-id="10fbc-102">IGCThreadControl::SuspensionStarting Method</span></span>
<span data-ttu-id="10fbc-103">Notifica all'host che il Runtime sta iniziando una sospensione di thread per un Garbage Collection o un'altra sospensione.</span><span class="sxs-lookup"><span data-stu-id="10fbc-103">Notifies the host that the runtime is beginning a thread suspension for a garbage collection or other suspension.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10fbc-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="10fbc-104">Syntax</span></span>  
  
```cpp  
HRESULT SuspensionStarting ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="10fbc-105">Note</span><span class="sxs-lookup"><span data-stu-id="10fbc-105">Remarks</span></span>  
 <span data-ttu-id="10fbc-106">Non ripianificare alcun thread durante il callback `SuspensionStarting`.</span><span class="sxs-lookup"><span data-stu-id="10fbc-106">Do not reschedule any threads during the `SuspensionStarting` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="10fbc-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="10fbc-107">Requirements</span></span>  
 <span data-ttu-id="10fbc-108">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="10fbc-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="10fbc-109">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="10fbc-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="10fbc-110">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="10fbc-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="10fbc-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="10fbc-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10fbc-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="10fbc-112">See also</span></span>

- [<span data-ttu-id="10fbc-113">Interfaccia IGCThreadControl</span><span class="sxs-lookup"><span data-stu-id="10fbc-113">IGCThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md)
