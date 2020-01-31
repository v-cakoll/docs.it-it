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
ms.openlocfilehash: fcf0ab73c79a5fa116a89cdfcc2e73b17d9eabfc
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76785489"
---
# <a name="iclrdatatargetgetimagebase-method"></a><span data-ttu-id="3eb00-102">Metodo ICLRDataTarget::GetImageBase</span><span class="sxs-lookup"><span data-stu-id="3eb00-102">ICLRDataTarget::GetImageBase Method</span></span>
<span data-ttu-id="3eb00-103">Ottiene l'indirizzo di memoria di base dell'immagine specificata.</span><span class="sxs-lookup"><span data-stu-id="3eb00-103">Gets the base memory address of the specified image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3eb00-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3eb00-104">Syntax</span></span>  
  
```cpp  
HRESULT GetImageBase (  
    [in, string] LPCWSTR    imagePath,  
    [out] CLRDATA_ADDRESS   *baseAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3eb00-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="3eb00-105">Parameters</span></span>  
 `imagePath`  
 <span data-ttu-id="3eb00-106">in Nome file dell'immagine, incluso il percorso.</span><span class="sxs-lookup"><span data-stu-id="3eb00-106">[in] The file name of the image, including its path.</span></span>  
  
 `baseAddress`  
 <span data-ttu-id="3eb00-107">out Puntatore a un CLRDATA_ADDRESS che archivia l'indirizzo di base dell'immagine.</span><span class="sxs-lookup"><span data-stu-id="3eb00-107">[out] A pointer to a CLRDATA_ADDRESS that stores the base address of the image.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3eb00-108">Note</span><span class="sxs-lookup"><span data-stu-id="3eb00-108">Remarks</span></span>  
 <span data-ttu-id="3eb00-109">Il nome del file di immagine non può contenere un percorso.</span><span class="sxs-lookup"><span data-stu-id="3eb00-109">The image file name may or may not have a path.</span></span> <span data-ttu-id="3eb00-110">Se viene specificato un percorso, la corrispondenza viene eseguita sull'intero percorso. in caso contrario, la corrispondenza viene eseguita solo sul nome del file.</span><span class="sxs-lookup"><span data-stu-id="3eb00-110">If a path is specified, matching is done on the whole path; otherwise, matching is done only on the file name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3eb00-111">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="3eb00-111">Requirements</span></span>  
 <span data-ttu-id="3eb00-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3eb00-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3eb00-113">**Intestazione:** ClrData. idl, ClrData. h</span><span class="sxs-lookup"><span data-stu-id="3eb00-113">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="3eb00-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3eb00-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3eb00-115">**Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3eb00-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3eb00-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3eb00-116">See also</span></span>

- [<span data-ttu-id="3eb00-117">Interfaccia ICLRDataTarget</span><span class="sxs-lookup"><span data-stu-id="3eb00-117">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
