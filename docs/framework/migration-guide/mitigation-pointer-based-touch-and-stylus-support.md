---
title: 'Mitigazione: Supporto di tocco e stilo basato su puntatore'
ms.date: 04/07/2017
helpviewer_keywords:
- retargeting changes
- .NET Framework 4.7 retargeting changes
- WPF retargeting changes
- WPF pointer-based touch and stylus stack
ms.assetid: f99126b5-c396-48f9-8233-8f36b4c9e717
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9264d8eb7923663061f9bccfffe5b8f5254549f0
ms.sourcegitcommit: 4735bb7741555bcb870d7b42964d3774f4897a6e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/30/2019
ms.locfileid: "66379898"
---
# <a name="mitigation-pointer-based-touch-and-stylus-support"></a>Mitigazione: Supporto di tocco e stilo basato su puntatore

Le applicazioni WPF destinate a .NET Framework 4.7 e che sono in esecuzione nei sistemi Windows a partire da Windows 10 Creators Update possono abilitare lo stack facoltativo di tocco/stilo basato su `WM_POINTER`.

## <a name="impact"></a>Impatto

Gli sviluppatori che non attivano in modo esplicito il supporto tocco/stilo basato su puntatore non dovrebbero riscontrare alcuna modifica nel comportamento di tocco/stilo WPF.

Di seguito sono riportati problemi noti correnti con lo stack tocco/stilo basato su `WM_POINTER`:

- Nessun supporto per l'input penna in tempo reale.

   Anche se i plug-in della stilo e dell'input penna continuano a funzionare, essi vengono elaborati nel thread dell'interfaccia utente, il che può comportare un peggioramento delle prestazioni.

- Modifiche del comportamento dovuti alla promozione da eventi di tocco/stilo agli eventi del mouse.

  - La modifica potrebbe avere un comportamento diverso.

  - L'opzione Trascina selezione non dà la risposta appropriata per l'input tocco. (Questa operazione non influisce sull'input della stilo.)

  - L'opzione Trascina selezione non può essere avviata per gli eventi di tocco/stilo.

      Questo può potenzialmente bloccare l'applicazione fino a quando non viene rilevato l'input del mouse. Gli sviluppatori dovranno quindi avviare l'opzione di trascinamento della selezione dagli eventi del mouse.

## <a name="opting-in-to-wmpointer-based-touchstylus-support"></a>Consenso esplicito al supporto di tocco/stilo basato su WM_POINTER

Gli sviluppatori che desiderano abilitare questo stack possono aggiungere quanto segue al file app.config dell'applicazione:

```xml
<configuration>
    <runtime>
        <AppContextSwitchOverrides value="Switch.System.Windows.Input.Stylus.EnablePointerSupport=true"/>
    </runtime>
</configuration>
```

Rimuovendo questa voce o impostandone il valore su `false`, questo stack facoltativo viene disattivato.

## <a name="see-also"></a>Vedere anche

- [Retargeting Changes in the .NET Framework 4.7 (Reindirizzamento delle modifiche in .NET Framework 4.7)](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-7.md)
