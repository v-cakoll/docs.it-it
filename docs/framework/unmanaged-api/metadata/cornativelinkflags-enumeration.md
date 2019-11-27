---
title: Enumerazione CorNativeLinkFlags
ms.date: 03/30/2017
api_name:
- CorNativeLinkFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorNativeLinkFlags
helpviewer_keywords:
- CorNativeLinkFlags enumeration [.NET Framework metadata]
ms.assetid: 8027df7c-cfad-4724-bda0-7538d9519070
topic_type:
- apiref
ms.openlocfilehash: 1362efbf518310240ce665badc93810d1c0b9b89
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450197"
---
# <a name="cornativelinkflags-enumeration"></a><span data-ttu-id="ba38f-102">Enumerazione CorNativeLinkFlags</span><span class="sxs-lookup"><span data-stu-id="ba38f-102">CorNativeLinkFlags Enumeration</span></span>
<span data-ttu-id="ba38f-103">Fornisce valori di flag usati dal linker durante il collegamento del codice nativo.</span><span class="sxs-lookup"><span data-stu-id="ba38f-103">Provides flag values used by the linker when linking native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba38f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ba38f-104">Syntax</span></span>  
  
```cpp  
typedef enum  
{  
    nlfNone         = 0x00,  
    nlfLastError    = 0x01,  
    nlfNoMangle     = 0x02,  
    nlfMaxValue     = 0x03  
} CorNativeLinkFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="ba38f-105">Membri</span><span class="sxs-lookup"><span data-stu-id="ba38f-105">Members</span></span>  
  
|<span data-ttu-id="ba38f-106">Membro</span><span class="sxs-lookup"><span data-stu-id="ba38f-106">Member</span></span>|<span data-ttu-id="ba38f-107">description</span><span class="sxs-lookup"><span data-stu-id="ba38f-107">Description</span></span>|  
|------------|-----------------|  
|`nlfNone`|<span data-ttu-id="ba38f-108">Indica nessun flag.</span><span class="sxs-lookup"><span data-stu-id="ba38f-108">Indicates no flags.</span></span>|  
|`nlfLastError`|<span data-ttu-id="ba38f-109">Indica una parola chiave `setLastError`.</span><span class="sxs-lookup"><span data-stu-id="ba38f-109">Indicates a `setLastError` keyword.</span></span>|  
|`nlfNoMangle`|<span data-ttu-id="ba38f-110">Indica una parola chiave `nomangle`.</span><span class="sxs-lookup"><span data-stu-id="ba38f-110">Indicates a `nomangle` keyword.</span></span>|  
|`nlfMaxValue`|<span data-ttu-id="ba38f-111">Non usato.</span><span class="sxs-lookup"><span data-stu-id="ba38f-111">Not used.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ba38f-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ba38f-112">Requirements</span></span>  
 <span data-ttu-id="ba38f-113">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ba38f-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ba38f-114">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="ba38f-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ba38f-115">**Libreria:** Incluso come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="ba38f-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ba38f-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ba38f-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba38f-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ba38f-117">See also</span></span>

- [<span data-ttu-id="ba38f-118">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="ba38f-118">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
