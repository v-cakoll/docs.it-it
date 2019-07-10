---
title: Metodo IMetaDataImport::IsValidToken
ms.date: 03/30/2017
api_name:
- IMetaDataImport.IsValidToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::IsValidToken
helpviewer_keywords:
- IMetaDataImport::IsValidToken method [.NET Framework metadata]
- IsValidToken method [.NET Framework metadata]
ms.assetid: aeb0fc63-9eff-4384-9284-cb9900572d74
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 753449924f3415eb826b59d3a887eb69b9efba39
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778778"
---
# <a name="imetadataimportisvalidtoken-method"></a><span data-ttu-id="db6c0-102">Metodo IMetaDataImport::IsValidToken</span><span class="sxs-lookup"><span data-stu-id="db6c0-102">IMetaDataImport::IsValidToken Method</span></span>
<span data-ttu-id="db6c0-103">Ottiene un valore che indica se il token specificato contiene un riferimento valido a un oggetto codice.</span><span class="sxs-lookup"><span data-stu-id="db6c0-103">Gets a value indicating whether the specified token holds a valid reference to a code object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db6c0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="db6c0-104">Syntax</span></span>  
  
```cpp  
BOOL IsValidToken (  
   [in] mdToken     tk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="db6c0-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="db6c0-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="db6c0-106">[in] Il token per verificare la validità del riferimento.</span><span class="sxs-lookup"><span data-stu-id="db6c0-106">[in] The token to check the reference validity for.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="db6c0-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="db6c0-107">Return Value</span></span>  
 <span data-ttu-id="db6c0-108">`true` Se `tk` è un token di metadati valido all'interno dell'ambito corrente.</span><span class="sxs-lookup"><span data-stu-id="db6c0-108">`true` if `tk` is a valid metadata token within the current scope.</span></span> <span data-ttu-id="db6c0-109">In caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="db6c0-109">Otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="db6c0-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="db6c0-110">Requirements</span></span>  
 <span data-ttu-id="db6c0-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="db6c0-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="db6c0-112">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="db6c0-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="db6c0-113">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="db6c0-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="db6c0-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="db6c0-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db6c0-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="db6c0-115">See also</span></span>

- [<span data-ttu-id="db6c0-116">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="db6c0-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="db6c0-117">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="db6c0-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
