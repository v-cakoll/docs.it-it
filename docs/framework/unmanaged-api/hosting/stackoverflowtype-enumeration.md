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
ms.openlocfilehash: 8541ea7b614ff4a6ca666f0e2549a7f50e190192
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59135876"
---
# <a name="stackoverflowtype-enumeration"></a><span data-ttu-id="d3936-102">Enumerazione StackOverflowType</span><span class="sxs-lookup"><span data-stu-id="d3936-102">StackOverflowType Enumeration</span></span>
<span data-ttu-id="d3936-103">Contiene valori che indicano la causa principale di un evento di stack overflow.</span><span class="sxs-lookup"><span data-stu-id="d3936-103">Contains values that indicate the underlying cause of a stack overflow event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3936-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d3936-104">Syntax</span></span>  
  
```  
typedef enum {  
    SO_Managed,  
    SO_ClrEngine,  
    SO_Other  
} StackOverflowType;  
```  
  
## <a name="members"></a><span data-ttu-id="d3936-105">Membri</span><span class="sxs-lookup"><span data-stu-id="d3936-105">Members</span></span>  
  
|<span data-ttu-id="d3936-106">Member</span><span class="sxs-lookup"><span data-stu-id="d3936-106">Member</span></span>|<span data-ttu-id="d3936-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d3936-107">Description</span></span>|  
|------------|-----------------|  
|`SO_ClrEngine`|<span data-ttu-id="d3936-108">L'overflow dello stack è stato causato dal motore di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="d3936-108">The stack overflow was caused by the execution engine.</span></span>|  
|`SO_Managed`|<span data-ttu-id="d3936-109">L'overflow dello stack è stato causato da codice gestito.</span><span class="sxs-lookup"><span data-stu-id="d3936-109">The stack overflow was caused by managed code.</span></span>|  
|`SO_Other`|<span data-ttu-id="d3936-110">L'overflow dello stack è stato causato da codice non gestito.</span><span class="sxs-lookup"><span data-stu-id="d3936-110">The stack overflow was caused by unmanaged code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d3936-111">Note</span><span class="sxs-lookup"><span data-stu-id="d3936-111">Remarks</span></span>  
 <span data-ttu-id="d3936-112">Queste informazioni vengono passate all'host tramite una chiamata per il [IActionOnCLREvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="d3936-112">This information is passed to the host through a call to the [IActionOnCLREvent::OnEvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d3936-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d3936-113">Requirements</span></span>  
 <span data-ttu-id="d3936-114">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d3936-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d3936-115">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d3936-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d3936-116">**Libreria:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d3936-116">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d3936-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d3936-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3936-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d3936-118">See also</span></span>

- [<span data-ttu-id="d3936-119">Enumerazioni di hosting</span><span class="sxs-lookup"><span data-stu-id="d3936-119">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
