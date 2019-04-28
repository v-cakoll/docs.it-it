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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 143b11f0a99081b7d49bfbb68b635d92cf1e9ba3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61777429"
---
# <a name="imetadataimportresetenum-method"></a><span data-ttu-id="0c366-102">Metodo IMetaDataImport::ResetEnum</span><span class="sxs-lookup"><span data-stu-id="0c366-102">IMetaDataImport::ResetEnum Method</span></span>
<span data-ttu-id="0c366-103">Reimposta l'enumeratore specificato nella posizione specificata.</span><span class="sxs-lookup"><span data-stu-id="0c366-103">Resets the specified enumerator to the specified position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c366-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0c366-104">Syntax</span></span>  
  
```  
HRESULT ResetEnum (  
   [in] HCORENUM    hEnum,   
   [in] ULONG       ulPos  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0c366-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="0c366-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="0c366-106">[in] L'enumeratore reimpostare.</span><span class="sxs-lookup"><span data-stu-id="0c366-106">[in] The enumerator to reset.</span></span>  
  
 `ulPos`  
 <span data-ttu-id="0c366-107">[in] La nuova posizione in corrispondenza del quale inserire l'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="0c366-107">[in] The new position at which to place the enumerator.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0c366-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0c366-108">Requirements</span></span>  
 <span data-ttu-id="0c366-109">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0c366-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0c366-110">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="0c366-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0c366-111">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="0c366-111">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0c366-112">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0c366-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c366-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0c366-113">See also</span></span>

- [<span data-ttu-id="0c366-114">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="0c366-114">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="0c366-115">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="0c366-115">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
