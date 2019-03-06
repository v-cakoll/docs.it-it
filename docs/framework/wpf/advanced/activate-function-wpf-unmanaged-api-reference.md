---
title: Funzione Activate (riferimenti alle API WPF non gestite)
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- Acrivate
api_location:
- PresentationHost_v0400.dll
ms.assetid: 1400329c-b598-465f-80f2-e3dabf044811
ms.openlocfilehash: 6410b05a1b858a7b75c9bff3220d47505beabd7c
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57357274"
---
# <a name="activate-function-wpf-unmanaged-api-reference"></a>Funzione Activate (riferimenti alle API WPF non gestite)
Questa API supporta l'infrastruttura Windows Presentation Foundation (WPF) e non deve essere usato direttamente dal codice.  
  
 Utilizzata dall'infrastruttura Windows Presentation Foundation (WPF) per la gestione di windows.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
void Activate(  
    const ActivateParameters* pParameters,  
    __deref_out_ecount(1) LPUNKNOWN* ppInner,  
    );  
```  
  
#### <a name="parameters"></a>Parametri  
 pParameters  
 Puntatore a parametri di attivazione della finestra.  
  
 ppInner  
 Un puntatore all'indirizzo di un buffer a elemento singolo che contiene un puntatore a un <xref:Microsoft.VisualStudio.OLE.Interop.IOleDocument> oggetto.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Visualizzare [requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **DLL:**  
  
 In .NET Framework 3.0 e 3.5: PresentationHostDLL.dll  
  
 In .NET Framework 4 e versioni successive: PresentationHost_v0400.dll  
  
 **Versione di .NET framework:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Riferimenti alle API non gestite di WPF](wpf-unmanaged-api-reference.md)
