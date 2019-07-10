---
title: Metodo IMetaDataEmit::SaveToStream
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SaveToStream
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SaveToStream
helpviewer_keywords:
- IMetaDataEmit::SaveToStream method [.NET Framework metadata]
- SaveToStream method [.NET Framework metadata]
ms.assetid: e0290a49-3818-4a43-ad46-3014faa34f97
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 96b3b270fb12aa451d9026435dd3d2c4c196b09c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782018"
---
# <a name="imetadataemitsavetostream-method"></a><span data-ttu-id="64452-102">Metodo IMetaDataEmit::SaveToStream</span><span class="sxs-lookup"><span data-stu-id="64452-102">IMetaDataEmit::SaveToStream Method</span></span>
<span data-ttu-id="64452-103">Salva tutti i metadati nell'ambito corrente specificato `IStream`.</span><span class="sxs-lookup"><span data-stu-id="64452-103">Saves all metadata in the current scope to the specified `IStream`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64452-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="64452-104">Syntax</span></span>  
  
```cpp  
HRESULT SaveToStream (   
    [in]  IStream     *pIStream,  
    [in]  DWORD       dwSaveFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="64452-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="64452-105">Parameters</span></span>  
 `pIStream`  
 <span data-ttu-id="64452-106">[in] Il flusso scrivibile per salvare.</span><span class="sxs-lookup"><span data-stu-id="64452-106">[in] The writable stream to save to.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="64452-107">[in] Riservato.</span><span class="sxs-lookup"><span data-stu-id="64452-107">[in] Reserved.</span></span> <span data-ttu-id="64452-108">Deve essere zero.</span><span class="sxs-lookup"><span data-stu-id="64452-108">Must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="64452-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="64452-109">Requirements</span></span>  
 <span data-ttu-id="64452-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="64452-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="64452-111">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="64452-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="64452-112">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="64452-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="64452-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="64452-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64452-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="64452-114">See also</span></span>

- [<span data-ttu-id="64452-115">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="64452-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="64452-116">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="64452-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
