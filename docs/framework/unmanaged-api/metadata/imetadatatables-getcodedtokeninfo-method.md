---
title: Metodo IMetaDataTables::GetCodedTokenInfo
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetCodedTokenInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetCodedTokenInfo
helpviewer_keywords:
- GetCodedTokenInfo method [.NET Framework metadata]
- IMetaDataTables::GetCodedTokenInfo method [.NET Framework metadata]
ms.assetid: 31214d3a-715e-49af-92b3-0fd11e4f218a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 11ab93e9cb4449ab77e5e9c4da81073aaf432382
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54669692"
---
# <a name="imetadatatablesgetcodedtokeninfo-method"></a><span data-ttu-id="a3f85-102">Metodo IMetaDataTables::GetCodedTokenInfo</span><span class="sxs-lookup"><span data-stu-id="a3f85-102">IMetaDataTables::GetCodedTokenInfo Method</span></span>
<span data-ttu-id="a3f85-103">Ottiene un puntatore a una matrice dei token associato con l'indice di riga specificato.</span><span class="sxs-lookup"><span data-stu-id="a3f85-103">Gets a pointer to an array of tokens associated with the specified row index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3f85-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a3f85-104">Syntax</span></span>  
  
```  
HRESULT GetCodedTokenInfo (   
    [in]  ULONG       ixCdTkn,  
    [out] ULONG       *pcTokens,  
    [out] ULONG       **ppTokens,  
    [out] const char  **ppName  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a3f85-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a3f85-105">Parameters</span></span>  
 `ixCdTkn`  
 <span data-ttu-id="a3f85-106">[in] Tipo di token codificato da restituire.</span><span class="sxs-lookup"><span data-stu-id="a3f85-106">[in] The kind of coded token to return.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="a3f85-107">[out] Un puntatore alla lunghezza di `ppTokens`.</span><span class="sxs-lookup"><span data-stu-id="a3f85-107">[out] A pointer to the length of `ppTokens`.</span></span>  
  
 `ppTokens`  
 <span data-ttu-id="a3f85-108">[out] Un puntatore a un puntatore a una matrice che contiene l'elenco dei token restituito.</span><span class="sxs-lookup"><span data-stu-id="a3f85-108">[out] A pointer to a pointer to an array that contains the list of returned tokens.</span></span>  
  
 `ppName`  
 <span data-ttu-id="a3f85-109">[out] Un puntatore a un puntatore al nome del token in `ixCdTkn`.</span><span class="sxs-lookup"><span data-stu-id="a3f85-109">[out] A pointer to a pointer to the name of the token at `ixCdTkn`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a3f85-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a3f85-110">Requirements</span></span>  
 <span data-ttu-id="a3f85-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a3f85-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a3f85-112">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="a3f85-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a3f85-113">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="a3f85-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a3f85-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a3f85-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3f85-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a3f85-115">See also</span></span>
- [<span data-ttu-id="a3f85-116">Interfaccia IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="a3f85-116">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="a3f85-117">Interfaccia IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="a3f85-117">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
