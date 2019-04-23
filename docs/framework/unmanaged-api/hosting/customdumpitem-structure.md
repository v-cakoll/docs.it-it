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
ms.openlocfilehash: 9000f35e9a8f7ecc6c40cf0ef9c220fc9f4f9c10
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59185926"
---
# <a name="customdumpitem-structure"></a><span data-ttu-id="30786-102">Struttura CustomDumpItem</span><span class="sxs-lookup"><span data-stu-id="30786-102">CustomDumpItem Structure</span></span>
<span data-ttu-id="30786-103">Viene descritto un elemento da aggiungere a un'immagine personalizzata in segnalazione errori.</span><span class="sxs-lookup"><span data-stu-id="30786-103">Describes an item to be added to a custom dump in error reporting.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30786-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="30786-104">Syntax</span></span>  
  
```  
struct {  
    ECustomDumpItemKind itemKind;   
    union {  
        UINT_PTR pReserved;  
    }  
} CustomDumpItem;  
```  
  
## <a name="members"></a><span data-ttu-id="30786-105">Membri</span><span class="sxs-lookup"><span data-stu-id="30786-105">Members</span></span>  
  
|<span data-ttu-id="30786-106">Member</span><span class="sxs-lookup"><span data-stu-id="30786-106">Member</span></span>|<span data-ttu-id="30786-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="30786-107">Description</span></span>|  
|------------|-----------------|  
|`itemKind`|<span data-ttu-id="30786-108">Un' [ECustomDumpItemKind](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md) valore che indica il tipo di elemento da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="30786-108">An [ECustomDumpItemKind](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md) value that indicates the kind of item to be added.</span></span>|  
|`pReserved`|<span data-ttu-id="30786-109">Non è attualmente utilizzato.</span><span class="sxs-lookup"><span data-stu-id="30786-109">Not currently used.</span></span> <span data-ttu-id="30786-110">Gli elementi aggiunti all'unione devono essere superiori a dimensioni del puntatore.</span><span class="sxs-lookup"><span data-stu-id="30786-110">Any items added to the union must be no larger than pointer size.</span></span> <span data-ttu-id="30786-111">Se un `struct` è obbligatorio, è necessario allocarla separatamente e su di esso.</span><span class="sxs-lookup"><span data-stu-id="30786-111">If a `struct` is required, you must allocate it separately and point to it.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="30786-112">Note</span><span class="sxs-lookup"><span data-stu-id="30786-112">Remarks</span></span>  
 <span data-ttu-id="30786-113">[ICLRErrorReportingManager](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) accetta un parametro di tipo `CustomDumpItem`.</span><span class="sxs-lookup"><span data-stu-id="30786-113">[ICLRErrorReportingManager::BeginCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) takes a parameter of type `CustomDumpItem`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="30786-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="30786-114">Requirements</span></span>  
 <span data-ttu-id="30786-115">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="30786-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="30786-116">**Intestazione:** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="30786-116">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="30786-117">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="30786-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="30786-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="30786-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30786-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="30786-119">See also</span></span>

- [<span data-ttu-id="30786-120">Strutture di hosting</span><span class="sxs-lookup"><span data-stu-id="30786-120">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
