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
ms.openlocfilehash: fe5ffbab93df7168015e2a31d6e32ec45dce0960
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007689"
---
# <a name="corlinkeroptions-enumeration"></a><span data-ttu-id="3fe64-102">Enumerazione CorLinkerOptions</span><span class="sxs-lookup"><span data-stu-id="3fe64-102">CorLinkerOptions Enumeration</span></span>
<span data-ttu-id="3fe64-103">Specifica i flag per selezionare le opzioni per il linker dei metadati.</span><span class="sxs-lookup"><span data-stu-id="3fe64-103">Specifies flags to select options for the metadata linker.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3fe64-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3fe64-104">Syntax</span></span>  
  
```cpp  
typedef enum CorLinkerOptions {  
    MDAssembly          = 0x00000000,  
    MDNetModule         = 0x00000001,  
} CorLinkerOptions;  
```  
  
## <a name="members"></a><span data-ttu-id="3fe64-105">Membri</span><span class="sxs-lookup"><span data-stu-id="3fe64-105">Members</span></span>  
  
|<span data-ttu-id="3fe64-106">Membro</span><span class="sxs-lookup"><span data-stu-id="3fe64-106">Member</span></span>|<span data-ttu-id="3fe64-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3fe64-107">Description</span></span>|  
|------------|-----------------|  
|`MDAssembly`|<span data-ttu-id="3fe64-108">I tipi privati e le funzioni globali non vengono mantenuti.</span><span class="sxs-lookup"><span data-stu-id="3fe64-108">The private types and global functions are not preserved.</span></span>|  
|`MDNetModule`|<span data-ttu-id="3fe64-109">I tipi privati e le funzioni globali vengono mantenuti.</span><span class="sxs-lookup"><span data-stu-id="3fe64-109">The private types and global functions are preserved.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3fe64-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3fe64-110">Requirements</span></span>  
 <span data-ttu-id="3fe64-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3fe64-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3fe64-112">**Intestazione:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="3fe64-112">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="3fe64-113">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3fe64-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3fe64-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3fe64-114">See also</span></span>

- [<span data-ttu-id="3fe64-115">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="3fe64-115">Metadata Enumerations</span></span>](metadata-enumerations.md)
