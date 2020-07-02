---
ms.openlocfilehash: 67e3ff5000ebd38064ed8a57e4fe561afa31f8d8
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614480"
---
### <a name="long-path-support"></a>Supporto del percorso lungo

#### <a name="details"></a>Dettagli

A partire dalle app destinate a .NET Framework 4.6.2, i percorsi lunghi (fino a 32 KB di caratteri) sono supportati e il limite di 260 caratteri (o `MAX_PATH`) per la lunghezza dei percorsi è stato rimosso. Per le app ricompilate con destinazione .NET Framework 4.6.2, i percorsi che in precedenza generavano una <xref:System.IO.PathTooLongException?displayProperty=fullName> a causa di un percorso più lungo di 260 caratteri genereranno ora una <xref:System.IO.PathTooLongException?displayProperty=fullName> solo nelle condizioni seguenti:

- La lunghezza del percorso è maggiore di <xref:System.Int16.MaxValue> (32.767) caratteri.
- Il sistema operativo restituisce `COR_E_PATHTOOLONG` o equivalente.
Per le app destinate a .NET Framework 4.6.1 e versioni precedenti, il runtime genera automaticamente un'eccezione <xref:System.IO.PathTooLongException?displayProperty=fullName> ogni volta che un percorso supera i 260 caratteri.

#### <a name="suggestion"></a>Suggerimento

Per le app destinate a .NET Framework 4.6.2, è possibile rifiutare esplicitamente il supporto di percorsi lunghi se non opportuno aggiungendo il codice seguente alla sezione `<runtime>` del file `app.config`:

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.IO.BlockLongPaths=true" />
</runtime>
```

Per le app destinate alle versioni precedenti di .NET Framework, ma eseguite in .NET Framework 4.6.2 o versioni successive è possibile acconsentire esplicitamente al supporto dei percorsi lunghi aggiungendo il codice seguente alla sezione `<runtime>` del file `app.config`:

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.IO.BlockLongPaths=false" />
</runtime>
```

| Nome    | Valore       |
|:--------|:------------|
| Scope   | Minorenne       |
| Version | 4.6.2       |
| Type    | Ridestinazione |
