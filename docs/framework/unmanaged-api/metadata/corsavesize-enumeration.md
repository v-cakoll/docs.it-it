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
ms.openlocfilehash: 22a7f87a5803dc185052a5ce7ed427eff9f8fb18
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009184"
---
# <a name="corsavesize-enumeration"></a><span data-ttu-id="543f4-102">Enumerazione CorSaveSize</span><span class="sxs-lookup"><span data-stu-id="543f4-102">CorSaveSize Enumeration</span></span>
<span data-ttu-id="543f4-103">Contiene valori che indicano il livello di precisione richiesto quando si eseguono query relative alla dimensione di un'operazione di salvataggio.</span><span class="sxs-lookup"><span data-stu-id="543f4-103">Contains values indicating the level of precision required when querying for the size of a save operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="543f4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="543f4-104">Syntax</span></span>  
  
```cpp  
typedef enum CorSaveSize {  
    cssAccurate                = 0x0000,
    cssQuick                   = 0x0001,
    cssDiscardTransientCAs     = 0x0002  
} CorSaveSize;  
```  
  
## <a name="members"></a><span data-ttu-id="543f4-105">Membri</span><span class="sxs-lookup"><span data-stu-id="543f4-105">Members</span></span>  
  
|<span data-ttu-id="543f4-106">Membro</span><span class="sxs-lookup"><span data-stu-id="543f4-106">Member</span></span>|<span data-ttu-id="543f4-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="543f4-107">Description</span></span>|  
|------------|-----------------|  
|`cssAccurate`|<span data-ttu-id="543f4-108">Specifica che il valore restituito deve essere esatto.</span><span class="sxs-lookup"><span data-stu-id="543f4-108">Specifies that the return value should be exact.</span></span>|  
|`cssQuick`|<span data-ttu-id="543f4-109">Specifica che il valore restituito deve essere stimato.</span><span class="sxs-lookup"><span data-stu-id="543f4-109">Specifies that the return value should be estimated.</span></span>|  
|`cssDiscardTransientCAs`|<span data-ttu-id="543f4-110">Specifica che i tipi scartabili devono essere rimossi.</span><span class="sxs-lookup"><span data-stu-id="543f4-110">Specifies that discardable types should be removed.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="543f4-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="543f4-111">Requirements</span></span>  
 <span data-ttu-id="543f4-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="543f4-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="543f4-113">**Intestazione:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="543f4-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="543f4-114">**Libreria:** Usato come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="543f4-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="543f4-115">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="543f4-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="543f4-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="543f4-116">See also</span></span>

- [<span data-ttu-id="543f4-117">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="543f4-117">Metadata Enumerations</span></span>](metadata-enumerations.md)
