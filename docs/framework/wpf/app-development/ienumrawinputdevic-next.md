---
title: IEnumRAWINPUTDEVIC:Next
ms.date: 03/30/2017
helpviewer_keywords:
- Next method [WPF]
ms.assetid: 3698b44d-510e-4d18-b32b-85f17188ee26
ms.openlocfilehash: 329a2cd96346e199ee834856dd6dbfac6175b722
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/03/2018
ms.locfileid: "43481178"
---
# <a name="ienumrawinputdevicnext"></a><span data-ttu-id="5c3b4-102">IEnumRAWINPUTDEVIC:Next</span><span class="sxs-lookup"><span data-stu-id="5c3b4-102">IEnumRAWINPUTDEVIC:Next</span></span>
<span data-ttu-id="5c3b4-103">Enumera le `celt` [RAWINPUTDEVICE](https://msdn.microsoft.com/library/default.asp?url=/library/winui/winui/windowsuserinterface/userinput/rawinput/rawinputreference/rawinputstructures/rawinputdevice.asp) nell'elenco dell'enumeratore, che vengono restituiti in strutture `rgelt` insieme al numero effettivo di elementi enumerati in `pceltFetched`.</span><span class="sxs-lookup"><span data-stu-id="5c3b4-103">Enumerates the next `celt` [RAWINPUTDEVICE](https://msdn.microsoft.com/library/default.asp?url=/library/winui/winui/windowsuserinterface/userinput/rawinput/rawinputreference/rawinputstructures/rawinputdevice.asp) structures in the enumerator's list, returning them in `rgelt` along with the actual number of enumerated elements in `pceltFetched`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c3b4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5c3b4-104">Syntax</span></span>  
  
```  
HRESULT Next(  
      [in] ULONG celt,  
      [out, size_is(celt), length_is(*pceltFetched)] RAWINPUTDEVICE *rgelt,  
      [out] ULONG *pceltFetched);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5c3b4-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="5c3b4-105">Parameters</span></span>  
 `celt`  
  
 <span data-ttu-id="5c3b4-106">[in] Numerosi [RAWINPUTDEVICE](https://msdn.microsoft.com/library/default.asp?url=/library/winui/winui/windowsuserinterface/userinput/rawinput/rawinputreference/rawinputstructures/rawinputdevice.asp) strutture restituite in `rgelt`.</span><span class="sxs-lookup"><span data-stu-id="5c3b4-106">[in] Number of [RAWINPUTDEVICE](https://msdn.microsoft.com/library/default.asp?url=/library/winui/winui/windowsuserinterface/userinput/rawinput/rawinputreference/rawinputstructures/rawinputdevice.asp) structures returned in `rgelt`.</span></span>  
  
 `rgelt`  
  
 <span data-ttu-id="5c3b4-107">[out] Matrice di dimensione celt (o superiore) per ricevere le strutture RAWINPUTDEVICE enumerate.</span><span class="sxs-lookup"><span data-stu-id="5c3b4-107">[out] Array of size celt (or larger) to receive enumerated RAWINPUTDEVICE structures.</span></span>  
  
 `pceltFetched`  
  
 <span data-ttu-id="5c3b4-108">[out] Puntatore al numero di elementi effettivamente forniti in `rgelt`.</span><span class="sxs-lookup"><span data-stu-id="5c3b4-108">[out] Pointer to the number of elements actually supplied in `rgelt`.</span></span> <span data-ttu-id="5c3b4-109">Il chiamante può passare `NULL` se `rgelt` è uno.</span><span class="sxs-lookup"><span data-stu-id="5c3b4-109">Caller can pass in `NULL` if `rgelt` is one.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="5c3b4-110">Valore proprietà/Valore restituito</span><span class="sxs-lookup"><span data-stu-id="5c3b4-110">Property Value/Return Value</span></span>  
 <span data-ttu-id="5c3b4-111">HRESULT: S_OK se il numero di elementi forniti è `celt`; in caso contrario S_FALSE.</span><span class="sxs-lookup"><span data-stu-id="5c3b4-111">HRESULT: S_OK if the number of elements supplied is `celt`; S_FALSE otherwise.</span></span>
