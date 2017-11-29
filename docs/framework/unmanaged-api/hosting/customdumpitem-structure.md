---
title: Struttura CustomDumpItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CustomDumpItem
api_location: mscoree.dll
api_type: COM
f1_keywords: CustomDumpItem
helpviewer_keywords: CustomDumpItem structure [.NET Framework hosting]
ms.assetid: fd9085ff-7beb-4c38-97f0-037cd8ba4f65
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 547204385b20d5b7e64bda9ea0a9e790f2ba3471
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="customdumpitem-structure"></a><span data-ttu-id="aac1d-102">Struttura CustomDumpItem</span><span class="sxs-lookup"><span data-stu-id="aac1d-102">CustomDumpItem Structure</span></span>
<span data-ttu-id="aac1d-103">Descrive un elemento da aggiungere a un'immagine personalizzata in segnalazione errori.</span><span class="sxs-lookup"><span data-stu-id="aac1d-103">Describes an item to be added to a custom dump in error reporting.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aac1d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="aac1d-104">Syntax</span></span>  
  
```  
struct {  
    ECustomDumpItemKind itemKind;   
    union {  
        UINT_PTR pReserved;  
    }  
} CustomDumpItem;  
```  
  
## <a name="members"></a><span data-ttu-id="aac1d-105">Membri</span><span class="sxs-lookup"><span data-stu-id="aac1d-105">Members</span></span>  
  
|<span data-ttu-id="aac1d-106">Membro</span><span class="sxs-lookup"><span data-stu-id="aac1d-106">Member</span></span>|<span data-ttu-id="aac1d-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="aac1d-107">Description</span></span>|  
|------------|-----------------|  
|`itemKind`|<span data-ttu-id="aac1d-108">Un [ECustomDumpItemKind](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md) valore che indica il tipo di elemento da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="aac1d-108">An [ECustomDumpItemKind](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md) value that indicates the kind of item to be added.</span></span>|  
|`pReserved`|<span data-ttu-id="aac1d-109">Non è attualmente utilizzato.</span><span class="sxs-lookup"><span data-stu-id="aac1d-109">Not currently used.</span></span> <span data-ttu-id="aac1d-110">Gli elementi aggiunti all'unione devono essere più grandi di dimensioni del puntatore.</span><span class="sxs-lookup"><span data-stu-id="aac1d-110">Any items added to the union must be no larger than pointer size.</span></span> <span data-ttu-id="aac1d-111">Se un `struct` è obbligatorio, è necessario allocarlo separatamente e su di esso.</span><span class="sxs-lookup"><span data-stu-id="aac1d-111">If a `struct` is required, you must allocate it separately and point to it.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="aac1d-112">Note</span><span class="sxs-lookup"><span data-stu-id="aac1d-112">Remarks</span></span>  
 <span data-ttu-id="aac1d-113">[ICLRErrorReportingManager:: BeginCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) accetta un parametro di tipo `CustomDumpItem`.</span><span class="sxs-lookup"><span data-stu-id="aac1d-113">[ICLRErrorReportingManager::BeginCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) takes a parameter of type `CustomDumpItem`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aac1d-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="aac1d-114">Requirements</span></span>  
 <span data-ttu-id="aac1d-115">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aac1d-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aac1d-116">**Intestazione:** Mscoree</span><span class="sxs-lookup"><span data-stu-id="aac1d-116">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="aac1d-117">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="aac1d-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="aac1d-118">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aac1d-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aac1d-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aac1d-119">See Also</span></span>  
 [<span data-ttu-id="aac1d-120">Strutture di hosting</span><span class="sxs-lookup"><span data-stu-id="aac1d-120">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
