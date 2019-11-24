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
ms.openlocfilehash: 086e17185df9caa823b44b51cf027f95d635c48d
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450267"
---
# <a name="corlinkeroptions-enumeration"></a><span data-ttu-id="a60c3-102">Enumerazione CorLinkerOptions</span><span class="sxs-lookup"><span data-stu-id="a60c3-102">CorLinkerOptions Enumeration</span></span>
<span data-ttu-id="a60c3-103">Specifica i flag per selezionare le opzioni per il linker dei metadati.</span><span class="sxs-lookup"><span data-stu-id="a60c3-103">Specifies flags to select options for the metadata linker.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a60c3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a60c3-104">Syntax</span></span>  
  
```cpp  
typedef enum CorLinkerOptions {  
    MDAssembly          = 0x00000000,  
    MDNetModule         = 0x00000001,  
} CorLinkerOptions;  
```  
  
## <a name="members"></a><span data-ttu-id="a60c3-105">Members</span><span class="sxs-lookup"><span data-stu-id="a60c3-105">Members</span></span>  
  
|<span data-ttu-id="a60c3-106">Member</span><span class="sxs-lookup"><span data-stu-id="a60c3-106">Member</span></span>|<span data-ttu-id="a60c3-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a60c3-107">Description</span></span>|  
|------------|-----------------|  
|`MDAssembly`|<span data-ttu-id="a60c3-108">The private types and global functions are not preserved.</span><span class="sxs-lookup"><span data-stu-id="a60c3-108">The private types and global functions are not preserved.</span></span>|  
|`MDNetModule`|<span data-ttu-id="a60c3-109">The private types and global functions are preserved.</span><span class="sxs-lookup"><span data-stu-id="a60c3-109">The private types and global functions are preserved.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a60c3-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a60c3-110">Requirements</span></span>  
 <span data-ttu-id="a60c3-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a60c3-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a60c3-112">**Header:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="a60c3-112">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="a60c3-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a60c3-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a60c3-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a60c3-114">See also</span></span>

- [<span data-ttu-id="a60c3-115">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="a60c3-115">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
