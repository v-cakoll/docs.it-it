---
title: Funzione CreateIDispatchSTAForwarder-informazioni di riferimento sulle API WPF non gestite
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- CreateIDispatchSTAForwarder
api_location:
- PresentationHost_v0400.dll
ms.assetid: 57a02dfa-f091-4ace-9c06-1f4ab52b3527
ms.openlocfilehash: 67f2542733fb9c6af197c99ede2bd097ce876b5d
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76738039"
---
# <a name="createidispatchstaforwarder-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="b49b3-102">Funzione CreateIDispatchSTAForwarder (riferimenti alle API non gestite WPF)</span><span class="sxs-lookup"><span data-stu-id="b49b3-102">CreateIDispatchSTAForwarder Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="b49b3-103">Questa API supporta l'infrastruttura Windows Presentation Foundation (WPF) e non può essere usata direttamente dal codice.</span><span class="sxs-lookup"><span data-stu-id="b49b3-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="b49b3-104">Utilizzato dall'infrastruttura Windows Presentation Foundation (WPF) per la gestione di thread e finestre.</span><span class="sxs-lookup"><span data-stu-id="b49b3-104">Used by the Windows Presentation Foundation (WPF) infrastructure for thread and windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b49b3-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b49b3-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateIDispatchSTAForwarder(  
   __in IDispatch *pDispatchDelegate,   
   __deref_out IDispatch **ppForwarder  
)  
```  
  
## <a name="parameters"></a><span data-ttu-id="b49b3-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="b49b3-106">Parameters</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="b49b3-107">Valore proprietà/Valore restituito</span><span class="sxs-lookup"><span data-stu-id="b49b3-107">Property Value/Return Value</span></span>  
 <span data-ttu-id="b49b3-108">pDispatchDelegate</span><span class="sxs-lookup"><span data-stu-id="b49b3-108">pDispatchDelegate</span></span>  
 <span data-ttu-id="b49b3-109">Puntatore a un'interfaccia `IDispatch`.</span><span class="sxs-lookup"><span data-stu-id="b49b3-109">A pointer to an `IDispatch` interface.</span></span>  
  
 <span data-ttu-id="b49b3-110">ppForwarder</span><span class="sxs-lookup"><span data-stu-id="b49b3-110">ppForwarder</span></span>  
 <span data-ttu-id="b49b3-111">Puntatore all'indirizzo di un'interfaccia `IDispatch`.</span><span class="sxs-lookup"><span data-stu-id="b49b3-111">A pointer to the address of an `IDispatch` interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b49b3-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b49b3-112">Requirements</span></span>  
 <span data-ttu-id="b49b3-113">**Piattaforme:** Vedere [.NET Framework requisiti di sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b49b3-113">**Platforms:** See [.NET Framework System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b49b3-114">**DLL**</span><span class="sxs-lookup"><span data-stu-id="b49b3-114">**DLL:**</span></span>  
  
 <span data-ttu-id="b49b3-115">Nel .NET Framework 3,0 e 3,5: PresentationHostDLL. dll</span><span class="sxs-lookup"><span data-stu-id="b49b3-115">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="b49b3-116">In .NET Framework 4 e versioni successive: PresentationHost_v0400. dll</span><span class="sxs-lookup"><span data-stu-id="b49b3-116">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="b49b3-117">**Versione .NET Framework:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b49b3-117">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b49b3-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b49b3-118">See also</span></span>

- [<span data-ttu-id="b49b3-119">Riferimenti alle API non gestite di WPF</span><span class="sxs-lookup"><span data-stu-id="b49b3-119">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
