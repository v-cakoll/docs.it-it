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
ms.openlocfilehash: 71b07e11cd3fec1a0dbebe986d98067c2e6f18e1
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860637"
---
# <a name="iclrdatatargetgetimagebase-method"></a><span data-ttu-id="618fb-102">Metodo ICLRDataTarget::GetImageBase</span><span class="sxs-lookup"><span data-stu-id="618fb-102">ICLRDataTarget::GetImageBase Method</span></span>
<span data-ttu-id="618fb-103">Ottiene l'indirizzo di memoria di base dell'immagine specificata.</span><span class="sxs-lookup"><span data-stu-id="618fb-103">Gets the base memory address of the specified image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="618fb-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="618fb-104">Syntax</span></span>  
  
```cpp  
HRESULT GetImageBase (  
    [in, string] LPCWSTR    imagePath,  
    [out] CLRDATA_ADDRESS   *baseAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="618fb-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="618fb-105">Parameters</span></span>  
 `imagePath`  
 <span data-ttu-id="618fb-106">in Nome file dell'immagine, incluso il percorso.</span><span class="sxs-lookup"><span data-stu-id="618fb-106">[in] The file name of the image, including its path.</span></span>  
  
 `baseAddress`  
 <span data-ttu-id="618fb-107">out Puntatore a un CLRDATA_ADDRESS che archivia l'indirizzo di base dell'immagine.</span><span class="sxs-lookup"><span data-stu-id="618fb-107">[out] A pointer to a CLRDATA_ADDRESS that stores the base address of the image.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="618fb-108">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="618fb-108">Remarks</span></span>  
 <span data-ttu-id="618fb-109">Il nome del file di immagine non può contenere un percorso.</span><span class="sxs-lookup"><span data-stu-id="618fb-109">The image file name may or may not have a path.</span></span> <span data-ttu-id="618fb-110">Se viene specificato un percorso, la corrispondenza viene eseguita sull'intero percorso. in caso contrario, la corrispondenza viene eseguita solo sul nome del file.</span><span class="sxs-lookup"><span data-stu-id="618fb-110">If a path is specified, matching is done on the whole path; otherwise, matching is done only on the file name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="618fb-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="618fb-111">Requirements</span></span>  
 <span data-ttu-id="618fb-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="618fb-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="618fb-113">**Intestazione:** ClrData. idl, ClrData. h</span><span class="sxs-lookup"><span data-stu-id="618fb-113">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="618fb-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="618fb-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="618fb-115">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="618fb-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="618fb-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="618fb-116">See also</span></span>

- [<span data-ttu-id="618fb-117">Interfaccia ICLRDataTarget</span><span class="sxs-lookup"><span data-stu-id="618fb-117">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
