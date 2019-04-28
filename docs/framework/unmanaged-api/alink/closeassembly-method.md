---
title: Metodo CloseAssembly
ms.date: 03/30/2017
api_name:
- IALink.CloseAssembly
- CloseAssembly
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- CloseAssembly
helpviewer_keywords:
- CloseAssembly method
ms.assetid: f66a43bc-a5c5-4190-acbe-63fd27640634
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 94c1c083d010cd82fd9e9e2f02b23e81d88fedd5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61790091"
---
# <a name="closeassembly-method"></a><span data-ttu-id="e8ccc-102">Metodo CloseAssembly</span><span class="sxs-lookup"><span data-stu-id="e8ccc-102">CloseAssembly Method</span></span>
<span data-ttu-id="e8ccc-103">Consente di finalizzare le operazioni di assembly.</span><span class="sxs-lookup"><span data-stu-id="e8ccc-103">Finalizes assembly operations.</span></span> <span data-ttu-id="e8ccc-104">Chiamare questo metodo prima di iniziare un nuovo assembly o un modulo non associato.</span><span class="sxs-lookup"><span data-stu-id="e8ccc-104">Call this method before beginning a new assembly or unbound module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8ccc-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e8ccc-105">Syntax</span></span>  
  
```  
HRESULT CloseAssembly(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="e8ccc-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="e8ccc-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="e8ccc-107">ID dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="e8ccc-107">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e8ccc-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="e8ccc-108">Return Value</span></span>  
 <span data-ttu-id="e8ccc-109">Restituisce S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="e8ccc-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e8ccc-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e8ccc-110">Requirements</span></span>  
 <span data-ttu-id="e8ccc-111">Richiede alink.h.</span><span class="sxs-lookup"><span data-stu-id="e8ccc-111">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8ccc-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e8ccc-112">See also</span></span>

- [<span data-ttu-id="e8ccc-113">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="e8ccc-113">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="e8ccc-114">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="e8ccc-114">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="e8ccc-115">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="e8ccc-115">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
