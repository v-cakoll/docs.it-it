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
ms.openlocfilehash: 644a8e724a280a8b23048a381a099acd6e655d2c
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2017
---
# <a name="ienumrawinputdevicnext"></a>IEnumRAWINPUTDEVIC:Next
Enumera le `celt` [RAWINPUTDEVICE](http://msdn.microsoft.com/library/default.asp?url=/library/winui/winui/windowsuserinterface/userinput/rawinput/rawinputreference/rawinputstructures/rawinputdevice.asp) strutture nell'elenco dell'enumeratore, che vengono restituiti in `rgelt` insieme al numero effettivo di elementi enumerati in `pceltFetched`.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT Next(  
      [in] ULONG celt,  
      [out, size_is(celt), length_is(*pceltFetched)] RAWINPUTDEVICE *rgelt,  
      [out] ULONG *pceltFetched);  
```  
  
#### <a name="parameters"></a>Parametri  
 `celt`  
  
 [in] Numero di [RAWINPUTDEVICE](http://msdn.microsoft.com/library/default.asp?url=/library/winui/winui/windowsuserinterface/userinput/rawinput/rawinputreference/rawinputstructures/rawinputdevice.asp) strutture restituite in `rgelt`.  
  
 `rgelt`  
  
 [out] Matrice di dimensione celt (o superiore) per ricevere le strutture RAWINPUTDEVICE enumerate.  
  
 `pceltFetched`  
  
 [out] Puntatore al numero di elementi effettivamente forniti in `rgelt`. Il chiamante può passare `NULL` se `rgelt` è uno.  
  
## <a name="property-valuereturn-value"></a>Valore proprietà/Valore restituito  
 HRESULT: S_OK se il numero di elementi forniti è `celt`; in caso contrario S_FALSE.
