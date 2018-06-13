---
title: IEnumRAWINPUTDEVIC:Clone
ms.date: 03/30/2017
helpviewer_keywords:
- Clone method [WPF]
ms.assetid: 2a6a1900-aa55-45fa-9382-241d569a2dc4
ms.openlocfilehash: da089e5342e641ffebe22ca6a4a593f97faeb89c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33545343"
---
# <a name="ienumrawinputdevicclone"></a><span data-ttu-id="2abb8-102">IEnumRAWINPUTDEVIC:Clone</span><span class="sxs-lookup"><span data-stu-id="2abb8-102">IEnumRAWINPUTDEVIC:Clone</span></span>
<span data-ttu-id="2abb8-103">Crea un altro enumeratore del dispositivo di input non elaborato con lo stesso stato dell'enumeratore corrente per eseguire l'iterazione dello stesso elenco.</span><span class="sxs-lookup"><span data-stu-id="2abb8-103">Creates another raw input device enumerator with the same state as the current enumerator to iterate over the same list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2abb8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2abb8-104">Syntax</span></span>  
  
```  
HRESULT Clone( [out] IEnumRAWINPUTDEVICE **ppenum);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2abb8-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="2abb8-105">Parameters</span></span>  
 `ppenum`  
  
 <span data-ttu-id="2abb8-106">[out] Indirizzo della variabile di output che riceve il [IEnumRAWINPUTDEVICE](../../../../docs/framework/wpf/app-development/ienumrawinputdevice.md) puntatore a interfaccia.</span><span class="sxs-lookup"><span data-stu-id="2abb8-106">[out] Address of output variable that receives the [IEnumRAWINPUTDEVICE](../../../../docs/framework/wpf/app-development/ienumrawinputdevice.md) interface pointer.</span></span> <span data-ttu-id="2abb8-107">Se il metodo ha esito negativo, il valore di questa variabile di output è definito.</span><span class="sxs-lookup"><span data-stu-id="2abb8-107">If the method is unsuccessful, the value of this output variable is undefined.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="2abb8-108">Valore proprietà/Valore restituito</span><span class="sxs-lookup"><span data-stu-id="2abb8-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="2abb8-109">HRESULT: Questo metodo supporta i valori restituiti standard E_INVALIDARG ed E_OUTOFMEMORY, E_UNEXPECTED.</span><span class="sxs-lookup"><span data-stu-id="2abb8-109">HRESULT: This method supports the standard return values E_INVALIDARG, E_OUTOFMEMORY, and E_UNEXPECTED.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2abb8-110">Note</span><span class="sxs-lookup"><span data-stu-id="2abb8-110">Remarks</span></span>  
 <span data-ttu-id="2abb8-111">Questo metodo consente di registrare un punto nella sequenza di enumerazione per tornare a quel punto in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="2abb8-111">This method makes it possible to record a point in the enumeration sequence in order to return to that point at a later time.</span></span> <span data-ttu-id="2abb8-112">Il chiamante deve rilasciare il nuovo enumeratore separatamente dal primo enumeratore.</span><span class="sxs-lookup"><span data-stu-id="2abb8-112">The caller must release this new enumerator separately from the first enumerator.</span></span>
