---
title: Funzione ForwardTranslateAccelerator (riferimenti alle API non gestita di WPF)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: cpp
api_name: ForwardTranslateAccelerator
api_location: PresentationHost_v0400.dll
ms.assetid: fff47a86-9d9f-4176-9530-10e1876e393f
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 663b28ed1a9430a6280ccd0ee9a44da2dea0c3cd
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="forwardtranslateaccelerator-function-wpf-unmanaged-api-reference"></a>Funzione ForwardTranslateAccelerator (riferimenti alle API non gestita di WPF)
Questa API supporta l'infrastruttura di Windows Presentation Foundation (WPF) e non deve essere utilizzato direttamente dal codice.  
  
 Utilizzata dall'infrastruttura di Windows Presentation Foundation (WPF) per la gestione di windows.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT ForwardTranslateAccelerator(  
   MSG* pMsg,   
   VARIANT_BOOL appUnhandled  
)  
```  
  
#### <a name="parameters"></a>Parametri  
 pMsg  
 Un puntatore a un messaggio.  
  
 appUnhandled  
 `true`Quando l'app è già stato fornito l'opportunità di gestire il messaggio di input, ma non è gestito. in caso contrario, `false`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **DLL:**  
  
 In .NET Framework 3.0 e 3.5: PresentationHostDLL.dll  
  
 In .NET Framework 4 e versioni successive: PresentationHost_v0400.dll  
  
 **Versione di .NET framework:**[!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Riferimenti alle API non gestite di WPF](../../../../docs/framework/wpf/advanced/wpf-unmanaged-api-reference.md)
