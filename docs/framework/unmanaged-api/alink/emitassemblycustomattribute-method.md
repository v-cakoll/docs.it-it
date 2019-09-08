---
title: Metodo EmitAssemblyCustomAttribute
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 77d54f6c8f67dda5132518d1fbd579a91ce82071
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70777448"
---
# <a name="emitassemblycustomattribute-method"></a><span data-ttu-id="1b35e-102">Metodo EmitAssemblyCustomAttribute</span><span class="sxs-lookup"><span data-stu-id="1b35e-102">EmitAssemblyCustomAttribute Method</span></span>
<span data-ttu-id="1b35e-103">Chiamare per impostare gli attributi personalizzati a livello di assembly.</span><span class="sxs-lookup"><span data-stu-id="1b35e-103">Call to set assembly-level custom attributes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b35e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1b35e-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="1b35e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="1b35e-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="1b35e-106">ID dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="1b35e-106">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="1b35e-107">File che defilerà l'attributo.</span><span class="sxs-lookup"><span data-stu-id="1b35e-107">File that defiles the attribute.</span></span> <span data-ttu-id="1b35e-108">Può essere null se `AssemblyID` non indica un netmodule non associato.</span><span class="sxs-lookup"><span data-stu-id="1b35e-108">Can be NULL if `AssemblyID` does not indicate an unbound netmodule.</span></span>  
  
 `tkType`  
 <span data-ttu-id="1b35e-109">Tipo dell'attributo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="1b35e-109">Type of the custom attribute.</span></span>  
  
 `pCustomValue`  
 <span data-ttu-id="1b35e-110">Dati del valore personalizzato.</span><span class="sxs-lookup"><span data-stu-id="1b35e-110">Custom value data.</span></span>  
  
 `cbCustomValue`  
 <span data-ttu-id="1b35e-111">Lunghezza dei dati del valore personalizzato.</span><span class="sxs-lookup"><span data-stu-id="1b35e-111">Length of custom value data.</span></span>  
  
 `bSecurity`  
 <span data-ttu-id="1b35e-112">TRUE se l'attributo personalizzato è correlato alla firma dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="1b35e-112">TRUE if the custom attribute is related to assembly signing.</span></span>  
  
 `bAllowMulti`  
 <span data-ttu-id="1b35e-113">TRUE se devono essere emessi più attributi.</span><span class="sxs-lookup"><span data-stu-id="1b35e-113">TRUE if multiple attributes are to be emitted.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1b35e-114">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="1b35e-114">Return Value</span></span>  
 <span data-ttu-id="1b35e-115">Restituisce S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="1b35e-115">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1b35e-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1b35e-116">Requirements</span></span>  
 <span data-ttu-id="1b35e-117">Richiede ALink. h</span><span class="sxs-lookup"><span data-stu-id="1b35e-117">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b35e-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1b35e-118">See also</span></span>

- [<span data-ttu-id="1b35e-119">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="1b35e-119">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="1b35e-120">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="1b35e-120">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="1b35e-121">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="1b35e-121">ALink API</span></span>](index.md)
