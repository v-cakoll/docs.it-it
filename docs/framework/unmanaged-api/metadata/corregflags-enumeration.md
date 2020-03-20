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
ms.openlocfilehash: 8fe6216e11a64ea182d796247d888b862b1e8377
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177932"
---
# <a name="corregflags-enumeration"></a><span data-ttu-id="2af04-102">Enumerazione CorRegFlags</span><span class="sxs-lookup"><span data-stu-id="2af04-102">CorRegFlags Enumeration</span></span>
<span data-ttu-id="2af04-103">Fornisce i valori di flag utilizzati per la registrazione durante l'installazione di un modulo o di un'immagine composita.</span><span class="sxs-lookup"><span data-stu-id="2af04-103">Provides flag values used for registration when installing a module or composite image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2af04-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2af04-104">Syntax</span></span>  
  
```cpp  
typedef enum
{  
    regNoCopy  = 0x00000001,  
    regConfig  = 0x00000002,  
    regHasRefs = 0x00000004  
} CorRegFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="2af04-105">Members</span><span class="sxs-lookup"><span data-stu-id="2af04-105">Members</span></span>  
  
|<span data-ttu-id="2af04-106">Membro</span><span class="sxs-lookup"><span data-stu-id="2af04-106">Member</span></span>|<span data-ttu-id="2af04-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2af04-107">Description</span></span>|  
|------------|-----------------|  
|`regNoCopy`|<span data-ttu-id="2af04-108">Specifica che i file non devono essere copiati nella destinazione.</span><span class="sxs-lookup"><span data-stu-id="2af04-108">Specifies that files should not be copied into the destination.</span></span>|  
|`regConfig`|<span data-ttu-id="2af04-109">Specifica che il modulo o il composito è una configurazione.</span><span class="sxs-lookup"><span data-stu-id="2af04-109">Specifies that the module or composite is a configuration.</span></span>|  
|`regHasRefs`|<span data-ttu-id="2af04-110">Specifica che il modulo o il composito dispone di riferimenti di classe.</span><span class="sxs-lookup"><span data-stu-id="2af04-110">Specifies that the module or composite has class references.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2af04-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2af04-111">Requirements</span></span>  
 <span data-ttu-id="2af04-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2af04-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2af04-113">**Intestazione:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="2af04-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2af04-114">**Biblioteca:** Incluso come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2af04-114">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2af04-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2af04-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2af04-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2af04-116">See also</span></span>

- [<span data-ttu-id="2af04-117">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="2af04-117">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
