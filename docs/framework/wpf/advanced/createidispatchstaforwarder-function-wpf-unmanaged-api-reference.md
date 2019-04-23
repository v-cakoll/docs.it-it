---
title: Funzione CreateIDispatchSTAForwarder (riferimenti alle API WPF non gestite)
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- CreateIDispatchSTAForwarder
api_location:
- PresentationHost_v0400.dll
ms.assetid: 57a02dfa-f091-4ace-9c06-1f4ab52b3527
ms.openlocfilehash: a89b29cd459060c93d5ca77bb2154e1a10b02d03
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59213650"
---
# <a name="createidispatchstaforwarder-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="f283d-102">Funzione CreateIDispatchSTAForwarder (riferimenti alle API WPF non gestite)</span><span class="sxs-lookup"><span data-stu-id="f283d-102">CreateIDispatchSTAForwarder Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="f283d-103">Questa API supporta l'infrastruttura Windows Presentation Foundation (WPF) e non deve essere usato direttamente dal codice.</span><span class="sxs-lookup"><span data-stu-id="f283d-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="f283d-104">Utilizzata dall'infrastruttura Windows Presentation Foundation (WPF) per la gestione dei thread e windows.</span><span class="sxs-lookup"><span data-stu-id="f283d-104">Used by the Windows Presentation Foundation (WPF) infrastructure for thread and windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f283d-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f283d-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateIDispatchSTAForwarder(  
   __in IDispatch *pDispatchDelegate,   
   __deref_out IDispatch **ppForwarder  
)  
```  
  
## <a name="parameters"></a><span data-ttu-id="f283d-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="f283d-106">Parameters</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="f283d-107">Valore proprietà/Valore restituito</span><span class="sxs-lookup"><span data-stu-id="f283d-107">Property Value/Return Value</span></span>  
 <span data-ttu-id="f283d-108">pDispatchDelegate</span><span class="sxs-lookup"><span data-stu-id="f283d-108">pDispatchDelegate</span></span>  
 <span data-ttu-id="f283d-109">Un puntatore a un `IDispatch` interfaccia.</span><span class="sxs-lookup"><span data-stu-id="f283d-109">A pointer to an `IDispatch` interface.</span></span>  
  
 <span data-ttu-id="f283d-110">ppForwarder</span><span class="sxs-lookup"><span data-stu-id="f283d-110">ppForwarder</span></span>  
 <span data-ttu-id="f283d-111">Un puntatore all'indirizzo di un `IDispatch` interfaccia.</span><span class="sxs-lookup"><span data-stu-id="f283d-111">A pointer to the address of an `IDispatch` interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f283d-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f283d-112">Requirements</span></span>  
 <span data-ttu-id="f283d-113">**Piattaforme:** Visualizzare [requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f283d-113">**Platforms:** See [.NET Framework System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f283d-114">**DLL:**</span><span class="sxs-lookup"><span data-stu-id="f283d-114">**DLL:**</span></span>  
  
 <span data-ttu-id="f283d-115">In .NET Framework 3.0 e 3.5: PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="f283d-115">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="f283d-116">In .NET Framework 4 e versioni successive: PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="f283d-116">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="f283d-117">**Versione di .NET framework:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f283d-117">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f283d-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f283d-118">See also</span></span>

- [<span data-ttu-id="f283d-119">Riferimenti alle API non gestite di WPF</span><span class="sxs-lookup"><span data-stu-id="f283d-119">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
