---
title: Metodo IMetaDataConverter::GetMetaDataFromTypeInfo
ms.date: 03/30/2017
api_name:
- IMetaDataConverter.GetMetaDataFromTypeInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataConverter::GetMetaDataFromTypeInfo
helpviewer_keywords:
- GetMetaDataFromTypeInfo method [.NET Framework metadata]
- IMetaDataConverter::GetMetaDataFromTypeInfo method [.NET Framework metadata]
ms.assetid: d44484bb-23a3-49c3-9e46-69d0d9ab4f0f
topic_type:
- apiref
ms.openlocfilehash: df7be11e8f275824fca658a9604178e7cf28e3ce
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436300"
---
# <a name="imetadataconvertergetmetadatafromtypeinfo-method"></a><span data-ttu-id="8ce75-102">Metodo IMetaDataConverter::GetMetaDataFromTypeInfo</span><span class="sxs-lookup"><span data-stu-id="8ce75-102">IMetaDataConverter::GetMetaDataFromTypeInfo Method</span></span>
<span data-ttu-id="8ce75-103">Ottiene un puntatore a un'istanza di [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) che rappresenta la firma dei metadati della libreria dei tipi a cui fa riferimento l'istanza di `ITypeInfo` specificata.</span><span class="sxs-lookup"><span data-stu-id="8ce75-103">Gets a pointer to an [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) instance that represents the metadata signature of the type library referenced by the specified `ITypeInfo` instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ce75-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8ce75-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMetaDataFromTypeInfo (  
    [in]  ITypeInfo         *pITI,  
    [out] IMetaDataImport   **ppMDI  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8ce75-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="8ce75-105">Parameters</span></span>  
 `pITI`  
 <span data-ttu-id="8ce75-106">in Puntatore a un oggetto `ITypeInfo` che fa riferimento alla libreria dei tipi.</span><span class="sxs-lookup"><span data-stu-id="8ce75-106">[in] A pointer to an `ITypeInfo` object that refers to the type library.</span></span>  
  
 `ppMDI`  
 <span data-ttu-id="8ce75-107">out Puntatore a una posizione che riceve l'indirizzo dell'istanza di `IMetaDataImport` che rappresenta la firma dei metadati.</span><span class="sxs-lookup"><span data-stu-id="8ce75-107">[out] A pointer to a location that receives the address of the `IMetaDataImport` instance that represents the metadata signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8ce75-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8ce75-108">Requirements</span></span>  
 <span data-ttu-id="8ce75-109">**Piattaforma:** Vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8ce75-109">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8ce75-110">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="8ce75-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8ce75-111">**Libreria:** Usato come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="8ce75-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8ce75-112">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8ce75-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ce75-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8ce75-113">See also</span></span>

- [<span data-ttu-id="8ce75-114">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="8ce75-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="8ce75-115">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="8ce75-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
