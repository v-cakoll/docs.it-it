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
ms.openlocfilehash: 8ac12d5b6bc2911e3bd879285a9a12f65c426f0d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67745850"
---
# <a name="imaptokenmap-method"></a><span data-ttu-id="8667a-102">Metodo IMapToken::Map</span><span class="sxs-lookup"><span data-stu-id="8667a-102">IMapToken::Map Method</span></span>
<span data-ttu-id="8667a-103">Esegue il mapping di una relazione tra gli assembly che utilizzano le firme di metadati.</span><span class="sxs-lookup"><span data-stu-id="8667a-103">Maps a relationship between the assemblies using metadata signatures.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8667a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8667a-104">Syntax</span></span>  
  
```cpp  
HRESULT Map (  
    [in]  mdToken tkImp,   
    [in]  mdToken tkEmit  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8667a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="8667a-105">Parameters</span></span>  
 `tkImp`  
 <span data-ttu-id="8667a-106">[in] Il token di metadati che rappresenta l'oggetto di codice importati.</span><span class="sxs-lookup"><span data-stu-id="8667a-106">[in] The metadata token that represents the imported code object.</span></span>  
  
 `tkEmit`  
 <span data-ttu-id="8667a-107">[in] Il token di metadati che rappresenta l'oggetto di codice generato.</span><span class="sxs-lookup"><span data-stu-id="8667a-107">[in] The metadata token that represents the emitted code object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8667a-108">Note</span><span class="sxs-lookup"><span data-stu-id="8667a-108">Remarks</span></span>  
 <span data-ttu-id="8667a-109">Quando la modifica del mapping dei token si verifica durante un'operazione di unione, il token originale è con ambito nell'ambito dei metadati importati (origine) e il nuovo token è con ambito nell'ambito dei metadati generato (destinazione).</span><span class="sxs-lookup"><span data-stu-id="8667a-109">When the token re-map occurs during a merge, the original token is scoped in the imported (source) metadata scope and the new token is scoped in the emitted (target) metadata scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8667a-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8667a-110">Requirements</span></span>  
 <span data-ttu-id="8667a-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8667a-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8667a-112">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="8667a-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8667a-113">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="8667a-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8667a-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8667a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8667a-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8667a-115">See also</span></span>

- [<span data-ttu-id="8667a-116">Interfaccia IMapToken</span><span class="sxs-lookup"><span data-stu-id="8667a-116">IMapToken Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md)
