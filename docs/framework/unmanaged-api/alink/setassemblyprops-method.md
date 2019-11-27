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
ms.openlocfilehash: 4bfad8b985a8ef059031464e99a8004842b276c0
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445580"
---
# <a name="setassemblyprops-method"></a><span data-ttu-id="b67ff-102">Metodo SetAssemblyProps</span><span class="sxs-lookup"><span data-stu-id="b67ff-102">SetAssemblyProps Method</span></span>
<span data-ttu-id="b67ff-103">Assegna proprietà a livello di assembly.</span><span class="sxs-lookup"><span data-stu-id="b67ff-103">Assigns assembly-level properties.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b67ff-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b67ff-104">Syntax</span></span>  
  
```cpp  
HRESULT SetAssemblyProps(  
    mdAssembly      AssemblyID,  
    mdToken         FileToken,  
    AssemblyOptions Option,  
    VARIANT         Value  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="b67ff-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b67ff-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="b67ff-106">ID dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="b67ff-106">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="b67ff-107">File che definisce la proprietà.</span><span class="sxs-lookup"><span data-stu-id="b67ff-107">File that defines the property.</span></span> <span data-ttu-id="b67ff-108">Può essere NULL se `AssemblyID` non indica un netmodule non associato.</span><span class="sxs-lookup"><span data-stu-id="b67ff-108">Can be NULL if `AssemblyID` does not indicate an unbound netmodule.</span></span>  
  
 `Option`  
 <span data-ttu-id="b67ff-109">Indica l'opzione da modificare.</span><span class="sxs-lookup"><span data-stu-id="b67ff-109">Indicates the option to modify.</span></span>  
  
 `Value`  
 <span data-ttu-id="b67ff-110">Nuovo valore dell'opzione.</span><span class="sxs-lookup"><span data-stu-id="b67ff-110">New value of the option.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b67ff-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="b67ff-111">Return Value</span></span>  
 <span data-ttu-id="b67ff-112">Restituisce S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="b67ff-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b67ff-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b67ff-113">Requirements</span></span>  
 <span data-ttu-id="b67ff-114">Richiede ALink. h.</span><span class="sxs-lookup"><span data-stu-id="b67ff-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b67ff-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b67ff-115">See also</span></span>

- [<span data-ttu-id="b67ff-116">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="b67ff-116">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="b67ff-117">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="b67ff-117">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="b67ff-118">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="b67ff-118">ALink API</span></span>](index.md)
