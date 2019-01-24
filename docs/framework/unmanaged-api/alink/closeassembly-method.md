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
ms.openlocfilehash: aa415926f4a818f697812f1a3c5531cb0ab7081b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54510169"
---
# <a name="closeassembly-method"></a><span data-ttu-id="f3f09-102">Metodo CloseAssembly</span><span class="sxs-lookup"><span data-stu-id="f3f09-102">CloseAssembly Method</span></span>
<span data-ttu-id="f3f09-103">Consente di finalizzare le operazioni di assembly.</span><span class="sxs-lookup"><span data-stu-id="f3f09-103">Finalizes assembly operations.</span></span> <span data-ttu-id="f3f09-104">Chiamare questo metodo prima di iniziare un nuovo assembly o un modulo non associato.</span><span class="sxs-lookup"><span data-stu-id="f3f09-104">Call this method before beginning a new assembly or unbound module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3f09-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f3f09-105">Syntax</span></span>  
  
```  
HRESULT CloseAssembly(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f3f09-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="f3f09-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="f3f09-107">ID dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="f3f09-107">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f3f09-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="f3f09-108">Return Value</span></span>  
 <span data-ttu-id="f3f09-109">Restituisce S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="f3f09-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f3f09-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f3f09-110">Requirements</span></span>  
 <span data-ttu-id="f3f09-111">Richiede alink.h.</span><span class="sxs-lookup"><span data-stu-id="f3f09-111">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3f09-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f3f09-112">See also</span></span>
- [<span data-ttu-id="f3f09-113">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="f3f09-113">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="f3f09-114">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="f3f09-114">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="f3f09-115">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="f3f09-115">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
