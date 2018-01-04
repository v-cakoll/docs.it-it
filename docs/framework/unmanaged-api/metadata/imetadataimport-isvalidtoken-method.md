---
title: Metodo IMetaDataImport::IsValidToken
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.IsValidToken
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::IsValidToken
helpviewer_keywords:
- IMetaDataImport::IsValidToken method [.NET Framework metadata]
- IsValidToken method [.NET Framework metadata]
ms.assetid: aeb0fc63-9eff-4384-9284-cb9900572d74
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 61af4f5e68ebd5d5e4639cbc4c581d1c66358ff8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportisvalidtoken-method"></a><span data-ttu-id="e75a8-102">Metodo IMetaDataImport::IsValidToken</span><span class="sxs-lookup"><span data-stu-id="e75a8-102">IMetaDataImport::IsValidToken Method</span></span>
<span data-ttu-id="e75a8-103">Ottiene un valore che indica se il token specificato contiene un riferimento valido a un oggetto codice.</span><span class="sxs-lookup"><span data-stu-id="e75a8-103">Gets a value indicating whether the specified token holds a valid reference to a code object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e75a8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e75a8-104">Syntax</span></span>  
  
```  
BOOL IsValidToken (  
   [in] mdToken     tk  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e75a8-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e75a8-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="e75a8-106">[in] Il token per verificare la validità del riferimento.</span><span class="sxs-lookup"><span data-stu-id="e75a8-106">[in] The token to check the reference validity for.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e75a8-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="e75a8-107">Return Value</span></span>  
 <span data-ttu-id="e75a8-108">`true`Se `tk` è un token di metadati valido all'interno dell'ambito corrente.</span><span class="sxs-lookup"><span data-stu-id="e75a8-108">`true` if `tk` is a valid metadata token within the current scope.</span></span> <span data-ttu-id="e75a8-109">In caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="e75a8-109">Otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e75a8-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e75a8-110">Requirements</span></span>  
 <span data-ttu-id="e75a8-111">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e75a8-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e75a8-112">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="e75a8-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e75a8-113">**Libreria:** inclusa come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e75a8-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e75a8-114">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e75a8-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e75a8-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e75a8-115">See Also</span></span>  
 [<span data-ttu-id="e75a8-116">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="e75a8-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="e75a8-117">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="e75a8-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
