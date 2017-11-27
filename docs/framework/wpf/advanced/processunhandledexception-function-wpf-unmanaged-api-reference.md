---
title: Funzione ProcessUnhandledException (riferimenti alle API non gestita di WPF)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: cpp
api_name: ProcessUnhandledException
api_location: PresentationHost_v0400.dll
ms.assetid: 495ce5f6-bb4d-4b30-807a-c3c35f1ca95c
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8328ae4bcbff54743e8df0a4b6ff6da3065ea470
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="processunhandledexception-function-wpf-unmanaged-api-reference"></a>Funzione ProcessUnhandledException (riferimenti alle API non gestita di WPF)
Questa API supporta l'infrastruttura di Windows Presentation Foundation (WPF) e non deve essere utilizzato direttamente dal codice.  
  
 Utilizzata dall'infrastruttura di Windows Presentation Foundation (WPF) per la gestione delle eccezioni.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
void __stdcall ProcessUnhandledException(  
   __in_ecount(1) BSTR errorMsg  
)  
```  
  
#### <a name="parameters"></a>Parametri  
 errorMsg  
 Messaggio di errore.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **DLL:**  
  
 In .NET Framework 3.0 e 3.5: PresentationHostDLL.dll  
  
 In .NET Framework 4 e versioni successive: PresentationHost_v0400.dll  
  
 **Versione di .NET framework:**[!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Riferimenti alle API non gestite di WPF](../../../../docs/framework/wpf/advanced/wpf-unmanaged-api-reference.md)
