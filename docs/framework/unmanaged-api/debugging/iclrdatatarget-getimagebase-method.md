---
title: Metodo ICLRDataTarget::GetImageBase
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDataTarget.GetImageBase
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICLRDataTarget::GetImageBase
helpviewer_keywords:
- ICLRDataTarget::GetImageBase method [.NET Framework debugging]
- GetImageBase method [.NET Framework debugging]
ms.assetid: 091c5f32-c160-49e3-a75f-4692e084c8e4
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 504c3ce7115cbab11d0510eaa2ebb0fdd9f1888b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="iclrdatatargetgetimagebase-method"></a><span data-ttu-id="daf64-102">Metodo ICLRDataTarget::GetImageBase</span><span class="sxs-lookup"><span data-stu-id="daf64-102">ICLRDataTarget::GetImageBase Method</span></span>
<span data-ttu-id="daf64-103">Ottiene l'indirizzo di memoria di base dell'immagine specificata.</span><span class="sxs-lookup"><span data-stu-id="daf64-103">Gets the base memory address of the specified image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="daf64-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="daf64-104">Syntax</span></span>  
  
```  
HRESULT GetImageBase (  
    [in, string] LPCWSTR    imagePath,  
    [out] CLRDATA_ADDRESS   *baseAddress  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="daf64-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="daf64-105">Parameters</span></span>  
 `imagePath`  
 <span data-ttu-id="daf64-106">[in] Il nome file dell'immagine, inclusi il relativo percorso.</span><span class="sxs-lookup"><span data-stu-id="daf64-106">[in] The file name of the image, including its path.</span></span>  
  
 `baseAddress`  
 <span data-ttu-id="daf64-107">[out] Un puntatore a un oggetto CLRDATA_ADDRESS che archivia l'indirizzo di base dell'immagine.</span><span class="sxs-lookup"><span data-stu-id="daf64-107">[out] A pointer to a CLRDATA_ADDRESS that stores the base address of the image.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="daf64-108">Note</span><span class="sxs-lookup"><span data-stu-id="daf64-108">Remarks</span></span>  
 <span data-ttu-id="daf64-109">Il nome di file immagine o potrebbe non disporre di un percorso.</span><span class="sxs-lookup"><span data-stu-id="daf64-109">The image file name may or may not have a path.</span></span> <span data-ttu-id="daf64-110">Se viene specificato un percorso, ciò avviene nel percorso di intero. in caso contrario, ciò avviene solo sul nome del file.</span><span class="sxs-lookup"><span data-stu-id="daf64-110">If a path is specified, matching is done on the whole path; otherwise, matching is done only on the file name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="daf64-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="daf64-111">Requirements</span></span>  
 <span data-ttu-id="daf64-112">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="daf64-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="daf64-113">**Intestazione:** ClrData.idl, Clrdata. H</span><span class="sxs-lookup"><span data-stu-id="daf64-113">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="daf64-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="daf64-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="daf64-115">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="daf64-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="daf64-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="daf64-116">See Also</span></span>  
 [<span data-ttu-id="daf64-117">Interfaccia ICLRDataTarget</span><span class="sxs-lookup"><span data-stu-id="daf64-117">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
