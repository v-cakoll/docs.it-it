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
ms.openlocfilehash: ec0a86e3396ad42152bc0a244f74ad13deba16e4
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446512"
---
# <a name="emitassemblycustomattribute-method"></a><span data-ttu-id="3c26f-102">Metodo EmitAssemblyCustomAttribute</span><span class="sxs-lookup"><span data-stu-id="3c26f-102">EmitAssemblyCustomAttribute Method</span></span>
<span data-ttu-id="3c26f-103">Chiamare per impostare gli attributi personalizzati a livello di assembly.</span><span class="sxs-lookup"><span data-stu-id="3c26f-103">Call to set assembly-level custom attributes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c26f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3c26f-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="3c26f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="3c26f-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="3c26f-106">ID dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="3c26f-106">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="3c26f-107">File che defilerà l'attributo.</span><span class="sxs-lookup"><span data-stu-id="3c26f-107">File that defiles the attribute.</span></span> <span data-ttu-id="3c26f-108">Può essere NULL se `AssemblyID` non indica un netmodule non associato.</span><span class="sxs-lookup"><span data-stu-id="3c26f-108">Can be NULL if `AssemblyID` does not indicate an unbound netmodule.</span></span>  
  
 `tkType`  
 <span data-ttu-id="3c26f-109">Tipo dell'attributo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="3c26f-109">Type of the custom attribute.</span></span>  
  
 `pCustomValue`  
 <span data-ttu-id="3c26f-110">Dati del valore personalizzato.</span><span class="sxs-lookup"><span data-stu-id="3c26f-110">Custom value data.</span></span>  
  
 `cbCustomValue`  
 <span data-ttu-id="3c26f-111">Lunghezza dei dati del valore personalizzato.</span><span class="sxs-lookup"><span data-stu-id="3c26f-111">Length of custom value data.</span></span>  
  
 `bSecurity`  
 <span data-ttu-id="3c26f-112">TRUE se l'attributo personalizzato è correlato alla firma dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="3c26f-112">TRUE if the custom attribute is related to assembly signing.</span></span>  
  
 `bAllowMulti`  
 <span data-ttu-id="3c26f-113">TRUE se devono essere emessi più attributi.</span><span class="sxs-lookup"><span data-stu-id="3c26f-113">TRUE if multiple attributes are to be emitted.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3c26f-114">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="3c26f-114">Return Value</span></span>  
 <span data-ttu-id="3c26f-115">Restituisce S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="3c26f-115">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3c26f-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3c26f-116">Requirements</span></span>  
 <span data-ttu-id="3c26f-117">Richiede ALink. h</span><span class="sxs-lookup"><span data-stu-id="3c26f-117">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c26f-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3c26f-118">See also</span></span>

- [<span data-ttu-id="3c26f-119">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="3c26f-119">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="3c26f-120">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="3c26f-120">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="3c26f-121">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="3c26f-121">ALink API</span></span>](index.md)
