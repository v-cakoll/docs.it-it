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
ms.openlocfilehash: c6c2e741df594e265fdef51a602a9a4927733b7c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67741868"
---
# <a name="getresolutionscope-method"></a><span data-ttu-id="e19a2-102">Metodo GetResolutionScope</span><span class="sxs-lookup"><span data-stu-id="e19a2-102">GetResolutionScope Method</span></span>
<span data-ttu-id="e19a2-103">Recupera l'ambito di un determinato tipo.</span><span class="sxs-lookup"><span data-stu-id="e19a2-103">Retrieves the scope of a given type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e19a2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e19a2-104">Syntax</span></span>  
  
```cpp  
HRESULT GetResolutionScope(  
    mdAssembly  AssemblyID,  
    mdToken     FileToken,  
    mdToken     TargetFile,  
    mdToken*    pScope  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="e19a2-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e19a2-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="e19a2-106">ID dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="e19a2-106">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="e19a2-107">File che richiede un riferimento.</span><span class="sxs-lookup"><span data-stu-id="e19a2-107">File that is in need of a reference.</span></span>  
  
 `TargetFile`  
 <span data-ttu-id="e19a2-108">Token del file di tipo è definito, in genere recuperato mediante [metodo ImportFile](../../../../docs/framework/unmanaged-api/alink/importfile-method.md).</span><span class="sxs-lookup"><span data-stu-id="e19a2-108">Token of file that type is defined in, usually retrieved with [ImportFile Method](../../../../docs/framework/unmanaged-api/alink/importfile-method.md).</span></span>  
  
 `pScope`  
 <span data-ttu-id="e19a2-109">Riceve il riferimento all'assembly o modulo.</span><span class="sxs-lookup"><span data-stu-id="e19a2-109">Receives the assembly or module reference.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e19a2-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="e19a2-110">Return Value</span></span>  
 <span data-ttu-id="e19a2-111">Restituisce S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="e19a2-111">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e19a2-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e19a2-112">Requirements</span></span>  
 <span data-ttu-id="e19a2-113">Richiede alink.h.</span><span class="sxs-lookup"><span data-stu-id="e19a2-113">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e19a2-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e19a2-114">See also</span></span>

- [<span data-ttu-id="e19a2-115">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="e19a2-115">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="e19a2-116">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="e19a2-116">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="e19a2-117">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="e19a2-117">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
