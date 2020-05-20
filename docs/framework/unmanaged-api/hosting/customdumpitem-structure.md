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
ms.openlocfilehash: 5c77a332593ba470d2e29b87cba182a770d5db7e
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616437"
---
# <a name="customdumpitem-structure"></a><span data-ttu-id="e3123-102">Struttura CustomDumpItem</span><span class="sxs-lookup"><span data-stu-id="e3123-102">CustomDumpItem Structure</span></span>
<span data-ttu-id="e3123-103">Descrive un elemento da aggiungere a un dump personalizzato nella segnalazione degli errori.</span><span class="sxs-lookup"><span data-stu-id="e3123-103">Describes an item to be added to a custom dump in error reporting.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3123-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e3123-104">Syntax</span></span>  
  
```cpp  
struct {  
    ECustomDumpItemKind itemKind;
    union {  
        UINT_PTR pReserved;  
    }  
} CustomDumpItem;  
```  
  
## <a name="members"></a><span data-ttu-id="e3123-105">Membri</span><span class="sxs-lookup"><span data-stu-id="e3123-105">Members</span></span>  
  
|<span data-ttu-id="e3123-106">Membro</span><span class="sxs-lookup"><span data-stu-id="e3123-106">Member</span></span>|<span data-ttu-id="e3123-107">Description</span><span class="sxs-lookup"><span data-stu-id="e3123-107">Description</span></span>|  
|------------|-----------------|  
|`itemKind`|<span data-ttu-id="e3123-108">Valore [ECustomDumpItemKind](ecustomdumpitemkind-enumeration.md) che indica il tipo di elemento da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="e3123-108">An [ECustomDumpItemKind](ecustomdumpitemkind-enumeration.md) value that indicates the kind of item to be added.</span></span>|  
|`pReserved`|<span data-ttu-id="e3123-109">Attualmente non utilizzato.</span><span class="sxs-lookup"><span data-stu-id="e3123-109">Not currently used.</span></span> <span data-ttu-id="e3123-110">Gli elementi aggiunti all'Unione non devono essere maggiori delle dimensioni del puntatore.</span><span class="sxs-lookup"><span data-stu-id="e3123-110">Any items added to the union must be no larger than pointer size.</span></span> <span data-ttu-id="e3123-111">Se `struct` è necessario, è necessario allocarlo separatamente e puntare a tale oggetto.</span><span class="sxs-lookup"><span data-stu-id="e3123-111">If a `struct` is required, you must allocate it separately and point to it.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e3123-112">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="e3123-112">Remarks</span></span>  
 <span data-ttu-id="e3123-113">[ICLRErrorReportingManager:: BeginCustomDump](iclrerrorreportingmanager-begincustomdump-method.md) accetta un parametro di tipo `CustomDumpItem` .</span><span class="sxs-lookup"><span data-stu-id="e3123-113">[ICLRErrorReportingManager::BeginCustomDump](iclrerrorreportingmanager-begincustomdump-method.md) takes a parameter of type `CustomDumpItem`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e3123-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e3123-114">Requirements</span></span>  
 <span data-ttu-id="e3123-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e3123-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e3123-116">**Intestazione:** MSCorEE. idl</span><span class="sxs-lookup"><span data-stu-id="e3123-116">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="e3123-117">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="e3123-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e3123-118">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e3123-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3123-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e3123-119">See also</span></span>

- [<span data-ttu-id="e3123-120">Strutture di hosting</span><span class="sxs-lookup"><span data-stu-id="e3123-120">Hosting Structures</span></span>](hosting-structures.md)
