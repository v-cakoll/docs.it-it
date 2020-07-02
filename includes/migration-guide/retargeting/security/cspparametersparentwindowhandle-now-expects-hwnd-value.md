---
ms.openlocfilehash: 4b5c886ad35afbbf0a68e03b3174ab9ea1f5524f
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614513"
---
### <a name="cspparametersparentwindowhandle-now-expects-hwnd-value"></a>CspParameters.ParentWindowHandle prevede ora un valore HWND

#### <a name="details"></a>Dettagli

Il valore <xref:System.Security.Cryptography.CspParameters.ParentWindowHandle>, introdotto in .NET Framework 2.0, consente a un'applicazione di registrare il valore di un handle di finestra padre in modo che qualsiasi interfaccia utente necessaria per accedere alla chiave (ad esempio, una finestra di dialogo di richiesta di PIN o di consenso) venga aperta come finestra figlio modale nella finestra specificata. A partire dalle app destinate a .NET Framework 4.7, un'applicazione Windows Forms può impostare la proprietà <xref:System.Security.Cryptography.CspParameters.ParentWindowHandle> con codice simile al seguente:

```csharp
cspParameters.ParentWindowHandle = form.Handle;
```

Nelle versioni precedenti di .NET Framework il valore previsto era una proprietà <xref:System.IntPtr?displayProperty=fullName> che rappresentava la posizione in memoria in cui risiedeva il valore [HWND](https://docs.microsoft.com/windows/desktop/WinProg/windows-data-types#HWND). L'impostazione di questa proprietà su form.Handle in Windows 7 e versioni precedenti non aveva alcun effetto, mentre in Windows 8 e versioni successive il risultato è &quot;<xref:System.Security.Cryptography.CryptographicException?displayProperty=fullName>: Parametro non corretto.&quot;

#### <a name="suggestion"></a>Suggerimento

Le applicazioni destinate a .NET Framework 4.7 o versioni successive che desiderano registrare una relazione della finestra padre sono invitate a usare la forma semplificata:

```csharp
cspParameters.ParentWindowHandle = form.Handle;
```

Gli utenti che hanno identificato che il valore corretto da passare era l'indirizzo della posizione di memoria contenente il valore `form.Handle` possono rifiutare esplicitamente la modifica funzionale impostando l'opzione di AppContext `Switch.System.Security.Cryptography.DoNotAddrOfCspParentWindowHandle` su `true`:

- Impostando a livello di codice le opzioni di compatibilità in AppContext, come spiegato [qui](https://devblogs.microsoft.com/dotnet/net-announcements-at-build-2015/#dotnet46).
- Aggiungendo la riga seguente alla sezione `<runtime>` del file app.config:

```xml
<runtime>
 <AppContextSwitchOverrides value="Switch.System.Security.Cryptography.DoNotAddrOfCspParentWindowHandle=true"/>
</runtime>
```

Al contrario, gli utenti che acconsentono esplicitamente al nuovo comportamento per il runtime di .NET Framework 4.7, quando l'applicazione viene caricata in versioni precedenti di .NET Framework possono impostare l'opzione AppContext su `false`.

| Nome    | Valore       |
|:--------|:------------|
| Scope   | Minorenne       |
| Version | 4.7         |
| Type    | Ridestinazione |

#### <a name="affected-apis"></a>API interessate

- <xref:System.Security.Cryptography.CspParameters.ParentWindowHandle?displayProperty=nameWithType>
