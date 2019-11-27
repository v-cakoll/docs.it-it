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
ms.openlocfilehash: 70dca19075d8c896408ec78f89549b0c539280de
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446575"
---
# <a name="closeassembly-method"></a><span data-ttu-id="ea72f-102">Metodo CloseAssembly</span><span class="sxs-lookup"><span data-stu-id="ea72f-102">CloseAssembly Method</span></span>
<span data-ttu-id="ea72f-103">Finalizza le operazioni di assembly.</span><span class="sxs-lookup"><span data-stu-id="ea72f-103">Finalizes assembly operations.</span></span> <span data-ttu-id="ea72f-104">Chiamare questo metodo prima di iniziare un nuovo modulo di assembly o non associato.</span><span class="sxs-lookup"><span data-stu-id="ea72f-104">Call this method before beginning a new assembly or unbound module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea72f-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ea72f-105">Syntax</span></span>  
  
```cpp  
HRESULT CloseAssembly(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="ea72f-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="ea72f-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="ea72f-107">ID dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="ea72f-107">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ea72f-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="ea72f-108">Return Value</span></span>  
 <span data-ttu-id="ea72f-109">Restituisce S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="ea72f-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ea72f-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ea72f-110">Requirements</span></span>  
 <span data-ttu-id="ea72f-111">Richiede ALink. h.</span><span class="sxs-lookup"><span data-stu-id="ea72f-111">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea72f-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ea72f-112">See also</span></span>

- [<span data-ttu-id="ea72f-113">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="ea72f-113">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="ea72f-114">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="ea72f-114">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="ea72f-115">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="ea72f-115">ALink API</span></span>](index.md)
