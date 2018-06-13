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
ms.openlocfilehash: 9e888b2359336c68ea6fdf52f798145fda12002e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33440869"
---
# <a name="stackoverflowtype-enumeration"></a><span data-ttu-id="8c7b2-102">Enumerazione StackOverflowType</span><span class="sxs-lookup"><span data-stu-id="8c7b2-102">StackOverflowType Enumeration</span></span>
<span data-ttu-id="8c7b2-103">Contiene valori che indicano la causa sottostante di un evento di overflow dello stack.</span><span class="sxs-lookup"><span data-stu-id="8c7b2-103">Contains values that indicate the underlying cause of a stack overflow event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c7b2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8c7b2-104">Syntax</span></span>  
  
```  
typedef enum {  
    SO_Managed,  
    SO_ClrEngine,  
    SO_Other  
} StackOverflowType;  
```  
  
## <a name="members"></a><span data-ttu-id="8c7b2-105">Membri</span><span class="sxs-lookup"><span data-stu-id="8c7b2-105">Members</span></span>  
  
|<span data-ttu-id="8c7b2-106">Membro</span><span class="sxs-lookup"><span data-stu-id="8c7b2-106">Member</span></span>|<span data-ttu-id="8c7b2-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8c7b2-107">Description</span></span>|  
|------------|-----------------|  
|`SO_ClrEngine`|<span data-ttu-id="8c7b2-108">L'overflow dello stack è stato causato dal motore di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="8c7b2-108">The stack overflow was caused by the execution engine.</span></span>|  
|`SO_Managed`|<span data-ttu-id="8c7b2-109">L'overflow dello stack è stato causato da codice gestito.</span><span class="sxs-lookup"><span data-stu-id="8c7b2-109">The stack overflow was caused by managed code.</span></span>|  
|`SO_Other`|<span data-ttu-id="8c7b2-110">L'overflow dello stack è stato causato da codice non gestito.</span><span class="sxs-lookup"><span data-stu-id="8c7b2-110">The stack overflow was caused by unmanaged code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8c7b2-111">Note</span><span class="sxs-lookup"><span data-stu-id="8c7b2-111">Remarks</span></span>  
 <span data-ttu-id="8c7b2-112">Queste informazioni vengono passate all'host tramite una chiamata al [IActionOnCLREvent:: OnEvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="8c7b2-112">This information is passed to the host through a call to the [IActionOnCLREvent::OnEvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8c7b2-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8c7b2-113">Requirements</span></span>  
 <span data-ttu-id="8c7b2-114">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8c7b2-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8c7b2-115">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="8c7b2-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8c7b2-116">**Libreria:** Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="8c7b2-116">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8c7b2-117">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8c7b2-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c7b2-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8c7b2-118">See Also</span></span>  
 [<span data-ttu-id="8c7b2-119">Enumerazioni di hosting</span><span class="sxs-lookup"><span data-stu-id="8c7b2-119">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
