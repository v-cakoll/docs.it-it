---
title: Unione CeeSectionRelocExtra
ms.date: 03/30/2017
api_name:
- CeeSectionRelocExtra Union
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CeeSectionRelocExtra
helpviewer_keywords:
- CeeSectionRelocExtra union [.NET Framework metadata]
ms.assetid: d9568cf6-7f98-4cd6-ab36-0a2bd509afcc
topic_type:
- apiref
ms.openlocfilehash: d11fefe220fdb00457cc48a6cd166673350be049
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84006032"
---
# <a name="ceesectionrelocextra-union"></a><span data-ttu-id="a67f2-102">Unione CeeSectionRelocExtra</span><span class="sxs-lookup"><span data-stu-id="a67f2-102">CeeSectionRelocExtra Union</span></span>
<span data-ttu-id="a67f2-103">Rappresenta un offset di indirizzo utilizzato dall'interfaccia [ICeeGen](iceegen-interface.md) per spostare una sezione.</span><span class="sxs-lookup"><span data-stu-id="a67f2-103">Represents an address offset that is used by the [ICeeGen](iceegen-interface.md) interface to relocate a section.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a67f2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a67f2-104">Syntax</span></span>  
  
```cpp  
typedef union  {  
    USHORT highAdj;  
} CeeSectionRelocExtra;  
```  
  
## <a name="members"></a><span data-ttu-id="a67f2-105">Membri</span><span class="sxs-lookup"><span data-stu-id="a67f2-105">Members</span></span>  
  
|<span data-ttu-id="a67f2-106">Membro</span><span class="sxs-lookup"><span data-stu-id="a67f2-106">Member</span></span>|<span data-ttu-id="a67f2-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a67f2-107">Description</span></span>|  
|------------|-----------------|  
|`highAdj`|<span data-ttu-id="a67f2-108">Regolazione dell'indirizzo superiore per la sezione.</span><span class="sxs-lookup"><span data-stu-id="a67f2-108">The upper address adjustment for the section.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a67f2-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a67f2-109">Requirements</span></span>  
 <span data-ttu-id="a67f2-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a67f2-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a67f2-111">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="a67f2-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a67f2-112">**Libreria:** Incluso come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="a67f2-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a67f2-113">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a67f2-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a67f2-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a67f2-114">See also</span></span>

- [<span data-ttu-id="a67f2-115">Unioni di metadati</span><span class="sxs-lookup"><span data-stu-id="a67f2-115">Metadata Unions</span></span>](metadata-unions.md)
