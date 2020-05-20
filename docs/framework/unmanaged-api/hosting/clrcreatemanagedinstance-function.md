---
title: Funzione ClrCreateManagedInstance
ms.date: 03/30/2017
api_name:
- ClrCreateManagedInstance
api_location:
- mscoree.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
- mscorsvr.dll
api_type:
- DLLExport
f1_keywords:
- ClrCreateManagedInstance
helpviewer_keywords:
- ClrCreateManagedInstance function [.NET Framework hosting]
ms.assetid: 58ba42c0-4857-43bf-a039-73a4dc6544c2
topic_type:
- apiref
ms.openlocfilehash: ecd618ecf08836ea5e38ce738f97fc91ee6426f4
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616814"
---
# <a name="clrcreatemanagedinstance-function"></a><span data-ttu-id="efb2c-102">Funzione ClrCreateManagedInstance</span><span class="sxs-lookup"><span data-stu-id="efb2c-102">ClrCreateManagedInstance Function</span></span>
<span data-ttu-id="efb2c-103">Crea un'istanza del tipo gestito specificato.</span><span class="sxs-lookup"><span data-stu-id="efb2c-103">Creates an instance of the specified managed type.</span></span>  
  
 <span data-ttu-id="efb2c-104">Questa funzione è stata deprecata nel .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="efb2c-104">This function has been deprecated in the .NET Framework 4.</span></span> <span data-ttu-id="efb2c-105">Utilizzare l'attivazione COM per creare un'istanza del tipo gestito oppure utilizzare l'hosting (vedere [le interfacce di hosting CLR aggiunte in .NET Framework 4 e 4,5](clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)).</span><span class="sxs-lookup"><span data-stu-id="efb2c-105">Use COM activation to create an instance of the managed type, or use hosting (see [CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5](clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="efb2c-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="efb2c-106">Syntax</span></span>  
  
```cpp  
STDAPI ClrCreateManagedInstance (  
    [in]  LPCWSTR  pTypeName,
    [in]  REFIID   riid,
    [out] void     **ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="efb2c-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="efb2c-107">Parameters</span></span>  
 `pTypeName`  
 <span data-ttu-id="efb2c-108">in Puntatore al nome del tipo di istanza richiesto.</span><span class="sxs-lookup"><span data-stu-id="efb2c-108">[in] A pointer to the name of the instance type being requested.</span></span>  
  
 `riid`  
 <span data-ttu-id="efb2c-109">in Oggetto `IID` del tipo di istanza richiesto.</span><span class="sxs-lookup"><span data-stu-id="efb2c-109">[in] The `IID` of the instance type being requested.</span></span>  
  
 `ppObject`  
 <span data-ttu-id="efb2c-110">out Puntatore a un puntatore a un'istanza del tipo gestito richiesta dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="efb2c-110">[out] A pointer to a pointer to an instance of the managed type that was requested by the caller.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="efb2c-111">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="efb2c-111">Remarks</span></span>  
 <span data-ttu-id="efb2c-112">Il Common Language Runtime deve essere già caricato in un processo.</span><span class="sxs-lookup"><span data-stu-id="efb2c-112">The common language runtime should already be loaded into a process.</span></span> <span data-ttu-id="efb2c-113">Ad esempio, può essere caricata utilizzando una chiamata alla funzione [CorBindToRuntimeEx](corbindtoruntimeex-function.md) prima che `ClrCreateManagedInstance` venga chiamata la funzione.</span><span class="sxs-lookup"><span data-stu-id="efb2c-113">For example, it can be loaded by using a call to the [CorBindToRuntimeEx](corbindtoruntimeex-function.md) function before the `ClrCreateManagedInstance` function is called.</span></span> <span data-ttu-id="efb2c-114">Se il runtime non è caricato, `ClrCreateManagedInstance` tenta innanzitutto di caricare v 1.0.3705 del runtime.</span><span class="sxs-lookup"><span data-stu-id="efb2c-114">If the runtime is not loaded, `ClrCreateManagedInstance` first tries to load v1.0.3705 of the runtime.</span></span> <span data-ttu-id="efb2c-115">Se l'operazione ha esito negativo, tenta di caricare la versione più recente del runtime.</span><span class="sxs-lookup"><span data-stu-id="efb2c-115">If that fails, it attempts to load the latest version of the runtime.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="efb2c-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="efb2c-116">Requirements</span></span>  
 <span data-ttu-id="efb2c-117">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="efb2c-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="efb2c-118">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="efb2c-118">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="efb2c-119">**Libreria:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="efb2c-119">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="efb2c-120">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="efb2c-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efb2c-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="efb2c-121">See also</span></span>

- [<span data-ttu-id="efb2c-122">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="efb2c-122">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
- [<span data-ttu-id="efb2c-123">Hosting</span><span class="sxs-lookup"><span data-stu-id="efb2c-123">Hosting</span></span>](index.md)
