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
ms.openlocfilehash: 09ccf731f0494b6eda49f6a15d04970a723c473b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67742065"
---
# <a name="enumcustomattributes-method"></a><span data-ttu-id="8ccb4-102">Metodo EnumCustomAttributes</span><span class="sxs-lookup"><span data-stu-id="8ccb4-102">EnumCustomAttributes Method</span></span>
<span data-ttu-id="8ccb4-103">Recupera gli attributi personalizzati a livello di assembly.</span><span class="sxs-lookup"><span data-stu-id="8ccb4-103">Retrieves assembly-level custom attributes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ccb4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8ccb4-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumCustomAttributes(  
    HALINKENUM hEnum,  
    mdToken tkType,  
    mdCustomAttribute rCustomValues[],  
    ULONG cMax,  
    ULONG* pcCustomValues  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="8ccb4-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="8ccb4-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="8ccb4-106">Handle dell'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="8ccb4-106">Handle of enumerator.</span></span>  
  
 `tkType`  
 <span data-ttu-id="8ccb4-107">Tipo degli attributi da enumerare.</span><span class="sxs-lookup"><span data-stu-id="8ccb4-107">Type of attributes to be enumerated.</span></span> <span data-ttu-id="8ccb4-108">Usare `mdTokenNill` per tutti gli attributi.</span><span class="sxs-lookup"><span data-stu-id="8ccb4-108">Use `mdTokenNill` for all attributes.</span></span>  
  
 `rCustomValues`  
 <span data-ttu-id="8ccb4-109">Riceve i token di attributi personalizzati.</span><span class="sxs-lookup"><span data-stu-id="8ccb4-109">Receives custom attributes tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="8ccb4-110">Specifica la dimensione di `rCustomValues` matrice.</span><span class="sxs-lookup"><span data-stu-id="8ccb4-110">Specifies size of `rCustomValues` array.</span></span>  
  
 `pcCustomValues`  
 <span data-ttu-id="8ccb4-111">Facoltativamente, riceve il numero di valori del token.</span><span class="sxs-lookup"><span data-stu-id="8ccb4-111">Optionally receives count of token values.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8ccb4-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="8ccb4-112">Return Value</span></span>  
 <span data-ttu-id="8ccb4-113">Restituisce S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="8ccb4-113">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8ccb4-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8ccb4-114">Requirements</span></span>  
 <span data-ttu-id="8ccb4-115">Richiede alink.h</span><span class="sxs-lookup"><span data-stu-id="8ccb4-115">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ccb4-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8ccb4-116">See also</span></span>

- [<span data-ttu-id="8ccb4-117">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="8ccb4-117">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="8ccb4-118">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="8ccb4-118">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="8ccb4-119">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="8ccb4-119">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
