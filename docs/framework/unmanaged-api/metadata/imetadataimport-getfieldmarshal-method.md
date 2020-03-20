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
ms.openlocfilehash: 91a19e5e15dddd446208dfa3b2c32826282067eb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175395"
---
# <a name="imetadataimportgetfieldmarshal-method"></a><span data-ttu-id="6e0ff-102">Metodo IMetaDataImport::GetFieldMarshal</span><span class="sxs-lookup"><span data-stu-id="6e0ff-102">IMetaDataImport::GetFieldMarshal Method</span></span>
<span data-ttu-id="6e0ff-103">Ottiene un puntatore al tipo nativo non gestito del campo rappresentato dal token di metadati del campo specificato.</span><span class="sxs-lookup"><span data-stu-id="6e0ff-103">Gets a pointer to the native, unmanaged type of the field represented by the specified field metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e0ff-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6e0ff-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFieldMarshal (  
   [in]  mdToken             tk,
   [out] PCCOR_SIGNATURE     *ppvNativeType,  
   [out] ULONG               *pcbNativeType
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6e0ff-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="6e0ff-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="6e0ff-106">[in] Token di metadati per cui rappresenta il campo per cui ottenere informazioni sul marshalling di interoperabilità.</span><span class="sxs-lookup"><span data-stu-id="6e0ff-106">[in] The metadata token that represents the field to get interop marshaling information for.</span></span>  
  
 `ppvNativeType`  
 <span data-ttu-id="6e0ff-107">[fuori] Puntatore alla firma dei metadati del tipo nativo del campo.</span><span class="sxs-lookup"><span data-stu-id="6e0ff-107">[out] A pointer to the metadata signature of the field's native type.</span></span>  
  
 `pcbNativeType`  
 <span data-ttu-id="6e0ff-108">[fuori] Dimensione in byte `ppvNativeType`di .</span><span class="sxs-lookup"><span data-stu-id="6e0ff-108">[out] The size in bytes of `ppvNativeType`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6e0ff-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6e0ff-109">Requirements</span></span>  
 <span data-ttu-id="6e0ff-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6e0ff-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6e0ff-111">**Intestazione:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="6e0ff-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6e0ff-112">**Biblioteca:** Incluso come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6e0ff-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6e0ff-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6e0ff-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e0ff-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6e0ff-114">See also</span></span>

- [<span data-ttu-id="6e0ff-115">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="6e0ff-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="6e0ff-116">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="6e0ff-116">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
