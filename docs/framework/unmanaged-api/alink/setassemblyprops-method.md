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
ms.openlocfilehash: 65d6e929a0a6fb5e1933a6c9216dfc5b56342113
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54560646"
---
# <a name="setassemblyprops-method"></a><span data-ttu-id="2bf4b-102">Metodo SetAssemblyProps</span><span class="sxs-lookup"><span data-stu-id="2bf4b-102">SetAssemblyProps Method</span></span>
<span data-ttu-id="2bf4b-103">Assegna la proprietà a livello di assembly.</span><span class="sxs-lookup"><span data-stu-id="2bf4b-103">Assigns assembly-level properties.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2bf4b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2bf4b-104">Syntax</span></span>  
  
```  
HRESULT SetAssemblyProps(  
    mdAssembly      AssemblyID,  
    mdToken         FileToken,  
    AssemblyOptions Option,  
    VARIANT         Value  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2bf4b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="2bf4b-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="2bf4b-106">ID dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="2bf4b-106">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="2bf4b-107">File che definisce la proprietà.</span><span class="sxs-lookup"><span data-stu-id="2bf4b-107">File that defines the property.</span></span> <span data-ttu-id="2bf4b-108">Può essere NULL se `AssemblyID` non indica un netmodule non associato.</span><span class="sxs-lookup"><span data-stu-id="2bf4b-108">Can be NULL if `AssemblyID` does not indicate an unbound netmodule.</span></span>  
  
 `Option`  
 <span data-ttu-id="2bf4b-109">Indica la possibilità di modificare.</span><span class="sxs-lookup"><span data-stu-id="2bf4b-109">Indicates the option to modify.</span></span>  
  
 `Value`  
 <span data-ttu-id="2bf4b-110">Nuovo valore dell'opzione.</span><span class="sxs-lookup"><span data-stu-id="2bf4b-110">New value of the option.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2bf4b-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="2bf4b-111">Return Value</span></span>  
 <span data-ttu-id="2bf4b-112">Restituisce S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="2bf4b-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2bf4b-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2bf4b-113">Requirements</span></span>  
 <span data-ttu-id="2bf4b-114">Richiede alink.h.</span><span class="sxs-lookup"><span data-stu-id="2bf4b-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2bf4b-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2bf4b-115">See also</span></span>
- [<span data-ttu-id="2bf4b-116">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="2bf4b-116">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="2bf4b-117">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="2bf4b-117">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="2bf4b-118">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="2bf4b-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
