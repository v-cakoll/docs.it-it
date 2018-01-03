---
title: Metodo SetAssemblyProps
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IALink.SetAssemblyProps
api_location: alink.dll
api_type: COM
f1_keywords: SetAssemblyProps
helpviewer_keywords: SetAssemblyProps method
ms.assetid: a3d7cf29-1414-49e6-8aae-9b3283c4f5f0
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ae13daab0352ad4367c7ad6e06d6c12af23c75bb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="setassemblyprops-method"></a><span data-ttu-id="ebe55-102">Metodo SetAssemblyProps</span><span class="sxs-lookup"><span data-stu-id="ebe55-102">SetAssemblyProps Method</span></span>
<span data-ttu-id="ebe55-103">Assegna la proprietà a livello di assembly.</span><span class="sxs-lookup"><span data-stu-id="ebe55-103">Assigns assembly-level properties.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ebe55-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ebe55-104">Syntax</span></span>  
  
```  
HRESULT SetAssemblyProps(  
    mdAssembly      AssemblyID,  
    mdToken         FileToken,  
    AssemblyOptions Option,  
    VARIANT         Value  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ebe55-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ebe55-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="ebe55-106">ID dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="ebe55-106">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="ebe55-107">File che definisce la proprietà.</span><span class="sxs-lookup"><span data-stu-id="ebe55-107">File that defines the property.</span></span> <span data-ttu-id="ebe55-108">Può essere NULL se `AssemblyID` non indica un netmodule non associato.</span><span class="sxs-lookup"><span data-stu-id="ebe55-108">Can be NULL if `AssemblyID` does not indicate an unbound netmodule.</span></span>  
  
 `Option`  
 <span data-ttu-id="ebe55-109">Indica la possibilità di modificare.</span><span class="sxs-lookup"><span data-stu-id="ebe55-109">Indicates the option to modify.</span></span>  
  
 `Value`  
 <span data-ttu-id="ebe55-110">Nuovo valore dell'opzione.</span><span class="sxs-lookup"><span data-stu-id="ebe55-110">New value of the option.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ebe55-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="ebe55-111">Return Value</span></span>  
 <span data-ttu-id="ebe55-112">Se il metodo ha esito positivo, restituisce S_OK.</span><span class="sxs-lookup"><span data-stu-id="ebe55-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ebe55-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ebe55-113">Requirements</span></span>  
 <span data-ttu-id="ebe55-114">Richiede alink.h.</span><span class="sxs-lookup"><span data-stu-id="ebe55-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ebe55-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ebe55-115">See Also</span></span>  
 [<span data-ttu-id="ebe55-116">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="ebe55-116">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="ebe55-117">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="ebe55-117">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="ebe55-118">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="ebe55-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
