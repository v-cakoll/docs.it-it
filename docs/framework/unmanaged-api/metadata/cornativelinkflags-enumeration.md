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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6be71878ba354ebe53b4b8b9b40db3222ec828f3
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781730"
---
# <a name="cornativelinkflags-enumeration"></a><span data-ttu-id="9afac-102">Enumerazione CorNativeLinkFlags</span><span class="sxs-lookup"><span data-stu-id="9afac-102">CorNativeLinkFlags Enumeration</span></span>
<span data-ttu-id="9afac-103">Fornisce valori di flag usati dal linker durante il collegamento del codice nativo.</span><span class="sxs-lookup"><span data-stu-id="9afac-103">Provides flag values used by the linker when linking native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9afac-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9afac-104">Syntax</span></span>  
  
```cpp  
typedef enum  
{  
    nlfNone         = 0x00,  
    nlfLastError    = 0x01,  
    nlfNoMangle     = 0x02,  
    nlfMaxValue     = 0x03  
} CorNativeLinkFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="9afac-105">Members</span><span class="sxs-lookup"><span data-stu-id="9afac-105">Members</span></span>  
  
|<span data-ttu-id="9afac-106">Member</span><span class="sxs-lookup"><span data-stu-id="9afac-106">Member</span></span>|<span data-ttu-id="9afac-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9afac-107">Description</span></span>|  
|------------|-----------------|  
|`nlfNone`|<span data-ttu-id="9afac-108">Non indica nessun flag.</span><span class="sxs-lookup"><span data-stu-id="9afac-108">Indicates no flags.</span></span>|  
|`nlfLastError`|<span data-ttu-id="9afac-109">Indica un `setLastError` (parola chiave).</span><span class="sxs-lookup"><span data-stu-id="9afac-109">Indicates a `setLastError` keyword.</span></span>|  
|`nlfNoMangle`|<span data-ttu-id="9afac-110">Indica un `nomangle` (parola chiave).</span><span class="sxs-lookup"><span data-stu-id="9afac-110">Indicates a `nomangle` keyword.</span></span>|  
|`nlfMaxValue`|<span data-ttu-id="9afac-111">Non usato.</span><span class="sxs-lookup"><span data-stu-id="9afac-111">Not used.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9afac-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9afac-112">Requirements</span></span>  
 <span data-ttu-id="9afac-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9afac-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9afac-114">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="9afac-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9afac-115">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="9afac-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9afac-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9afac-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9afac-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9afac-117">See also</span></span>

- [<span data-ttu-id="9afac-118">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="9afac-118">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
