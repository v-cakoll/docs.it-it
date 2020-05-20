---
title: Enumerazione HOST_TYPE
ms.date: 03/30/2017
api_name:
- HOST_TYPE
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- HOST_TYPE
helpviewer_keywords:
- HOST_TYPE enumeration [.NET Framework hosting]
ms.assetid: 51f848be-84c5-4036-9839-c762c576bbf5
topic_type:
- apiref
ms.openlocfilehash: e8dda83df8a320733f45dbcc13599cdf37d26492
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83617152"
---
# <a name="host_type-enumeration"></a><span data-ttu-id="cb742-102">Enumerazione HOST_TYPE</span><span class="sxs-lookup"><span data-stu-id="cb742-102">HOST_TYPE Enumeration</span></span>
<span data-ttu-id="cb742-103">Contiene valori che specificano il tipo di host che avvia un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="cb742-103">Contains values that specify the type of host that is launching an application.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb742-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cb742-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    HOST_TYPE_DEFAULT     = 0x0,  
    HOST_TYPE_APPLAUNCH   = 0x1,  
    HOST_TYPE_CORFLAG     = 0x2  
} HOST_TYPE;  
```  
  
## <a name="members"></a><span data-ttu-id="cb742-105">Membri</span><span class="sxs-lookup"><span data-stu-id="cb742-105">Members</span></span>  
  
|<span data-ttu-id="cb742-106">Membro</span><span class="sxs-lookup"><span data-stu-id="cb742-106">Member</span></span>|<span data-ttu-id="cb742-107">Description</span><span class="sxs-lookup"><span data-stu-id="cb742-107">Description</span></span>|  
|------------|-----------------|  
|`HOST_TYPE_APPLAUNCH`|<span data-ttu-id="cb742-108">Avviare l'applicazione da AppLaunch. exe.</span><span class="sxs-lookup"><span data-stu-id="cb742-108">Launch the application from AppLaunch.exe.</span></span><br /><br /> <span data-ttu-id="cb742-109">Utilizzare questo valore per le applicazioni parzialmente attendibili.</span><span class="sxs-lookup"><span data-stu-id="cb742-109">Use this value for partially-trusted applications.</span></span>|  
|`HOST_TYPE_CORFLAG`|<span data-ttu-id="cb742-110">Avviare direttamente l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="cb742-110">Launch the application directly.</span></span> <span data-ttu-id="cb742-111">Ovvero avviare l'applicazione dal proprio file con estensione exe.</span><span class="sxs-lookup"><span data-stu-id="cb742-111">That is, launch the application from its own .exe file.</span></span><br /><br /> <span data-ttu-id="cb742-112">Utilizzare questo valore per le applicazioni completamente attendibili.</span><span class="sxs-lookup"><span data-stu-id="cb742-112">Use this value for fully-trusted applications.</span></span>|  
|`HOST_TYPE_DEFAULT`|<span data-ttu-id="cb742-113">Uguale a HOST_TYPE_APPLAUNCH.</span><span class="sxs-lookup"><span data-stu-id="cb742-113">Same as HOST_TYPE_APPLAUNCH.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="cb742-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="cb742-114">Requirements</span></span>  
 <span data-ttu-id="cb742-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cb742-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cb742-116">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="cb742-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cb742-117">**Libreria:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="cb742-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cb742-118">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cb742-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb742-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cb742-119">See also</span></span>

- [<span data-ttu-id="cb742-120">Enumerazioni di hosting</span><span class="sxs-lookup"><span data-stu-id="cb742-120">Hosting Enumerations</span></span>](hosting-enumerations.md)
