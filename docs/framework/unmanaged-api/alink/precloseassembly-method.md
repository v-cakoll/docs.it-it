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
ms.openlocfilehash: 82421fa83a6f0d24492d70f961e731b679c25728
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33400718"
---
# <a name="precloseassembly-method"></a><span data-ttu-id="456e1-102">Metodo PreCloseAssembly</span><span class="sxs-lookup"><span data-stu-id="456e1-102">PreCloseAssembly Method</span></span>
<span data-ttu-id="456e1-103">Chiude il file di assembly.</span><span class="sxs-lookup"><span data-stu-id="456e1-103">Closes the assembly file.</span></span> <span data-ttu-id="456e1-104">Chiamare questo metodo dopo la chiusura di tutti gli altri file, ma prima di chiudere il file di assembly.</span><span class="sxs-lookup"><span data-stu-id="456e1-104">Call this method after closing all other files, but before closing the assembly file.</span></span> <span data-ttu-id="456e1-105">Non chiamare questo metodo per i moduli non associati.</span><span class="sxs-lookup"><span data-stu-id="456e1-105">Do not call this method for unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="456e1-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="456e1-106">Syntax</span></span>  
  
```  
HRESULT PreCloseAssembly(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="456e1-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="456e1-107">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="456e1-108">ID dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="456e1-108">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="456e1-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="456e1-109">Return Value</span></span>  
 <span data-ttu-id="456e1-110">Se il metodo ha esito positivo, restituisce S_OK.</span><span class="sxs-lookup"><span data-stu-id="456e1-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="456e1-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="456e1-111">Requirements</span></span>  
 <span data-ttu-id="456e1-112">Richiede alink.h.</span><span class="sxs-lookup"><span data-stu-id="456e1-112">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="456e1-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="456e1-113">See Also</span></span>  
 [<span data-ttu-id="456e1-114">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="456e1-114">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="456e1-115">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="456e1-115">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="456e1-116">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="456e1-116">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
