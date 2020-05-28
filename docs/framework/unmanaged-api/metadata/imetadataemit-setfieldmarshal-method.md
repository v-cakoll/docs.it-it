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
ms.openlocfilehash: d0066c6590a9e0cf278e036111c2739f7cfaf679
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84003906"
---
# <a name="imetadataemitsetfieldmarshal-method"></a><span data-ttu-id="0ab7b-102">Metodo IMetaDataEmit::SetFieldMarshal</span><span class="sxs-lookup"><span data-stu-id="0ab7b-102">IMetaDataEmit::SetFieldMarshal Method</span></span>
<span data-ttu-id="0ab7b-103">Imposta le informazioni di marshalling PInvoke per il campo, il ritorno del metodo o il parametro del metodo a cui fa riferimento il token specificato.</span><span class="sxs-lookup"><span data-stu-id="0ab7b-103">Sets the PInvoke marshaling information for the field, method return, or method parameter referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ab7b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0ab7b-104">Syntax</span></span>  
  
```cpp  
HRESULT SetFieldMarshal (  
    [in]  mdToken          tk,
    [in]  PCCOR_SIGNATURE  pvNativeType,
    [in]  ULONG            cbNativeType
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0ab7b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="0ab7b-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="0ab7b-106">in Token per l'elemento di dati di destinazione.</span><span class="sxs-lookup"><span data-stu-id="0ab7b-106">[in] The token for target data item.</span></span> <span data-ttu-id="0ab7b-107">Si tratta di un `mdFieldDef` token o `mdParamDef` .</span><span class="sxs-lookup"><span data-stu-id="0ab7b-107">This is either a `mdFieldDef` or a `mdParamDef` token.</span></span>  
  
 `pvNativeType`  
 <span data-ttu-id="0ab7b-108">in Firma per il tipo non gestito.</span><span class="sxs-lookup"><span data-stu-id="0ab7b-108">[in] The signature for unmanaged type.</span></span>  
  
 `cbNativeType`  
 <span data-ttu-id="0ab7b-109">in Numero di byte in `pvNativeType` .</span><span class="sxs-lookup"><span data-stu-id="0ab7b-109">[in] The count of bytes in `pvNativeType`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0ab7b-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0ab7b-110">Requirements</span></span>  
 <span data-ttu-id="0ab7b-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0ab7b-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0ab7b-112">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="0ab7b-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0ab7b-113">**Libreria:** Usato come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="0ab7b-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0ab7b-114">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0ab7b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ab7b-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0ab7b-115">See also</span></span>

- [<span data-ttu-id="0ab7b-116">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="0ab7b-116">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="0ab7b-117">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="0ab7b-117">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
