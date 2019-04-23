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
ms.openlocfilehash: 589bd7b2132693c89dc10ae1a5c8d0bf52ed481e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59218992"
---
# <a name="setassemblyprops-method"></a><span data-ttu-id="9f1bb-102">Metodo SetAssemblyProps</span><span class="sxs-lookup"><span data-stu-id="9f1bb-102">SetAssemblyProps Method</span></span>
<span data-ttu-id="9f1bb-103">Assegna la proprietà a livello di assembly.</span><span class="sxs-lookup"><span data-stu-id="9f1bb-103">Assigns assembly-level properties.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f1bb-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9f1bb-104">Syntax</span></span>  
  
```  
HRESULT SetAssemblyProps(  
    mdAssembly      AssemblyID,  
    mdToken         FileToken,  
    AssemblyOptions Option,  
    VARIANT         Value  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="9f1bb-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="9f1bb-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="9f1bb-106">ID dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="9f1bb-106">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="9f1bb-107">File che definisce la proprietà.</span><span class="sxs-lookup"><span data-stu-id="9f1bb-107">File that defines the property.</span></span> <span data-ttu-id="9f1bb-108">Può essere NULL se `AssemblyID` non indica un netmodule non associato.</span><span class="sxs-lookup"><span data-stu-id="9f1bb-108">Can be NULL if `AssemblyID` does not indicate an unbound netmodule.</span></span>  
  
 `Option`  
 <span data-ttu-id="9f1bb-109">Indica la possibilità di modificare.</span><span class="sxs-lookup"><span data-stu-id="9f1bb-109">Indicates the option to modify.</span></span>  
  
 `Value`  
 <span data-ttu-id="9f1bb-110">Nuovo valore dell'opzione.</span><span class="sxs-lookup"><span data-stu-id="9f1bb-110">New value of the option.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9f1bb-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="9f1bb-111">Return Value</span></span>  
 <span data-ttu-id="9f1bb-112">Restituisce S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="9f1bb-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9f1bb-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9f1bb-113">Requirements</span></span>  
 <span data-ttu-id="9f1bb-114">Richiede alink.h.</span><span class="sxs-lookup"><span data-stu-id="9f1bb-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f1bb-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9f1bb-115">See also</span></span>

- [<span data-ttu-id="9f1bb-116">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="9f1bb-116">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="9f1bb-117">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="9f1bb-117">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="9f1bb-118">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="9f1bb-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
