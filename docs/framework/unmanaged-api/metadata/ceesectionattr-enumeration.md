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
ms.openlocfilehash: 6da8a111f716906e403d85bc0b1a29eba7238100
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84006064"
---
# <a name="ceesectionattr-enumeration"></a><span data-ttu-id="a3f21-102">Enumerazione CeeSectionAttr</span><span class="sxs-lookup"><span data-stu-id="a3f21-102">CeeSectionAttr Enumeration</span></span>
<span data-ttu-id="a3f21-103">Fornisce valori che specificano gli attributi di una sezione per l'utilizzo da parte dell'interfaccia [ICeeGen](iceegen-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="a3f21-103">Provides values that specify attributes of a section for use by the [ICeeGen](iceegen-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3f21-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a3f21-104">Syntax</span></span>  
  
```cpp  
typedef enum  {  
    sdNone      = 0,  
    sdReadOnly  = IMAGE_SCN_CNT_INITIALIZED_DATA |  
                  IMAGE_SCN_MEM_READ,  
    sdReadWrite = sdReadOnly | IMAGE_SCN_MEM_WRITE,  
    sdExecute   = IMAGE_SCN_MEM_READ | IMAGE_SCN_CNT_CODE |  
                  IMAGE_SCN_MEM_EXECUTE  
} CeeSectionAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="a3f21-105">Membri</span><span class="sxs-lookup"><span data-stu-id="a3f21-105">Members</span></span>  
  
|<span data-ttu-id="a3f21-106">Membro</span><span class="sxs-lookup"><span data-stu-id="a3f21-106">Member</span></span>|<span data-ttu-id="a3f21-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a3f21-107">Description</span></span>|  
|------------|-----------------|  
|`sdNone`|<span data-ttu-id="a3f21-108">La sezione non ha attributi.</span><span class="sxs-lookup"><span data-stu-id="a3f21-108">Section has no attributes.</span></span>|  
|`sdReadOnly`|<span data-ttu-id="a3f21-109">La sezione contiene dati inizializzati che possono essere letti solo e non aggiornati.</span><span class="sxs-lookup"><span data-stu-id="a3f21-109">Section contains initialized data that can be only read, not updated.</span></span>|  
|`sdReadWrite`|<span data-ttu-id="a3f21-110">La sezione contiene dati inizializzati che è possibile leggere o aggiornare.</span><span class="sxs-lookup"><span data-stu-id="a3f21-110">Section contains initialized data that can be read or updated.</span></span>|  
|`sdExecute`|<span data-ttu-id="a3f21-111">La sezione contiene codice eseguibile che può essere letto ed eseguito.</span><span class="sxs-lookup"><span data-stu-id="a3f21-111">Section contains executable code that is allowed to be read and executed.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a3f21-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a3f21-112">Requirements</span></span>  
 <span data-ttu-id="a3f21-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a3f21-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a3f21-114">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="a3f21-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a3f21-115">**Libreria:** Incluso come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="a3f21-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a3f21-116">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a3f21-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3f21-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a3f21-117">See also</span></span>

- [<span data-ttu-id="a3f21-118">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="a3f21-118">Metadata Enumerations</span></span>](metadata-enumerations.md)
