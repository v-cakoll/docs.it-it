---
title: Metodo SetAssemblyProps
ms.date: 03/30/2017
api_name:
- IALink.SetAssemblyProps
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- SetAssemblyProps
helpviewer_keywords:
- SetAssemblyProps method
ms.assetid: a3d7cf29-1414-49e6-8aae-9b3283c4f5f0
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1e9f51799ea56cb1e5819d708a0e4a8136a94f3d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67741489"
---
# <a name="setassemblyprops-method"></a><span data-ttu-id="d9ab2-102">Metodo SetAssemblyProps</span><span class="sxs-lookup"><span data-stu-id="d9ab2-102">SetAssemblyProps Method</span></span>
<span data-ttu-id="d9ab2-103">Assegna la proprietà a livello di assembly.</span><span class="sxs-lookup"><span data-stu-id="d9ab2-103">Assigns assembly-level properties.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9ab2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d9ab2-104">Syntax</span></span>  
  
```cpp  
HRESULT SetAssemblyProps(  
    mdAssembly      AssemblyID,  
    mdToken         FileToken,  
    AssemblyOptions Option,  
    VARIANT         Value  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="d9ab2-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d9ab2-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="d9ab2-106">ID dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="d9ab2-106">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="d9ab2-107">File che definisce la proprietà.</span><span class="sxs-lookup"><span data-stu-id="d9ab2-107">File that defines the property.</span></span> <span data-ttu-id="d9ab2-108">Può essere NULL se `AssemblyID` non indica un netmodule non associato.</span><span class="sxs-lookup"><span data-stu-id="d9ab2-108">Can be NULL if `AssemblyID` does not indicate an unbound netmodule.</span></span>  
  
 `Option`  
 <span data-ttu-id="d9ab2-109">Indica la possibilità di modificare.</span><span class="sxs-lookup"><span data-stu-id="d9ab2-109">Indicates the option to modify.</span></span>  
  
 `Value`  
 <span data-ttu-id="d9ab2-110">Nuovo valore dell'opzione.</span><span class="sxs-lookup"><span data-stu-id="d9ab2-110">New value of the option.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d9ab2-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="d9ab2-111">Return Value</span></span>  
 <span data-ttu-id="d9ab2-112">Restituisce S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="d9ab2-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d9ab2-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d9ab2-113">Requirements</span></span>  
 <span data-ttu-id="d9ab2-114">Richiede alink.h.</span><span class="sxs-lookup"><span data-stu-id="d9ab2-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9ab2-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d9ab2-115">See also</span></span>

- [<span data-ttu-id="d9ab2-116">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="d9ab2-116">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="d9ab2-117">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="d9ab2-117">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="d9ab2-118">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="d9ab2-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
