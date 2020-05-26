---
title: Metodo IGCHost::SetVirtualMemLimit
ms.date: 03/30/2017
api_name:
- IGCHost.SetVirtualMemLimit
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SetVirtualMemLimit
helpviewer_keywords:
- IGCHost::SetVirtualMemLimit method [.NET Framework hosting]
- SetVirtualMemLimit method [.NET Framework hosting]
ms.assetid: c7e7c2d0-e58c-4650-b40c-47b2be2cda45
topic_type:
- apiref
ms.openlocfilehash: 93ed63b4abacce1d8943434965aacf67190631b6
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/22/2020
ms.locfileid: "83805197"
---
# <a name="igchostsetvirtualmemlimit-method"></a><span data-ttu-id="16cf9-102">Metodo IGCHost::SetVirtualMemLimit</span><span class="sxs-lookup"><span data-stu-id="16cf9-102">IGCHost::SetVirtualMemLimit Method</span></span>
<span data-ttu-id="16cf9-103">Imposta la dimensione massima della memoria virtuale del runtime.</span><span class="sxs-lookup"><span data-stu-id="16cf9-103">Sets the maximum size of the runtime's virtual memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16cf9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="16cf9-104">Syntax</span></span>  
  
```cpp  
HRESULT SetVirtualMemLimit (  
    [in] SIZE_T sztMaxVirtualMemMB  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="16cf9-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="16cf9-105">Parameters</span></span>  
 `sztMaxVirtualMemMB`  
 <span data-ttu-id="16cf9-106">in Dimensione massima, in megabyte, della memoria virtuale del runtime.</span><span class="sxs-lookup"><span data-stu-id="16cf9-106">[in] The maximum size, in megabytes, of the runtime's virtual memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="16cf9-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="16cf9-107">Remarks</span></span>  
 <span data-ttu-id="16cf9-108">È possibile modificare dinamicamente le dimensioni massime della memoria virtuale del runtime.</span><span class="sxs-lookup"><span data-stu-id="16cf9-108">The maximum size of the runtime's virtual memory can be changed dynamically.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="16cf9-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="16cf9-109">Requirements</span></span>  
 <span data-ttu-id="16cf9-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="16cf9-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="16cf9-111">**Intestazione:** GCHost. idl, GCHost. h</span><span class="sxs-lookup"><span data-stu-id="16cf9-111">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="16cf9-112">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="16cf9-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="16cf9-113">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="16cf9-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16cf9-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="16cf9-114">See also</span></span>

- [<span data-ttu-id="16cf9-115">Interfaccia IGCHost</span><span class="sxs-lookup"><span data-stu-id="16cf9-115">IGCHost Interface</span></span>](igchost-interface.md)
