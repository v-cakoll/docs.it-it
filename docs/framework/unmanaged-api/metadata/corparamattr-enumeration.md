---
title: Enumerazione CorParamAttr
ms.date: 03/30/2017
api_name:
- CorParamAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorParamAttr
helpviewer_keywords:
- CorParamAttr enumeration [.NET Framework metadata]
ms.assetid: a7ff90ad-dad8-48e8-917d-4aa9a118cbc8
topic_type:
- apiref
ms.openlocfilehash: e8afcb972cab9757458c7032c3678d45c6418fac
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007572"
---
# <a name="corparamattr-enumeration"></a><span data-ttu-id="b0453-102">Enumerazione CorParamAttr</span><span class="sxs-lookup"><span data-stu-id="b0453-102">CorParamAttr Enumeration</span></span>
<span data-ttu-id="b0453-103">Contiene valori che descrivono i metadati di un parametro di metodo.</span><span class="sxs-lookup"><span data-stu-id="b0453-103">Contains values that describe the metadata of a method parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0453-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b0453-104">Syntax</span></span>  
  
```cpp  
typedef enum CorParamAttr {  
  
    pdIn                        =   0x0001,  
    pdOut                       =   0x0002,  
    pdOptional                  =   0x0010,  
  
    pdReservedMask              =   0xf000,  
    pdHasDefault                =   0x1000,  
    pdHasFieldMarshal           =   0x2000,  
  
    pdUnused                    =   0xcfe0  
  
} CorParamAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="b0453-105">Membri</span><span class="sxs-lookup"><span data-stu-id="b0453-105">Members</span></span>  
  
|<span data-ttu-id="b0453-106">Membro</span><span class="sxs-lookup"><span data-stu-id="b0453-106">Member</span></span>|<span data-ttu-id="b0453-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b0453-107">Description</span></span>|  
|------------|-----------------|  
|`pdIn`|<span data-ttu-id="b0453-108">Specifica che il parametro viene passato alla chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="b0453-108">Specifies that the parameter is passed into the method call.</span></span>|  
|`pdOut`|<span data-ttu-id="b0453-109">Specifica che il parametro viene passato dal metodo restituito.</span><span class="sxs-lookup"><span data-stu-id="b0453-109">Specifies that the parameter is passed from the method return.</span></span>|  
|`pdOptional`|<span data-ttu-id="b0453-110">Specifica che si tratta di un parametro opzionale.</span><span class="sxs-lookup"><span data-stu-id="b0453-110">Specifies that the parameter is optional.</span></span>|  
|`pdReservedMask`|<span data-ttu-id="b0453-111">Riservato per uso interno da parte del Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="b0453-111">Reserved for internal use by the common language runtime.</span></span>|  
|`pdHasDefault`|<span data-ttu-id="b0453-112">Specifica che il parametro ha un valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="b0453-112">Specifies that the parameter has a default value.</span></span>|  
|`pdHasFieldMarshal`|<span data-ttu-id="b0453-113">Specifica che il parametro dispone di informazioni di marshalling.</span><span class="sxs-lookup"><span data-stu-id="b0453-113">Specifies that the parameter has marshaling information.</span></span>|  
|`pdUnused`|<span data-ttu-id="b0453-114">Non utilizzato.</span><span class="sxs-lookup"><span data-stu-id="b0453-114">Unused.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b0453-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b0453-115">Requirements</span></span>  
 <span data-ttu-id="b0453-116">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b0453-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b0453-117">**Intestazione:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="b0453-117">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="b0453-118">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b0453-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0453-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b0453-119">See also</span></span>

- [<span data-ttu-id="b0453-120">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="b0453-120">Metadata Enumerations</span></span>](metadata-enumerations.md)
