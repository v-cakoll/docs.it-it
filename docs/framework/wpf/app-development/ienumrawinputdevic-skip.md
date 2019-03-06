---
title: IEnumRAWINPUTDEVIC:Skip
ms.date: 03/30/2017
helpviewer_keywords:
- Skip method [WPF]
ms.assetid: c967b0f8-1c6a-459c-8c16-d4f08918ab65
ms.openlocfilehash: fadf7b5526598f446eb7e49640bf4d43ec7395bf
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57354518"
---
# <a name="ienumrawinputdevicskip"></a><span data-ttu-id="d4e16-102">IEnumRAWINPUTDEVIC:Skip</span><span class="sxs-lookup"><span data-stu-id="d4e16-102">IEnumRAWINPUTDEVIC:Skip</span></span>
<span data-ttu-id="d4e16-103">Indica all'enumeratore di ignorare i successivi `celt` gli elementi nell'enumerazione in modo che alla successiva chiamata a [ienumrawinputdevic: Next](ienumrawinputdevic-next.md) non restituirà gli elementi.</span><span class="sxs-lookup"><span data-stu-id="d4e16-103">Instructs the enumerator to skip the next `celt` elements in the enumeration so that the next call to [IEnumRAWINPUTDEVIC:Next](ienumrawinputdevic-next.md) will not return those elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4e16-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d4e16-104">Syntax</span></span>  
  
```  
HRESULT Skip( [in] ULONG celt);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d4e16-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d4e16-105">Parameters</span></span>  
 `celt`  
  
 <span data-ttu-id="d4e16-106">[in] Numero di elementi da ignorare.</span><span class="sxs-lookup"><span data-stu-id="d4e16-106">[in] Number of elements to be skipped.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="d4e16-107">Valore proprietà/Valore restituito</span><span class="sxs-lookup"><span data-stu-id="d4e16-107">Property Value/Return Value</span></span>  
 <span data-ttu-id="d4e16-108">HRESULT: S_OK se il numero di elementi forniti è `celt`; In caso contrario S_FALSE.</span><span class="sxs-lookup"><span data-stu-id="d4e16-108">HRESULT: S_OK if the number of elements supplied is `celt`; S_FALSE otherwise.</span></span>
