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
ms.openlocfilehash: 46e3356df6578f2adf2ceee00b1363b65fd014ea
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67760237"
---
# <a name="flockclrversioncallback-function-pointer"></a><span data-ttu-id="b2270-102">Puntatore alla funzione FLockClrVersionCallback</span><span class="sxs-lookup"><span data-stu-id="b2270-102">FLockClrVersionCallback Function Pointer</span></span>
<span data-ttu-id="b2270-103">Punta a una funzione che il common language runtime (CLR) chiama per indicare che l'inizializzazione è avviato o completato.</span><span class="sxs-lookup"><span data-stu-id="b2270-103">Points to a function that the common language runtime (CLR) calls to indicate that initialization has either started or completed.</span></span>  
  
 <span data-ttu-id="b2270-104">Questo puntatore a funzione è stato deprecato in .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="b2270-104">This function pointer has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2270-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b2270-105">Syntax</span></span>  
  
```cpp  
typedef HRESULT (__stdcall *FLockClrVersionCallback) ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="b2270-106">Note</span><span class="sxs-lookup"><span data-stu-id="b2270-106">Remarks</span></span>  
 <span data-ttu-id="b2270-107">Questa funzione viene implementata dall'host.</span><span class="sxs-lookup"><span data-stu-id="b2270-107">This function is implemented by the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b2270-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b2270-108">Requirements</span></span>  
 <span data-ttu-id="b2270-109">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b2270-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b2270-110">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b2270-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b2270-111">**Libreria:** MSCorWks.dll</span><span class="sxs-lookup"><span data-stu-id="b2270-111">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="b2270-112">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b2270-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2270-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b2270-113">See also</span></span>

- [<span data-ttu-id="b2270-114">Funzione LockClrVersion</span><span class="sxs-lookup"><span data-stu-id="b2270-114">LockClrVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md)
- [<span data-ttu-id="b2270-115">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="b2270-115">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
