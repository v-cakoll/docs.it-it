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
ms.openlocfilehash: ae64edd8a3a628100d4c51d0b78be1bc8d49fc17
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138288"
---
# <a name="customdumpitem-structure"></a><span data-ttu-id="53105-102">Struttura CustomDumpItem</span><span class="sxs-lookup"><span data-stu-id="53105-102">CustomDumpItem Structure</span></span>
<span data-ttu-id="53105-103">Descrive un elemento da aggiungere a un dump personalizzato nella segnalazione degli errori.</span><span class="sxs-lookup"><span data-stu-id="53105-103">Describes an item to be added to a custom dump in error reporting.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53105-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="53105-104">Syntax</span></span>  
  
```cpp  
struct {  
    ECustomDumpItemKind itemKind;   
    union {  
        UINT_PTR pReserved;  
    }  
} CustomDumpItem;  
```  
  
## <a name="members"></a><span data-ttu-id="53105-105">Members</span><span class="sxs-lookup"><span data-stu-id="53105-105">Members</span></span>  
  
|<span data-ttu-id="53105-106">Member</span><span class="sxs-lookup"><span data-stu-id="53105-106">Member</span></span>|<span data-ttu-id="53105-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="53105-107">Description</span></span>|  
|------------|-----------------|  
|`itemKind`|<span data-ttu-id="53105-108">Valore [ECustomDumpItemKind](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md) che indica il tipo di elemento da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="53105-108">An [ECustomDumpItemKind](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md) value that indicates the kind of item to be added.</span></span>|  
|`pReserved`|<span data-ttu-id="53105-109">Attualmente non in uso.</span><span class="sxs-lookup"><span data-stu-id="53105-109">Not currently used.</span></span> <span data-ttu-id="53105-110">Gli elementi aggiunti all'Unione non devono essere maggiori delle dimensioni del puntatore.</span><span class="sxs-lookup"><span data-stu-id="53105-110">Any items added to the union must be no larger than pointer size.</span></span> <span data-ttu-id="53105-111">Se è necessaria una `struct`, è necessario allocarla separatamente e puntare a essa.</span><span class="sxs-lookup"><span data-stu-id="53105-111">If a `struct` is required, you must allocate it separately and point to it.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="53105-112">Note</span><span class="sxs-lookup"><span data-stu-id="53105-112">Remarks</span></span>  
 <span data-ttu-id="53105-113">[ICLRErrorReportingManager:: BeginCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) accetta un parametro di tipo `CustomDumpItem`.</span><span class="sxs-lookup"><span data-stu-id="53105-113">[ICLRErrorReportingManager::BeginCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) takes a parameter of type `CustomDumpItem`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="53105-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="53105-114">Requirements</span></span>  
 <span data-ttu-id="53105-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="53105-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="53105-116">**Intestazione:** MSCorEE. idl</span><span class="sxs-lookup"><span data-stu-id="53105-116">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="53105-117">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="53105-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="53105-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="53105-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53105-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="53105-119">See also</span></span>

- [<span data-ttu-id="53105-120">Strutture di hosting</span><span class="sxs-lookup"><span data-stu-id="53105-120">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
