---
title: Metodo IMapToken::Map
ms.date: 03/30/2017
api_name:
- IMapToken.Map
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMapToken::Map
helpviewer_keywords:
- IMapToken::Map method [.NET Framework metadata]
- Map method [.NET Framework metadata]
ms.assetid: b9b4bf2f-1098-43d6-9619-a99b4bda1940
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 31c18061ad5f21e26665cd0d6883b0eb26afd1d4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54557475"
---
# <a name="imaptokenmap-method"></a><span data-ttu-id="deda4-102">Metodo IMapToken::Map</span><span class="sxs-lookup"><span data-stu-id="deda4-102">IMapToken::Map Method</span></span>
<span data-ttu-id="deda4-103">Esegue il mapping di una relazione tra gli assembly che utilizzano le firme di metadati.</span><span class="sxs-lookup"><span data-stu-id="deda4-103">Maps a relationship between the assemblies using metadata signatures.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="deda4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="deda4-104">Syntax</span></span>  
  
```  
HRESULT Map (  
    [in]  mdToken tkImp,   
    [in]  mdToken tkEmit  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="deda4-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="deda4-105">Parameters</span></span>  
 `tkImp`  
 <span data-ttu-id="deda4-106">[in] Il token di metadati che rappresenta l'oggetto di codice importati.</span><span class="sxs-lookup"><span data-stu-id="deda4-106">[in] The metadata token that represents the imported code object.</span></span>  
  
 `tkEmit`  
 <span data-ttu-id="deda4-107">[in] Il token di metadati che rappresenta l'oggetto di codice generato.</span><span class="sxs-lookup"><span data-stu-id="deda4-107">[in] The metadata token that represents the emitted code object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="deda4-108">Note</span><span class="sxs-lookup"><span data-stu-id="deda4-108">Remarks</span></span>  
 <span data-ttu-id="deda4-109">Quando la modifica del mapping dei token si verifica durante un'operazione di unione, il token originale è con ambito nell'ambito dei metadati importati (origine) e il nuovo token è con ambito nell'ambito dei metadati generato (destinazione).</span><span class="sxs-lookup"><span data-stu-id="deda4-109">When the token re-map occurs during a merge, the original token is scoped in the imported (source) metadata scope and the new token is scoped in the emitted (target) metadata scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="deda4-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="deda4-110">Requirements</span></span>  
 <span data-ttu-id="deda4-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="deda4-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="deda4-112">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="deda4-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="deda4-113">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="deda4-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="deda4-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="deda4-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="deda4-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="deda4-115">See also</span></span>
- [<span data-ttu-id="deda4-116">Interfaccia IMapToken</span><span class="sxs-lookup"><span data-stu-id="deda4-116">IMapToken Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md)
