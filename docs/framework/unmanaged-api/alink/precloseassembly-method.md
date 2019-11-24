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
ms.openlocfilehash: fcfd3e79bbb52837a333b5ffacf5c13ae60f2490
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445621"
---
# <a name="precloseassembly-method"></a><span data-ttu-id="62c38-102">Metodo PreCloseAssembly</span><span class="sxs-lookup"><span data-stu-id="62c38-102">PreCloseAssembly Method</span></span>
<span data-ttu-id="62c38-103">Chiude il file di assembly.</span><span class="sxs-lookup"><span data-stu-id="62c38-103">Closes the assembly file.</span></span> <span data-ttu-id="62c38-104">Chiamare questo metodo dopo la chiusura di tutti gli altri file, ma prima di chiudere il file di assembly.</span><span class="sxs-lookup"><span data-stu-id="62c38-104">Call this method after closing all other files, but before closing the assembly file.</span></span> <span data-ttu-id="62c38-105">Non chiamare questo metodo per i moduli non associati.</span><span class="sxs-lookup"><span data-stu-id="62c38-105">Do not call this method for unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62c38-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="62c38-106">Syntax</span></span>  
  
```cpp  
HRESULT PreCloseAssembly(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="62c38-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="62c38-107">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="62c38-108">ID dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="62c38-108">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="62c38-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="62c38-109">Return Value</span></span>  
 <span data-ttu-id="62c38-110">Restituisce S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="62c38-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="62c38-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="62c38-111">Requirements</span></span>  
 <span data-ttu-id="62c38-112">Richiede ALink. h.</span><span class="sxs-lookup"><span data-stu-id="62c38-112">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62c38-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="62c38-113">See also</span></span>

- [<span data-ttu-id="62c38-114">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="62c38-114">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="62c38-115">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="62c38-115">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="62c38-116">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="62c38-116">ALink API</span></span>](index.md)
