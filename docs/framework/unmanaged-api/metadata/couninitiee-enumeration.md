---
title: Enumerazione COUNINITIEE
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COUNINITIEE
api_location: mscoree.dll
api_type: COM
f1_keywords: COUNINITIEE
helpviewer_keywords: COUNINITIEE enumeration [.NET Framework metadata]
ms.assetid: c42baa79-f469-4330-95a2-baf7f021c2fc
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c849a32850b5fc9aaca7ea75fdfb30db3de5d8c9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="couninitiee-enumeration"></a><span data-ttu-id="68f42-102">Enumerazione COUNINITIEE</span><span class="sxs-lookup"><span data-stu-id="68f42-102">COUNINITIEE Enumeration</span></span>
<span data-ttu-id="68f42-103">Specifica le costanti usate da [CoUninitializeEE](../../../../docs/framework/unmanaged-api/hosting/couninitializeee-function.md) durante l'inizializzazione di common language runtime.</span><span class="sxs-lookup"><span data-stu-id="68f42-103">Specifies constants used by [CoUninitializeEE](../../../../docs/framework/unmanaged-api/hosting/couninitializeee-function.md) when initializing the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="68f42-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="68f42-104">Syntax</span></span>  
  
```  
typedef enum tagCOUNINITEE  
{  
    COUNINITEE_DEFAULT  = 0x0,   
    COUNINITEE_DLL      = 0x1  
} COUNINITIEE;  
```  
  
## <a name="members"></a><span data-ttu-id="68f42-105">Membri</span><span class="sxs-lookup"><span data-stu-id="68f42-105">Members</span></span>  
  
|<span data-ttu-id="68f42-106">Membro</span><span class="sxs-lookup"><span data-stu-id="68f42-106">Member</span></span>|<span data-ttu-id="68f42-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="68f42-107">Description</span></span>|  
|------------|-----------------|  
|`COUNINITEE_DEFAULT`|<span data-ttu-id="68f42-108">Indica la modalità di annullamento dell'inizializzazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="68f42-108">Indicates default uninitialization mode.</span></span>|  
|`COUNINITEE_DLL`|<span data-ttu-id="68f42-109">Indica la modalità di annullamento dell'inizializzazione per lo scaricamento di un assembly.</span><span class="sxs-lookup"><span data-stu-id="68f42-109">Indicates uninitialization mode for unloading an assembly.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="68f42-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="68f42-110">Requirements</span></span>  
 <span data-ttu-id="68f42-111">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="68f42-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="68f42-112">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="68f42-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="68f42-113">**Libreria:** inclusa come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="68f42-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="68f42-114">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="68f42-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68f42-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="68f42-115">See Also</span></span>  
 [<span data-ttu-id="68f42-116">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="68f42-116">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
