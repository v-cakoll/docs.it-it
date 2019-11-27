---
title: Metodo IMetaDataConverter::GetMetaDataFromTypeLib
ms.date: 03/30/2017
api_name:
- IMetaDataConverter.GetMetaDataFromTypeLib
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataConverter::GetMetaDataFromTypeLib
helpviewer_keywords:
- IMetaDataConverter::GetMetaDataFromTypeLib method [.NET Framework metadata]
- GetMetaDataFromTypeLib method [.NET Framework metadata]
ms.assetid: 97dc3a56-adfa-431f-889e-06a35ac84d51
topic_type:
- apiref
ms.openlocfilehash: 6391e819d53c3ed8f0d596b15c4a2bb268f72fd5
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436279"
---
# <a name="imetadataconvertergetmetadatafromtypelib-method"></a><span data-ttu-id="7d8a2-102">Metodo IMetaDataConverter::GetMetaDataFromTypeLib</span><span class="sxs-lookup"><span data-stu-id="7d8a2-102">IMetaDataConverter::GetMetaDataFromTypeLib Method</span></span>
<span data-ttu-id="7d8a2-103">Ottiene un puntatore a interfaccia a un'istanza di [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) che rappresenta la firma dei metadati della libreria dei tipi rappresentata dall'istanza di `ITypeLib` specificata.</span><span class="sxs-lookup"><span data-stu-id="7d8a2-103">Gets an interface pointer to an [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) instance that represents the metadata signature of the type library represented by the specified `ITypeLib` instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d8a2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7d8a2-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMetaDataFromTypeLib (  
    [in]  ITypeLib        *pITL,   
    [out] IMetaDataImport **ppMDI  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7d8a2-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="7d8a2-105">Parameters</span></span>  
 `pITL`  
 <span data-ttu-id="7d8a2-106">in Puntatore a un oggetto `ITypeLib` che rappresenta la libreria dei tipi.</span><span class="sxs-lookup"><span data-stu-id="7d8a2-106">[in] Pointer to an `ITypeLib` object that represents the type library.</span></span>  
  
 `ppMDI`  
 <span data-ttu-id="7d8a2-107">out Puntatore a una posizione che riceve l'indirizzo dell'istanza di `IMetaDataImport` che rappresenta la firma dei metadati.</span><span class="sxs-lookup"><span data-stu-id="7d8a2-107">[out] Pointer to a location that receives the address of the `IMetaDataImport` instance that represents the metadata signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7d8a2-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7d8a2-108">Requirements</span></span>  
 <span data-ttu-id="7d8a2-109">**Piattaforma:** Vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7d8a2-109">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7d8a2-110">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="7d8a2-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7d8a2-111">**Libreria:** Usato come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="7d8a2-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7d8a2-112">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7d8a2-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d8a2-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7d8a2-113">See also</span></span>

- [<span data-ttu-id="7d8a2-114">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="7d8a2-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="7d8a2-115">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="7d8a2-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
