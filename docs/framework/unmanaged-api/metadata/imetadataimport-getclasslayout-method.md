---
title: Metodo IMetaDataImport::GetClassLayout
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetClassLayout
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetClassLayout
helpviewer_keywords:
- IMetaDataImport::GetClassLayout method [.NET Framework metadata]
- GetClassLayout method, IMetaDataImport interface [.NET Framework metadata]
ms.assetid: 8f35414d-f40b-4b99-8768-9adb675c622a
topic_type:
- apiref
ms.openlocfilehash: e02d7dd4b287d027b633ae9bf2e98e036062bdd0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175408"
---
# <a name="imetadataimportgetclasslayout-method"></a><span data-ttu-id="3c353-102">Metodo IMetaDataImport::GetClassLayout</span><span class="sxs-lookup"><span data-stu-id="3c353-102">IMetaDataImport::GetClassLayout Method</span></span>
<span data-ttu-id="3c353-103">Ottiene le informazioni sul layout per la classe a cui fa riferimento il token TypeDef specificato.</span><span class="sxs-lookup"><span data-stu-id="3c353-103">Gets layout information for the class referenced by the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c353-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3c353-104">Syntax</span></span>  
  
```cpp  
HRESULT GetClassLayout  (
   [in]  mdTypeDef          td,
   [out] DWORD              *pdwPackSize,  
   [out] COR_FIELD_OFFSET   rFieldOffset[],  
   [in]  ULONG              cMax,  
   [out] ULONG              *pcFieldOffset,  
   [out] ULONG              *pulClassSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3c353-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="3c353-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="3c353-106">[in] Token TypeDef per la classe con il layout da restituire.</span><span class="sxs-lookup"><span data-stu-id="3c353-106">[in] The TypeDef token for the class with the layout to return.</span></span>  
  
 `pdwPackSize`  
 <span data-ttu-id="3c353-107">[fuori] Uno dei valori 1, 2, 4, 8 o 16, che rappresenta la dimensione del pacchetto della classe.</span><span class="sxs-lookup"><span data-stu-id="3c353-107">[out] One of the values 1, 2, 4, 8, or 16, representing the pack size of the class.</span></span>  
  
 `rFieldOffset`  
 <span data-ttu-id="3c353-108">[fuori] Matrice di [valori di COR_FIELD_OFFSET.](../../../../docs/framework/unmanaged-api/metadata/cor-field-offset-structure.md)</span><span class="sxs-lookup"><span data-stu-id="3c353-108">[out] An array of [COR_FIELD_OFFSET](../../../../docs/framework/unmanaged-api/metadata/cor-field-offset-structure.md) values.</span></span>  
  
 `cMax`  
 <span data-ttu-id="3c353-109">[in] Dimensione massima della matrice `rFieldOffset`.</span><span class="sxs-lookup"><span data-stu-id="3c353-109">[in] The maximum size of the `rFieldOffset` array.</span></span>  
  
 `pcFieldOffset`  
 <span data-ttu-id="3c353-110">[fuori] Numero di elementi restituiti in `rFieldOffset`.</span><span class="sxs-lookup"><span data-stu-id="3c353-110">[out] The number of elements returned in `rFieldOffset`.</span></span>  
  
 `pulClassSize`  
 <span data-ttu-id="3c353-111">[fuori] Dimensione in byte della classe `td`rappresentata da .</span><span class="sxs-lookup"><span data-stu-id="3c353-111">[out] The size in bytes of the class represented by `td`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3c353-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3c353-112">Requirements</span></span>  
 <span data-ttu-id="3c353-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3c353-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3c353-114">**Intestazione:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="3c353-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3c353-115">**Biblioteca:** Incluso come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3c353-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3c353-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3c353-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c353-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3c353-117">See also</span></span>

- [<span data-ttu-id="3c353-118">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="3c353-118">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="3c353-119">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="3c353-119">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
