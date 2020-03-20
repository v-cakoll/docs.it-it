---
title: Funzione LoadFromHistory - Riferimento all'API non gestita WPF
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- LoadFromHistory
api_location:
- PresentationHost_v0400.dll
ms.assetid: d037c062-a911-4949-b251-ccd3e48b1d17
ms.openlocfilehash: be9b8658614e678b4370044a753554859d230fed
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141575"
---
# <a name="loadfromhistory-function-wpf-unmanaged-api-reference"></a>LoadFromHistory Function (WPF Unmanaged API Reference)
Questa API supporta l'infrastruttura Windows Presentation Foundation (WPF) e non può essere utilizzata direttamente dal codice.  
  
 Utilizzato dall'infrastruttura di Windows Presentation Foundation (WPF) per la gestione delle finestre.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT LoadFromHistory_export(  
        IStream* pHistoryStream,
        IBindCtx* pBindCtx  
)  
```  
  
## <a name="parameters"></a>Parametri  
 pHistoryStream (corso)  
 Puntatore a un flusso di informazioni sulla cronologia.  
  
 pBindCtx (informazioni in stato in questo stato indetto in  
 Puntatore a un contesto di associazione.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere Requisiti di sistema [di .NET Framework](../../get-started/system-requirements.md).  
  
 **DLL:**  
  
 In .NET Framework 3.0 e 3.5: PresentationHostDLL.dll  
  
 In .NET Framework 4 e versioni successive: PresentationHost_v0400.dll  
  
 **Versione di .NET Framework:**[!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Riferimenti alle API non gestite WPF](wpf-unmanaged-api-reference.md)
