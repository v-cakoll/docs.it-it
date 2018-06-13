---
title: Enumerazione CorPEKind
ms.date: 03/30/2017
api_name:
- CorPEKind
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorPEKind
helpviewer_keywords:
- CorPEKind enumeration [.NET Framework metadata]
ms.assetid: 22dc6dea-b1b9-4982-a730-a022d586b117
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b5869eb16bd768d58a6f27a83f2d8d51914a8aed
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33443115"
---
# <a name="corpekind-enumeration"></a><span data-ttu-id="f3c8a-102">Enumerazione CorPEKind</span><span class="sxs-lookup"><span data-stu-id="f3c8a-102">CorPEKind Enumeration</span></span>
<span data-ttu-id="f3c8a-103">Contiene valori che descrivono un file eseguibile portabile (PE), come restituito da una chiamata a [IMetaDataImport2:: GetPEKind](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getpekind-method.md).</span><span class="sxs-lookup"><span data-stu-id="f3c8a-103">Contains values that describe a portable executable (PE) file, as returned from a call to [IMetaDataImport2::GetPEKind](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getpekind-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3c8a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f3c8a-104">Syntax</span></span>  
  
```  
typedef enum CorPEKind {  
  
    peNot           = 0x00000000,  
    peILonly        = 0x00000001,  
    pe32BitRequired = 0x00000002,  
    pe32Plus        = 0x00000004,  
    pe32Unmanaged   = 0x00000008,  
    pe32BitPreferred= 0x00000010  
  
} CorPEKind;  
```  
  
## <a name="members"></a><span data-ttu-id="f3c8a-105">Membri</span><span class="sxs-lookup"><span data-stu-id="f3c8a-105">Members</span></span>  
  
|<span data-ttu-id="f3c8a-106">Membro</span><span class="sxs-lookup"><span data-stu-id="f3c8a-106">Member</span></span>|<span data-ttu-id="f3c8a-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f3c8a-107">Description</span></span>|  
|------------|-----------------|  
|`peNot`|<span data-ttu-id="f3c8a-108">Indica che questo non è un file PE.</span><span class="sxs-lookup"><span data-stu-id="f3c8a-108">Indicates that this is not a PE file.</span></span>|  
|`peILOnly`|<span data-ttu-id="f3c8a-109">Indica che il file PE contiene solo codice gestito.</span><span class="sxs-lookup"><span data-stu-id="f3c8a-109">Indicates that this PE file contains only managed code.</span></span>|  
|`pe32BitRequired`|<span data-ttu-id="f3c8a-110">Indica che il file PE effettua chiamate Win32.</span><span class="sxs-lookup"><span data-stu-id="f3c8a-110">Indicates that this PE file makes Win32 calls.</span></span>|  
|`pe32Plus`|<span data-ttu-id="f3c8a-111">Indica che il file PE viene eseguito su una piattaforma a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="f3c8a-111">Indicates that this PE file runs on a 64-bit platform.</span></span>|  
|`pe32Unmanaged`|<span data-ttu-id="f3c8a-112">Indica che il file PE è codice nativo.</span><span class="sxs-lookup"><span data-stu-id="f3c8a-112">Indicates that this PE file is native code.</span></span>|  
|<span data-ttu-id="f3c8a-113">pe32BitPreferred</span><span class="sxs-lookup"><span data-stu-id="f3c8a-113">pe32BitPreferred</span></span>|<span data-ttu-id="f3c8a-114">Indica che il file PE è indipendente dalla piattaforma e si preferisce essere caricati in un ambiente a 32 bit.</span><span class="sxs-lookup"><span data-stu-id="f3c8a-114">Indicates that this PE file is platform-neutral and prefers to be loaded in a 32-bit environment.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f3c8a-115">Note</span><span class="sxs-lookup"><span data-stu-id="f3c8a-115">Remarks</span></span>  
 <span data-ttu-id="f3c8a-116">Questi valori possono essere utilizzati in combinazioni bit per bit.</span><span class="sxs-lookup"><span data-stu-id="f3c8a-116">These values can be used in bitwise combinations.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f3c8a-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f3c8a-117">Requirements</span></span>  
 <span data-ttu-id="f3c8a-118">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f3c8a-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f3c8a-119">**Intestazione:** CorHdr. H</span><span class="sxs-lookup"><span data-stu-id="f3c8a-119">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="f3c8a-120">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f3c8a-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3c8a-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f3c8a-121">See Also</span></span>  
 [<span data-ttu-id="f3c8a-122">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="f3c8a-122">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
