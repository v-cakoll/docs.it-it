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
ms.openlocfilehash: af42de820b2d835e8ea137a2643a51678e382ff0
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83617282"
---
# <a name="flockclrversioncallback-function-pointer"></a><span data-ttu-id="85225-102">Puntatore alla funzione FLockClrVersionCallback</span><span class="sxs-lookup"><span data-stu-id="85225-102">FLockClrVersionCallback Function Pointer</span></span>
<span data-ttu-id="85225-103">Punta a una funzione chiamata da Common Language Runtime (CLR) per indicare che l'inizializzazione è stata avviata o completata.</span><span class="sxs-lookup"><span data-stu-id="85225-103">Points to a function that the common language runtime (CLR) calls to indicate that initialization has either started or completed.</span></span>  
  
 <span data-ttu-id="85225-104">Questo puntatore a funzione è stato deprecato in .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="85225-104">This function pointer has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85225-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="85225-105">Syntax</span></span>  
  
```cpp  
typedef HRESULT (__stdcall *FLockClrVersionCallback) ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="85225-106">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="85225-106">Remarks</span></span>  
 <span data-ttu-id="85225-107">Questa funzione viene implementata dall'host.</span><span class="sxs-lookup"><span data-stu-id="85225-107">This function is implemented by the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="85225-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="85225-108">Requirements</span></span>  
 <span data-ttu-id="85225-109">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="85225-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="85225-110">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="85225-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="85225-111">**Libreria:** MSCorWks. dll</span><span class="sxs-lookup"><span data-stu-id="85225-111">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="85225-112">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="85225-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85225-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="85225-113">See also</span></span>

- [<span data-ttu-id="85225-114">Funzione LockClrVersion</span><span class="sxs-lookup"><span data-stu-id="85225-114">LockClrVersion Function</span></span>](lockclrversion-function.md)
- [<span data-ttu-id="85225-115">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="85225-115">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
