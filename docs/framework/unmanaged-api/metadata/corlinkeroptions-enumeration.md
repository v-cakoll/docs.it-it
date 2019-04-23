---
title: Enumerazione CorLinkerOptions
ms.date: 03/30/2017
api_name:
- CorLinkerOptions
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorLinkerOptions
helpviewer_keywords:
- CorLinkerOptions enumeration [.NET Framework metadata]
ms.assetid: a656aad6-cc7e-4994-8251-004a6a45e18f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: dc0554ed89d21607978d059b26c4ad69e59a2d4c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59166634"
---
# <a name="corlinkeroptions-enumeration"></a><span data-ttu-id="10c36-102">Enumerazione CorLinkerOptions</span><span class="sxs-lookup"><span data-stu-id="10c36-102">CorLinkerOptions Enumeration</span></span>
<span data-ttu-id="10c36-103">Specifica i flag per selezionare le opzioni per il linker dei metadati.</span><span class="sxs-lookup"><span data-stu-id="10c36-103">Specifies flags to select options for the metadata linker.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10c36-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="10c36-104">Syntax</span></span>  
  
```  
typedef enum CorLinkerOptions {  
    MDAssembly          = 0x00000000,  
    MDNetModule         = 0x00000001,  
} CorLinkerOptions;  
```  
  
## <a name="members"></a><span data-ttu-id="10c36-105">Membri</span><span class="sxs-lookup"><span data-stu-id="10c36-105">Members</span></span>  
  
|<span data-ttu-id="10c36-106">Member</span><span class="sxs-lookup"><span data-stu-id="10c36-106">Member</span></span>|<span data-ttu-id="10c36-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="10c36-107">Description</span></span>|  
|------------|-----------------|  
|`MDAssembly`|<span data-ttu-id="10c36-108">Le funzioni globali e tipi privati non vengono mantenute.</span><span class="sxs-lookup"><span data-stu-id="10c36-108">The private types and global functions are not preserved.</span></span>|  
|`MDNetModule`|<span data-ttu-id="10c36-109">I tipi privati e funzioni globali vengono mantenute.</span><span class="sxs-lookup"><span data-stu-id="10c36-109">The private types and global functions are preserved.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="10c36-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="10c36-110">Requirements</span></span>  
 <span data-ttu-id="10c36-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="10c36-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="10c36-112">**Intestazione:** CorHdr. H</span><span class="sxs-lookup"><span data-stu-id="10c36-112">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="10c36-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="10c36-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10c36-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="10c36-114">See also</span></span>

- [<span data-ttu-id="10c36-115">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="10c36-115">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
