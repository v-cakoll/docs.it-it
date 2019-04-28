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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61789974"
---
# <a name="enumcustomattributes-method"></a><span data-ttu-id="970e6-102">Metodo EnumCustomAttributes</span><span class="sxs-lookup"><span data-stu-id="970e6-102">EnumCustomAttributes Method</span></span>
<span data-ttu-id="970e6-103">Recupera gli attributi personalizzati a livello di assembly.</span><span class="sxs-lookup"><span data-stu-id="970e6-103">Retrieves assembly-level custom attributes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="970e6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="970e6-104">Syntax</span></span>  
  
```  
HRESULT EnumCustomAttributes(  
    HALINKENUM hEnum,  
    mdToken tkType,  
    mdCustomAttribute rCustomValues[],  
    ULONG cMax,  
    ULONG* pcCustomValues  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="970e6-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="970e6-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="970e6-106">Handle dell'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="970e6-106">Handle of enumerator.</span></span>  
  
 `tkType`  
 <span data-ttu-id="970e6-107">Tipo degli attributi da enumerare.</span><span class="sxs-lookup"><span data-stu-id="970e6-107">Type of attributes to be enumerated.</span></span> <span data-ttu-id="970e6-108">Usare `mdTokenNill` per tutti gli attributi.</span><span class="sxs-lookup"><span data-stu-id="970e6-108">Use `mdTokenNill` for all attributes.</span></span>  
  
 `rCustomValues`  
 <span data-ttu-id="970e6-109">Riceve i token di attributi personalizzati.</span><span class="sxs-lookup"><span data-stu-id="970e6-109">Receives custom attributes tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="970e6-110">Specifica la dimensione di `rCustomValues` matrice.</span><span class="sxs-lookup"><span data-stu-id="970e6-110">Specifies size of `rCustomValues` array.</span></span>  
  
 `pcCustomValues`  
 <span data-ttu-id="970e6-111">Facoltativamente, riceve il numero di valori del token.</span><span class="sxs-lookup"><span data-stu-id="970e6-111">Optionally receives count of token values.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="970e6-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="970e6-112">Return Value</span></span>  
 <span data-ttu-id="970e6-113">Restituisce S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="970e6-113">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="970e6-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="970e6-114">Requirements</span></span>  
 <span data-ttu-id="970e6-115">Richiede alink.h</span><span class="sxs-lookup"><span data-stu-id="970e6-115">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="970e6-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="970e6-116">See also</span></span>

- [<span data-ttu-id="970e6-117">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="970e6-117">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="970e6-118">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="970e6-118">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="970e6-119">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="970e6-119">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
