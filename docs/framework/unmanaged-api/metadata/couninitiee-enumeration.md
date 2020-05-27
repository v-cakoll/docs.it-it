---
title: Enumerazione COUNINITIEE
ms.date: 03/30/2017
api_name:
- COUNINITIEE
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COUNINITIEE
helpviewer_keywords:
- COUNINITIEE enumeration [.NET Framework metadata]
ms.assetid: c42baa79-f469-4330-95a2-baf7f021c2fc
topic_type:
- apiref
ms.openlocfilehash: 14942680a79c4d1fcc69092a4f752738db1fb0b0
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008917"
---
# <a name="couninitiee-enumeration"></a><span data-ttu-id="174f9-102">Enumerazione COUNINITIEE</span><span class="sxs-lookup"><span data-stu-id="174f9-102">COUNINITIEE Enumeration</span></span>
<span data-ttu-id="174f9-103">Specifica le costanti usate da [CoUninitializeEE](../hosting/couninitializeee-function.md) durante l'inizializzazione del Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="174f9-103">Specifies constants used by [CoUninitializeEE](../hosting/couninitializeee-function.md) when initializing the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="174f9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="174f9-104">Syntax</span></span>  
  
```cpp  
typedef enum tagCOUNINITEE  
{  
    COUNINITEE_DEFAULT  = 0x0,
    COUNINITEE_DLL      = 0x1  
} COUNINITIEE;  
```  
  
## <a name="members"></a><span data-ttu-id="174f9-105">Membri</span><span class="sxs-lookup"><span data-stu-id="174f9-105">Members</span></span>  
  
|<span data-ttu-id="174f9-106">Membro</span><span class="sxs-lookup"><span data-stu-id="174f9-106">Member</span></span>|<span data-ttu-id="174f9-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="174f9-107">Description</span></span>|  
|------------|-----------------|  
|`COUNINITEE_DEFAULT`|<span data-ttu-id="174f9-108">Indica la modalità di inizializzazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="174f9-108">Indicates default uninitialization mode.</span></span>|  
|`COUNINITEE_DLL`|<span data-ttu-id="174f9-109">Indica la modalità di non inizializzazione per lo scaricamento di un assembly.</span><span class="sxs-lookup"><span data-stu-id="174f9-109">Indicates uninitialization mode for unloading an assembly.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="174f9-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="174f9-110">Requirements</span></span>  
 <span data-ttu-id="174f9-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="174f9-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="174f9-112">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="174f9-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="174f9-113">**Libreria:** Incluso come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="174f9-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="174f9-114">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="174f9-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="174f9-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="174f9-115">See also</span></span>

- [<span data-ttu-id="174f9-116">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="174f9-116">Metadata Enumerations</span></span>](metadata-enumerations.md)
