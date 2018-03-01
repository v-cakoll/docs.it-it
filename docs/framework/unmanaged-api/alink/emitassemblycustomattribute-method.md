---
title: Metodo EmitAssemblyCustomAttribute
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IALink.EmitAssemblyCustomAttribute
- EmitAssemblyCustomAttribute
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EmitAssemblyCustomAttribute
helpviewer_keywords:
- EmitAssemblyCustomAttribute method
ms.assetid: b72f5409-79af-4fa7-90a7-7630eec170f1
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 9cc7709ef060642f12a8bc7d048e520427a5c674
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="emitassemblycustomattribute-method"></a><span data-ttu-id="b042b-102">Metodo EmitAssemblyCustomAttribute</span><span class="sxs-lookup"><span data-stu-id="b042b-102">EmitAssemblyCustomAttribute Method</span></span>
<span data-ttu-id="b042b-103">Chiamata eseguita per impostare gli attributi personalizzati a livello di assembly.</span><span class="sxs-lookup"><span data-stu-id="b042b-103">Call to set assembly-level custom attributes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b042b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b042b-104">Syntax</span></span>  
  
```  
HRESULT EmitAssemblyCustomAttribute(  
    mdAssembly   AssemblyID,  
    mdToken      FileToken,  
    mdToken      tkType,  
    void const*  pCustomValue,  
    DWORD        cbCustomValue,  
    BOOL         bSecurity,  
    BOOL         bAllowMulti  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b042b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b042b-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="b042b-106">ID dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="b042b-106">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="b042b-107">File che definisce l'attributo.</span><span class="sxs-lookup"><span data-stu-id="b042b-107">File that defiles the attribute.</span></span> <span data-ttu-id="b042b-108">Può essere NULL se `AssemblyID` non indica un netmodule non associato.</span><span class="sxs-lookup"><span data-stu-id="b042b-108">Can be NULL if `AssemblyID` does not indicate an unbound netmodule.</span></span>  
  
 `tkType`  
 <span data-ttu-id="b042b-109">Tipo dell'attributo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="b042b-109">Type of the custom attribute.</span></span>  
  
 `pCustomValue`  
 <span data-ttu-id="b042b-110">Dati di valore personalizzato.</span><span class="sxs-lookup"><span data-stu-id="b042b-110">Custom value data.</span></span>  
  
 `cbCustomValue`  
 <span data-ttu-id="b042b-111">Lunghezza dei dati di valore personalizzato.</span><span class="sxs-lookup"><span data-stu-id="b042b-111">Length of custom value data.</span></span>  
  
 `bSecurity`  
 <span data-ttu-id="b042b-112">TRUE se l'attributo personalizzato è correlata alla firma dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="b042b-112">TRUE if the custom attribute is related to assembly signing.</span></span>  
  
 `bAllowMulti`  
 <span data-ttu-id="b042b-113">TRUE se più attributi devono essere inviati.</span><span class="sxs-lookup"><span data-stu-id="b042b-113">TRUE if multiple attributes are to be emitted.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b042b-114">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="b042b-114">Return Value</span></span>  
 <span data-ttu-id="b042b-115">Se il metodo ha esito positivo, restituisce S_OK.</span><span class="sxs-lookup"><span data-stu-id="b042b-115">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b042b-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b042b-116">Requirements</span></span>  
 <span data-ttu-id="b042b-117">Richiede alink.h</span><span class="sxs-lookup"><span data-stu-id="b042b-117">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b042b-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b042b-118">See Also</span></span>  
 [<span data-ttu-id="b042b-119">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="b042b-119">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="b042b-120">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="b042b-120">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="b042b-121">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="b042b-121">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
