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
ms.openlocfilehash: 656f5ee20e50ea9ac5c03711adfd0b8264fbcca0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33444958"
---
# <a name="imetadataemitsavetostream-method"></a><span data-ttu-id="1993d-102">Metodo IMetaDataEmit::SaveToStream</span><span class="sxs-lookup"><span data-stu-id="1993d-102">IMetaDataEmit::SaveToStream Method</span></span>
<span data-ttu-id="1993d-103">Salva tutti i metadati nell'ambito corrente specificato `IStream`.</span><span class="sxs-lookup"><span data-stu-id="1993d-103">Saves all metadata in the current scope to the specified `IStream`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1993d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1993d-104">Syntax</span></span>  
  
```  
HRESULT SaveToStream (   
    [in]  IStream     *pIStream,  
    [in]  DWORD       dwSaveFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1993d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="1993d-105">Parameters</span></span>  
 `pIStream`  
 <span data-ttu-id="1993d-106">[in] Flusso scrivibile da salvare.</span><span class="sxs-lookup"><span data-stu-id="1993d-106">[in] The writable stream to save to.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="1993d-107">[in] Riservato.</span><span class="sxs-lookup"><span data-stu-id="1993d-107">[in] Reserved.</span></span> <span data-ttu-id="1993d-108">Deve essere zero.</span><span class="sxs-lookup"><span data-stu-id="1993d-108">Must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1993d-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1993d-109">Requirements</span></span>  
 <span data-ttu-id="1993d-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1993d-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1993d-111">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="1993d-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1993d-112">**Libreria:** usata come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="1993d-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1993d-113">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1993d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1993d-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1993d-114">See Also</span></span>  
 [<span data-ttu-id="1993d-115">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="1993d-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="1993d-116">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="1993d-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
