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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f756e8688299fbe9d53822851be83703f4aa6348
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54550630"
---
# <a name="corsavesize-enumeration"></a><span data-ttu-id="5db39-102">Enumerazione CorSaveSize</span><span class="sxs-lookup"><span data-stu-id="5db39-102">CorSaveSize Enumeration</span></span>
<span data-ttu-id="5db39-103">Contiene valori che indicano il livello di precisione richiesto quando si eseguono query relative alla dimensione di un'operazione di salvataggio.</span><span class="sxs-lookup"><span data-stu-id="5db39-103">Contains values indicating the level of precision required when querying for the size of a save operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5db39-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5db39-104">Syntax</span></span>  
  
```  
typedef enum CorSaveSize {  
    cssAccurate                = 0x0000,   
    cssQuick                   = 0x0001,   
    cssDiscardTransientCAs     = 0x0002  
} CorSaveSize;  
```  
  
## <a name="members"></a><span data-ttu-id="5db39-105">Membri</span><span class="sxs-lookup"><span data-stu-id="5db39-105">Members</span></span>  
  
|<span data-ttu-id="5db39-106">Membro</span><span class="sxs-lookup"><span data-stu-id="5db39-106">Member</span></span>|<span data-ttu-id="5db39-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5db39-107">Description</span></span>|  
|------------|-----------------|  
|`cssAccurate`|<span data-ttu-id="5db39-108">Specifica che il valore restituito deve essere esatto.</span><span class="sxs-lookup"><span data-stu-id="5db39-108">Specifies that the return value should be exact.</span></span>|  
|`cssQuick`|<span data-ttu-id="5db39-109">Specifica che il valore restituito deve essere stimato.</span><span class="sxs-lookup"><span data-stu-id="5db39-109">Specifies that the return value should be estimated.</span></span>|  
|`cssDiscardTransientCAs`|<span data-ttu-id="5db39-110">Specifica che i tipi eliminabili devono essere rimossi.</span><span class="sxs-lookup"><span data-stu-id="5db39-110">Specifies that discardable types should be removed.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5db39-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5db39-111">Requirements</span></span>  
 <span data-ttu-id="5db39-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5db39-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5db39-113">**Intestazione:** CorHdr. H</span><span class="sxs-lookup"><span data-stu-id="5db39-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="5db39-114">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="5db39-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5db39-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5db39-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5db39-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5db39-116">See also</span></span>
- [<span data-ttu-id="5db39-117">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="5db39-117">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
