---
title: IEnumRAWINPUTDEVIC:Next
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Next method [WPF]
ms.assetid: 3698b44d-510e-4d18-b32b-85f17188ee26
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: af6cb5bfe07923e13f1b76c785d830a9af15eaf9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ienumrawinputdevicnext"></a><span data-ttu-id="d77e9-102">IEnumRAWINPUTDEVIC:Next</span><span class="sxs-lookup"><span data-stu-id="d77e9-102">IEnumRAWINPUTDEVIC:Next</span></span>
<span data-ttu-id="d77e9-103">Enumera le `celt` [RAWINPUTDEVICE](http://msdn.microsoft.com/library/default.asp?url=/library/winui/winui/windowsuserinterface/userinput/rawinput/rawinputreference/rawinputstructures/rawinputdevice.asp) strutture nell'elenco dell'enumeratore, che vengono restituiti in `rgelt` insieme al numero effettivo di elementi enumerati in `pceltFetched`.</span><span class="sxs-lookup"><span data-stu-id="d77e9-103">Enumerates the next `celt` [RAWINPUTDEVICE](http://msdn.microsoft.com/library/default.asp?url=/library/winui/winui/windowsuserinterface/userinput/rawinput/rawinputreference/rawinputstructures/rawinputdevice.asp) structures in the enumerator's list, returning them in `rgelt` along with the actual number of enumerated elements in `pceltFetched`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d77e9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d77e9-104">Syntax</span></span>  
  
```  
HRESULT Next(  
      [in] ULONG celt,  
      [out, size_is(celt), length_is(*pceltFetched)] RAWINPUTDEVICE *rgelt,  
      [out] ULONG *pceltFetched);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d77e9-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d77e9-105">Parameters</span></span>  
 `celt`  
  
 <span data-ttu-id="d77e9-106">[in] Numero di [RAWINPUTDEVICE](http://msdn.microsoft.com/library/default.asp?url=/library/winui/winui/windowsuserinterface/userinput/rawinput/rawinputreference/rawinputstructures/rawinputdevice.asp) strutture restituite in `rgelt`.</span><span class="sxs-lookup"><span data-stu-id="d77e9-106">[in] Number of [RAWINPUTDEVICE](http://msdn.microsoft.com/library/default.asp?url=/library/winui/winui/windowsuserinterface/userinput/rawinput/rawinputreference/rawinputstructures/rawinputdevice.asp) structures returned in `rgelt`.</span></span>  
  
 `rgelt`  
  
 <span data-ttu-id="d77e9-107">[out] Matrice di dimensione celt (o superiore) per ricevere le strutture RAWINPUTDEVICE enumerate.</span><span class="sxs-lookup"><span data-stu-id="d77e9-107">[out] Array of size celt (or larger) to receive enumerated RAWINPUTDEVICE structures.</span></span>  
  
 `pceltFetched`  
  
 <span data-ttu-id="d77e9-108">[out] Puntatore al numero di elementi effettivamente forniti in `rgelt`.</span><span class="sxs-lookup"><span data-stu-id="d77e9-108">[out] Pointer to the number of elements actually supplied in `rgelt`.</span></span> <span data-ttu-id="d77e9-109">Il chiamante può passare `NULL` se `rgelt` è uno.</span><span class="sxs-lookup"><span data-stu-id="d77e9-109">Caller can pass in `NULL` if `rgelt` is one.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="d77e9-110">Valore proprietà/Valore restituito</span><span class="sxs-lookup"><span data-stu-id="d77e9-110">Property Value/Return Value</span></span>  
 <span data-ttu-id="d77e9-111">HRESULT: S_OK se il numero di elementi forniti è `celt`; in caso contrario S_FALSE.</span><span class="sxs-lookup"><span data-stu-id="d77e9-111">HRESULT: S_OK if the number of elements supplied is `celt`; S_FALSE otherwise.</span></span>
