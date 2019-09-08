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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9a48dbd38d357b668c2794ae6305ceb9cad3dcf4
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70787188"
---
# <a name="setpekind-method"></a><span data-ttu-id="334f7-102">Metodo SetPEKind</span><span class="sxs-lookup"><span data-stu-id="334f7-102">SetPEKind Method</span></span>
<span data-ttu-id="334f7-103">Determina il tipo di eseguibile portatile, specifico del computer o indipendente dal computer.</span><span class="sxs-lookup"><span data-stu-id="334f7-103">Determines the portable executable type, either machine-specific or machine-agnostic.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="334f7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="334f7-104">Syntax</span></span>  
  
```cpp  
HRESULT SetPEKind(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwPEKind,  
    DWORD dwMachine  
) PURE;   
```  
  
## <a name="parameters"></a><span data-ttu-id="334f7-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="334f7-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="334f7-106">ID dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="334f7-106">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="334f7-107">Token del file per il quale deve essere impostato il tipo PE.</span><span class="sxs-lookup"><span data-stu-id="334f7-107">Token of file for which the PE type is to be set.</span></span> <span data-ttu-id="334f7-108">Può essere null se `AssemblyID` non indica un netmodule non associato.</span><span class="sxs-lookup"><span data-stu-id="334f7-108">Can be NULL if `AssemblyID` does not indicate an unbound netmodule.</span></span>  
  
 `dwPEKind`  
 <span data-ttu-id="334f7-109">Tipo di PE, come indicato dall' [enumerazione CorPEKind](../metadata/corpekind-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="334f7-109">The type of PE, as indicated by the [CorPEKind Enumeration](../metadata/corpekind-enumeration.md).</span></span>  
  
 `dwMachine`  
 <span data-ttu-id="334f7-110">L'architettura del computer di destinazione, come indicato nell'intestazione NT.</span><span class="sxs-lookup"><span data-stu-id="334f7-110">The target machine architecture, as indicated in the NT header.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="334f7-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="334f7-111">Return Value</span></span>  
 <span data-ttu-id="334f7-112">Restituisce S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="334f7-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="334f7-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="334f7-113">Requirements</span></span>  
 <span data-ttu-id="334f7-114">Richiede ALink. h.</span><span class="sxs-lookup"><span data-stu-id="334f7-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="334f7-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="334f7-115">See also</span></span>

- [<span data-ttu-id="334f7-116">Metodo GetPEKind</span><span class="sxs-lookup"><span data-stu-id="334f7-116">GetPEKind Method</span></span>](../metadata/imetadataimport2-getpekind-method.md)
- [<span data-ttu-id="334f7-117">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="334f7-117">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="334f7-118">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="334f7-118">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="334f7-119">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="334f7-119">ALink API</span></span>](index.md)
