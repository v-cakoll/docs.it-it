---
title: Puntatore alla funzione FLockClrVersionCallback
ms.date: 03/30/2017
api_name:
- FLockClrVersionCallback
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- FLockClrVersionCallback
helpviewer_keywords:
- FLockClrVersionCallback function pointer [.NET Framework hosting]
ms.assetid: 98a4762d-9ad2-45bd-9d03-39064a028b44
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d25afe5ecc8dd23e78fd60fbf8452e28c5aa8be5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54610591"
---
# <a name="flockclrversioncallback-function-pointer"></a><span data-ttu-id="87dcb-102">Puntatore alla funzione FLockClrVersionCallback</span><span class="sxs-lookup"><span data-stu-id="87dcb-102">FLockClrVersionCallback Function Pointer</span></span>
<span data-ttu-id="87dcb-103">Punta a una funzione che il common language runtime (CLR) chiama per indicare che l'inizializzazione è avviato o completato.</span><span class="sxs-lookup"><span data-stu-id="87dcb-103">Points to a function that the common language runtime (CLR) calls to indicate that initialization has either started or completed.</span></span>  
  
 <span data-ttu-id="87dcb-104">Questo puntatore a funzione è stato deprecato nel [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="87dcb-104">This function pointer has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87dcb-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="87dcb-105">Syntax</span></span>  
  
```  
typedef HRESULT (__stdcall *FLockClrVersionCallback) ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="87dcb-106">Note</span><span class="sxs-lookup"><span data-stu-id="87dcb-106">Remarks</span></span>  
 <span data-ttu-id="87dcb-107">Questa funzione viene implementata dall'host.</span><span class="sxs-lookup"><span data-stu-id="87dcb-107">This function is implemented by the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="87dcb-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="87dcb-108">Requirements</span></span>  
 <span data-ttu-id="87dcb-109">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="87dcb-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="87dcb-110">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="87dcb-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="87dcb-111">**Libreria:** MSCorWks.dll</span><span class="sxs-lookup"><span data-stu-id="87dcb-111">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="87dcb-112">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="87dcb-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87dcb-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="87dcb-113">See also</span></span>
- [<span data-ttu-id="87dcb-114">Funzione LockClrVersion</span><span class="sxs-lookup"><span data-stu-id="87dcb-114">LockClrVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md)
- [<span data-ttu-id="87dcb-115">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="87dcb-115">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
