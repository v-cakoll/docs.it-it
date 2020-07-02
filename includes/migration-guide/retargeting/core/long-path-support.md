---
ms.openlocfilehash: 67e3ff5000ebd38064ed8a57e4fe561afa31f8d8
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614480"
---
### <a name="long-path-support"></a><span data-ttu-id="7cb6c-101">Supporto del percorso lungo</span><span class="sxs-lookup"><span data-stu-id="7cb6c-101">Long path support</span></span>

#### <a name="details"></a><span data-ttu-id="7cb6c-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="7cb6c-102">Details</span></span>

<span data-ttu-id="7cb6c-103">A partire dalle app destinate a .NET Framework 4.6.2, i percorsi lunghi (fino a 32 KB di caratteri) sono supportati e il limite di 260 caratteri (o `MAX_PATH`) per la lunghezza dei percorsi è stato rimosso. Per le app ricompilate con destinazione .NET Framework 4.6.2, i percorsi che in precedenza generavano una <xref:System.IO.PathTooLongException?displayProperty=fullName> a causa di un percorso più lungo di 260 caratteri genereranno ora una <xref:System.IO.PathTooLongException?displayProperty=fullName> solo nelle condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7cb6c-103">Starting with apps that target the .NET Framework 4.6.2, long paths (of up to 32K characters) are supported, and the 260-character (or `MAX_PATH`) limitation on path lengths has been removed.For apps that are recompiled to target the .NET Framework 4.6.2, code paths that previously threw a <xref:System.IO.PathTooLongException?displayProperty=fullName> because a path exceeded 260 characters will now throw a <xref:System.IO.PathTooLongException?displayProperty=fullName> only under the following conditions:</span></span>

- <span data-ttu-id="7cb6c-104">La lunghezza del percorso è maggiore di <xref:System.Int16.MaxValue> (32.767) caratteri.</span><span class="sxs-lookup"><span data-stu-id="7cb6c-104">The length of the path is greater than <xref:System.Int16.MaxValue> (32,767) characters.</span></span>
- <span data-ttu-id="7cb6c-105">Il sistema operativo restituisce `COR_E_PATHTOOLONG` o equivalente.</span><span class="sxs-lookup"><span data-stu-id="7cb6c-105">The operating system returns `COR_E_PATHTOOLONG` or its equivalent.</span></span>
<span data-ttu-id="7cb6c-106">Per le app destinate a .NET Framework 4.6.1 e versioni precedenti, il runtime genera automaticamente un'eccezione <xref:System.IO.PathTooLongException?displayProperty=fullName> ogni volta che un percorso supera i 260 caratteri.</span><span class="sxs-lookup"><span data-stu-id="7cb6c-106">For apps that target the .NET Framework 4.6.1 and earlier versions, the runtime automatically throws a <xref:System.IO.PathTooLongException?displayProperty=fullName> whenever a path exceeds 260 characters.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="7cb6c-107">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="7cb6c-107">Suggestion</span></span>

<span data-ttu-id="7cb6c-108">Per le app destinate a .NET Framework 4.6.2, è possibile rifiutare esplicitamente il supporto di percorsi lunghi se non opportuno aggiungendo il codice seguente alla sezione `<runtime>` del file `app.config`:</span><span class="sxs-lookup"><span data-stu-id="7cb6c-108">For apps that target the .NET Framework 4.6.2, you can opt out of long path support if it is not desirable by adding the following to the `<runtime>` section of your `app.config` file:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.IO.BlockLongPaths=true" />
</runtime>
```

<span data-ttu-id="7cb6c-109">Per le app destinate alle versioni precedenti di .NET Framework, ma eseguite in .NET Framework 4.6.2 o versioni successive è possibile acconsentire esplicitamente al supporto dei percorsi lunghi aggiungendo il codice seguente alla sezione `<runtime>` del file `app.config`:</span><span class="sxs-lookup"><span data-stu-id="7cb6c-109">For apps that target earlier versions of the .NET Framework but run on the .NET Framework 4.6.2 or later, you can opt in to long path support by adding the following to the `<runtime>` section of your `app.config` file:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.IO.BlockLongPaths=false" />
</runtime>
```

| <span data-ttu-id="7cb6c-110">Nome</span><span class="sxs-lookup"><span data-stu-id="7cb6c-110">Name</span></span>    | <span data-ttu-id="7cb6c-111">Valore</span><span class="sxs-lookup"><span data-stu-id="7cb6c-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="7cb6c-112">Scope</span><span class="sxs-lookup"><span data-stu-id="7cb6c-112">Scope</span></span>   | <span data-ttu-id="7cb6c-113">Minorenne</span><span class="sxs-lookup"><span data-stu-id="7cb6c-113">Minor</span></span>       |
| <span data-ttu-id="7cb6c-114">Version</span><span class="sxs-lookup"><span data-stu-id="7cb6c-114">Version</span></span> | <span data-ttu-id="7cb6c-115">4.6.2</span><span class="sxs-lookup"><span data-stu-id="7cb6c-115">4.6.2</span></span>       |
| <span data-ttu-id="7cb6c-116">Type</span><span class="sxs-lookup"><span data-stu-id="7cb6c-116">Type</span></span>    | <span data-ttu-id="7cb6c-117">Ridestinazione</span><span class="sxs-lookup"><span data-stu-id="7cb6c-117">Retargeting</span></span> |
