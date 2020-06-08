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
ms.openlocfilehash: 8ab16ad5b2b2838125e07511ef47be737f40671c
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501209"
---
# <a name="imetadatatablesgetcodedtokeninfo-method"></a><span data-ttu-id="a8b9e-102">Metodo IMetaDataTables::GetCodedTokenInfo</span><span class="sxs-lookup"><span data-stu-id="a8b9e-102">IMetaDataTables::GetCodedTokenInfo Method</span></span>
<span data-ttu-id="a8b9e-103">Ottiene un puntatore a una matrice di token associati all'indice di riga specificato.</span><span class="sxs-lookup"><span data-stu-id="a8b9e-103">Gets a pointer to an array of tokens associated with the specified row index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8b9e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a8b9e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCodedTokenInfo (
    [in]  ULONG       ixCdTkn,  
    [out] ULONG       *pcTokens,  
    [out] ULONG       **ppTokens,  
    [out] const char  **ppName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a8b9e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a8b9e-105">Parameters</span></span>  
 `ixCdTkn`  
 <span data-ttu-id="a8b9e-106">in Tipo di token codificato da restituire.</span><span class="sxs-lookup"><span data-stu-id="a8b9e-106">[in] The kind of coded token to return.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="a8b9e-107">out Puntatore alla lunghezza di `ppTokens` .</span><span class="sxs-lookup"><span data-stu-id="a8b9e-107">[out] A pointer to the length of `ppTokens`.</span></span>  
  
 `ppTokens`  
 <span data-ttu-id="a8b9e-108">out Puntatore a un puntatore a una matrice che contiene l'elenco dei token restituiti.</span><span class="sxs-lookup"><span data-stu-id="a8b9e-108">[out] A pointer to a pointer to an array that contains the list of returned tokens.</span></span>  
  
 `ppName`  
 <span data-ttu-id="a8b9e-109">out Puntatore a un puntatore al nome del token in `ixCdTkn` .</span><span class="sxs-lookup"><span data-stu-id="a8b9e-109">[out] A pointer to a pointer to the name of the token at `ixCdTkn`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a8b9e-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a8b9e-110">Requirements</span></span>  
 <span data-ttu-id="a8b9e-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a8b9e-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a8b9e-112">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="a8b9e-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a8b9e-113">**Libreria:** Usato come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="a8b9e-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a8b9e-114">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a8b9e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8b9e-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a8b9e-115">See also</span></span>

- [<span data-ttu-id="a8b9e-116">Interfaccia IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="a8b9e-116">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="a8b9e-117">Interfaccia IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="a8b9e-117">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
