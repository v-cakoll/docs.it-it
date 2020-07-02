---
ms.openlocfilehash: 4b5c886ad35afbbf0a68e03b3174ab9ea1f5524f
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614513"
---
### <a name="cspparametersparentwindowhandle-now-expects-hwnd-value"></a><span data-ttu-id="2bcc7-101">CspParameters.ParentWindowHandle prevede ora un valore HWND</span><span class="sxs-lookup"><span data-stu-id="2bcc7-101">CspParameters.ParentWindowHandle now expects HWND value</span></span>

#### <a name="details"></a><span data-ttu-id="2bcc7-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="2bcc7-102">Details</span></span>

<span data-ttu-id="2bcc7-103">Il valore <xref:System.Security.Cryptography.CspParameters.ParentWindowHandle>, introdotto in .NET Framework 2.0, consente a un'applicazione di registrare il valore di un handle di finestra padre in modo che qualsiasi interfaccia utente necessaria per accedere alla chiave (ad esempio, una finestra di dialogo di richiesta di PIN o di consenso) venga aperta come finestra figlio modale nella finestra specificata. A partire dalle app destinate a .NET Framework 4.7, un'applicazione Windows Forms può impostare la proprietà <xref:System.Security.Cryptography.CspParameters.ParentWindowHandle> con codice simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="2bcc7-103">The <xref:System.Security.Cryptography.CspParameters.ParentWindowHandle> value, introduced in .NET Framework 2.0, allows an application to register a parent window handle value such that any UI required to access the key (such as a PIN prompt or consent dialog) opens as a modal child to the specified window.Starting with apps that target the .NET Framework 4.7, a Windows Forms application can set the <xref:System.Security.Cryptography.CspParameters.ParentWindowHandle> property with code like the following:</span></span>

```csharp
cspParameters.ParentWindowHandle = form.Handle;
```

<span data-ttu-id="2bcc7-104">Nelle versioni precedenti di .NET Framework il valore previsto era una proprietà <xref:System.IntPtr?displayProperty=fullName> che rappresentava la posizione in memoria in cui risiedeva il valore [HWND](https://docs.microsoft.com/windows/desktop/WinProg/windows-data-types#HWND).</span><span class="sxs-lookup"><span data-stu-id="2bcc7-104">In previous versions of the .NET Framework, the value was expected to be an <xref:System.IntPtr?displayProperty=fullName> representing a location in memory where the [HWND](https://docs.microsoft.com/windows/desktop/WinProg/windows-data-types#HWND) value resided.</span></span> <span data-ttu-id="2bcc7-105">L'impostazione di questa proprietà su form.Handle in Windows 7 e versioni precedenti non aveva alcun effetto, mentre in Windows 8 e versioni successive il risultato è &quot;<xref:System.Security.Cryptography.CryptographicException?displayProperty=fullName>: Parametro non corretto.&quot;</span><span class="sxs-lookup"><span data-stu-id="2bcc7-105">Setting the property to form.Handle on Windows 7 and earlier versions had no effect, but on Windows 8 and later versions, it results in a &quot;<xref:System.Security.Cryptography.CryptographicException?displayProperty=fullName>: The parameter is incorrect.&quot;</span></span>

#### <a name="suggestion"></a><span data-ttu-id="2bcc7-106">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="2bcc7-106">Suggestion</span></span>

<span data-ttu-id="2bcc7-107">Le applicazioni destinate a .NET Framework 4.7 o versioni successive che desiderano registrare una relazione della finestra padre sono invitate a usare la forma semplificata:</span><span class="sxs-lookup"><span data-stu-id="2bcc7-107">Applications targeting .NET Framework 4.7 or higher wishing to register a parent window relationship are encouraged to use the simplified form:</span></span>

```csharp
cspParameters.ParentWindowHandle = form.Handle;
```

<span data-ttu-id="2bcc7-108">Gli utenti che hanno identificato che il valore corretto da passare era l'indirizzo della posizione di memoria contenente il valore `form.Handle` possono rifiutare esplicitamente la modifica funzionale impostando l'opzione di AppContext `Switch.System.Security.Cryptography.DoNotAddrOfCspParentWindowHandle` su `true`:</span><span class="sxs-lookup"><span data-stu-id="2bcc7-108">Users who had identified that the correct value to pass was the address of a memory location which held the value `form.Handle` can opt out of the behavior change by setting the AppContext switch `Switch.System.Security.Cryptography.DoNotAddrOfCspParentWindowHandle` to `true`:</span></span>

- <span data-ttu-id="2bcc7-109">Impostando a livello di codice le opzioni di compatibilità in AppContext, come spiegato [qui](https://devblogs.microsoft.com/dotnet/net-announcements-at-build-2015/#dotnet46).</span><span class="sxs-lookup"><span data-stu-id="2bcc7-109">By programmatically setting compat switches on the AppContext, as explained [here](https://devblogs.microsoft.com/dotnet/net-announcements-at-build-2015/#dotnet46).</span></span>
- <span data-ttu-id="2bcc7-110">Aggiungendo la riga seguente alla sezione `<runtime>` del file app.config:</span><span class="sxs-lookup"><span data-stu-id="2bcc7-110">By adding the following line to the `<runtime>` section of the app.config file:</span></span>

```xml
<runtime>
 <AppContextSwitchOverrides value="Switch.System.Security.Cryptography.DoNotAddrOfCspParentWindowHandle=true"/>
</runtime>
```

<span data-ttu-id="2bcc7-111">Al contrario, gli utenti che acconsentono esplicitamente al nuovo comportamento per il runtime di .NET Framework 4.7, quando l'applicazione viene caricata in versioni precedenti di .NET Framework possono impostare l'opzione AppContext su `false`.</span><span class="sxs-lookup"><span data-stu-id="2bcc7-111">Conversely, users who wish to opt in to the new behavior on the .NET Framework 4.7 runtime when the application loads under older .NET Framework versions can set the AppContext switch to `false`.</span></span>

| <span data-ttu-id="2bcc7-112">Nome</span><span class="sxs-lookup"><span data-stu-id="2bcc7-112">Name</span></span>    | <span data-ttu-id="2bcc7-113">Valore</span><span class="sxs-lookup"><span data-stu-id="2bcc7-113">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="2bcc7-114">Scope</span><span class="sxs-lookup"><span data-stu-id="2bcc7-114">Scope</span></span>   | <span data-ttu-id="2bcc7-115">Minorenne</span><span class="sxs-lookup"><span data-stu-id="2bcc7-115">Minor</span></span>       |
| <span data-ttu-id="2bcc7-116">Version</span><span class="sxs-lookup"><span data-stu-id="2bcc7-116">Version</span></span> | <span data-ttu-id="2bcc7-117">4.7</span><span class="sxs-lookup"><span data-stu-id="2bcc7-117">4.7</span></span>         |
| <span data-ttu-id="2bcc7-118">Type</span><span class="sxs-lookup"><span data-stu-id="2bcc7-118">Type</span></span>    | <span data-ttu-id="2bcc7-119">Ridestinazione</span><span class="sxs-lookup"><span data-stu-id="2bcc7-119">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="2bcc7-120">API interessate</span><span class="sxs-lookup"><span data-stu-id="2bcc7-120">Affected APIs</span></span>

- <xref:System.Security.Cryptography.CspParameters.ParentWindowHandle?displayProperty=nameWithType>
