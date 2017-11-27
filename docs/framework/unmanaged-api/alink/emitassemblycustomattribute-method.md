---
title: Metodo EmitAssemblyCustomAttribute
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IALink.EmitAssemblyCustomAttribute
- EmitAssemblyCustomAttribute
api_location: alink.dll
api_type: COM
f1_keywords: EmitAssemblyCustomAttribute
helpviewer_keywords: EmitAssemblyCustomAttribute method
ms.assetid: b72f5409-79af-4fa7-90a7-7630eec170f1
topic_type: apiref
caps.latest.revision: "5"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: bb21ee1396a9dd0426b9b91711c2345ef66c09f9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="emitassemblycustomattribute-method"></a><span data-ttu-id="49746-102">Metodo EmitAssemblyCustomAttribute</span><span class="sxs-lookup"><span data-stu-id="49746-102">EmitAssemblyCustomAttribute Method</span></span>
<span data-ttu-id="49746-103">Chiamata eseguita per impostare gli attributi personalizzati a livello di assembly.</span><span class="sxs-lookup"><span data-stu-id="49746-103">Call to set assembly-level custom attributes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49746-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="49746-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="49746-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="49746-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="49746-106">ID dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="49746-106">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="49746-107">File che definisce l'attributo.</span><span class="sxs-lookup"><span data-stu-id="49746-107">File that defiles the attribute.</span></span> <span data-ttu-id="49746-108">Può essere NULL se `AssemblyID` non indica un netmodule non associato.</span><span class="sxs-lookup"><span data-stu-id="49746-108">Can be NULL if `AssemblyID` does not indicate an unbound netmodule.</span></span>  
  
 `tkType`  
 <span data-ttu-id="49746-109">Tipo dell'attributo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="49746-109">Type of the custom attribute.</span></span>  
  
 `pCustomValue`  
 <span data-ttu-id="49746-110">Dati di valore personalizzato.</span><span class="sxs-lookup"><span data-stu-id="49746-110">Custom value data.</span></span>  
  
 `cbCustomValue`  
 <span data-ttu-id="49746-111">Lunghezza dei dati di valore personalizzato.</span><span class="sxs-lookup"><span data-stu-id="49746-111">Length of custom value data.</span></span>  
  
 `bSecurity`  
 <span data-ttu-id="49746-112">TRUE se l'attributo personalizzato è correlata alla firma dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="49746-112">TRUE if the custom attribute is related to assembly signing.</span></span>  
  
 `bAllowMulti`  
 <span data-ttu-id="49746-113">TRUE se più attributi devono essere inviati.</span><span class="sxs-lookup"><span data-stu-id="49746-113">TRUE if multiple attributes are to be emitted.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="49746-114">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="49746-114">Return Value</span></span>  
 <span data-ttu-id="49746-115">Se il metodo ha esito positivo, restituisce S_OK.</span><span class="sxs-lookup"><span data-stu-id="49746-115">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="49746-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="49746-116">Requirements</span></span>  
 <span data-ttu-id="49746-117">Richiede alink.h</span><span class="sxs-lookup"><span data-stu-id="49746-117">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49746-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="49746-118">See Also</span></span>  
 [<span data-ttu-id="49746-119">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="49746-119">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="49746-120">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="49746-120">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="49746-121">ALink (API)</span><span class="sxs-lookup"><span data-stu-id="49746-121">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
