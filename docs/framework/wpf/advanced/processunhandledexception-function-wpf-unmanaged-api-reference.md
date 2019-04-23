---
title: Funzione ProcessUnhandledException (riferimenti alle API WPF non gestite)
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ProcessUnhandledException
api_location:
- PresentationHost_v0400.dll
ms.assetid: 495ce5f6-bb4d-4b30-807a-c3c35f1ca95c
ms.openlocfilehash: 0c8751454be6e0eed547c38e9d0bc7931abaec3d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59196970"
---
# <a name="processunhandledexception-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="0ef81-102">Funzione ProcessUnhandledException (riferimenti alle API WPF non gestite)</span><span class="sxs-lookup"><span data-stu-id="0ef81-102">ProcessUnhandledException Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="0ef81-103">Questa API supporta l'infrastruttura Windows Presentation Foundation (WPF) e non deve essere usato direttamente dal codice.</span><span class="sxs-lookup"><span data-stu-id="0ef81-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="0ef81-104">Utilizzata dall'infrastruttura Windows Presentation Foundation (WPF) per la gestione delle eccezioni.</span><span class="sxs-lookup"><span data-stu-id="0ef81-104">Used by the Windows Presentation Foundation (WPF) infrastructure for exception handling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ef81-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0ef81-105">Syntax</span></span>  
  
```cpp  
void __stdcall ProcessUnhandledException(  
   __in_ecount(1) BSTR errorMsg  
)  
```  
  
## <a name="parameters"></a><span data-ttu-id="0ef81-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="0ef81-106">Parameters</span></span>  
 <span data-ttu-id="0ef81-107">errorMsg</span><span class="sxs-lookup"><span data-stu-id="0ef81-107">errorMsg</span></span>  
 <span data-ttu-id="0ef81-108">Messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="0ef81-108">The error message.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0ef81-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0ef81-109">Requirements</span></span>  
 <span data-ttu-id="0ef81-110">**Piattaforme:** Visualizzare [requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0ef81-110">**Platforms:** See [.NET Framework System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0ef81-111">**DLL:**</span><span class="sxs-lookup"><span data-stu-id="0ef81-111">**DLL:**</span></span>  
  
 <span data-ttu-id="0ef81-112">In .NET Framework 3.0 e 3.5: PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="0ef81-112">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="0ef81-113">In .NET Framework 4 e versioni successive: PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="0ef81-113">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="0ef81-114">**Versione di .NET framework:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0ef81-114">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ef81-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0ef81-115">See also</span></span>

- [<span data-ttu-id="0ef81-116">Riferimenti alle API non gestite di WPF</span><span class="sxs-lookup"><span data-stu-id="0ef81-116">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
