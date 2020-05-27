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
ms.openlocfilehash: 8f8c0c2cb8dea8ad2b9c0040654122ef5942aca0
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008391"
---
# <a name="imetadataconvertergetmetadatafromtypelib-method"></a><span data-ttu-id="c72f6-102">Metodo IMetaDataConverter::GetMetaDataFromTypeLib</span><span class="sxs-lookup"><span data-stu-id="c72f6-102">IMetaDataConverter::GetMetaDataFromTypeLib Method</span></span>
<span data-ttu-id="c72f6-103">Ottiene un puntatore a interfaccia a un'istanza di [IMetaDataImport](imetadataimport-interface.md) che rappresenta la firma dei metadati della libreria dei tipi rappresentata dall'istanza di specificata `ITypeLib` .</span><span class="sxs-lookup"><span data-stu-id="c72f6-103">Gets an interface pointer to an [IMetaDataImport](imetadataimport-interface.md) instance that represents the metadata signature of the type library represented by the specified `ITypeLib` instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c72f6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c72f6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMetaDataFromTypeLib (  
    [in]  ITypeLib        *pITL,
    [out] IMetaDataImport **ppMDI  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c72f6-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c72f6-105">Parameters</span></span>  
 `pITL`  
 <span data-ttu-id="c72f6-106">in Puntatore a un `ITypeLib` oggetto che rappresenta la libreria dei tipi.</span><span class="sxs-lookup"><span data-stu-id="c72f6-106">[in] Pointer to an `ITypeLib` object that represents the type library.</span></span>  
  
 `ppMDI`  
 <span data-ttu-id="c72f6-107">out Puntatore a una posizione che riceve l'indirizzo dell' `IMetaDataImport` istanza di che rappresenta la firma dei metadati.</span><span class="sxs-lookup"><span data-stu-id="c72f6-107">[out] Pointer to a location that receives the address of the `IMetaDataImport` instance that represents the metadata signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c72f6-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c72f6-108">Requirements</span></span>  
 <span data-ttu-id="c72f6-109">**Piattaforma:** Vedere [requisiti di sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c72f6-109">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c72f6-110">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="c72f6-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c72f6-111">**Libreria:** Usato come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="c72f6-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c72f6-112">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c72f6-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c72f6-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c72f6-113">See also</span></span>

- [<span data-ttu-id="c72f6-114">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="c72f6-114">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="c72f6-115">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="c72f6-115">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
