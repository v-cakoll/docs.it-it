---
title: Funzione CreateIDispatchSTAForwarder - Riferimento all'API non gestita WPFCreateIDispatchSTAForwarder Function - WPF unmanaged API reference
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- CreateIDispatchSTAForwarder
api_location:
- PresentationHost_v0400.dll
ms.assetid: 57a02dfa-f091-4ace-9c06-1f4ab52b3527
ms.openlocfilehash: e151ffa6eb5f1dc7479c699e0d7f9f3f57833ebd
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174719"
---
# <a name="createidispatchstaforwarder-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="7ce05-102">CreateIDispatchSTAForwarder Function (WPF Unmanaged API Reference)</span><span class="sxs-lookup"><span data-stu-id="7ce05-102">CreateIDispatchSTAForwarder Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="7ce05-103">Questa API supporta l'infrastruttura Windows Presentation Foundation (WPF) e non può essere utilizzata direttamente dal codice.</span><span class="sxs-lookup"><span data-stu-id="7ce05-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="7ce05-104">Utilizzato dall'infrastruttura di Windows Presentation Foundation (WPF) per la gestione di thread e finestre.</span><span class="sxs-lookup"><span data-stu-id="7ce05-104">Used by the Windows Presentation Foundation (WPF) infrastructure for thread and windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ce05-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7ce05-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateIDispatchSTAForwarder(  
   __in IDispatch *pDispatchDelegate,
   __deref_out IDispatch **ppForwarder  
)  
```  
  
## <a name="parameters"></a><span data-ttu-id="7ce05-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="7ce05-106">Parameters</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="7ce05-107">Valore proprietà/Valore restituito</span><span class="sxs-lookup"><span data-stu-id="7ce05-107">Property Value/Return Value</span></span>  
 <span data-ttu-id="7ce05-108">pDispatchDelegate</span><span class="sxs-lookup"><span data-stu-id="7ce05-108">pDispatchDelegate</span></span>  
 <span data-ttu-id="7ce05-109">Puntatore a `IDispatch` un'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="7ce05-109">A pointer to an `IDispatch` interface.</span></span>  
  
 <span data-ttu-id="7ce05-110">ppForwarder (ppForwarder)</span><span class="sxs-lookup"><span data-stu-id="7ce05-110">ppForwarder</span></span>  
 <span data-ttu-id="7ce05-111">Puntatore all'indirizzo `IDispatch` di un'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="7ce05-111">A pointer to the address of an `IDispatch` interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7ce05-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7ce05-112">Requirements</span></span>  
 <span data-ttu-id="7ce05-113">**Piattaforme:** Vedere Requisiti di sistema [di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7ce05-113">**Platforms:** See [.NET Framework System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7ce05-114">**DLL:**</span><span class="sxs-lookup"><span data-stu-id="7ce05-114">**DLL:**</span></span>  
  
 <span data-ttu-id="7ce05-115">In .NET Framework 3.0 e 3.5: PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="7ce05-115">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="7ce05-116">In .NET Framework 4 e versioni successive: PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="7ce05-116">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="7ce05-117">**Versione di .NET Framework:**[!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7ce05-117">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ce05-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7ce05-118">See also</span></span>

- [<span data-ttu-id="7ce05-119">Riferimenti alle API non gestite WPF</span><span class="sxs-lookup"><span data-stu-id="7ce05-119">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
