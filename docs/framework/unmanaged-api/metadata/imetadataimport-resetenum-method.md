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
ms.openlocfilehash: 3dd82588cf2dbf92fdda66fd7674c17ddc8b7306
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177194"
---
# <a name="imetadataimportresetenum-method"></a><span data-ttu-id="a4118-102">Metodo IMetaDataImport::ResetEnum</span><span class="sxs-lookup"><span data-stu-id="a4118-102">IMetaDataImport::ResetEnum Method</span></span>
<span data-ttu-id="a4118-103">Reimposta l'enumeratore specificato nella posizione specificata.</span><span class="sxs-lookup"><span data-stu-id="a4118-103">Resets the specified enumerator to the specified position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4118-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a4118-104">Syntax</span></span>  
  
```cpp  
HRESULT ResetEnum (  
   [in] HCORENUM    hEnum,
   [in] ULONG       ulPos  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a4118-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a4118-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="a4118-106">[in] Enumeratore da reimpostare.</span><span class="sxs-lookup"><span data-stu-id="a4118-106">[in] The enumerator to reset.</span></span>  
  
 `ulPos`  
 <span data-ttu-id="a4118-107">[in] Nuova posizione in cui posizionare l'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="a4118-107">[in] The new position at which to place the enumerator.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a4118-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a4118-108">Requirements</span></span>  
 <span data-ttu-id="a4118-109">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a4118-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a4118-110">**Intestazione:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="a4118-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a4118-111">**Biblioteca:** Incluso come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a4118-111">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a4118-112">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a4118-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4118-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a4118-113">See also</span></span>

- [<span data-ttu-id="a4118-114">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="a4118-114">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="a4118-115">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="a4118-115">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
