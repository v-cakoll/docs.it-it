---
title: Metodo IMetaDataImport::GetFieldMarshal
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetFieldMarshal
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetFieldMarshal
helpviewer_keywords:
- GetFieldMarshal method [.NET Framework metadata]
- IMetaDataImport::GetFieldMarshal method [.NET Framework metadata]
ms.assetid: 4e2d88c6-8a3a-4fbe-900b-b4f4c06bf6bf
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 837b2142e200e224fe32c2c673be0f317633452a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33445358"
---
# <a name="imetadataimportgetfieldmarshal-method"></a><span data-ttu-id="a430c-102">Metodo IMetaDataImport::GetFieldMarshal</span><span class="sxs-lookup"><span data-stu-id="a430c-102">IMetaDataImport::GetFieldMarshal Method</span></span>
<span data-ttu-id="a430c-103">Ottiene un puntatore al tipo nativo non gestito del campo rappresentato dal token di metadati specificato.</span><span class="sxs-lookup"><span data-stu-id="a430c-103">Gets a pointer to the native, unmanaged type of the field represented by the specified field metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a430c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a430c-104">Syntax</span></span>  
  
```  
HRESULT GetFieldMarshal (  
   [in]  mdToken             tk,   
   [out] PCCOR_SIGNATURE     *ppvNativeType,  
   [out] ULONG               *pcbNativeType   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a430c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a430c-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="a430c-106">[in] Il token di metadati che rappresenta il campo per ottenere le informazioni di marshalling di interoperabilità per.</span><span class="sxs-lookup"><span data-stu-id="a430c-106">[in] The metadata token that represents the field to get interop marshaling information for.</span></span>  
  
 `ppvNativeType`  
 <span data-ttu-id="a430c-107">[out] Un puntatore per la firma dei metadati di tipo nativo del campo.</span><span class="sxs-lookup"><span data-stu-id="a430c-107">[out] A pointer to the metadata signature of the field's native type.</span></span>  
  
 `pcbNativeType`  
 <span data-ttu-id="a430c-108">[out] Le dimensioni in byte di `ppvNativeType`.</span><span class="sxs-lookup"><span data-stu-id="a430c-108">[out] The size in bytes of `ppvNativeType`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a430c-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a430c-109">Requirements</span></span>  
 <span data-ttu-id="a430c-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a430c-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a430c-111">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="a430c-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a430c-112">**Libreria:** inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="a430c-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a430c-113">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a430c-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a430c-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a430c-114">See Also</span></span>  
 [<span data-ttu-id="a430c-115">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="a430c-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="a430c-116">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="a430c-116">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
