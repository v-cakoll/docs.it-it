---
title: Enumerazione CorThreadSafetyOptions
ms.date: 03/30/2017
api_name:
- CorThreadSafetyOptions
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorThreadSafetyOptions
helpviewer_keywords:
- CorThreadSafetyOptions enumeration [.NET Framework metadata]
ms.assetid: dae07d9b-df51-488c-b17e-52d6e48217bd
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3407fcac420b8129dd39eabf84aec84b58651944
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33442840"
---
# <a name="corthreadsafetyoptions-enumeration"></a><span data-ttu-id="38a37-102">Enumerazione CorThreadSafetyOptions</span><span class="sxs-lookup"><span data-stu-id="38a37-102">CorThreadSafetyOptions Enumeration</span></span>
<span data-ttu-id="38a37-103">Specifica i flag per selezionare le opzioni per la thread safety.</span><span class="sxs-lookup"><span data-stu-id="38a37-103">Specifies flags to select options for thread safety.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38a37-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="38a37-104">Syntax</span></span>  
  
```  
typedef enum CorThreadSafetyOptions {  
    MDThreadSafetyDefault       = 0x00000000,  
    MDThreadSafetyOff           = 0x00000000,  
    MDThreadSafetyOn            = 0x00000001,  
} CorThreadSafetyOptions;  
```  
  
## <a name="members"></a><span data-ttu-id="38a37-105">Membri</span><span class="sxs-lookup"><span data-stu-id="38a37-105">Members</span></span>  
  
|<span data-ttu-id="38a37-106">Membro</span><span class="sxs-lookup"><span data-stu-id="38a37-106">Member</span></span>|<span data-ttu-id="38a37-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="38a37-107">Description</span></span>|  
|------------|-----------------|  
|`MDThreadSatetyDefault`|<span data-ttu-id="38a37-108">Valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="38a37-108">Default value.</span></span> <span data-ttu-id="38a37-109">Uguale a `MDThreadSatetyOff`.</span><span class="sxs-lookup"><span data-stu-id="38a37-109">Same as `MDThreadSatetyOff`.</span></span>|  
|`MDThreadSatetyOff`|<span data-ttu-id="38a37-110">Indica che non può essere impostato un blocco di lettura/scrittura.</span><span class="sxs-lookup"><span data-stu-id="38a37-110">Indicates that a reader/writer lock cannot be set.</span></span>|  
|`MDThreadSatetyOn`|<span data-ttu-id="38a37-111">Indica che è possibile impostare un blocco di lettura/scrittura.</span><span class="sxs-lookup"><span data-stu-id="38a37-111">Indicates that a reader/writer lock can be set.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="38a37-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="38a37-112">Requirements</span></span>  
 <span data-ttu-id="38a37-113">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="38a37-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="38a37-114">**Intestazione:** CorHdr. H</span><span class="sxs-lookup"><span data-stu-id="38a37-114">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="38a37-115">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="38a37-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38a37-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="38a37-116">See Also</span></span>  
 [<span data-ttu-id="38a37-117">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="38a37-117">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
