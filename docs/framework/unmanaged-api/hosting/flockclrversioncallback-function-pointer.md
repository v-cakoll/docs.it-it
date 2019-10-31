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
ms.openlocfilehash: f1ad414c30788801e14a33e98a0893e2a0f58d0c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136509"
---
# <a name="flockclrversioncallback-function-pointer"></a><span data-ttu-id="b58a0-102">Puntatore alla funzione FLockClrVersionCallback</span><span class="sxs-lookup"><span data-stu-id="b58a0-102">FLockClrVersionCallback Function Pointer</span></span>
<span data-ttu-id="b58a0-103">Punta a una funzione chiamata da Common Language Runtime (CLR) per indicare che l'inizializzazione è stata avviata o completata.</span><span class="sxs-lookup"><span data-stu-id="b58a0-103">Points to a function that the common language runtime (CLR) calls to indicate that initialization has either started or completed.</span></span>  
  
 <span data-ttu-id="b58a0-104">Questo puntatore a funzione è stato deprecato in .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="b58a0-104">This function pointer has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b58a0-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b58a0-105">Syntax</span></span>  
  
```cpp  
typedef HRESULT (__stdcall *FLockClrVersionCallback) ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="b58a0-106">Note</span><span class="sxs-lookup"><span data-stu-id="b58a0-106">Remarks</span></span>  
 <span data-ttu-id="b58a0-107">Questa funzione viene implementata dall'host.</span><span class="sxs-lookup"><span data-stu-id="b58a0-107">This function is implemented by the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b58a0-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b58a0-108">Requirements</span></span>  
 <span data-ttu-id="b58a0-109">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b58a0-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b58a0-110">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="b58a0-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b58a0-111">**Libreria:** MSCorWks. dll</span><span class="sxs-lookup"><span data-stu-id="b58a0-111">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="b58a0-112">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b58a0-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b58a0-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b58a0-113">See also</span></span>

- [<span data-ttu-id="b58a0-114">Funzione LockClrVersion</span><span class="sxs-lookup"><span data-stu-id="b58a0-114">LockClrVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md)
- [<span data-ttu-id="b58a0-115">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="b58a0-115">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
