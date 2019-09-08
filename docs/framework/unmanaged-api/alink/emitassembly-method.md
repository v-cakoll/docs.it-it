---
title: Metodo EmitAssembly
ms.date: 03/30/2017
api_name:
- IALink2.EmitAssembly
- EmitAssembly
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EmitAssembly
helpviewer_keywords:
- EmitAssembly method
ms.assetid: 605ff39e-e5cc-4bff-8196-e8d68a9715b9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a2adf53d1e29fda077cdcf7b79891f6271993109
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70787586"
---
# <a name="emitassembly-method"></a><span data-ttu-id="b27ce-102">Metodo EmitAssembly</span><span class="sxs-lookup"><span data-stu-id="b27ce-102">EmitAssembly Method</span></span>
<span data-ttu-id="b27ce-103">Crea l'assembly.</span><span class="sxs-lookup"><span data-stu-id="b27ce-103">Creates the assembly.</span></span> <span data-ttu-id="b27ce-104">Chiamare questo metodo dopo la chiusura di tutti gli altri file, ad eccezione del file di assembly.</span><span class="sxs-lookup"><span data-stu-id="b27ce-104">Call this method after all other files are closed except for the assembly file.</span></span> <span data-ttu-id="b27ce-105">Non chiamare questo metodo quando si producono moduli non associati.</span><span class="sxs-lookup"><span data-stu-id="b27ce-105">Do not call this method when producing unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b27ce-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b27ce-106">Syntax</span></span>  
  
```cpp  
HRESULT EmitAssembly(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="b27ce-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="b27ce-107">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="b27ce-108">ID dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="b27ce-108">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b27ce-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="b27ce-109">Return Value</span></span>  
 <span data-ttu-id="b27ce-110">Restituisce S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="b27ce-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b27ce-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b27ce-111">Requirements</span></span>  
 <span data-ttu-id="b27ce-112">Richiede ALink. h</span><span class="sxs-lookup"><span data-stu-id="b27ce-112">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b27ce-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b27ce-113">See also</span></span>

- [<span data-ttu-id="b27ce-114">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="b27ce-114">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="b27ce-115">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="b27ce-115">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="b27ce-116">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="b27ce-116">ALink API</span></span>](index.md)
