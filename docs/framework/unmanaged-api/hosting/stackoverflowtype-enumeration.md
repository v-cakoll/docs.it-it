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
ms.openlocfilehash: f09c6bb79d7bd28f4d8b74237b6f343a07b79062
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141478"
---
# <a name="stackoverflowtype-enumeration"></a><span data-ttu-id="fa974-102">Enumerazione StackOverflowType</span><span class="sxs-lookup"><span data-stu-id="fa974-102">StackOverflowType Enumeration</span></span>
<span data-ttu-id="fa974-103">Contiene valori che indicano la cause sottostante di un evento di overflow dello stack.</span><span class="sxs-lookup"><span data-stu-id="fa974-103">Contains values that indicate the underlying cause of a stack overflow event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa974-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fa974-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    SO_Managed,  
    SO_ClrEngine,  
    SO_Other  
} StackOverflowType;  
```  
  
## <a name="members"></a><span data-ttu-id="fa974-105">Members</span><span class="sxs-lookup"><span data-stu-id="fa974-105">Members</span></span>  
  
|<span data-ttu-id="fa974-106">Member</span><span class="sxs-lookup"><span data-stu-id="fa974-106">Member</span></span>|<span data-ttu-id="fa974-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fa974-107">Description</span></span>|  
|------------|-----------------|  
|`SO_ClrEngine`|<span data-ttu-id="fa974-108">L'overflow dello stack è stato causato dal motore di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="fa974-108">The stack overflow was caused by the execution engine.</span></span>|  
|`SO_Managed`|<span data-ttu-id="fa974-109">L'overflow dello stack è stato causato dal codice gestito.</span><span class="sxs-lookup"><span data-stu-id="fa974-109">The stack overflow was caused by managed code.</span></span>|  
|`SO_Other`|<span data-ttu-id="fa974-110">L'overflow dello stack è stato causato da codice non gestito.</span><span class="sxs-lookup"><span data-stu-id="fa974-110">The stack overflow was caused by unmanaged code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fa974-111">Note</span><span class="sxs-lookup"><span data-stu-id="fa974-111">Remarks</span></span>  
 <span data-ttu-id="fa974-112">Queste informazioni vengono passate all'host tramite una chiamata al metodo [IActionOnCLREvent:: OnEvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md) .</span><span class="sxs-lookup"><span data-stu-id="fa974-112">This information is passed to the host through a call to the [IActionOnCLREvent::OnEvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa974-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fa974-113">Requirements</span></span>  
 <span data-ttu-id="fa974-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fa974-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fa974-115">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="fa974-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fa974-116">**Libreria:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="fa974-116">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fa974-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fa974-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa974-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fa974-118">See also</span></span>

- [<span data-ttu-id="fa974-119">Enumerazioni di hosting</span><span class="sxs-lookup"><span data-stu-id="fa974-119">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
