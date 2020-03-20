---
ms.openlocfilehash: 72f907c117748fb19ca0663f24445a8c978afd32
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "68235486"
---
### <a name="cspparametersparentwindowhandle-now-expects-hwnd-value"></a>CspParameters.ParentWindowHandle prevede ora un valore HWND

|   |   |
|---|---|
|Dettagli|Il valore <xref:System.Security.Cryptography.CspParameters.ParentWindowHandle>, introdotto in .NET Framework 2.0, consente a un'applicazione di registrare il valore di un handle di finestra padre in modo che qualsiasi interfaccia utente necessaria per accedere alla chiave (ad esempio, una finestra di dialogo di richiesta di PIN o di consenso) venga aperta come finestra figlio modale nella finestra specificata. A partire dalle app destinate a .NET Framework 4.7, un'applicazione Windows Forms può impostare la proprietà <xref:System.Security.Cryptography.CspParameters.ParentWindowHandle> con codice simile al seguente:<pre><code class="lang-csharp">cspParameters.ParentWindowHandle = form.Handle;&#13;&#10;</code></pre>Nelle versioni precedenti di .NET Framework il valore previsto era una proprietà <xref:System.IntPtr?displayProperty=name> che rappresentava la posizione in memoria in cui risiedeva il valore [HWND](https://docs.microsoft.com/windows/desktop/WinProg/windows-data-types#HWND). L'impostazione di questa proprietà su form.Handle in Windows 7 e versioni precedenti non aveva alcun effetto, mentre in Windows 8 e versioni successive il risultato è &quot;<xref:System.Security.Cryptography.CryptographicException?displayProperty=name>: Parametro non corretto.&quot;|
|Suggerimento|Le applicazioni destinate a .NET Framework 4.7 o versioni successive che desiderano registrare una relazione della finestra padre sono invitate a usare la forma semplificata:<pre><code class="lang-csharp">cspParameters.ParentWindowHandle = form.Handle;&#13;&#10;</code></pre>Gli utenti che hanno identificato che il valore corretto da passare era l'indirizzo della posizione di memoria contenente il valore <code>form.Handle</code> possono rifiutare esplicitamente la modifica funzionale impostando l'opzione di AppContext <code>Switch.System.Security.Cryptography.DoNotAddrOfCspParentWindowHandle</code> su <code>true</code>:<ol><li>Impostando a livello di codice le opzioni di compatibilità in AppContext, come spiegato [qui](https://devblogs.microsoft.com/dotnet/net-announcements-at-build-2015/#dotnet46).</li><li>Aggiungendo la riga seguente alla sezione <code>&lt;runtime&gt;</code> del file app.config:</li></ol><pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Security.Cryptography.DoNotAddrOfCspParentWindowHandle=true&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>Al contrario, gli utenti che acconsentono esplicitamente al nuovo comportamento per il runtime di .NET Framework 4.7, quando l'applicazione viene caricata in versioni precedenti di .NET Framework possono impostare l'opzione AppContext su <code>false</code>.|
|Scope|Minorenne|
|Versione|4.7|
|Type|Ridestinazione|
|API interessate|<ul><li><xref:System.Security.Cryptography.CspParameters.ParentWindowHandle?displayProperty=nameWithType></li></ul>|
