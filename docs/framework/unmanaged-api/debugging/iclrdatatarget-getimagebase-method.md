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
ms.openlocfilehash: 1d397995266d6063164510a4b563ba94f7f54950
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="iclrdatatargetgetimagebase-method"></a><span data-ttu-id="f1f5d-102">Metodo ICLRDataTarget::GetImageBase</span><span class="sxs-lookup"><span data-stu-id="f1f5d-102">ICLRDataTarget::GetImageBase Method</span></span>
<span data-ttu-id="f1f5d-103">Ottiene l'indirizzo di memoria di base dell'immagine specificata.</span><span class="sxs-lookup"><span data-stu-id="f1f5d-103">Gets the base memory address of the specified image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1f5d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f1f5d-104">Syntax</span></span>  
  
```  
HRESULT GetImageBase (  
    [in, string] LPCWSTR    imagePath,  
    [out] CLRDATA_ADDRESS   *baseAddress  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f1f5d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f1f5d-105">Parameters</span></span>  
 `imagePath`  
 <span data-ttu-id="f1f5d-106">[in] Il nome file dell'immagine, inclusi il relativo percorso.</span><span class="sxs-lookup"><span data-stu-id="f1f5d-106">[in] The file name of the image, including its path.</span></span>  
  
 `baseAddress`  
 <span data-ttu-id="f1f5d-107">[out] Un puntatore a un oggetto CLRDATA_ADDRESS che archivia l'indirizzo di base dell'immagine.</span><span class="sxs-lookup"><span data-stu-id="f1f5d-107">[out] A pointer to a CLRDATA_ADDRESS that stores the base address of the image.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f1f5d-108">Note</span><span class="sxs-lookup"><span data-stu-id="f1f5d-108">Remarks</span></span>  
 <span data-ttu-id="f1f5d-109">Il nome di file immagine o potrebbe non disporre di un percorso.</span><span class="sxs-lookup"><span data-stu-id="f1f5d-109">The image file name may or may not have a path.</span></span> <span data-ttu-id="f1f5d-110">Se viene specificato un percorso, ciò avviene nel percorso di intero. in caso contrario, ciò avviene solo sul nome del file.</span><span class="sxs-lookup"><span data-stu-id="f1f5d-110">If a path is specified, matching is done on the whole path; otherwise, matching is done only on the file name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f1f5d-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f1f5d-111">Requirements</span></span>  
 <span data-ttu-id="f1f5d-112">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f1f5d-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f1f5d-113">**Intestazione:** ClrData.idl, Clrdata. H</span><span class="sxs-lookup"><span data-stu-id="f1f5d-113">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="f1f5d-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f1f5d-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f1f5d-115">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f1f5d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1f5d-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f1f5d-116">See Also</span></span>  
 [<span data-ttu-id="f1f5d-117">ICLRDataTarget (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="f1f5d-117">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
