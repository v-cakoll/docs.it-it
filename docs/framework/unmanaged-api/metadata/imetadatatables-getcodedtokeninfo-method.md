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
ms.openlocfilehash: 64c70fe0b657047ae35dccb763fa57120403deef
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177147"
---
# <a name="imetadatatablesgetcodedtokeninfo-method"></a><span data-ttu-id="bb838-102">Metodo IMetaDataTables::GetCodedTokenInfo</span><span class="sxs-lookup"><span data-stu-id="bb838-102">IMetaDataTables::GetCodedTokenInfo Method</span></span>
<span data-ttu-id="bb838-103">Ottiene un puntatore a una matrice di token associati all'indice di riga specificato.</span><span class="sxs-lookup"><span data-stu-id="bb838-103">Gets a pointer to an array of tokens associated with the specified row index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb838-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bb838-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCodedTokenInfo (
    [in]  ULONG       ixCdTkn,  
    [out] ULONG       *pcTokens,  
    [out] ULONG       **ppTokens,  
    [out] const char  **ppName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bb838-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="bb838-105">Parameters</span></span>  
 `ixCdTkn`  
 <span data-ttu-id="bb838-106">[in] Tipo di token codificato da restituire.</span><span class="sxs-lookup"><span data-stu-id="bb838-106">[in] The kind of coded token to return.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="bb838-107">[fuori] Puntatore alla lunghezza `ppTokens`di .</span><span class="sxs-lookup"><span data-stu-id="bb838-107">[out] A pointer to the length of `ppTokens`.</span></span>  
  
 `ppTokens`  
 <span data-ttu-id="bb838-108">[fuori] Puntatore a un puntatore a una matrice che contiene l'elenco di token restituiti.</span><span class="sxs-lookup"><span data-stu-id="bb838-108">[out] A pointer to a pointer to an array that contains the list of returned tokens.</span></span>  
  
 `ppName`  
 <span data-ttu-id="bb838-109">[fuori] Puntatore a un puntatore al `ixCdTkn`nome del token in .</span><span class="sxs-lookup"><span data-stu-id="bb838-109">[out] A pointer to a pointer to the name of the token at `ixCdTkn`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bb838-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="bb838-110">Requirements</span></span>  
 <span data-ttu-id="bb838-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bb838-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bb838-112">**Intestazione:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="bb838-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="bb838-113">**Biblioteca:** Utilizzato come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="bb838-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="bb838-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bb838-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb838-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bb838-115">See also</span></span>

- [<span data-ttu-id="bb838-116">Interfaccia IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="bb838-116">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="bb838-117">Interfaccia IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="bb838-117">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
