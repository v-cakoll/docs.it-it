---
title: Metodo IMetaDataImport::GetTypeSpecFromToken
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetTypeSpecFromToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetTypeSpecFromToken
helpviewer_keywords:
- GetTypeSpecFromToken method [.NET Framework metadata]
- IMetaDataImport::GetTypeSpecFromToken method [.NET Framework metadata]
ms.assetid: ee518bda-3296-482e-a7b7-e9d51dd1a181
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 362cbe9ff19e74bafc73fde857d231185179efbe
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59079552"
---
# <a name="imetadataimportgettypespecfromtoken-method"></a><span data-ttu-id="a45ab-102">Metodo IMetaDataImport::GetTypeSpecFromToken</span><span class="sxs-lookup"><span data-stu-id="a45ab-102">IMetaDataImport::GetTypeSpecFromToken Method</span></span>
<span data-ttu-id="a45ab-103">Ottiene la firma binaria dei metadati della specifica del tipo rappresentata dal token indicato.</span><span class="sxs-lookup"><span data-stu-id="a45ab-103">Gets the binary metadata signature of the type specification represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a45ab-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a45ab-104">Syntax</span></span>  
  
```  
HRESULT GetTypeSpecFromToken (   
   [in]  mdTypeSpec            typespec,   
   [out] PCCOR_SIGNATURE       *ppvSig,   
   [out] ULONG                 *pcbSig  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a45ab-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a45ab-105">Parameters</span></span>  
 `typespec`  
 <span data-ttu-id="a45ab-106">[in] Il token TypeSpec associato alla firma richiesta dei metadati.</span><span class="sxs-lookup"><span data-stu-id="a45ab-106">[in] The TypeSpec token associated with the requested metadata signature.</span></span>  
  
 `ppvSig`  
 <span data-ttu-id="a45ab-107">[out] Un puntatore per la firma binaria dei metadati.</span><span class="sxs-lookup"><span data-stu-id="a45ab-107">[out] A pointer to the binary metadata signature.</span></span>  
  
 `pcbSig`  
 <span data-ttu-id="a45ab-108">[out] Le dimensioni, in byte, della firma dei metadati.</span><span class="sxs-lookup"><span data-stu-id="a45ab-108">[out] The size, in bytes, of the metadata signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a45ab-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="a45ab-109">Return Value</span></span>  
 <span data-ttu-id="a45ab-110">HRESULT che indica l'esito positivo o negativo.</span><span class="sxs-lookup"><span data-stu-id="a45ab-110">An HRESULT that indicates success or failure.</span></span> <span data-ttu-id="a45ab-111">Gli errori possono essere testati con la macro FAILED.</span><span class="sxs-lookup"><span data-stu-id="a45ab-111">Failures can be tested with the FAILED macro.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a45ab-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a45ab-112">Requirements</span></span>  
 <span data-ttu-id="a45ab-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a45ab-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a45ab-114">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="a45ab-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a45ab-115">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="a45ab-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a45ab-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a45ab-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a45ab-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a45ab-117">See also</span></span>

- [<span data-ttu-id="a45ab-118">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="a45ab-118">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="a45ab-119">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="a45ab-119">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
