---
title: Metodo GetResolutionScope
ms.date: 03/30/2017
api_name:
- IALink.GetResolutionScope
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetResolutionScope
helpviewer_keywords:
- GetResolutionScope method
ms.assetid: 5b48ca60-dacd-44b2-9979-4a5122f00812
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a2bfb43002b79fd3e499272b87756bdc3ab0b589
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70787336"
---
# <a name="getresolutionscope-method"></a><span data-ttu-id="3f1e4-102">Metodo GetResolutionScope</span><span class="sxs-lookup"><span data-stu-id="3f1e4-102">GetResolutionScope Method</span></span>
<span data-ttu-id="3f1e4-103">Recupera l'ambito di un tipo specificato.</span><span class="sxs-lookup"><span data-stu-id="3f1e4-103">Retrieves the scope of a given type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f1e4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3f1e4-104">Syntax</span></span>  
  
```cpp  
HRESULT GetResolutionScope(  
    mdAssembly  AssemblyID,  
    mdToken     FileToken,  
    mdToken     TargetFile,  
    mdToken*    pScope  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="3f1e4-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="3f1e4-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="3f1e4-106">ID dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="3f1e4-106">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="3f1e4-107">File che necessita di un riferimento.</span><span class="sxs-lookup"><span data-stu-id="3f1e4-107">File that is in need of a reference.</span></span>  
  
 `TargetFile`  
 <span data-ttu-id="3f1e4-108">Token del file in cui è definito il tipo, generalmente recuperato con il [metodo ImportFile](importfile-method.md).</span><span class="sxs-lookup"><span data-stu-id="3f1e4-108">Token of file that type is defined in, usually retrieved with [ImportFile Method](importfile-method.md).</span></span>  
  
 `pScope`  
 <span data-ttu-id="3f1e4-109">Riceve il riferimento all'assembly o al modulo.</span><span class="sxs-lookup"><span data-stu-id="3f1e4-109">Receives the assembly or module reference.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3f1e4-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="3f1e4-110">Return Value</span></span>  
 <span data-ttu-id="3f1e4-111">Restituisce S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="3f1e4-111">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3f1e4-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3f1e4-112">Requirements</span></span>  
 <span data-ttu-id="3f1e4-113">Richiede ALink. h.</span><span class="sxs-lookup"><span data-stu-id="3f1e4-113">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f1e4-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3f1e4-114">See also</span></span>

- [<span data-ttu-id="3f1e4-115">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="3f1e4-115">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="3f1e4-116">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="3f1e4-116">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="3f1e4-117">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="3f1e4-117">ALink API</span></span>](index.md)
