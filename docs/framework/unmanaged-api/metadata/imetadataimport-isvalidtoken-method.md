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
ms.openlocfilehash: 3a99ed42f500b83b5109631b21a88029995b43d6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59123878"
---
# <a name="imetadataimportisvalidtoken-method"></a><span data-ttu-id="d2450-102">Metodo IMetaDataImport::IsValidToken</span><span class="sxs-lookup"><span data-stu-id="d2450-102">IMetaDataImport::IsValidToken Method</span></span>
<span data-ttu-id="d2450-103">Ottiene un valore che indica se il token specificato contiene un riferimento valido a un oggetto codice.</span><span class="sxs-lookup"><span data-stu-id="d2450-103">Gets a value indicating whether the specified token holds a valid reference to a code object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2450-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d2450-104">Syntax</span></span>  
  
```  
BOOL IsValidToken (  
   [in] mdToken     tk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d2450-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d2450-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="d2450-106">[in] Il token per verificare la validità del riferimento.</span><span class="sxs-lookup"><span data-stu-id="d2450-106">[in] The token to check the reference validity for.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d2450-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="d2450-107">Return Value</span></span>  
 `true` <span data-ttu-id="d2450-108">Se `tk` è un token di metadati valido all'interno dell'ambito corrente.</span><span class="sxs-lookup"><span data-stu-id="d2450-108">if `tk` is a valid metadata token within the current scope.</span></span> <span data-ttu-id="d2450-109">In caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="d2450-109">Otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d2450-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d2450-110">Requirements</span></span>  
 <span data-ttu-id="d2450-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d2450-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d2450-112">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="d2450-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d2450-113">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="d2450-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="d2450-114">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="d2450-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d2450-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d2450-115">See also</span></span>

- [<span data-ttu-id="d2450-116">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="d2450-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="d2450-117">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="d2450-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
