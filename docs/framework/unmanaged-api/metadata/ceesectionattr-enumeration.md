---
title: Enumerazione CeeSectionAttr
ms.date: 03/30/2017
api_name:
- CeeSectionAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CeeSectionAttr
helpviewer_keywords:
- CeeSectionAttr enumeration [.NET Framework metadata]
ms.assetid: 0db51881-b869-4677-a715-1726a9216489
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c317524cefd7ed654e76bdd7051cdcd7653062db
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59101790"
---
# <a name="ceesectionattr-enumeration"></a><span data-ttu-id="6f2c4-102">Enumerazione CeeSectionAttr</span><span class="sxs-lookup"><span data-stu-id="6f2c4-102">CeeSectionAttr Enumeration</span></span>
<span data-ttu-id="6f2c4-103">Fornisce i valori che specificano gli attributi di una sezione per l'utilizzo da parte di [ICeeGen](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md) interfaccia.</span><span class="sxs-lookup"><span data-stu-id="6f2c4-103">Provides values that specify attributes of a section for use by the [ICeeGen](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f2c4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6f2c4-104">Syntax</span></span>  
  
```  
typedef enum  {  
    sdNone      = 0,  
    sdReadOnly  = IMAGE_SCN_CNT_INITIALIZED_DATA |  
                  IMAGE_SCN_MEM_READ,  
    sdReadWrite = sdReadOnly | IMAGE_SCN_MEM_WRITE,  
    sdExecute   = IMAGE_SCN_MEM_READ | IMAGE_SCN_CNT_CODE |  
                  IMAGE_SCN_MEM_EXECUTE  
} CeeSectionAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="6f2c4-105">Membri</span><span class="sxs-lookup"><span data-stu-id="6f2c4-105">Members</span></span>  
  
|<span data-ttu-id="6f2c4-106">Member</span><span class="sxs-lookup"><span data-stu-id="6f2c4-106">Member</span></span>|<span data-ttu-id="6f2c4-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6f2c4-107">Description</span></span>|  
|------------|-----------------|  
|`sdNone`|<span data-ttu-id="6f2c4-108">Sezione non dispone di attributi.</span><span class="sxs-lookup"><span data-stu-id="6f2c4-108">Section has no attributes.</span></span>|  
|`sdReadOnly`|<span data-ttu-id="6f2c4-109">Sezione contiene i dati inizializzati che possono essere solo letto, non aggiornati.</span><span class="sxs-lookup"><span data-stu-id="6f2c4-109">Section contains initialized data that can be only read, not updated.</span></span>|  
|`sdReadWrite`|<span data-ttu-id="6f2c4-110">Sezione contiene i dati inizializzati che possono essere letti o aggiornati.</span><span class="sxs-lookup"><span data-stu-id="6f2c4-110">Section contains initialized data that can be read or updated.</span></span>|  
|`sdExecute`|<span data-ttu-id="6f2c4-111">Sezione contiene codice eseguibile che può essere letto ed eseguito.</span><span class="sxs-lookup"><span data-stu-id="6f2c4-111">Section contains executable code that is allowed to be read and executed.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6f2c4-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6f2c4-112">Requirements</span></span>  
 <span data-ttu-id="6f2c4-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6f2c4-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6f2c4-114">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="6f2c4-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6f2c4-115">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="6f2c4-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="6f2c4-116">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="6f2c4-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="6f2c4-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6f2c4-117">See also</span></span>

- [<span data-ttu-id="6f2c4-118">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="6f2c4-118">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
