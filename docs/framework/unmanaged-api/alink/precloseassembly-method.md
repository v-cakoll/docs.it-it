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
ms.openlocfilehash: d4cf862ae3676b85a7fc3f09a4f5794e01284737
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70787226"
---
# <a name="precloseassembly-method"></a><span data-ttu-id="74875-102">Metodo PreCloseAssembly</span><span class="sxs-lookup"><span data-stu-id="74875-102">PreCloseAssembly Method</span></span>
<span data-ttu-id="74875-103">Chiude il file di assembly.</span><span class="sxs-lookup"><span data-stu-id="74875-103">Closes the assembly file.</span></span> <span data-ttu-id="74875-104">Chiamare questo metodo dopo la chiusura di tutti gli altri file, ma prima di chiudere il file di assembly.</span><span class="sxs-lookup"><span data-stu-id="74875-104">Call this method after closing all other files, but before closing the assembly file.</span></span> <span data-ttu-id="74875-105">Non chiamare questo metodo per i moduli non associati.</span><span class="sxs-lookup"><span data-stu-id="74875-105">Do not call this method for unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74875-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="74875-106">Syntax</span></span>  
  
```cpp  
HRESULT PreCloseAssembly(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="74875-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="74875-107">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="74875-108">ID dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="74875-108">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="74875-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="74875-109">Return Value</span></span>  
 <span data-ttu-id="74875-110">Restituisce S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="74875-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="74875-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="74875-111">Requirements</span></span>  
 <span data-ttu-id="74875-112">Richiede ALink. h.</span><span class="sxs-lookup"><span data-stu-id="74875-112">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74875-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="74875-113">See also</span></span>

- [<span data-ttu-id="74875-114">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="74875-114">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="74875-115">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="74875-115">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="74875-116">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="74875-116">ALink API</span></span>](index.md)
