---
title: Metodo PreCloseAssembly
ms.date: 03/30/2017
api_name:
- IALink.PreCloseAssembly
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- PreCloseAssembly
helpviewer_keywords:
- PreCloseAssembly method
ms.assetid: 6d23ac54-15ea-4027-a172-9ebef43e8f56
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6fab522adbdb1b50448dfabfd23d663fb223c6da
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54499197"
---
# <a name="precloseassembly-method"></a><span data-ttu-id="fa84b-102">Metodo PreCloseAssembly</span><span class="sxs-lookup"><span data-stu-id="fa84b-102">PreCloseAssembly Method</span></span>
<span data-ttu-id="fa84b-103">Chiude il file di assembly.</span><span class="sxs-lookup"><span data-stu-id="fa84b-103">Closes the assembly file.</span></span> <span data-ttu-id="fa84b-104">Chiamare questo metodo dopo la chiusura di tutti gli altri file, ma prima di chiudere il file di assembly.</span><span class="sxs-lookup"><span data-stu-id="fa84b-104">Call this method after closing all other files, but before closing the assembly file.</span></span> <span data-ttu-id="fa84b-105">Non chiamare questo metodo per i moduli non associati.</span><span class="sxs-lookup"><span data-stu-id="fa84b-105">Do not call this method for unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa84b-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fa84b-106">Syntax</span></span>  
  
```  
HRESULT PreCloseAssembly(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fa84b-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="fa84b-107">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="fa84b-108">ID dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="fa84b-108">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fa84b-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="fa84b-109">Return Value</span></span>  
 <span data-ttu-id="fa84b-110">Restituisce S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="fa84b-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa84b-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fa84b-111">Requirements</span></span>  
 <span data-ttu-id="fa84b-112">Richiede alink.h.</span><span class="sxs-lookup"><span data-stu-id="fa84b-112">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa84b-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fa84b-113">See also</span></span>
- [<span data-ttu-id="fa84b-114">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="fa84b-114">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="fa84b-115">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="fa84b-115">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="fa84b-116">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="fa84b-116">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
