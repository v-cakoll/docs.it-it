---
title: Metodo EnumCustomAttributes
ms.date: 03/30/2017
api_name:
- EnumCustomAttributes
- IALink.EnumCustomAttributes
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EnumCustomAttributes
helpviewer_keywords:
- EnumCustomAttributes method
ms.assetid: 08dff60c-f01b-4050-8865-ea3f95361c9f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b419962982fc80591ed565cceb28afb88a39495e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59199141"
---
# <a name="enumcustomattributes-method"></a><span data-ttu-id="9fec5-102">Metodo EnumCustomAttributes</span><span class="sxs-lookup"><span data-stu-id="9fec5-102">EnumCustomAttributes Method</span></span>
<span data-ttu-id="9fec5-103">Recupera gli attributi personalizzati a livello di assembly.</span><span class="sxs-lookup"><span data-stu-id="9fec5-103">Retrieves assembly-level custom attributes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9fec5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9fec5-104">Syntax</span></span>  
  
```  
HRESULT EnumCustomAttributes(  
    HALINKENUM hEnum,  
    mdToken tkType,  
    mdCustomAttribute rCustomValues[],  
    ULONG cMax,  
    ULONG* pcCustomValues  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="9fec5-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="9fec5-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="9fec5-106">Handle dell'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="9fec5-106">Handle of enumerator.</span></span>  
  
 `tkType`  
 <span data-ttu-id="9fec5-107">Tipo degli attributi da enumerare.</span><span class="sxs-lookup"><span data-stu-id="9fec5-107">Type of attributes to be enumerated.</span></span> <span data-ttu-id="9fec5-108">Usare `mdTokenNill` per tutti gli attributi.</span><span class="sxs-lookup"><span data-stu-id="9fec5-108">Use `mdTokenNill` for all attributes.</span></span>  
  
 `rCustomValues`  
 <span data-ttu-id="9fec5-109">Riceve i token di attributi personalizzati.</span><span class="sxs-lookup"><span data-stu-id="9fec5-109">Receives custom attributes tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="9fec5-110">Specifica la dimensione di `rCustomValues` matrice.</span><span class="sxs-lookup"><span data-stu-id="9fec5-110">Specifies size of `rCustomValues` array.</span></span>  
  
 `pcCustomValues`  
 <span data-ttu-id="9fec5-111">Facoltativamente, riceve il numero di valori del token.</span><span class="sxs-lookup"><span data-stu-id="9fec5-111">Optionally receives count of token values.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9fec5-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="9fec5-112">Return Value</span></span>  
 <span data-ttu-id="9fec5-113">Restituisce S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="9fec5-113">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9fec5-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9fec5-114">Requirements</span></span>  
 <span data-ttu-id="9fec5-115">Richiede alink.h</span><span class="sxs-lookup"><span data-stu-id="9fec5-115">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9fec5-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9fec5-116">See also</span></span>

- [<span data-ttu-id="9fec5-117">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="9fec5-117">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="9fec5-118">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="9fec5-118">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="9fec5-119">API Alink</span><span class="sxs-lookup"><span data-stu-id="9fec5-119">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
