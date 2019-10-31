---
title: Funzione CreateAssemblyNameObject
ms.date: 03/30/2017
api_name:
- CreateAssemblyNameObject
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- CreateAssemblyNameObject
helpviewer_keywords:
- CreateAssemblyNameObject function [.NET Framework fusion]
ms.assetid: 55c8b41e-fbe4-4ae0-aa29-68fbb2311691
topic_type:
- apiref
ms.openlocfilehash: 00345f6c95c67f0494aa721c662f56a9e98cdd7f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73108705"
---
# <a name="createassemblynameobject-function"></a><span data-ttu-id="6bf7c-102">Funzione CreateAssemblyNameObject</span><span class="sxs-lookup"><span data-stu-id="6bf7c-102">CreateAssemblyNameObject Function</span></span>
<span data-ttu-id="6bf7c-103">Ottiene un puntatore a interfaccia a un'istanza di [IAssemblyName](iassemblyname-interface.md) che rappresenta l'identità univoca dell'assembly con il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="6bf7c-103">Gets an interface pointer to an [IAssemblyName](iassemblyname-interface.md) instance that represents the unique identity of the assembly with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6bf7c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6bf7c-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateAssemblyNameObject (  
    [out] LPASSEMBLYNAME  *ppAssemblyNameObj,  
    [in]  LPCWSTR         szAssemblyName,  
    [in]  DWORD           dwFlags,  
    [in]  LPVOID          pvReserved  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="6bf7c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="6bf7c-105">Parameters</span></span>  
 `ppAssemblyNameObj`  
 <span data-ttu-id="6bf7c-106">out `IAssemblyName`restituito.</span><span class="sxs-lookup"><span data-stu-id="6bf7c-106">[out] The returned `IAssemblyName`.</span></span>  
  
 `szAssemblyName`  
 <span data-ttu-id="6bf7c-107">in Nome dell'assembly per il quale creare la nuova istanza di `IAssemblyName`.</span><span class="sxs-lookup"><span data-stu-id="6bf7c-107">[in] The name of the assembly for which to create the new `IAssemblyName` instance.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="6bf7c-108">in Flag da passare al costruttore dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="6bf7c-108">[in] Flags to pass to the object constructor.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="6bf7c-109">in Riservato per l'estendibilità futura.</span><span class="sxs-lookup"><span data-stu-id="6bf7c-109">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="6bf7c-110">`pvReserved` deve essere un riferimento null.</span><span class="sxs-lookup"><span data-stu-id="6bf7c-110">`pvReserved` must be a null reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6bf7c-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6bf7c-111">Requirements</span></span>  
 <span data-ttu-id="6bf7c-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6bf7c-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6bf7c-113">**Intestazione:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="6bf7c-113">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="6bf7c-114">**Libreria:** Incluso come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="6bf7c-114">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6bf7c-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6bf7c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6bf7c-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6bf7c-116">See also</span></span>

- [<span data-ttu-id="6bf7c-117">Interfaccia IAssemblyName</span><span class="sxs-lookup"><span data-stu-id="6bf7c-117">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
- [<span data-ttu-id="6bf7c-118">Funzioni statiche globali Fusion</span><span class="sxs-lookup"><span data-stu-id="6bf7c-118">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
