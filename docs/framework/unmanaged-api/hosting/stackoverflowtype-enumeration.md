---
title: Enumerazione StackOverflowType
ms.date: 03/30/2017
api_name:
- StackOverflowType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- StackOverflowType
helpviewer_keywords:
- StackOverflowType enumeration [.NET Framework hosting]
ms.assetid: dab648ad-972b-479c-b129-b4c1dcbd932e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 06c9119a2b842a0efcd4af752ba72dbfda03bf13
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54653861"
---
# <a name="stackoverflowtype-enumeration"></a><span data-ttu-id="21052-102">Enumerazione StackOverflowType</span><span class="sxs-lookup"><span data-stu-id="21052-102">StackOverflowType Enumeration</span></span>
<span data-ttu-id="21052-103">Contiene valori che indicano la causa principale di un evento di stack overflow.</span><span class="sxs-lookup"><span data-stu-id="21052-103">Contains values that indicate the underlying cause of a stack overflow event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21052-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="21052-104">Syntax</span></span>  
  
```  
typedef enum {  
    SO_Managed,  
    SO_ClrEngine,  
    SO_Other  
} StackOverflowType;  
```  
  
## <a name="members"></a><span data-ttu-id="21052-105">Membri</span><span class="sxs-lookup"><span data-stu-id="21052-105">Members</span></span>  
  
|<span data-ttu-id="21052-106">Membro</span><span class="sxs-lookup"><span data-stu-id="21052-106">Member</span></span>|<span data-ttu-id="21052-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="21052-107">Description</span></span>|  
|------------|-----------------|  
|`SO_ClrEngine`|<span data-ttu-id="21052-108">L'overflow dello stack è stato causato dal motore di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="21052-108">The stack overflow was caused by the execution engine.</span></span>|  
|`SO_Managed`|<span data-ttu-id="21052-109">L'overflow dello stack è stato causato da codice gestito.</span><span class="sxs-lookup"><span data-stu-id="21052-109">The stack overflow was caused by managed code.</span></span>|  
|`SO_Other`|<span data-ttu-id="21052-110">L'overflow dello stack è stato causato da codice non gestito.</span><span class="sxs-lookup"><span data-stu-id="21052-110">The stack overflow was caused by unmanaged code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="21052-111">Note</span><span class="sxs-lookup"><span data-stu-id="21052-111">Remarks</span></span>  
 <span data-ttu-id="21052-112">Queste informazioni vengono passate all'host tramite una chiamata per il [IActionOnCLREvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="21052-112">This information is passed to the host through a call to the [IActionOnCLREvent::OnEvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="21052-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="21052-113">Requirements</span></span>  
 <span data-ttu-id="21052-114">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="21052-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="21052-115">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="21052-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="21052-116">**Libreria:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="21052-116">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="21052-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="21052-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21052-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="21052-118">See also</span></span>
- [<span data-ttu-id="21052-119">Enumerazioni di hosting</span><span class="sxs-lookup"><span data-stu-id="21052-119">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
