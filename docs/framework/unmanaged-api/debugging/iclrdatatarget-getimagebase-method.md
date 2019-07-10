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
ms.openlocfilehash: 9dbb655d6ed0b9bd88c5eedf61a191401a805fb3
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67738761"
---
# <a name="iclrdatatargetgetimagebase-method"></a><span data-ttu-id="2652b-102">Metodo ICLRDataTarget::GetImageBase</span><span class="sxs-lookup"><span data-stu-id="2652b-102">ICLRDataTarget::GetImageBase Method</span></span>
<span data-ttu-id="2652b-103">Ottiene l'indirizzo di memoria di base dell'immagine specificata.</span><span class="sxs-lookup"><span data-stu-id="2652b-103">Gets the base memory address of the specified image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2652b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2652b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetImageBase (  
    [in, string] LPCWSTR    imagePath,  
    [out] CLRDATA_ADDRESS   *baseAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2652b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="2652b-105">Parameters</span></span>  
 `imagePath`  
 <span data-ttu-id="2652b-106">[in] Nome file dell'immagine, incluso il relativo percorso.</span><span class="sxs-lookup"><span data-stu-id="2652b-106">[in] The file name of the image, including its path.</span></span>  
  
 `baseAddress`  
 <span data-ttu-id="2652b-107">[out] Un puntatore a un oggetto CLRDATA_ADDRESS che archivia l'indirizzo di base dell'immagine.</span><span class="sxs-lookup"><span data-stu-id="2652b-107">[out] A pointer to a CLRDATA_ADDRESS that stores the base address of the image.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2652b-108">Note</span><span class="sxs-lookup"><span data-stu-id="2652b-108">Remarks</span></span>  
 <span data-ttu-id="2652b-109">Il nome del file immagine potrebbe o non abbia un percorso.</span><span class="sxs-lookup"><span data-stu-id="2652b-109">The image file name may or may not have a path.</span></span> <span data-ttu-id="2652b-110">Se viene specificato un percorso, ciò avviene nel percorso di intero. corrispondenza in caso contrario, viene eseguita solo sul nome del file.</span><span class="sxs-lookup"><span data-stu-id="2652b-110">If a path is specified, matching is done on the whole path; otherwise, matching is done only on the file name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2652b-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2652b-111">Requirements</span></span>  
 <span data-ttu-id="2652b-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2652b-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2652b-113">**Intestazione:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="2652b-113">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="2652b-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2652b-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2652b-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2652b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2652b-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2652b-116">See also</span></span>

- [<span data-ttu-id="2652b-117">Interfaccia ICLRDataTarget</span><span class="sxs-lookup"><span data-stu-id="2652b-117">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
