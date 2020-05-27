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
ms.openlocfilehash: f9f3e3f196f74a7dea3c722925f1d03968688882
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009002"
---
# <a name="imetadataconvertergetmetadatafromtypeinfo-method"></a><span data-ttu-id="2c4de-102">Metodo IMetaDataConverter::GetMetaDataFromTypeInfo</span><span class="sxs-lookup"><span data-stu-id="2c4de-102">IMetaDataConverter::GetMetaDataFromTypeInfo Method</span></span>
<span data-ttu-id="2c4de-103">Ottiene un puntatore a un'istanza di [IMetaDataImport](imetadataimport-interface.md) che rappresenta la firma dei metadati della libreria dei tipi a cui fa riferimento l' `ITypeInfo` istanza specificata.</span><span class="sxs-lookup"><span data-stu-id="2c4de-103">Gets a pointer to an [IMetaDataImport](imetadataimport-interface.md) instance that represents the metadata signature of the type library referenced by the specified `ITypeInfo` instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c4de-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2c4de-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMetaDataFromTypeInfo (  
    [in]  ITypeInfo         *pITI,  
    [out] IMetaDataImport   **ppMDI  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2c4de-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="2c4de-105">Parameters</span></span>  
 `pITI`  
 <span data-ttu-id="2c4de-106">in Puntatore a un `ITypeInfo` oggetto che fa riferimento alla libreria dei tipi.</span><span class="sxs-lookup"><span data-stu-id="2c4de-106">[in] A pointer to an `ITypeInfo` object that refers to the type library.</span></span>  
  
 `ppMDI`  
 <span data-ttu-id="2c4de-107">out Puntatore a una posizione che riceve l'indirizzo dell'istanza di `IMetaDataImport` che rappresenta la firma dei metadati.</span><span class="sxs-lookup"><span data-stu-id="2c4de-107">[out] A pointer to a location that receives the address of the `IMetaDataImport` instance that represents the metadata signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2c4de-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2c4de-108">Requirements</span></span>  
 <span data-ttu-id="2c4de-109">**Piattaforma:** Vedere [requisiti di sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2c4de-109">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2c4de-110">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="2c4de-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2c4de-111">**Libreria:** Usato come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="2c4de-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2c4de-112">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2c4de-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c4de-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2c4de-113">See also</span></span>

- [<span data-ttu-id="2c4de-114">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="2c4de-114">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="2c4de-115">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="2c4de-115">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
