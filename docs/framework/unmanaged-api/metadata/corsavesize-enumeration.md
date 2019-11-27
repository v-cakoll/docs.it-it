---
title: Enumerazione CorSaveSize
ms.date: 03/30/2017
api_name:
- CorSaveSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorSaveSize
helpviewer_keywords:
- CorSaveSize enumeration [.NET Framework metadata]
ms.assetid: eb95ce39-5688-43c1-a34d-578794b32faa
topic_type:
- apiref
ms.openlocfilehash: 0f870d9d7d1bc292b213d690df508a6c28bac2ab
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450106"
---
# <a name="corsavesize-enumeration"></a><span data-ttu-id="547d5-102">Enumerazione CorSaveSize</span><span class="sxs-lookup"><span data-stu-id="547d5-102">CorSaveSize Enumeration</span></span>
<span data-ttu-id="547d5-103">Contiene valori che indicano il livello di precisione richiesto quando si eseguono query relative alla dimensione di un'operazione di salvataggio.</span><span class="sxs-lookup"><span data-stu-id="547d5-103">Contains values indicating the level of precision required when querying for the size of a save operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="547d5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="547d5-104">Syntax</span></span>  
  
```cpp  
typedef enum CorSaveSize {  
    cssAccurate                = 0x0000,   
    cssQuick                   = 0x0001,   
    cssDiscardTransientCAs     = 0x0002  
} CorSaveSize;  
```  
  
## <a name="members"></a><span data-ttu-id="547d5-105">Members</span><span class="sxs-lookup"><span data-stu-id="547d5-105">Members</span></span>  
  
|<span data-ttu-id="547d5-106">Membro</span><span class="sxs-lookup"><span data-stu-id="547d5-106">Member</span></span>|<span data-ttu-id="547d5-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="547d5-107">Description</span></span>|  
|------------|-----------------|  
|`cssAccurate`|<span data-ttu-id="547d5-108">Specifica che il valore restituito deve essere esatto.</span><span class="sxs-lookup"><span data-stu-id="547d5-108">Specifies that the return value should be exact.</span></span>|  
|`cssQuick`|<span data-ttu-id="547d5-109">Specifica che il valore restituito deve essere stimato.</span><span class="sxs-lookup"><span data-stu-id="547d5-109">Specifies that the return value should be estimated.</span></span>|  
|`cssDiscardTransientCAs`|<span data-ttu-id="547d5-110">Specifica che i tipi scartabili devono essere rimossi.</span><span class="sxs-lookup"><span data-stu-id="547d5-110">Specifies that discardable types should be removed.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="547d5-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="547d5-111">Requirements</span></span>  
 <span data-ttu-id="547d5-112">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="547d5-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="547d5-113">**Intestazione:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="547d5-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="547d5-114">**Libreria:** Usato come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="547d5-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="547d5-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="547d5-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="547d5-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="547d5-116">See also</span></span>

- [<span data-ttu-id="547d5-117">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="547d5-117">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
