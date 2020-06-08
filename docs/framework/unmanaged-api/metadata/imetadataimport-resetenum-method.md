---
title: Metodo IMetaDataImport::ResetEnum
ms.date: 03/30/2017
api_name:
- IMetaDataImport.ResetEnum
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::ResetEnum
helpviewer_keywords:
- ResetEnum method [.NET Framework metadata]
- IMetaDataImport::ResetEnum method [.NET Framework metadata]
ms.assetid: dda867b5-1050-49ba-b01c-fcc83b7a5617
topic_type:
- apiref
ms.openlocfilehash: bc7f1740d666211b63cd93e6f1c0e6955f61ec5d
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503458"
---
# <a name="imetadataimportresetenum-method"></a><span data-ttu-id="30fed-102">Metodo IMetaDataImport::ResetEnum</span><span class="sxs-lookup"><span data-stu-id="30fed-102">IMetaDataImport::ResetEnum Method</span></span>
<span data-ttu-id="30fed-103">Reimposta l'enumeratore specificato nella posizione specificata.</span><span class="sxs-lookup"><span data-stu-id="30fed-103">Resets the specified enumerator to the specified position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30fed-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="30fed-104">Syntax</span></span>  
  
```cpp  
HRESULT ResetEnum (  
   [in] HCORENUM    hEnum,
   [in] ULONG       ulPos  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="30fed-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="30fed-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="30fed-106">in Enumeratore da reimpostare.</span><span class="sxs-lookup"><span data-stu-id="30fed-106">[in] The enumerator to reset.</span></span>  
  
 `ulPos`  
 <span data-ttu-id="30fed-107">in Nuova posizione in cui posizionare l'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="30fed-107">[in] The new position at which to place the enumerator.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="30fed-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="30fed-108">Requirements</span></span>  
 <span data-ttu-id="30fed-109">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="30fed-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="30fed-110">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="30fed-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="30fed-111">**Libreria:** Incluso come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="30fed-111">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="30fed-112">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="30fed-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30fed-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="30fed-113">See also</span></span>

- [<span data-ttu-id="30fed-114">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="30fed-114">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="30fed-115">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="30fed-115">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
