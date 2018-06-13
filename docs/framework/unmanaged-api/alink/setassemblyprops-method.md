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
ms.openlocfilehash: aed553a3a8d54b5229a122e76b61e3e58d4af3c1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33401966"
---
# <a name="setassemblyprops-method"></a><span data-ttu-id="c44bd-102">Metodo SetAssemblyProps</span><span class="sxs-lookup"><span data-stu-id="c44bd-102">SetAssemblyProps Method</span></span>
<span data-ttu-id="c44bd-103">Assegna la proprietà a livello di assembly.</span><span class="sxs-lookup"><span data-stu-id="c44bd-103">Assigns assembly-level properties.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c44bd-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c44bd-104">Syntax</span></span>  
  
```  
HRESULT SetAssemblyProps(  
    mdAssembly      AssemblyID,  
    mdToken         FileToken,  
    AssemblyOptions Option,  
    VARIANT         Value  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c44bd-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c44bd-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="c44bd-106">ID dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="c44bd-106">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="c44bd-107">File che definisce la proprietà.</span><span class="sxs-lookup"><span data-stu-id="c44bd-107">File that defines the property.</span></span> <span data-ttu-id="c44bd-108">Può essere NULL se `AssemblyID` non indica un netmodule non associato.</span><span class="sxs-lookup"><span data-stu-id="c44bd-108">Can be NULL if `AssemblyID` does not indicate an unbound netmodule.</span></span>  
  
 `Option`  
 <span data-ttu-id="c44bd-109">Indica la possibilità di modificare.</span><span class="sxs-lookup"><span data-stu-id="c44bd-109">Indicates the option to modify.</span></span>  
  
 `Value`  
 <span data-ttu-id="c44bd-110">Nuovo valore dell'opzione.</span><span class="sxs-lookup"><span data-stu-id="c44bd-110">New value of the option.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c44bd-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="c44bd-111">Return Value</span></span>  
 <span data-ttu-id="c44bd-112">Se il metodo ha esito positivo, restituisce S_OK.</span><span class="sxs-lookup"><span data-stu-id="c44bd-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c44bd-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c44bd-113">Requirements</span></span>  
 <span data-ttu-id="c44bd-114">Richiede alink.h.</span><span class="sxs-lookup"><span data-stu-id="c44bd-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c44bd-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c44bd-115">See Also</span></span>  
 [<span data-ttu-id="c44bd-116">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="c44bd-116">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="c44bd-117">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="c44bd-117">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="c44bd-118">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="c44bd-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
