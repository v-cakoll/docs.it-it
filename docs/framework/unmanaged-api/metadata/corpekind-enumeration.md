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
ms.openlocfilehash: 8b6eab8156f72847eb6dd3369950f9b46a3fc877
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007559"
---
# <a name="corpekind-enumeration"></a><span data-ttu-id="249c8-102">Enumerazione CorPEKind</span><span class="sxs-lookup"><span data-stu-id="249c8-102">CorPEKind Enumeration</span></span>
<span data-ttu-id="249c8-103">Contiene valori che descrivono un file eseguibile portabile (PE), come restituito da una chiamata a [IMetaDataImport2:: GetPEKind](imetadataimport2-getpekind-method.md).</span><span class="sxs-lookup"><span data-stu-id="249c8-103">Contains values that describe a portable executable (PE) file, as returned from a call to [IMetaDataImport2::GetPEKind](imetadataimport2-getpekind-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="249c8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="249c8-104">Syntax</span></span>  
  
```cpp  
typedef enum CorPEKind {  
  
    peNot           = 0x00000000,  
    peILonly        = 0x00000001,  
    pe32BitRequired = 0x00000002,  
    pe32Plus        = 0x00000004,  
    pe32Unmanaged   = 0x00000008,  
    pe32BitPreferred= 0x00000010  
  
} CorPEKind;  
```  
  
## <a name="members"></a><span data-ttu-id="249c8-105">Membri</span><span class="sxs-lookup"><span data-stu-id="249c8-105">Members</span></span>  
  
|<span data-ttu-id="249c8-106">Membro</span><span class="sxs-lookup"><span data-stu-id="249c8-106">Member</span></span>|<span data-ttu-id="249c8-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="249c8-107">Description</span></span>|  
|------------|-----------------|  
|`peNot`|<span data-ttu-id="249c8-108">Indica che non si tratta di un file PE.</span><span class="sxs-lookup"><span data-stu-id="249c8-108">Indicates that this is not a PE file.</span></span>|  
|`peILOnly`|<span data-ttu-id="249c8-109">Indica che il file PE contiene solo codice gestito.</span><span class="sxs-lookup"><span data-stu-id="249c8-109">Indicates that this PE file contains only managed code.</span></span>|  
|`pe32BitRequired`|<span data-ttu-id="249c8-110">Indica che il file PE esegue chiamate Win32.</span><span class="sxs-lookup"><span data-stu-id="249c8-110">Indicates that this PE file makes Win32 calls.</span></span>|  
|`pe32Plus`|<span data-ttu-id="249c8-111">Indica che il file PE viene eseguito su una piattaforma a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="249c8-111">Indicates that this PE file runs on a 64-bit platform.</span></span>|  
|`pe32Unmanaged`|<span data-ttu-id="249c8-112">Indica che il file PE è codice nativo.</span><span class="sxs-lookup"><span data-stu-id="249c8-112">Indicates that this PE file is native code.</span></span>|  
|<span data-ttu-id="249c8-113">pe32BitPreferred</span><span class="sxs-lookup"><span data-stu-id="249c8-113">pe32BitPreferred</span></span>|<span data-ttu-id="249c8-114">Indica che il file PE è indipendente dalla piattaforma e preferisce essere caricato in un ambiente a 32 bit.</span><span class="sxs-lookup"><span data-stu-id="249c8-114">Indicates that this PE file is platform-neutral and prefers to be loaded in a 32-bit environment.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="249c8-115">Commenti</span><span class="sxs-lookup"><span data-stu-id="249c8-115">Remarks</span></span>  
 <span data-ttu-id="249c8-116">Questi valori possono essere utilizzati in combinazioni bit per bit.</span><span class="sxs-lookup"><span data-stu-id="249c8-116">These values can be used in bitwise combinations.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="249c8-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="249c8-117">Requirements</span></span>  
 <span data-ttu-id="249c8-118">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="249c8-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="249c8-119">**Intestazione:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="249c8-119">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="249c8-120">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="249c8-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="249c8-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="249c8-121">See also</span></span>

- [<span data-ttu-id="249c8-122">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="249c8-122">Metadata Enumerations</span></span>](metadata-enumerations.md)
