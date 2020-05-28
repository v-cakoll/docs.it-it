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
ms.openlocfilehash: f399d33dbe05cb5768aa45533ef30d28409e18e2
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84006467"
---
# <a name="stackoverflowtype-enumeration"></a><span data-ttu-id="add9c-102">Enumerazione StackOverflowType</span><span class="sxs-lookup"><span data-stu-id="add9c-102">StackOverflowType Enumeration</span></span>
<span data-ttu-id="add9c-103">Contiene valori che indicano la cause sottostante di un evento di overflow dello stack.</span><span class="sxs-lookup"><span data-stu-id="add9c-103">Contains values that indicate the underlying cause of a stack overflow event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="add9c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="add9c-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    SO_Managed,  
    SO_ClrEngine,  
    SO_Other  
} StackOverflowType;  
```  
  
## <a name="members"></a><span data-ttu-id="add9c-105">Membri</span><span class="sxs-lookup"><span data-stu-id="add9c-105">Members</span></span>  
  
|<span data-ttu-id="add9c-106">Membro</span><span class="sxs-lookup"><span data-stu-id="add9c-106">Member</span></span>|<span data-ttu-id="add9c-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="add9c-107">Description</span></span>|  
|------------|-----------------|  
|`SO_ClrEngine`|<span data-ttu-id="add9c-108">L'overflow dello stack è stato causato dal motore di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="add9c-108">The stack overflow was caused by the execution engine.</span></span>|  
|`SO_Managed`|<span data-ttu-id="add9c-109">L'overflow dello stack è stato causato dal codice gestito.</span><span class="sxs-lookup"><span data-stu-id="add9c-109">The stack overflow was caused by managed code.</span></span>|  
|`SO_Other`|<span data-ttu-id="add9c-110">L'overflow dello stack è stato causato da codice non gestito.</span><span class="sxs-lookup"><span data-stu-id="add9c-110">The stack overflow was caused by unmanaged code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="add9c-111">Commenti</span><span class="sxs-lookup"><span data-stu-id="add9c-111">Remarks</span></span>  
 <span data-ttu-id="add9c-112">Queste informazioni vengono passate all'host tramite una chiamata al metodo [IActionOnCLREvent:: OnEvent](iactiononclrevent-onevent-method.md) .</span><span class="sxs-lookup"><span data-stu-id="add9c-112">This information is passed to the host through a call to the [IActionOnCLREvent::OnEvent](iactiononclrevent-onevent-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="add9c-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="add9c-113">Requirements</span></span>  
 <span data-ttu-id="add9c-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="add9c-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="add9c-115">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="add9c-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="add9c-116">**Libreria:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="add9c-116">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="add9c-117">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="add9c-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="add9c-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="add9c-118">See also</span></span>

- [<span data-ttu-id="add9c-119">Enumerazioni di hosting</span><span class="sxs-lookup"><span data-stu-id="add9c-119">Hosting Enumerations</span></span>](hosting-enumerations.md)
