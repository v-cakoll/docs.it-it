---
title: IEnumRAWINPUTDEVIC:Clone
ms.date: 03/30/2017
helpviewer_keywords:
- Clone method [WPF]
ms.assetid: 2a6a1900-aa55-45fa-9382-241d569a2dc4
ms.openlocfilehash: abc8a6e4780c8fe50afcf1b04f7e14aeb6452704
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57485408"
---
# <a name="ienumrawinputdevicclone"></a><span data-ttu-id="24230-102">IEnumRAWINPUTDEVIC:Clone</span><span class="sxs-lookup"><span data-stu-id="24230-102">IEnumRAWINPUTDEVIC:Clone</span></span>
<span data-ttu-id="24230-103">Crea un altro enumeratore del dispositivo di input non elaborato con lo stesso stato dell'enumeratore corrente per eseguire l'iterazione dello stesso elenco.</span><span class="sxs-lookup"><span data-stu-id="24230-103">Creates another raw input device enumerator with the same state as the current enumerator to iterate over the same list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24230-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="24230-104">Syntax</span></span>  
  
```  
HRESULT Clone( [out] IEnumRAWINPUTDEVICE **ppenum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="24230-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="24230-105">Parameters</span></span>  
 `ppenum`  
  
 <span data-ttu-id="24230-106">[out] Indirizzo della variabile di output che riceve la [IEnumRAWINPUTDEVICE](ienumrawinputdevice.md) puntatore a interfaccia.</span><span class="sxs-lookup"><span data-stu-id="24230-106">[out] Address of output variable that receives the [IEnumRAWINPUTDEVICE](ienumrawinputdevice.md) interface pointer.</span></span> <span data-ttu-id="24230-107">Se il metodo ha esito negativo, il valore di questa variabile di output non è definito.</span><span class="sxs-lookup"><span data-stu-id="24230-107">If the method is unsuccessful, the value of this output variable is undefined.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="24230-108">Valore proprietà/Valore restituito</span><span class="sxs-lookup"><span data-stu-id="24230-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="24230-109">HRESULT: Questo metodo supporta i valori restituiti standard E_INVALIDARG ed E_OUTOFMEMORY E_UNEXPECTED.</span><span class="sxs-lookup"><span data-stu-id="24230-109">HRESULT: This method supports the standard return values E_INVALIDARG, E_OUTOFMEMORY, and E_UNEXPECTED.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="24230-110">Note</span><span class="sxs-lookup"><span data-stu-id="24230-110">Remarks</span></span>  
 <span data-ttu-id="24230-111">Questo metodo rende possibile registrare un punto nella sequenza di enumerazione per tornare a quel punto in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="24230-111">This method makes it possible to record a point in the enumeration sequence in order to return to that point at a later time.</span></span> <span data-ttu-id="24230-112">Il chiamante deve rilasciare il nuovo enumeratore separatamente dal primo enumeratore.</span><span class="sxs-lookup"><span data-stu-id="24230-112">The caller must release this new enumerator separately from the first enumerator.</span></span>
