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
ms.openlocfilehash: 154beef9398029f31dcb4d081019b9f292238af4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176474"
---
# <a name="customdumpitem-structure"></a><span data-ttu-id="775e5-102">Struttura CustomDumpItem</span><span class="sxs-lookup"><span data-stu-id="775e5-102">CustomDumpItem Structure</span></span>
<span data-ttu-id="775e5-103">Descrive un elemento da aggiungere a un dump personalizzato nella segnalazione errori.</span><span class="sxs-lookup"><span data-stu-id="775e5-103">Describes an item to be added to a custom dump in error reporting.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="775e5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="775e5-104">Syntax</span></span>  
  
```cpp  
struct {  
    ECustomDumpItemKind itemKind;
    union {  
        UINT_PTR pReserved;  
    }  
} CustomDumpItem;  
```  
  
## <a name="members"></a><span data-ttu-id="775e5-105">Members</span><span class="sxs-lookup"><span data-stu-id="775e5-105">Members</span></span>  
  
|<span data-ttu-id="775e5-106">Membro</span><span class="sxs-lookup"><span data-stu-id="775e5-106">Member</span></span>|<span data-ttu-id="775e5-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="775e5-107">Description</span></span>|  
|------------|-----------------|  
|`itemKind`|<span data-ttu-id="775e5-108">Valore [ECustomDumpItemKind](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md) che indica il tipo di elemento da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="775e5-108">An [ECustomDumpItemKind](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md) value that indicates the kind of item to be added.</span></span>|  
|`pReserved`|<span data-ttu-id="775e5-109">Attualmente non utilizzato.</span><span class="sxs-lookup"><span data-stu-id="775e5-109">Not currently used.</span></span> <span data-ttu-id="775e5-110">Tutti gli elementi aggiunti all'unione non devono essere maggiori delle dimensioni del puntatore.</span><span class="sxs-lookup"><span data-stu-id="775e5-110">Any items added to the union must be no larger than pointer size.</span></span> <span data-ttu-id="775e5-111">Se `struct` è necessario, è necessario allocarlo separatamente e puntare a esso.</span><span class="sxs-lookup"><span data-stu-id="775e5-111">If a `struct` is required, you must allocate it separately and point to it.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="775e5-112">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="775e5-112">Remarks</span></span>  
 <span data-ttu-id="775e5-113">[ICLRErrorReportingManager::BeginCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) accetta un `CustomDumpItem`parametro di tipo .</span><span class="sxs-lookup"><span data-stu-id="775e5-113">[ICLRErrorReportingManager::BeginCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) takes a parameter of type `CustomDumpItem`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="775e5-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="775e5-114">Requirements</span></span>  
 <span data-ttu-id="775e5-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="775e5-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="775e5-116">**Intestazione:** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="775e5-116">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="775e5-117">**Biblioteca:** Incluso come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="775e5-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="775e5-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="775e5-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="775e5-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="775e5-119">See also</span></span>

- [<span data-ttu-id="775e5-120">Strutture di hosting</span><span class="sxs-lookup"><span data-stu-id="775e5-120">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
