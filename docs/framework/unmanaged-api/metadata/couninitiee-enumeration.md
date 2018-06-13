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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: dcd7dc7c51caa94308760c0086384c8eea184ee9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33443597"
---
# <a name="couninitiee-enumeration"></a><span data-ttu-id="02ab4-102">Enumerazione COUNINITIEE</span><span class="sxs-lookup"><span data-stu-id="02ab4-102">COUNINITIEE Enumeration</span></span>
<span data-ttu-id="02ab4-103">Specifica le costanti usate da [CoUninitializeEE](../../../../docs/framework/unmanaged-api/hosting/couninitializeee-function.md) durante l'inizializzazione di common language runtime.</span><span class="sxs-lookup"><span data-stu-id="02ab4-103">Specifies constants used by [CoUninitializeEE](../../../../docs/framework/unmanaged-api/hosting/couninitializeee-function.md) when initializing the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02ab4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="02ab4-104">Syntax</span></span>  
  
```  
typedef enum tagCOUNINITEE  
{  
    COUNINITEE_DEFAULT  = 0x0,   
    COUNINITEE_DLL      = 0x1  
} COUNINITIEE;  
```  
  
## <a name="members"></a><span data-ttu-id="02ab4-105">Membri</span><span class="sxs-lookup"><span data-stu-id="02ab4-105">Members</span></span>  
  
|<span data-ttu-id="02ab4-106">Membro</span><span class="sxs-lookup"><span data-stu-id="02ab4-106">Member</span></span>|<span data-ttu-id="02ab4-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="02ab4-107">Description</span></span>|  
|------------|-----------------|  
|`COUNINITEE_DEFAULT`|<span data-ttu-id="02ab4-108">Indica la modalità di annullamento dell'inizializzazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="02ab4-108">Indicates default uninitialization mode.</span></span>|  
|`COUNINITEE_DLL`|<span data-ttu-id="02ab4-109">Indica la modalità di annullamento dell'inizializzazione per lo scaricamento di un assembly.</span><span class="sxs-lookup"><span data-stu-id="02ab4-109">Indicates uninitialization mode for unloading an assembly.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="02ab4-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="02ab4-110">Requirements</span></span>  
 <span data-ttu-id="02ab4-111">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="02ab4-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="02ab4-112">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="02ab4-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="02ab4-113">**Libreria:** inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="02ab4-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="02ab4-114">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="02ab4-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02ab4-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="02ab4-115">See Also</span></span>  
 [<span data-ttu-id="02ab4-116">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="02ab4-116">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
