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
ms.openlocfilehash: 5fe770ffc5a9c187e9069e8a66553976f9a53b2f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54709884"
---
# <a name="setpekind-method"></a><span data-ttu-id="bc87a-102">Metodo SetPEKind</span><span class="sxs-lookup"><span data-stu-id="bc87a-102">SetPEKind Method</span></span>
<span data-ttu-id="bc87a-103">Determina il tipo di eseguibile portabile, specifiche del computer o indipendente dal computer.</span><span class="sxs-lookup"><span data-stu-id="bc87a-103">Determines the portable executable type, either machine-specific or machine-agnostic.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc87a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bc87a-104">Syntax</span></span>  
  
```  
HRESULT SetPEKind(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwPEKind,  
    DWORD dwMachine  
) PURE;   
```  
  
#### <a name="parameters"></a><span data-ttu-id="bc87a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="bc87a-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="bc87a-106">ID dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="bc87a-106">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="bc87a-107">Token del file per cui è necessario impostare il tipo PE.</span><span class="sxs-lookup"><span data-stu-id="bc87a-107">Token of file for which the PE type is to be set.</span></span> <span data-ttu-id="bc87a-108">Può essere NULL se `AssemblyID` non indica un netmodule non associato.</span><span class="sxs-lookup"><span data-stu-id="bc87a-108">Can be NULL if `AssemblyID` does not indicate an unbound netmodule.</span></span>  
  
 `dwPEKind`  
 <span data-ttu-id="bc87a-109">Il tipo di PE, come indicato dal [Enumerazione CorPEKind](../../../../docs/framework/unmanaged-api/metadata/corpekind-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="bc87a-109">The type of PE, as indicated by the [CorPEKind Enumeration](../../../../docs/framework/unmanaged-api/metadata/corpekind-enumeration.md).</span></span>  
  
 `dwMachine`  
 <span data-ttu-id="bc87a-110">Architettura del computer di destinazione, come indicato nell'intestazione NT.</span><span class="sxs-lookup"><span data-stu-id="bc87a-110">The target machine architecture, as indicated in the NT header.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bc87a-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="bc87a-111">Return Value</span></span>  
 <span data-ttu-id="bc87a-112">Restituisce S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="bc87a-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bc87a-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="bc87a-113">Requirements</span></span>  
 <span data-ttu-id="bc87a-114">Richiede alink.h.</span><span class="sxs-lookup"><span data-stu-id="bc87a-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc87a-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bc87a-115">See also</span></span>
- [<span data-ttu-id="bc87a-116">Metodo GetPEKind</span><span class="sxs-lookup"><span data-stu-id="bc87a-116">GetPEKind Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getpekind-method.md)
- [<span data-ttu-id="bc87a-117">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="bc87a-117">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="bc87a-118">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="bc87a-118">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="bc87a-119">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="bc87a-119">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
