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
ms.openlocfilehash: 6c6d298c84b801b87832c56026b05f647cb5a9dd
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59135180"
---
# <a name="getresolutionscope-method"></a><span data-ttu-id="aaa73-102">Metodo GetResolutionScope</span><span class="sxs-lookup"><span data-stu-id="aaa73-102">GetResolutionScope Method</span></span>
<span data-ttu-id="aaa73-103">Recupera l'ambito di un determinato tipo.</span><span class="sxs-lookup"><span data-stu-id="aaa73-103">Retrieves the scope of a given type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aaa73-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="aaa73-104">Syntax</span></span>  
  
```  
HRESULT GetResolutionScope(  
    mdAssembly  AssemblyID,  
    mdToken     FileToken,  
    mdToken     TargetFile,  
    mdToken*    pScope  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="aaa73-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="aaa73-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="aaa73-106">ID dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="aaa73-106">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="aaa73-107">File che richiede un riferimento.</span><span class="sxs-lookup"><span data-stu-id="aaa73-107">File that is in need of a reference.</span></span>  
  
 `TargetFile`  
 <span data-ttu-id="aaa73-108">Token del file di tipo è definito, in genere recuperato mediante [metodo ImportFile](../../../../docs/framework/unmanaged-api/alink/importfile-method.md).</span><span class="sxs-lookup"><span data-stu-id="aaa73-108">Token of file that type is defined in, usually retrieved with [ImportFile Method](../../../../docs/framework/unmanaged-api/alink/importfile-method.md).</span></span>  
  
 `pScope`  
 <span data-ttu-id="aaa73-109">Riceve il riferimento all'assembly o modulo.</span><span class="sxs-lookup"><span data-stu-id="aaa73-109">Receives the assembly or module reference.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="aaa73-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="aaa73-110">Return Value</span></span>  
 <span data-ttu-id="aaa73-111">Restituisce S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="aaa73-111">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aaa73-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="aaa73-112">Requirements</span></span>  
 <span data-ttu-id="aaa73-113">Richiede alink.h.</span><span class="sxs-lookup"><span data-stu-id="aaa73-113">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aaa73-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aaa73-114">See also</span></span>

- [<span data-ttu-id="aaa73-115">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="aaa73-115">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="aaa73-116">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="aaa73-116">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="aaa73-117">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="aaa73-117">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
