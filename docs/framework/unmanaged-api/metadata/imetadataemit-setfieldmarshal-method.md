---
title: Metodo IMetaDataEmit::SetFieldMarshal
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetFieldMarshal
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetFieldMarshal
helpviewer_keywords:
- SetFieldMarshal method [.NET Framework metadata]
- IMetaDataEmit::SetFieldMarshal method [.NET Framework metadata]
ms.assetid: be232314-7f69-4855-bfab-63361bd22307
topic_type:
- apiref
ms.openlocfilehash: cdbcdb9359d295ad9bed2050ed36499feba74d9e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74442268"
---
# <a name="imetadataemitsetfieldmarshal-method"></a><span data-ttu-id="fcf90-102">Metodo IMetaDataEmit::SetFieldMarshal</span><span class="sxs-lookup"><span data-stu-id="fcf90-102">IMetaDataEmit::SetFieldMarshal Method</span></span>
<span data-ttu-id="fcf90-103">Imposta le informazioni di marshalling PInvoke per il campo, il ritorno del metodo o il parametro del metodo a cui fa riferimento il token specificato.</span><span class="sxs-lookup"><span data-stu-id="fcf90-103">Sets the PInvoke marshaling information for the field, method return, or method parameter referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fcf90-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fcf90-104">Syntax</span></span>  
  
```cpp  
HRESULT SetFieldMarshal (  
    [in]  mdToken          tk,   
    [in]  PCCOR_SIGNATURE  pvNativeType,   
    [in]  ULONG            cbNativeType   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fcf90-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="fcf90-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="fcf90-106">in Token per l'elemento di dati di destinazione.</span><span class="sxs-lookup"><span data-stu-id="fcf90-106">[in] The token for target data item.</span></span> <span data-ttu-id="fcf90-107">Si tratta di un token `mdFieldDef` o `mdParamDef`.</span><span class="sxs-lookup"><span data-stu-id="fcf90-107">This is either a `mdFieldDef` or a `mdParamDef` token.</span></span>  
  
 `pvNativeType`  
 <span data-ttu-id="fcf90-108">in Firma per il tipo non gestito.</span><span class="sxs-lookup"><span data-stu-id="fcf90-108">[in] The signature for unmanaged type.</span></span>  
  
 `cbNativeType`  
 <span data-ttu-id="fcf90-109">in Conteggio dei byte in `pvNativeType`.</span><span class="sxs-lookup"><span data-stu-id="fcf90-109">[in] The count of bytes in `pvNativeType`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fcf90-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fcf90-110">Requirements</span></span>  
 <span data-ttu-id="fcf90-111">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fcf90-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fcf90-112">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="fcf90-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fcf90-113">**Libreria:** Usato come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="fcf90-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fcf90-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fcf90-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fcf90-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fcf90-115">See also</span></span>

- [<span data-ttu-id="fcf90-116">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="fcf90-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="fcf90-117">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="fcf90-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
