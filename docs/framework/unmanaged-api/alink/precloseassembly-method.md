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
ms.openlocfilehash: aab42e939651d75b1933962d72ba8bec1090f52d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59184509"
---
# <a name="precloseassembly-method"></a><span data-ttu-id="c2612-102">Metodo PreCloseAssembly</span><span class="sxs-lookup"><span data-stu-id="c2612-102">PreCloseAssembly Method</span></span>
<span data-ttu-id="c2612-103">Chiude il file di assembly.</span><span class="sxs-lookup"><span data-stu-id="c2612-103">Closes the assembly file.</span></span> <span data-ttu-id="c2612-104">Chiamare questo metodo dopo la chiusura di tutti gli altri file, ma prima di chiudere il file di assembly.</span><span class="sxs-lookup"><span data-stu-id="c2612-104">Call this method after closing all other files, but before closing the assembly file.</span></span> <span data-ttu-id="c2612-105">Non chiamare questo metodo per i moduli non associati.</span><span class="sxs-lookup"><span data-stu-id="c2612-105">Do not call this method for unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2612-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c2612-106">Syntax</span></span>  
  
```  
HRESULT PreCloseAssembly(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="c2612-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="c2612-107">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="c2612-108">ID dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="c2612-108">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c2612-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="c2612-109">Return Value</span></span>  
 <span data-ttu-id="c2612-110">Restituisce S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="c2612-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c2612-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c2612-111">Requirements</span></span>  
 <span data-ttu-id="c2612-112">Richiede alink.h.</span><span class="sxs-lookup"><span data-stu-id="c2612-112">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2612-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c2612-113">See also</span></span>

- [<span data-ttu-id="c2612-114">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="c2612-114">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="c2612-115">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="c2612-115">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="c2612-116">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="c2612-116">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
