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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b031fc35a4687a8535e3cb5e9ef2a53bab9fe376
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33445507"
---
# <a name="imetadataimportgetclasslayout-method"></a><span data-ttu-id="6bb58-102">Metodo IMetaDataImport::GetClassLayout</span><span class="sxs-lookup"><span data-stu-id="6bb58-102">IMetaDataImport::GetClassLayout Method</span></span>
<span data-ttu-id="6bb58-103">Ottiene le informazioni sul layout per la classe a cui fa riferimento il token TypeDef specificato.</span><span class="sxs-lookup"><span data-stu-id="6bb58-103">Gets layout information for the class referenced by the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6bb58-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6bb58-104">Syntax</span></span>  
  
```  
HRESULT GetClassLayout  (   
   [in]  mdTypeDef          td,   
   [out] DWORD              *pdwPackSize,  
   [out] COR_FIELD_OFFSET   rFieldOffset[],  
   [in]  ULONG              cMax,  
   [out] ULONG              *pcFieldOffset,  
   [out] ULONG              *pulClassSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6bb58-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="6bb58-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="6bb58-106">[in] Il token TypeDef per la classe con il layout da restituire.</span><span class="sxs-lookup"><span data-stu-id="6bb58-106">[in] The TypeDef token for the class with the layout to return.</span></span>  
  
 `pdwPackSize`  
 <span data-ttu-id="6bb58-107">[out] Uno dei valori 1, 2, 4, 8 o 16, che rappresenta la dimensione di compressione della classe.</span><span class="sxs-lookup"><span data-stu-id="6bb58-107">[out] One of the values 1, 2, 4, 8, or 16, representing the pack size of the class.</span></span>  
  
 `rFieldOffset`  
 <span data-ttu-id="6bb58-108">[out] Matrice di [COR_FIELD_OFFSET](../../../../docs/framework/unmanaged-api/metadata/cor-field-offset-structure.md) valori.</span><span class="sxs-lookup"><span data-stu-id="6bb58-108">[out] An array of [COR_FIELD_OFFSET](../../../../docs/framework/unmanaged-api/metadata/cor-field-offset-structure.md) values.</span></span>  
  
 `cMax`  
 <span data-ttu-id="6bb58-109">[in] Dimensione massima della matrice `rFieldOffset`.</span><span class="sxs-lookup"><span data-stu-id="6bb58-109">[in] The maximum size of the `rFieldOffset` array.</span></span>  
  
 `pcFieldOffset`  
 <span data-ttu-id="6bb58-110">[out] Il numero di elementi restituiti nella `rFieldOffset`.</span><span class="sxs-lookup"><span data-stu-id="6bb58-110">[out] The number of elements returned in `rFieldOffset`.</span></span>  
  
 `pulClassSize`  
 <span data-ttu-id="6bb58-111">[out] Le dimensioni in byte della classe rappresentata dall'oggetto `td`.</span><span class="sxs-lookup"><span data-stu-id="6bb58-111">[out] The size in bytes of the class represented by `td`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6bb58-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6bb58-112">Requirements</span></span>  
 <span data-ttu-id="6bb58-113">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6bb58-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6bb58-114">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="6bb58-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6bb58-115">**Libreria:** inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="6bb58-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6bb58-116">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6bb58-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6bb58-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6bb58-117">See Also</span></span>  
 [<span data-ttu-id="6bb58-118">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="6bb58-118">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="6bb58-119">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="6bb58-119">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
