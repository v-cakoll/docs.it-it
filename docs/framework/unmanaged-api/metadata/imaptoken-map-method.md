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
ms.openlocfilehash: 027694cee1b3e4d990796ba31300918f6d859679
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008196"
---
# <a name="imaptokenmap-method"></a><span data-ttu-id="2db94-102">Metodo IMapToken::Map</span><span class="sxs-lookup"><span data-stu-id="2db94-102">IMapToken::Map Method</span></span>
<span data-ttu-id="2db94-103">Esegue il mapping di una relazione tra gli assembly utilizzando le firme dei metadati.</span><span class="sxs-lookup"><span data-stu-id="2db94-103">Maps a relationship between the assemblies using metadata signatures.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2db94-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2db94-104">Syntax</span></span>  
  
```cpp  
HRESULT Map (  
    [in]  mdToken tkImp,
    [in]  mdToken tkEmit  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2db94-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="2db94-105">Parameters</span></span>  
 `tkImp`  
 <span data-ttu-id="2db94-106">in Token di metadati che rappresenta l'oggetto di codice importato.</span><span class="sxs-lookup"><span data-stu-id="2db94-106">[in] The metadata token that represents the imported code object.</span></span>  
  
 `tkEmit`  
 <span data-ttu-id="2db94-107">in Token di metadati che rappresenta l'oggetto di codice emesso.</span><span class="sxs-lookup"><span data-stu-id="2db94-107">[in] The metadata token that represents the emitted code object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2db94-108">Commenti</span><span class="sxs-lookup"><span data-stu-id="2db94-108">Remarks</span></span>  
 <span data-ttu-id="2db94-109">Quando il mapping del token viene eseguito durante un'operazione di merge, il token originale viene definito nell'ambito dei metadati importati (di origine) e l'ambito del nuovo token viene definito nell'ambito dei metadati generato (destinazione).</span><span class="sxs-lookup"><span data-stu-id="2db94-109">When the token re-map occurs during a merge, the original token is scoped in the imported (source) metadata scope and the new token is scoped in the emitted (target) metadata scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2db94-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2db94-110">Requirements</span></span>  
 <span data-ttu-id="2db94-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2db94-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2db94-112">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="2db94-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2db94-113">**Libreria:** Usato come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="2db94-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2db94-114">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2db94-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2db94-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2db94-115">See also</span></span>

- [<span data-ttu-id="2db94-116">Interfaccia IMapToken</span><span class="sxs-lookup"><span data-stu-id="2db94-116">IMapToken Interface</span></span>](imaptoken-interface.md)
