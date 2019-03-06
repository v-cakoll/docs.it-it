---
title: Metodo IMetaDataImport::CloseEnum
ms.date: 03/30/2017
api_name:
- IMetaDataImport.CloseEnum
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::CloseEnum
helpviewer_keywords:
- IMetaDataImport::CloseEnum method [.NET Framework metadata]
- CloseEnum method, IMetaDataImport interface [.NET Framework metadata]
ms.assetid: 727819d5-1dab-4ebb-ac25-950b4111dc72
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: dda94acc2ec5da456cdc41ba0902cdc414b11524
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57486381"
---
# <a name="imetadataimportcloseenum-method"></a><span data-ttu-id="9a970-102">Metodo IMetaDataImport::CloseEnum</span><span class="sxs-lookup"><span data-stu-id="9a970-102">IMetaDataImport::CloseEnum Method</span></span>
<span data-ttu-id="9a970-103">Chiude l'enumeratore che è identificato dall'handle specificato.</span><span class="sxs-lookup"><span data-stu-id="9a970-103">Closes the enumerator that is identified by the specified handle.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a970-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9a970-104">Syntax</span></span>  
  
```  
void CloseEnum (  
   [in] HCORENUM hEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9a970-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="9a970-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="9a970-106">[in] L'handle per l'enumeratore chiudere.</span><span class="sxs-lookup"><span data-stu-id="9a970-106">[in] The handle for the enumerator to close.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9a970-107">Note</span><span class="sxs-lookup"><span data-stu-id="9a970-107">Remarks</span></span>  
 <span data-ttu-id="9a970-108">L'handle specificato da `hEnum` ottenuto da una precedente `Enum` *nome* chiamare (ad esempio [EnumTypeDefs](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumtypedefs-method.md)).</span><span class="sxs-lookup"><span data-stu-id="9a970-108">The handle specified by `hEnum` is obtained from a previous `Enum`*Name* call (for example, [IMetaDataImport::EnumTypeDefs](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumtypedefs-method.md)).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9a970-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9a970-109">Requirements</span></span>  
 <span data-ttu-id="9a970-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9a970-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9a970-111">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="9a970-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9a970-112">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="9a970-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9a970-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9a970-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a970-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9a970-114">See also</span></span>
- [<span data-ttu-id="9a970-115">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="9a970-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="9a970-116">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="9a970-116">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
