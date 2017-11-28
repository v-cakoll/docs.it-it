---
title: IEnumRAWINPUTDEVIC:Clone
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Clone method [WPF]
ms.assetid: 2a6a1900-aa55-45fa-9382-241d569a2dc4
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 35f3c00f3a0efd41c425ba29f8465a73e78d624c
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2017
---
# <a name="ienumrawinputdevicclone"></a>IEnumRAWINPUTDEVIC:Clone
Crea un altro enumeratore del dispositivo di input non elaborato con lo stesso stato dell'enumeratore corrente per eseguire l'iterazione dello stesso elenco.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT Clone( [out] IEnumRAWINPUTDEVICE **ppenum);  
```  
  
#### <a name="parameters"></a>Parametri  
 `ppenum`  
  
 [out] Indirizzo della variabile di output che riceve il [IEnumRAWINPUTDEVICE](../../../../docs/framework/wpf/app-development/ienumrawinputdevice.md) puntatore a interfaccia. Se il metodo ha esito negativo, il valore di questa variabile di output è definito.  
  
## <a name="property-valuereturn-value"></a>Valore proprietà/Valore restituito  
 HRESULT: Questo metodo supporta i valori restituiti standard E_INVALIDARG ed E_OUTOFMEMORY, E_UNEXPECTED.  
  
## <a name="remarks"></a>Note  
 Questo metodo consente di registrare un punto nella sequenza di enumerazione per tornare a quel punto in un secondo momento. Il chiamante deve rilasciare il nuovo enumeratore separatamente dal primo enumeratore.
