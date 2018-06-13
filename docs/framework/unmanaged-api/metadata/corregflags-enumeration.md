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
ms.openlocfilehash: f7b935b8f59e434c9da364be1986dbed654a1efd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33445809"
---
# <a name="corregflags-enumeration"></a><span data-ttu-id="fb062-102">Enumerazione CorRegFlags</span><span class="sxs-lookup"><span data-stu-id="fb062-102">CorRegFlags Enumeration</span></span>
<span data-ttu-id="fb062-103">Fornisce valori di flag usati per la registrazione quando si installa un modulo o immagine composita.</span><span class="sxs-lookup"><span data-stu-id="fb062-103">Provides flag values used for registration when installing a module or composite image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb062-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fb062-104">Syntax</span></span>  
  
```  
typedef enum   
{  
    regNoCopy  = 0x00000001,  
    regConfig  = 0x00000002,  
    regHasRefs = 0x00000004  
} CorRegFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="fb062-105">Membri</span><span class="sxs-lookup"><span data-stu-id="fb062-105">Members</span></span>  
  
|<span data-ttu-id="fb062-106">Membro</span><span class="sxs-lookup"><span data-stu-id="fb062-106">Member</span></span>|<span data-ttu-id="fb062-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fb062-107">Description</span></span>|  
|------------|-----------------|  
|`regNoCopy`|<span data-ttu-id="fb062-108">Specifica che i file non devono essere copiati nella destinazione.</span><span class="sxs-lookup"><span data-stu-id="fb062-108">Specifies that files should not be copied into the destination.</span></span>|  
|`regConfig`|<span data-ttu-id="fb062-109">Specifica che il modulo o composita è una configurazione.</span><span class="sxs-lookup"><span data-stu-id="fb062-109">Specifies that the module or composite is a configuration.</span></span>|  
|`regHasRefs`|<span data-ttu-id="fb062-110">Specifica che il modulo o l'insieme dispone di riferimenti alla classe.</span><span class="sxs-lookup"><span data-stu-id="fb062-110">Specifies that the module or composite has class references.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="fb062-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fb062-111">Requirements</span></span>  
 <span data-ttu-id="fb062-112">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fb062-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fb062-113">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="fb062-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fb062-114">**Libreria:** inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="fb062-114">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="fb062-115">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fb062-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb062-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fb062-116">See Also</span></span>  
 [<span data-ttu-id="fb062-117">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="fb062-117">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
