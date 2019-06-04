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
ms.openlocfilehash: ef308b624525c3a139c892e6118a24d6adb6e14a
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2019
ms.locfileid: "66490457"
---
# <a name="flockclrversioncallback-function-pointer"></a><span data-ttu-id="6c082-102">Puntatore alla funzione FLockClrVersionCallback</span><span class="sxs-lookup"><span data-stu-id="6c082-102">FLockClrVersionCallback Function Pointer</span></span>
<span data-ttu-id="6c082-103">Punta a una funzione che il common language runtime (CLR) chiama per indicare che l'inizializzazione è avviato o completato.</span><span class="sxs-lookup"><span data-stu-id="6c082-103">Points to a function that the common language runtime (CLR) calls to indicate that initialization has either started or completed.</span></span>  
  
 <span data-ttu-id="6c082-104">Questo puntatore a funzione è stato deprecato in .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="6c082-104">This function pointer has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c082-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6c082-105">Syntax</span></span>  
  
```  
typedef HRESULT (__stdcall *FLockClrVersionCallback) ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="6c082-106">Note</span><span class="sxs-lookup"><span data-stu-id="6c082-106">Remarks</span></span>  
 <span data-ttu-id="6c082-107">Questa funzione viene implementata dall'host.</span><span class="sxs-lookup"><span data-stu-id="6c082-107">This function is implemented by the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6c082-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6c082-108">Requirements</span></span>  
 <span data-ttu-id="6c082-109">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6c082-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6c082-110">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="6c082-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6c082-111">**Libreria:** MSCorWks.dll</span><span class="sxs-lookup"><span data-stu-id="6c082-111">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="6c082-112">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6c082-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c082-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6c082-113">See also</span></span>

- [<span data-ttu-id="6c082-114">Funzione LockClrVersion</span><span class="sxs-lookup"><span data-stu-id="6c082-114">LockClrVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md)
- [<span data-ttu-id="6c082-115">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="6c082-115">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
