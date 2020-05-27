---
title: Enumerazione CorNativeLinkFlags
ms.date: 03/30/2017
api_name:
- CorNativeLinkFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorNativeLinkFlags
helpviewer_keywords:
- CorNativeLinkFlags enumeration [.NET Framework metadata]
ms.assetid: 8027df7c-cfad-4724-bda0-7538d9519070
topic_type:
- apiref
ms.openlocfilehash: 9211af4726617598f3dd8772383cade6368e6c08
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007624"
---
# <a name="cornativelinkflags-enumeration"></a><span data-ttu-id="6d773-102">Enumerazione CorNativeLinkFlags</span><span class="sxs-lookup"><span data-stu-id="6d773-102">CorNativeLinkFlags Enumeration</span></span>
<span data-ttu-id="6d773-103">Fornisce valori di flag usati dal linker durante il collegamento del codice nativo.</span><span class="sxs-lookup"><span data-stu-id="6d773-103">Provides flag values used by the linker when linking native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d773-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6d773-104">Syntax</span></span>  
  
```cpp  
typedef enum  
{  
    nlfNone         = 0x00,  
    nlfLastError    = 0x01,  
    nlfNoMangle     = 0x02,  
    nlfMaxValue     = 0x03  
} CorNativeLinkFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="6d773-105">Membri</span><span class="sxs-lookup"><span data-stu-id="6d773-105">Members</span></span>  
  
|<span data-ttu-id="6d773-106">Membro</span><span class="sxs-lookup"><span data-stu-id="6d773-106">Member</span></span>|<span data-ttu-id="6d773-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6d773-107">Description</span></span>|  
|------------|-----------------|  
|`nlfNone`|<span data-ttu-id="6d773-108">Indica nessun flag.</span><span class="sxs-lookup"><span data-stu-id="6d773-108">Indicates no flags.</span></span>|  
|`nlfLastError`|<span data-ttu-id="6d773-109">Indica una `setLastError` parola chiave.</span><span class="sxs-lookup"><span data-stu-id="6d773-109">Indicates a `setLastError` keyword.</span></span>|  
|`nlfNoMangle`|<span data-ttu-id="6d773-110">Indica una `nomangle` parola chiave.</span><span class="sxs-lookup"><span data-stu-id="6d773-110">Indicates a `nomangle` keyword.</span></span>|  
|`nlfMaxValue`|<span data-ttu-id="6d773-111">Non usato.</span><span class="sxs-lookup"><span data-stu-id="6d773-111">Not used.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6d773-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6d773-112">Requirements</span></span>  
 <span data-ttu-id="6d773-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6d773-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6d773-114">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="6d773-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6d773-115">**Libreria:** Incluso come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="6d773-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6d773-116">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6d773-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d773-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6d773-117">See also</span></span>

- [<span data-ttu-id="6d773-118">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="6d773-118">Metadata Enumerations</span></span>](metadata-enumerations.md)
