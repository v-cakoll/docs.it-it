---
title: 'Funzione Activate: informazioni di riferimento sulle API WPF non gestite'
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- Activate
api_location:
- PresentationHost_v0400.dll
ms.assetid: 1400329c-b598-465f-80f2-e3dabf044811
ms.openlocfilehash: 9c0a235e8b94294ab82da88e43f7446c29739c12
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76734506"
---
# <a name="activate-function-wpf-unmanaged-api-reference"></a>Funzione Activate (riferimenti alle API non gestite WPF)

Questa API supporta l'infrastruttura Windows Presentation Foundation (WPF) e non può essere usata direttamente dal codice.

Utilizzato dall'infrastruttura Windows Presentation Foundation (WPF) per la gestione di Windows.

## <a name="syntax"></a>Sintassi

```cpp
void Activate(
    const ActivateParameters* pParameters,
    __deref_out_ecount(1) LPUNKNOWN* ppInner,
    );
```

## <a name="parameters"></a>Parametri

`pParameters`\
Puntatore ai parametri di attivazione della finestra.

`ppInner`\
Puntatore all'indirizzo di un buffer a elemento singolo che contiene un puntatore a un oggetto <xref:Microsoft.VisualStudio.OLE.Interop.IOleDocument>.

## <a name="requirements"></a>Requisiti

**Piattaforme:** Vedere [.NET Framework requisiti di sistema](../../get-started/system-requirements.md).

**DLL**

Nel .NET Framework 3,0 e 3,5: PresentationHostDLL. dll

In .NET Framework 4 e versioni successive: PresentationHost_v0400. dll

**Versione .NET Framework:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]

## <a name="see-also"></a>Vedere anche

- [Riferimenti alle API non gestite di WPF](wpf-unmanaged-api-reference.md)
