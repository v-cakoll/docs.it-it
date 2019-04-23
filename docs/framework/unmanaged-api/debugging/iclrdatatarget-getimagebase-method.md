---
title: Metodo ICLRDataTarget::GetImageBase
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.GetImageBase
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::GetImageBase
helpviewer_keywords:
- ICLRDataTarget::GetImageBase method [.NET Framework debugging]
- GetImageBase method [.NET Framework debugging]
ms.assetid: 091c5f32-c160-49e3-a75f-4692e084c8e4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e823911280f52e16c745c9c77fe17b49bd35dc0b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59129831"
---
# <a name="iclrdatatargetgetimagebase-method"></a><span data-ttu-id="a6dec-102">Metodo ICLRDataTarget::GetImageBase</span><span class="sxs-lookup"><span data-stu-id="a6dec-102">ICLRDataTarget::GetImageBase Method</span></span>
<span data-ttu-id="a6dec-103">Ottiene l'indirizzo di memoria di base dell'immagine specificata.</span><span class="sxs-lookup"><span data-stu-id="a6dec-103">Gets the base memory address of the specified image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6dec-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a6dec-104">Syntax</span></span>  
  
```  
HRESULT GetImageBase (  
    [in, string] LPCWSTR    imagePath,  
    [out] CLRDATA_ADDRESS   *baseAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a6dec-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a6dec-105">Parameters</span></span>  
 `imagePath`  
 <span data-ttu-id="a6dec-106">[in] Nome file dell'immagine, incluso il relativo percorso.</span><span class="sxs-lookup"><span data-stu-id="a6dec-106">[in] The file name of the image, including its path.</span></span>  
  
 `baseAddress`  
 <span data-ttu-id="a6dec-107">[out] Un puntatore a un oggetto CLRDATA_ADDRESS che archivia l'indirizzo di base dell'immagine.</span><span class="sxs-lookup"><span data-stu-id="a6dec-107">[out] A pointer to a CLRDATA_ADDRESS that stores the base address of the image.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a6dec-108">Note</span><span class="sxs-lookup"><span data-stu-id="a6dec-108">Remarks</span></span>  
 <span data-ttu-id="a6dec-109">Il nome del file immagine potrebbe o non abbia un percorso.</span><span class="sxs-lookup"><span data-stu-id="a6dec-109">The image file name may or may not have a path.</span></span> <span data-ttu-id="a6dec-110">Se viene specificato un percorso, ciò avviene nel percorso di intero. corrispondenza in caso contrario, viene eseguita solo sul nome del file.</span><span class="sxs-lookup"><span data-stu-id="a6dec-110">If a path is specified, matching is done on the whole path; otherwise, matching is done only on the file name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a6dec-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a6dec-111">Requirements</span></span>  
 <span data-ttu-id="a6dec-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a6dec-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a6dec-113">**Intestazione:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="a6dec-113">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="a6dec-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a6dec-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a6dec-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a6dec-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6dec-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a6dec-116">See also</span></span>

- [<span data-ttu-id="a6dec-117">Interfaccia ICLRDataTarget</span><span class="sxs-lookup"><span data-stu-id="a6dec-117">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
