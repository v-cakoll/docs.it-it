---
title: Enumerazione CorRegFlags
ms.date: 03/30/2017
api_name:
- CorRegFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorRegFlags
helpviewer_keywords:
- CorRegFlags enumeration [.NET Framework metadata]
ms.assetid: 8d3080ee-39fe-4c57-8950-51323632d045
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 52b59a4e52d3e0cda7353ec1b39c5307bd7b218e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54532266"
---
# <a name="corregflags-enumeration"></a><span data-ttu-id="ae471-102">Enumerazione CorRegFlags</span><span class="sxs-lookup"><span data-stu-id="ae471-102">CorRegFlags Enumeration</span></span>
<span data-ttu-id="ae471-103">Fornisce i valori di flag usati per la registrazione quando si installa un modulo o un'immagine composita.</span><span class="sxs-lookup"><span data-stu-id="ae471-103">Provides flag values used for registration when installing a module or composite image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae471-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ae471-104">Syntax</span></span>  
  
```  
typedef enum   
{  
    regNoCopy  = 0x00000001,  
    regConfig  = 0x00000002,  
    regHasRefs = 0x00000004  
} CorRegFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="ae471-105">Membri</span><span class="sxs-lookup"><span data-stu-id="ae471-105">Members</span></span>  
  
|<span data-ttu-id="ae471-106">Membro</span><span class="sxs-lookup"><span data-stu-id="ae471-106">Member</span></span>|<span data-ttu-id="ae471-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ae471-107">Description</span></span>|  
|------------|-----------------|  
|`regNoCopy`|<span data-ttu-id="ae471-108">Specifica che i file non devono essere copiati nella destinazione.</span><span class="sxs-lookup"><span data-stu-id="ae471-108">Specifies that files should not be copied into the destination.</span></span>|  
|`regConfig`|<span data-ttu-id="ae471-109">Specifica che il modulo o un insieme è una configurazione.</span><span class="sxs-lookup"><span data-stu-id="ae471-109">Specifies that the module or composite is a configuration.</span></span>|  
|`regHasRefs`|<span data-ttu-id="ae471-110">Specifica che il modulo o un insieme contiene riferimenti a classi.</span><span class="sxs-lookup"><span data-stu-id="ae471-110">Specifies that the module or composite has class references.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ae471-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ae471-111">Requirements</span></span>  
 <span data-ttu-id="ae471-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ae471-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ae471-113">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="ae471-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ae471-114">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="ae471-114">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ae471-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae471-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae471-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ae471-116">See also</span></span>
- [<span data-ttu-id="ae471-117">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="ae471-117">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
