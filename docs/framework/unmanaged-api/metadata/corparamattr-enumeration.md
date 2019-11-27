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
ms.openlocfilehash: 1d58c8c0413346536c3e61e67ca0077c08c2b387
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436483"
---
# <a name="corparamattr-enumeration"></a><span data-ttu-id="61549-102">Enumerazione CorParamAttr</span><span class="sxs-lookup"><span data-stu-id="61549-102">CorParamAttr Enumeration</span></span>
<span data-ttu-id="61549-103">Contiene valori che descrivono i metadati di un parametro di metodo.</span><span class="sxs-lookup"><span data-stu-id="61549-103">Contains values that describe the metadata of a method parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61549-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="61549-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="61549-105">Members</span><span class="sxs-lookup"><span data-stu-id="61549-105">Members</span></span>  
  
|<span data-ttu-id="61549-106">Membro</span><span class="sxs-lookup"><span data-stu-id="61549-106">Member</span></span>|<span data-ttu-id="61549-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="61549-107">Description</span></span>|  
|------------|-----------------|  
|`pdIn`|<span data-ttu-id="61549-108">Specifica che il parametro viene passato alla chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="61549-108">Specifies that the parameter is passed into the method call.</span></span>|  
|`pdOut`|<span data-ttu-id="61549-109">Specifica che il parametro viene passato dal metodo restituito.</span><span class="sxs-lookup"><span data-stu-id="61549-109">Specifies that the parameter is passed from the method return.</span></span>|  
|`pdOptional`|<span data-ttu-id="61549-110">Specifica che il parametro è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="61549-110">Specifies that the parameter is optional.</span></span>|  
|`pdReservedMask`|<span data-ttu-id="61549-111">Riservato per uso interno da parte del Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="61549-111">Reserved for internal use by the common language runtime.</span></span>|  
|`pdHasDefault`|<span data-ttu-id="61549-112">Specifica che il parametro ha un valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="61549-112">Specifies that the parameter has a default value.</span></span>|  
|`pdHasFieldMarshal`|<span data-ttu-id="61549-113">Specifica che il parametro dispone di informazioni di marshalling.</span><span class="sxs-lookup"><span data-stu-id="61549-113">Specifies that the parameter has marshaling information.</span></span>|  
|`pdUnused`|<span data-ttu-id="61549-114">Non usato.</span><span class="sxs-lookup"><span data-stu-id="61549-114">Unused.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="61549-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="61549-115">Requirements</span></span>  
 <span data-ttu-id="61549-116">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="61549-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="61549-117">**Intestazione:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="61549-117">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="61549-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="61549-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61549-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="61549-119">See also</span></span>

- [<span data-ttu-id="61549-120">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="61549-120">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
