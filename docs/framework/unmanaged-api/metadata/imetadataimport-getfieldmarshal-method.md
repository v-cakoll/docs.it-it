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
ms.openlocfilehash: 35e780c330d0184d40bd99f34c3454f83075c1e0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61777780"
---
# <a name="imetadataimportgetfieldmarshal-method"></a><span data-ttu-id="3092f-102">Metodo IMetaDataImport::GetFieldMarshal</span><span class="sxs-lookup"><span data-stu-id="3092f-102">IMetaDataImport::GetFieldMarshal Method</span></span>
<span data-ttu-id="3092f-103">Ottiene un puntatore al tipo nativo non gestito del campo rappresentato dal token di metadati specificato.</span><span class="sxs-lookup"><span data-stu-id="3092f-103">Gets a pointer to the native, unmanaged type of the field represented by the specified field metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3092f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3092f-104">Syntax</span></span>  
  
```  
HRESULT GetFieldMarshal (  
   [in]  mdToken             tk,   
   [out] PCCOR_SIGNATURE     *ppvNativeType,  
   [out] ULONG               *pcbNativeType   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3092f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="3092f-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="3092f-106">[in] Il token di metadati che rappresenta il campo per ottenere le informazioni di marshalling di interoperabilità.</span><span class="sxs-lookup"><span data-stu-id="3092f-106">[in] The metadata token that represents the field to get interop marshaling information for.</span></span>  
  
 `ppvNativeType`  
 <span data-ttu-id="3092f-107">[out] Un puntatore per la firma dei metadati di tipo nativo del campo.</span><span class="sxs-lookup"><span data-stu-id="3092f-107">[out] A pointer to the metadata signature of the field's native type.</span></span>  
  
 `pcbNativeType`  
 <span data-ttu-id="3092f-108">[out] La dimensione in byte di `ppvNativeType`.</span><span class="sxs-lookup"><span data-stu-id="3092f-108">[out] The size in bytes of `ppvNativeType`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3092f-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3092f-109">Requirements</span></span>  
 <span data-ttu-id="3092f-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3092f-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3092f-111">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="3092f-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3092f-112">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="3092f-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3092f-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3092f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3092f-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3092f-114">See also</span></span>

- [<span data-ttu-id="3092f-115">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="3092f-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="3092f-116">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="3092f-116">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
