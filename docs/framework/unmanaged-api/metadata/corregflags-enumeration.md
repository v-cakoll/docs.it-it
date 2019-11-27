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
ms.openlocfilehash: 79a9e4513a98a29edc11cc76c599f03c9c3a72b4
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450108"
---
# <a name="corregflags-enumeration"></a><span data-ttu-id="aa5db-102">Enumerazione CorRegFlags</span><span class="sxs-lookup"><span data-stu-id="aa5db-102">CorRegFlags Enumeration</span></span>
<span data-ttu-id="aa5db-103">Fornisce valori di flag usati per la registrazione durante l'installazione di un modulo o un'immagine composita.</span><span class="sxs-lookup"><span data-stu-id="aa5db-103">Provides flag values used for registration when installing a module or composite image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa5db-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="aa5db-104">Syntax</span></span>  
  
```cpp  
typedef enum   
{  
    regNoCopy  = 0x00000001,  
    regConfig  = 0x00000002,  
    regHasRefs = 0x00000004  
} CorRegFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="aa5db-105">Members</span><span class="sxs-lookup"><span data-stu-id="aa5db-105">Members</span></span>  
  
|<span data-ttu-id="aa5db-106">Membro</span><span class="sxs-lookup"><span data-stu-id="aa5db-106">Member</span></span>|<span data-ttu-id="aa5db-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="aa5db-107">Description</span></span>|  
|------------|-----------------|  
|`regNoCopy`|<span data-ttu-id="aa5db-108">Specifica che i file non devono essere copiati nella destinazione.</span><span class="sxs-lookup"><span data-stu-id="aa5db-108">Specifies that files should not be copied into the destination.</span></span>|  
|`regConfig`|<span data-ttu-id="aa5db-109">Specifica che il modulo o composito è una configurazione.</span><span class="sxs-lookup"><span data-stu-id="aa5db-109">Specifies that the module or composite is a configuration.</span></span>|  
|`regHasRefs`|<span data-ttu-id="aa5db-110">Specifica che il modulo o composito contiene riferimenti a classi.</span><span class="sxs-lookup"><span data-stu-id="aa5db-110">Specifies that the module or composite has class references.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="aa5db-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="aa5db-111">Requirements</span></span>  
 <span data-ttu-id="aa5db-112">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aa5db-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aa5db-113">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="aa5db-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="aa5db-114">**Libreria:** Incluso come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="aa5db-114">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="aa5db-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aa5db-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa5db-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aa5db-116">See also</span></span>

- [<span data-ttu-id="aa5db-117">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="aa5db-117">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
