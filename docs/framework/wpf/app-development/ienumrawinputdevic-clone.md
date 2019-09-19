---
title: IEnumRAWINPUTDEVIC:Clone
ms.date: 03/30/2017
helpviewer_keywords:
- Clone method [WPF]
ms.assetid: 2a6a1900-aa55-45fa-9382-241d569a2dc4
ms.openlocfilehash: cd634b4d4a88d83d425b787ed8493f9aa2504988
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053413"
---
# <a name="ienumrawinputdevicclone"></a>IEnumRAWINPUTDEVIC:Clone
Crea un altro enumeratore del dispositivo di input non elaborato con lo stesso stato dell'enumeratore corrente per eseguire l'iterazione dello stesso elenco.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT Clone( [out] IEnumRAWINPUTDEVICE **ppenum);  
```  
  
## <a name="parameters"></a>Parametri  
 `ppenum`  
  
 out Indirizzo della variabile di output che riceve il puntatore all'interfaccia [IEnumRAWINPUTDEVICE](ienumrawinputdevice.md) . Se il metodo ha esito negativo, il valore di questa variabile di output non è definito.  
  
## <a name="property-valuereturn-value"></a>Valore proprietà/Valore restituito  
 HRESULT: Questo metodo supporta i valori restituiti standard E_INVALIDARG, E_OUTOFMEMORY e E_UNEXPECTED.  
  
## <a name="remarks"></a>Note  
 Questo metodo consente di registrare un punto nella sequenza di enumerazione per tornare a tale punto in un secondo momento. Il chiamante deve rilasciare questo nuovo enumeratore separatamente dal primo enumeratore.
