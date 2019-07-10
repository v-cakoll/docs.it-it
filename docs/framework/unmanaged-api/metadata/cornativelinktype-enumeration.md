---
title: Enumerazione CorNativeLinkType
ms.date: 03/30/2017
api_name:
- CorNativeLinkType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorNativeLinkType
helpviewer_keywords:
- CorNativeLinkType enumeration [.NET Framework metadata]
ms.assetid: 4f86ff37-2dab-4e64-819a-76b3bfe828ff
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 944c641c39ddef7add0e9f382dc7d35068668455
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781723"
---
# <a name="cornativelinktype-enumeration"></a><span data-ttu-id="48520-102">Enumerazione CorNativeLinkType</span><span class="sxs-lookup"><span data-stu-id="48520-102">CorNativeLinkType Enumeration</span></span>
<span data-ttu-id="48520-103">Fornisce valori che indicano il tipo collegato nel codice nativo.</span><span class="sxs-lookup"><span data-stu-id="48520-103">Provides values that indicate the type linked in native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48520-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="48520-104">Syntax</span></span>  
  
```cpp  
typedef enum   
{  
    nltNone       = 1,  
    nltAnsi       = 2,  
    nltUnicode    = 3,  
    nltAuto       = 4,  
    nltOle        = 5,  
    nltMaxValue   = 7  
} CorNativeLinkType;  
```  
  
## <a name="members"></a><span data-ttu-id="48520-105">Membri</span><span class="sxs-lookup"><span data-stu-id="48520-105">Members</span></span>  
  
|<span data-ttu-id="48520-106">Member</span><span class="sxs-lookup"><span data-stu-id="48520-106">Member</span></span>|<span data-ttu-id="48520-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="48520-107">Description</span></span>|  
|------------|-----------------|  
|`nltNone`|<span data-ttu-id="48520-108">Indica che nessuna delle parole chiave sono stata specificata.</span><span class="sxs-lookup"><span data-stu-id="48520-108">Indicates that none of the keywords are specified.</span></span>|  
|`nltAnsi`|<span data-ttu-id="48520-109">Indica che è specificata una parola chiave ANSI.</span><span class="sxs-lookup"><span data-stu-id="48520-109">Indicates that an ANSI keyword is specified.</span></span>|  
|`nltUnicode`|<span data-ttu-id="48520-110">Indica che è specificata una parola chiave Unicode</span><span class="sxs-lookup"><span data-stu-id="48520-110">Indicates that a Unicode keyword is specified</span></span>|  
|`nltAuto`|<span data-ttu-id="48520-111">Indica che è specificata una parola chiave auto.</span><span class="sxs-lookup"><span data-stu-id="48520-111">Indicates that an auto keyword is specified.</span></span>|  
|`nltOle`|<span data-ttu-id="48520-112">Indica che è specificata una parola chiave OLE.</span><span class="sxs-lookup"><span data-stu-id="48520-112">Indicates that an OLE keyword is specified.</span></span>|  
|`nltMaxValue`|<span data-ttu-id="48520-113">Non usato.</span><span class="sxs-lookup"><span data-stu-id="48520-113">Not used.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="48520-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="48520-114">Requirements</span></span>  
 <span data-ttu-id="48520-115">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="48520-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="48520-116">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="48520-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="48520-117">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="48520-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="48520-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="48520-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48520-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="48520-119">See also</span></span>

- [<span data-ttu-id="48520-120">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="48520-120">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
