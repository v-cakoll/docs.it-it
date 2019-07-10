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
ms.openlocfilehash: fa5a446ba7bfd70330601c7cbc129800761cdb7c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782624"
---
# <a name="imetadataimportresetenum-method"></a><span data-ttu-id="cf47b-102">Metodo IMetaDataImport::ResetEnum</span><span class="sxs-lookup"><span data-stu-id="cf47b-102">IMetaDataImport::ResetEnum Method</span></span>
<span data-ttu-id="cf47b-103">Reimposta l'enumeratore specificato nella posizione specificata.</span><span class="sxs-lookup"><span data-stu-id="cf47b-103">Resets the specified enumerator to the specified position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf47b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cf47b-104">Syntax</span></span>  
  
```cpp  
HRESULT ResetEnum (  
   [in] HCORENUM    hEnum,   
   [in] ULONG       ulPos  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cf47b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="cf47b-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="cf47b-106">[in] L'enumeratore reimpostare.</span><span class="sxs-lookup"><span data-stu-id="cf47b-106">[in] The enumerator to reset.</span></span>  
  
 `ulPos`  
 <span data-ttu-id="cf47b-107">[in] La nuova posizione in corrispondenza del quale inserire l'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="cf47b-107">[in] The new position at which to place the enumerator.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cf47b-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="cf47b-108">Requirements</span></span>  
 <span data-ttu-id="cf47b-109">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cf47b-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cf47b-110">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="cf47b-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="cf47b-111">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="cf47b-111">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="cf47b-112">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cf47b-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf47b-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cf47b-113">See also</span></span>

- [<span data-ttu-id="cf47b-114">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="cf47b-114">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="cf47b-115">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="cf47b-115">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
