---
title: Metodo SetPEKind
ms.date: 03/30/2017
api_name:
- IALink2.SetPEKind
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- SetPEKind
helpviewer_keywords:
- SetPEKind method
ms.assetid: 050e77ee-3014-45c0-9e29-2ebe29347b0d
topic_type:
- apiref
ms.openlocfilehash: 5a8442b1f0869e1592a05dfeeb0f5e6d583f3ea8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179381"
---
# <a name="setpekind-method"></a><span data-ttu-id="925b1-102">Metodo SetPEKind</span><span class="sxs-lookup"><span data-stu-id="925b1-102">SetPEKind Method</span></span>
<span data-ttu-id="925b1-103">Determina il tipo di eseguibile portabile, specifico del computer o indipendente dal computer.</span><span class="sxs-lookup"><span data-stu-id="925b1-103">Determines the portable executable type, either machine-specific or machine-agnostic.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="925b1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="925b1-104">Syntax</span></span>  
  
```cpp  
HRESULT SetPEKind(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwPEKind,  
    DWORD dwMachine  
) PURE;
```  
  
## <a name="parameters"></a><span data-ttu-id="925b1-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="925b1-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="925b1-106">ID dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="925b1-106">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="925b1-107">Token del file per il quale deve essere impostato il tipo PE.</span><span class="sxs-lookup"><span data-stu-id="925b1-107">Token of file for which the PE type is to be set.</span></span> <span data-ttu-id="925b1-108">Può essere `AssemblyID` NULL se non indica un netmodule non associato.</span><span class="sxs-lookup"><span data-stu-id="925b1-108">Can be NULL if `AssemblyID` does not indicate an unbound netmodule.</span></span>  
  
 `dwPEKind`  
 <span data-ttu-id="925b1-109">Tipo di PE, come indicato [dall'enumerazione CorPEKind](../metadata/corpekind-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="925b1-109">The type of PE, as indicated by the [CorPEKind Enumeration](../metadata/corpekind-enumeration.md).</span></span>  
  
 `dwMachine`  
 <span data-ttu-id="925b1-110">Architettura del computer di destinazione, come indicato nell'intestazione NT.</span><span class="sxs-lookup"><span data-stu-id="925b1-110">The target machine architecture, as indicated in the NT header.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="925b1-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="925b1-111">Return Value</span></span>  
 <span data-ttu-id="925b1-112">Restituisce S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="925b1-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="925b1-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="925b1-113">Requirements</span></span>  
 <span data-ttu-id="925b1-114">Richiede alink.h.</span><span class="sxs-lookup"><span data-stu-id="925b1-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="925b1-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="925b1-115">See also</span></span>

- [<span data-ttu-id="925b1-116">Metodo GetPEKind</span><span class="sxs-lookup"><span data-stu-id="925b1-116">GetPEKind Method</span></span>](../metadata/imetadataimport2-getpekind-method.md)
- [<span data-ttu-id="925b1-117">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="925b1-117">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="925b1-118">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="925b1-118">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="925b1-119">API Alink</span><span class="sxs-lookup"><span data-stu-id="925b1-119">ALink API</span></span>](index.md)
