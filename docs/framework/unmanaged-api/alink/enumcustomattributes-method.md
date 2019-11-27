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
ms.openlocfilehash: 6a5b3f1e9bf1444feb73949ef7133fbd9ae35134
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446468"
---
# <a name="enumcustomattributes-method"></a><span data-ttu-id="b8452-102">Metodo EnumCustomAttributes</span><span class="sxs-lookup"><span data-stu-id="b8452-102">EnumCustomAttributes Method</span></span>
<span data-ttu-id="b8452-103">Recupera gli attributi personalizzati a livello di assembly.</span><span class="sxs-lookup"><span data-stu-id="b8452-103">Retrieves assembly-level custom attributes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8452-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b8452-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumCustomAttributes(  
    HALINKENUM hEnum,  
    mdToken tkType,  
    mdCustomAttribute rCustomValues[],  
    ULONG cMax,  
    ULONG* pcCustomValues  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="b8452-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b8452-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="b8452-106">Handle dell'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="b8452-106">Handle of enumerator.</span></span>  
  
 `tkType`  
 <span data-ttu-id="b8452-107">Tipo di attributi da enumerare.</span><span class="sxs-lookup"><span data-stu-id="b8452-107">Type of attributes to be enumerated.</span></span> <span data-ttu-id="b8452-108">Usare `mdTokenNill` per tutti gli attributi.</span><span class="sxs-lookup"><span data-stu-id="b8452-108">Use `mdTokenNill` for all attributes.</span></span>  
  
 `rCustomValues`  
 <span data-ttu-id="b8452-109">Riceve i token degli attributi personalizzati.</span><span class="sxs-lookup"><span data-stu-id="b8452-109">Receives custom attributes tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="b8452-110">Specifica le dimensioni della matrice `rCustomValues`.</span><span class="sxs-lookup"><span data-stu-id="b8452-110">Specifies size of `rCustomValues` array.</span></span>  
  
 `pcCustomValues`  
 <span data-ttu-id="b8452-111">Riceve facoltativamente il numero di valori di token.</span><span class="sxs-lookup"><span data-stu-id="b8452-111">Optionally receives count of token values.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b8452-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="b8452-112">Return Value</span></span>  
 <span data-ttu-id="b8452-113">Restituisce S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="b8452-113">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b8452-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b8452-114">Requirements</span></span>  
 <span data-ttu-id="b8452-115">Richiede ALink. h</span><span class="sxs-lookup"><span data-stu-id="b8452-115">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8452-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b8452-116">See also</span></span>

- [<span data-ttu-id="b8452-117">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="b8452-117">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="b8452-118">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="b8452-118">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="b8452-119">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="b8452-119">ALink API</span></span>](index.md)
