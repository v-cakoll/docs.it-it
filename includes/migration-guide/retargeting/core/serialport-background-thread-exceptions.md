---
ms.openlocfilehash: e66a5c2a33a4ab5cf35013c1843936ffd01f90a2
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614504"
---
### <a name="serialport-background-thread-exceptions"></a>Eccezioni di thread in background SerialPort

#### <a name="details"></a>Dettagli

I thread in background creati con flussi <xref:System.IO.Ports.SerialPort> non terminano più il processo quando vengono generate eccezioni del sistema operativo. <br/>Nelle applicazioni destinate a .NET Framework 4.7 e versioni precedenti, un processo viene terminato quando viene generata un'eccezione del sistema operativo in un thread in background creato con un flusso <xref:System.IO.Ports.SerialPort>. <br/>Nelle applicazioni destinate a .NET Framework 4.7.1 o versioni successive, i thread in background attendono gli eventi del sistema operativo relativi alla porta seriale attiva e possono arrestarsi in modo anomalo in alcuni casi, ad esempio in caso di rimozione improvvisa della porta seriale.

#### <a name="suggestion"></a>Suggerimento

Per le app destinate a .NET Framework 4.7.1, è possibile rifiutare esplicitamente la gestione delle eccezioni, nel caso non sia opportuna, aggiungendo il codice seguente alla sezione `<runtime>` del file `app.config`:

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.IO.Ports.DoNotCatchSerialStreamThreadExceptions=true" />
</runtime>
```

Per le app destinate alle versioni precedenti di .NET Framework, ma eseguite in .NET Framework 4.7.1 o versioni successive è possibile acconsentire esplicitamente alla gestione delle eccezioni aggiungendo il codice seguente alla sezione `<runtime>` del file `app.config`:

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.IO.Ports.DoNotCatchSerialStreamThreadExceptions=false" />
</runtime>
```

| Nome    | Valore       |
|:--------|:------------|
| Scope   | Minorenne       |
| Version | 4.7.1       |
| Type    | Ridestinazione |

#### <a name="affected-apis"></a>API interessate

- <xref:System.IO.Ports.SerialPort?displayProperty=nameWithType>
