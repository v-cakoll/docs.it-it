---
title: Metodo IMetaDataImport::GetInterfaceImplProps
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetInterfaceImplProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetInterfaceImplProps
helpviewer_keywords:
- IMetaDataImport::GetInterfaceImplProps method [.NET Framework metadata]
- GetInterfaceImpProps method [.NET Framework metadata]
ms.assetid: be3f5985-b1e4-4036-8602-c16e8508d4af
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9fca044b5dce260a1eed55b01531e7ae21a16ebd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33446163"
---
# <a name="imetadataimportgetinterfaceimplprops-method"></a><span data-ttu-id="80a02-102">Metodo IMetaDataImport::GetInterfaceImplProps</span><span class="sxs-lookup"><span data-stu-id="80a02-102">IMetaDataImport::GetInterfaceImplProps Method</span></span>
<span data-ttu-id="80a02-103">Ottiene un puntatore al token di metadati per il <xref:System.Type> che implementa il metodo specificato e per l'interfaccia che dichiara tale metodo.</span><span class="sxs-lookup"><span data-stu-id="80a02-103">Gets a pointer to the metadata tokens for the <xref:System.Type> that implements the specified method, and for the interface that declares that method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80a02-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="80a02-104">Syntax</span></span>  
  
```  
HRESULT GetInterfaceImplProps (  
   [in]  mdInterfaceImpl        iiImpl,  
   [out] mdTypeDef              *pClass,  
   [out] mdToken                *ptkIface  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="80a02-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="80a02-105">Parameters</span></span>  
 `iiImpl`  
 <span data-ttu-id="80a02-106">[in] Che rappresenta il metodo per restituire i token di classe e interfaccia per il token di metadati.</span><span class="sxs-lookup"><span data-stu-id="80a02-106">[in] The metadata token representing the method to return the class and interface tokens for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="80a02-107">[out] Il token di metadati che rappresenta la classe che implementa il metodo.</span><span class="sxs-lookup"><span data-stu-id="80a02-107">[out] The metadata token representing the class that implements the method.</span></span>  
  
 `ptkIface`  
 <span data-ttu-id="80a02-108">[out] Il token di metadati che rappresenta l'interfaccia che definisce il metodo implementato.</span><span class="sxs-lookup"><span data-stu-id="80a02-108">[out] The metadata token representing the interface that defines the implemented method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="80a02-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="80a02-109">Requirements</span></span>  
 <span data-ttu-id="80a02-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="80a02-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="80a02-111">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="80a02-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="80a02-112">**Libreria:** inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="80a02-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="80a02-113">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="80a02-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80a02-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="80a02-114">See Also</span></span>  
 [<span data-ttu-id="80a02-115">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="80a02-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="80a02-116">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="80a02-116">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
