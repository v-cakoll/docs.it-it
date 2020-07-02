---
ms.openlocfilehash: e66a5c2a33a4ab5cf35013c1843936ffd01f90a2
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614504"
---
### <a name="serialport-background-thread-exceptions"></a><span data-ttu-id="244d3-101">Eccezioni di thread in background SerialPort</span><span class="sxs-lookup"><span data-stu-id="244d3-101">SerialPort background thread exceptions</span></span>

#### <a name="details"></a><span data-ttu-id="244d3-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="244d3-102">Details</span></span>

<span data-ttu-id="244d3-103">I thread in background creati con flussi <xref:System.IO.Ports.SerialPort> non terminano più il processo quando vengono generate eccezioni del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="244d3-103">Background threads created with <xref:System.IO.Ports.SerialPort> streams no longer terminate the process when OS exceptions are thrown.</span></span> <br/><span data-ttu-id="244d3-104">Nelle applicazioni destinate a .NET Framework 4.7 e versioni precedenti, un processo viene terminato quando viene generata un'eccezione del sistema operativo in un thread in background creato con un flusso <xref:System.IO.Ports.SerialPort>.</span><span class="sxs-lookup"><span data-stu-id="244d3-104">In applications that target the .NET Framework 4.7 and earlier versions, a process is terminated when an operating system exception is thrown on a background thread created with a <xref:System.IO.Ports.SerialPort> stream.</span></span> <br/><span data-ttu-id="244d3-105">Nelle applicazioni destinate a .NET Framework 4.7.1 o versioni successive, i thread in background attendono gli eventi del sistema operativo relativi alla porta seriale attiva e possono arrestarsi in modo anomalo in alcuni casi, ad esempio in caso di rimozione improvvisa della porta seriale.</span><span class="sxs-lookup"><span data-stu-id="244d3-105">In applications that target the .NET Framework 4.7.1 or a later version, background threads wait for OS events related to the active serial port and could crash in some cases, such as sudden removal of the serial port.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="244d3-106">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="244d3-106">Suggestion</span></span>

<span data-ttu-id="244d3-107">Per le app destinate a .NET Framework 4.7.1, è possibile rifiutare esplicitamente la gestione delle eccezioni, nel caso non sia opportuna, aggiungendo il codice seguente alla sezione `<runtime>` del file `app.config`:</span><span class="sxs-lookup"><span data-stu-id="244d3-107">For apps that target the .NET Framework 4.7.1, you can opt out of the exception handling if it is not desirable by adding the following to the `<runtime>` section of your `app.config` file:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.IO.Ports.DoNotCatchSerialStreamThreadExceptions=true" />
</runtime>
```

<span data-ttu-id="244d3-108">Per le app destinate alle versioni precedenti di .NET Framework, ma eseguite in .NET Framework 4.7.1 o versioni successive è possibile acconsentire esplicitamente alla gestione delle eccezioni aggiungendo il codice seguente alla sezione `<runtime>` del file `app.config`:</span><span class="sxs-lookup"><span data-stu-id="244d3-108">For apps that target earlier versions of the .NET Framework but run on the .NET Framework 4.7.1 or later, you can opt in to the exception handling by adding the following to the `<runtime>` section of your `app.config` file:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.IO.Ports.DoNotCatchSerialStreamThreadExceptions=false" />
</runtime>
```

| <span data-ttu-id="244d3-109">Nome</span><span class="sxs-lookup"><span data-stu-id="244d3-109">Name</span></span>    | <span data-ttu-id="244d3-110">Valore</span><span class="sxs-lookup"><span data-stu-id="244d3-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="244d3-111">Scope</span><span class="sxs-lookup"><span data-stu-id="244d3-111">Scope</span></span>   | <span data-ttu-id="244d3-112">Minorenne</span><span class="sxs-lookup"><span data-stu-id="244d3-112">Minor</span></span>       |
| <span data-ttu-id="244d3-113">Version</span><span class="sxs-lookup"><span data-stu-id="244d3-113">Version</span></span> | <span data-ttu-id="244d3-114">4.7.1</span><span class="sxs-lookup"><span data-stu-id="244d3-114">4.7.1</span></span>       |
| <span data-ttu-id="244d3-115">Type</span><span class="sxs-lookup"><span data-stu-id="244d3-115">Type</span></span>    | <span data-ttu-id="244d3-116">Ridestinazione</span><span class="sxs-lookup"><span data-stu-id="244d3-116">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="244d3-117">API interessate</span><span class="sxs-lookup"><span data-stu-id="244d3-117">Affected APIs</span></span>

- <xref:System.IO.Ports.SerialPort?displayProperty=nameWithType>
