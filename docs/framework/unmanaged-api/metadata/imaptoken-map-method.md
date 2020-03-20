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
ms.openlocfilehash: 428b022ed560648f59798154d5987d382938c280
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176071"
---
# <a name="imaptokenmap-method"></a><span data-ttu-id="fa89b-102">Metodo IMapToken::Map</span><span class="sxs-lookup"><span data-stu-id="fa89b-102">IMapToken::Map Method</span></span>
<span data-ttu-id="fa89b-103">Esegue il mapping di una relazione tra gli assembly utilizzando le firme dei metadati.</span><span class="sxs-lookup"><span data-stu-id="fa89b-103">Maps a relationship between the assemblies using metadata signatures.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa89b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fa89b-104">Syntax</span></span>  
  
```cpp  
HRESULT Map (  
    [in]  mdToken tkImp,
    [in]  mdToken tkEmit  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fa89b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="fa89b-105">Parameters</span></span>  
 `tkImp`  
 <span data-ttu-id="fa89b-106">[in] Token di metadati che rappresenta l'oggetto di codice importato.</span><span class="sxs-lookup"><span data-stu-id="fa89b-106">[in] The metadata token that represents the imported code object.</span></span>  
  
 `tkEmit`  
 <span data-ttu-id="fa89b-107">[in] Token di metadati che rappresenta l'oggetto di codice generato.</span><span class="sxs-lookup"><span data-stu-id="fa89b-107">[in] The metadata token that represents the emitted code object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fa89b-108">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="fa89b-108">Remarks</span></span>  
 <span data-ttu-id="fa89b-109">Quando il rimappatura del token si verifica durante un'unione, l'ambito del token originale viene definito nell'ambito dei metadati importati (origine) e il nuovo token viene definito nell'ambito dei metadati generato (destinazione).</span><span class="sxs-lookup"><span data-stu-id="fa89b-109">When the token re-map occurs during a merge, the original token is scoped in the imported (source) metadata scope and the new token is scoped in the emitted (target) metadata scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa89b-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fa89b-110">Requirements</span></span>  
 <span data-ttu-id="fa89b-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fa89b-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fa89b-112">**Intestazione:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="fa89b-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fa89b-113">**Biblioteca:** Utilizzato come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="fa89b-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="fa89b-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fa89b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa89b-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fa89b-115">See also</span></span>

- [<span data-ttu-id="fa89b-116">Interfaccia IMapToken</span><span class="sxs-lookup"><span data-stu-id="fa89b-116">IMapToken Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md)
