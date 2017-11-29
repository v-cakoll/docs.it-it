---
title: Enumerazione CorSaveSize
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorSaveSize
api_location: mscoree.dll
api_type: COM
f1_keywords: CorSaveSize
helpviewer_keywords: CorSaveSize enumeration [.NET Framework metadata]
ms.assetid: eb95ce39-5688-43c1-a34d-578794b32faa
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 34d4d42c7cf385bca77de37dce52689778aa5b1f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="corsavesize-enumeration"></a><span data-ttu-id="ffae7-102">Enumerazione CorSaveSize</span><span class="sxs-lookup"><span data-stu-id="ffae7-102">CorSaveSize Enumeration</span></span>
<span data-ttu-id="ffae7-103">Contiene valori che indicano il livello di precisione richiesto quando si eseguono query relative alla dimensione di un'operazione di salvataggio.</span><span class="sxs-lookup"><span data-stu-id="ffae7-103">Contains values indicating the level of precision required when querying for the size of a save operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ffae7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ffae7-104">Syntax</span></span>  
  
```  
typedef enum CorSaveSize {  
    cssAccurate                = 0x0000,   
    cssQuick                   = 0x0001,   
    cssDiscardTransientCAs     = 0x0002  
} CorSaveSize;  
```  
  
## <a name="members"></a><span data-ttu-id="ffae7-105">Membri</span><span class="sxs-lookup"><span data-stu-id="ffae7-105">Members</span></span>  
  
|<span data-ttu-id="ffae7-106">Membro</span><span class="sxs-lookup"><span data-stu-id="ffae7-106">Member</span></span>|<span data-ttu-id="ffae7-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ffae7-107">Description</span></span>|  
|------------|-----------------|  
|`cssAccurate`|<span data-ttu-id="ffae7-108">Specifica che il valore restituito deve essere esatto.</span><span class="sxs-lookup"><span data-stu-id="ffae7-108">Specifies that the return value should be exact.</span></span>|  
|`cssQuick`|<span data-ttu-id="ffae7-109">Specifica che il valore restituito deve essere stimato.</span><span class="sxs-lookup"><span data-stu-id="ffae7-109">Specifies that the return value should be estimated.</span></span>|  
|`cssDiscardTransientCAs`|<span data-ttu-id="ffae7-110">Specifica che i tipi eliminabili devono essere rimossi.</span><span class="sxs-lookup"><span data-stu-id="ffae7-110">Specifies that discardable types should be removed.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ffae7-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ffae7-111">Requirements</span></span>  
 <span data-ttu-id="ffae7-112">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ffae7-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ffae7-113">**Intestazione:** CorHdr. H</span><span class="sxs-lookup"><span data-stu-id="ffae7-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="ffae7-114">**Libreria:** usata come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ffae7-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ffae7-115">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ffae7-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ffae7-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ffae7-116">See Also</span></span>  
 [<span data-ttu-id="ffae7-117">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="ffae7-117">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
