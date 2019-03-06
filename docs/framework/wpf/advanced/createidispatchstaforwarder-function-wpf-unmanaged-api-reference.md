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
ms.openlocfilehash: 1a19b7699c7a9e2b663149ea31bccb67189e68c4
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57487824"
---
# <a name="createidispatchstaforwarder-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="28964-102">Funzione CreateIDispatchSTAForwarder (riferimenti alle API WPF non gestite)</span><span class="sxs-lookup"><span data-stu-id="28964-102">CreateIDispatchSTAForwarder Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="28964-103">Questa API supporta l'infrastruttura Windows Presentation Foundation (WPF) e non deve essere usato direttamente dal codice.</span><span class="sxs-lookup"><span data-stu-id="28964-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="28964-104">Utilizzata dall'infrastruttura Windows Presentation Foundation (WPF) per la gestione dei thread e windows.</span><span class="sxs-lookup"><span data-stu-id="28964-104">Used by the Windows Presentation Foundation (WPF) infrastructure for thread and windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28964-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="28964-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateIDispatchSTAForwarder(  
   __in IDispatch *pDispatchDelegate,   
   __deref_out IDispatch **ppForwarder  
)  
```  
  
## <a name="parameters"></a><span data-ttu-id="28964-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="28964-106">Parameters</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="28964-107">Valore proprietà/Valore restituito</span><span class="sxs-lookup"><span data-stu-id="28964-107">Property Value/Return Value</span></span>  
 <span data-ttu-id="28964-108">pDispatchDelegate</span><span class="sxs-lookup"><span data-stu-id="28964-108">pDispatchDelegate</span></span>  
 <span data-ttu-id="28964-109">Un puntatore a un `IDispatch` interfaccia.</span><span class="sxs-lookup"><span data-stu-id="28964-109">A pointer to an `IDispatch` interface.</span></span>  
  
 <span data-ttu-id="28964-110">ppForwarder</span><span class="sxs-lookup"><span data-stu-id="28964-110">ppForwarder</span></span>  
 <span data-ttu-id="28964-111">Un puntatore all'indirizzo di un `IDispatch` interfaccia.</span><span class="sxs-lookup"><span data-stu-id="28964-111">A pointer to the address of an `IDispatch` interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="28964-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="28964-112">Requirements</span></span>  
 <span data-ttu-id="28964-113">**Piattaforme:** Visualizzare [requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="28964-113">**Platforms:** See [.NET Framework System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="28964-114">**DLL:**</span><span class="sxs-lookup"><span data-stu-id="28964-114">**DLL:**</span></span>  
  
 <span data-ttu-id="28964-115">In .NET Framework 3.0 e 3.5: PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="28964-115">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="28964-116">In .NET Framework 4 e versioni successive: PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="28964-116">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="28964-117">**Versione di .NET framework:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="28964-117">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28964-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="28964-118">See also</span></span>
- [<span data-ttu-id="28964-119">Riferimenti alle API non gestite di WPF</span><span class="sxs-lookup"><span data-stu-id="28964-119">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
