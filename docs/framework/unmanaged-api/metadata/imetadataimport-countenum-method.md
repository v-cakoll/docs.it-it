---
title: Metodo IMetaDataImport::CountEnum
ms.date: 03/30/2017
api_name:
- IMetaDataImport.CountEnum
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::CountEnum
helpviewer_keywords:
- CountEnum method [.NET Framework metadata]
- IMetaDataImport::CountEnum method [.NET Framework metadata]
ms.assetid: d1de53ad-9435-4b5f-9df7-07f21210e5b5
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b5015dc42497d269cdc2de944f14454558be6c07
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59142987"
---
# <a name="imetadataimportcountenum-method"></a><span data-ttu-id="5b47e-102">Metodo IMetaDataImport::CountEnum</span><span class="sxs-lookup"><span data-stu-id="5b47e-102">IMetaDataImport::CountEnum Method</span></span>
<span data-ttu-id="5b47e-103">Ottiene il numero di elementi nell'enumerazione recuperato dall'enumeratore specificato.</span><span class="sxs-lookup"><span data-stu-id="5b47e-103">Gets the number of elements in the enumeration that was retrieved by the specified enumerator.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b47e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5b47e-104">Syntax</span></span>  
  
```  
HRESULT CountEnum (  
   [in]  HCORENUM    hEnum,   
   [out] ULONG       *pulCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5b47e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="5b47e-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="5b47e-106">[in] L'handle per l'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="5b47e-106">[in] The handle for the enumerator.</span></span>  
  
 `pulCount`  
 <span data-ttu-id="5b47e-107">[out] Il numero di elementi enumerati.</span><span class="sxs-lookup"><span data-stu-id="5b47e-107">[out] The number of elements enumerated.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5b47e-108">Note</span><span class="sxs-lookup"><span data-stu-id="5b47e-108">Remarks</span></span>  
 <span data-ttu-id="5b47e-109">L'handle specificato da `hEnum` ottenuto da una precedente `Enum` *nome* chiamare (ad esempio [EnumTypeDefs](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumtypedefs-method.md)).</span><span class="sxs-lookup"><span data-stu-id="5b47e-109">The handle specified by `hEnum` is obtained from a previous `Enum`*Name* call (for example, [IMetaDataImport::EnumTypeDefs](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumtypedefs-method.md)).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5b47e-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5b47e-110">Requirements</span></span>  
 <span data-ttu-id="5b47e-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5b47e-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5b47e-112">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="5b47e-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5b47e-113">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="5b47e-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="5b47e-114">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="5b47e-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5b47e-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5b47e-115">See also</span></span>

- [<span data-ttu-id="5b47e-116">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="5b47e-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="5b47e-117">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="5b47e-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
