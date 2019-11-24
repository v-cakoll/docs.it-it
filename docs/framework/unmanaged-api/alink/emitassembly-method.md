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
ms.openlocfilehash: 6bbe5db75ded15f32a6ff3564e1116d40a745a65
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446529"
---
# <a name="emitassembly-method"></a><span data-ttu-id="f4767-102">Metodo EmitAssembly</span><span class="sxs-lookup"><span data-stu-id="f4767-102">EmitAssembly Method</span></span>
<span data-ttu-id="f4767-103">Creates the assembly.</span><span class="sxs-lookup"><span data-stu-id="f4767-103">Creates the assembly.</span></span> <span data-ttu-id="f4767-104">Call this method after all other files are closed except for the assembly file.</span><span class="sxs-lookup"><span data-stu-id="f4767-104">Call this method after all other files are closed except for the assembly file.</span></span> <span data-ttu-id="f4767-105">Do not call this method when producing unbound modules.</span><span class="sxs-lookup"><span data-stu-id="f4767-105">Do not call this method when producing unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f4767-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f4767-106">Syntax</span></span>  
  
```cpp  
HRESULT EmitAssembly(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="f4767-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="f4767-107">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="f4767-108">ID of the assembly.</span><span class="sxs-lookup"><span data-stu-id="f4767-108">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f4767-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="f4767-109">Return Value</span></span>  
 <span data-ttu-id="f4767-110">Returns S_OK if the method succeeds.</span><span class="sxs-lookup"><span data-stu-id="f4767-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f4767-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f4767-111">Requirements</span></span>  
 <span data-ttu-id="f4767-112">Requires alink.h</span><span class="sxs-lookup"><span data-stu-id="f4767-112">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4767-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f4767-113">See also</span></span>

- [<span data-ttu-id="f4767-114">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="f4767-114">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="f4767-115">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="f4767-115">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="f4767-116">API ALink</span><span class="sxs-lookup"><span data-stu-id="f4767-116">ALink API</span></span>](index.md)
