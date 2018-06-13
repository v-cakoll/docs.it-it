---
title: Funzione ProcessUnhandledException (riferimenti alle API non gestita di WPF)
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ProcessUnhandledException
api_location:
- PresentationHost_v0400.dll
ms.assetid: 495ce5f6-bb4d-4b30-807a-c3c35f1ca95c
ms.openlocfilehash: bcde3fe6d3fdc1749f29a5c9f7625f802dd49535
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33544524"
---
# <a name="processunhandledexception-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="9eb69-102">Funzione ProcessUnhandledException (riferimenti alle API non gestita di WPF)</span><span class="sxs-lookup"><span data-stu-id="9eb69-102">ProcessUnhandledException Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="9eb69-103">Questa API supporta l'infrastruttura di Windows Presentation Foundation (WPF) e non deve essere utilizzato direttamente dal codice.</span><span class="sxs-lookup"><span data-stu-id="9eb69-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="9eb69-104">Utilizzata dall'infrastruttura di Windows Presentation Foundation (WPF) per la gestione delle eccezioni.</span><span class="sxs-lookup"><span data-stu-id="9eb69-104">Used by the Windows Presentation Foundation (WPF) infrastructure for exception handling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9eb69-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9eb69-105">Syntax</span></span>  
  
```cpp  
void __stdcall ProcessUnhandledException(  
   __in_ecount(1) BSTR errorMsg  
)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9eb69-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="9eb69-106">Parameters</span></span>  
 <span data-ttu-id="9eb69-107">errorMsg</span><span class="sxs-lookup"><span data-stu-id="9eb69-107">errorMsg</span></span>  
 <span data-ttu-id="9eb69-108">Messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="9eb69-108">The error message.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9eb69-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9eb69-109">Requirements</span></span>  
 <span data-ttu-id="9eb69-110">**Piattaforme:** vedere [requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9eb69-110">**Platforms:** See [.NET Framework System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9eb69-111">**DLL:**</span><span class="sxs-lookup"><span data-stu-id="9eb69-111">**DLL:**</span></span>  
  
 <span data-ttu-id="9eb69-112">In .NET Framework 3.0 e 3.5: PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="9eb69-112">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="9eb69-113">In .NET Framework 4 e versioni successive: PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="9eb69-113">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="9eb69-114">**Versione di .NET framework:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9eb69-114">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9eb69-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9eb69-115">See Also</span></span>  
 [<span data-ttu-id="9eb69-116">Riferimenti alle API non gestite di WPF</span><span class="sxs-lookup"><span data-stu-id="9eb69-116">WPF Unmanaged API Reference</span></span>](../../../../docs/framework/wpf/advanced/wpf-unmanaged-api-reference.md)
