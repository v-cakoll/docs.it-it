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
ms.openlocfilehash: 0d154985e9c1614e6b8f13a55410ead0cb5e861b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33441055"
---
# <a name="corlinkeroptions-enumeration"></a><span data-ttu-id="1c5bf-102">Enumerazione CorLinkerOptions</span><span class="sxs-lookup"><span data-stu-id="1c5bf-102">CorLinkerOptions Enumeration</span></span>
<span data-ttu-id="1c5bf-103">Specifica i flag per selezionare le opzioni per il linker dei metadati.</span><span class="sxs-lookup"><span data-stu-id="1c5bf-103">Specifies flags to select options for the metadata linker.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c5bf-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1c5bf-104">Syntax</span></span>  
  
```  
typedef enum CorLinkerOptions {  
    MDAssembly          = 0x00000000,  
    MDNetModule         = 0x00000001,  
} CorLinkerOptions;  
```  
  
## <a name="members"></a><span data-ttu-id="1c5bf-105">Membri</span><span class="sxs-lookup"><span data-stu-id="1c5bf-105">Members</span></span>  
  
|<span data-ttu-id="1c5bf-106">Membro</span><span class="sxs-lookup"><span data-stu-id="1c5bf-106">Member</span></span>|<span data-ttu-id="1c5bf-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1c5bf-107">Description</span></span>|  
|------------|-----------------|  
|`MDAssembly`|<span data-ttu-id="1c5bf-108">Le funzioni globali e i tipi privati non vengono mantenute.</span><span class="sxs-lookup"><span data-stu-id="1c5bf-108">The private types and global functions are not preserved.</span></span>|  
|`MDNetModule`|<span data-ttu-id="1c5bf-109">I tipi privati e funzioni globali vengono mantenute.</span><span class="sxs-lookup"><span data-stu-id="1c5bf-109">The private types and global functions are preserved.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1c5bf-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1c5bf-110">Requirements</span></span>  
 <span data-ttu-id="1c5bf-111">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1c5bf-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1c5bf-112">**Intestazione:** CorHdr. H</span><span class="sxs-lookup"><span data-stu-id="1c5bf-112">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="1c5bf-113">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1c5bf-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c5bf-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1c5bf-114">See Also</span></span>  
 [<span data-ttu-id="1c5bf-115">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="1c5bf-115">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
