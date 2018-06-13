---
title: Struttura CustomDumpItem
ms.date: 03/30/2017
api_name:
- CustomDumpItem
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CustomDumpItem
helpviewer_keywords:
- CustomDumpItem structure [.NET Framework hosting]
ms.assetid: fd9085ff-7beb-4c38-97f0-037cd8ba4f65
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f742d219d603488bbade091f7a8192785d3e84f6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33433096"
---
# <a name="customdumpitem-structure"></a><span data-ttu-id="785aa-102">Struttura CustomDumpItem</span><span class="sxs-lookup"><span data-stu-id="785aa-102">CustomDumpItem Structure</span></span>
<span data-ttu-id="785aa-103">Descrive un elemento da aggiungere a un'immagine personalizzata in segnalazione errori.</span><span class="sxs-lookup"><span data-stu-id="785aa-103">Describes an item to be added to a custom dump in error reporting.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="785aa-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="785aa-104">Syntax</span></span>  
  
```  
struct {  
    ECustomDumpItemKind itemKind;   
    union {  
        UINT_PTR pReserved;  
    }  
} CustomDumpItem;  
```  
  
## <a name="members"></a><span data-ttu-id="785aa-105">Membri</span><span class="sxs-lookup"><span data-stu-id="785aa-105">Members</span></span>  
  
|<span data-ttu-id="785aa-106">Membro</span><span class="sxs-lookup"><span data-stu-id="785aa-106">Member</span></span>|<span data-ttu-id="785aa-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="785aa-107">Description</span></span>|  
|------------|-----------------|  
|`itemKind`|<span data-ttu-id="785aa-108">Un [ECustomDumpItemKind](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md) valore che indica il tipo di elemento da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="785aa-108">An [ECustomDumpItemKind](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md) value that indicates the kind of item to be added.</span></span>|  
|`pReserved`|<span data-ttu-id="785aa-109">Non è attualmente utilizzato.</span><span class="sxs-lookup"><span data-stu-id="785aa-109">Not currently used.</span></span> <span data-ttu-id="785aa-110">Gli elementi aggiunti all'unione devono essere più grandi di dimensioni del puntatore.</span><span class="sxs-lookup"><span data-stu-id="785aa-110">Any items added to the union must be no larger than pointer size.</span></span> <span data-ttu-id="785aa-111">Se un `struct` è obbligatorio, è necessario allocarlo separatamente e su di esso.</span><span class="sxs-lookup"><span data-stu-id="785aa-111">If a `struct` is required, you must allocate it separately and point to it.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="785aa-112">Note</span><span class="sxs-lookup"><span data-stu-id="785aa-112">Remarks</span></span>  
 <span data-ttu-id="785aa-113">[ICLRErrorReportingManager:: BeginCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) accetta un parametro di tipo `CustomDumpItem`.</span><span class="sxs-lookup"><span data-stu-id="785aa-113">[ICLRErrorReportingManager::BeginCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) takes a parameter of type `CustomDumpItem`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="785aa-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="785aa-114">Requirements</span></span>  
 <span data-ttu-id="785aa-115">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="785aa-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="785aa-116">**Intestazione:** Mscoree</span><span class="sxs-lookup"><span data-stu-id="785aa-116">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="785aa-117">**Libreria:** inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="785aa-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="785aa-118">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="785aa-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="785aa-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="785aa-119">See Also</span></span>  
 [<span data-ttu-id="785aa-120">Strutture di hosting</span><span class="sxs-lookup"><span data-stu-id="785aa-120">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
