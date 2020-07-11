---
ms.openlocfilehash: f87d0dbeda6094bd745f5b580772b1161f30d0d5
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2020
ms.locfileid: "86218232"
---
### <a name="change-in-path-separator-character-in-fullname-property-of-ziparchiveentry-objects"></a><span data-ttu-id="b8299-101">Modifica del carattere separatore di percorso nella proprietà FullName degli oggetti ZipArchiveEntry</span><span class="sxs-lookup"><span data-stu-id="b8299-101">Change in path separator character in FullName property of ZipArchiveEntry objects</span></span>

#### <a name="details"></a><span data-ttu-id="b8299-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="b8299-102">Details</span></span>

<span data-ttu-id="b8299-103">Per le app destinate a .NET Framework 4.6.1 e versioni successive, il carattere separatore di percorso è stato modificato da una barra rovesciata (" \\ ") a una barra ("/") nella <xref:System.IO.Compression.ZipArchiveEntry.FullName> proprietà degli <xref:System.IO.Compression.ZipArchiveEntry> oggetti creati da overload del <xref:System.IO.Compression.ZipFile.CreateFromDirectory%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="b8299-103">For apps that target the .NET Framework 4.6.1 and later versions, the path separator character has changed from a backslash ("\\") to a forward slash ("/") in the <xref:System.IO.Compression.ZipArchiveEntry.FullName> property of <xref:System.IO.Compression.ZipArchiveEntry>  objects created by overloads of the <xref:System.IO.Compression.ZipFile.CreateFromDirectory%2A> method.</span></span> <span data-ttu-id="b8299-104">Questa modifica garantisce la conformità dell'implementazione .NET alla sezione 4.4.17.1 della [specifica relativa al formato di file ZIP](https://pkware.cachefly.net/webdocs/casestudies/APPNOTE.TXT) e consente agli archivi con estensione ZIP di essere decompressi anche in sistemi non Windows.</span><span class="sxs-lookup"><span data-stu-id="b8299-104">The change brings the .NET implementation into conformity with section 4.4.17.1 of the [.ZIP File Format Specification](https://pkware.cachefly.net/webdocs/casestudies/APPNOTE.TXT) and allows .ZIP archives to be decompressed on non-Windows systems.</span></span><br /><span data-ttu-id="b8299-105">La decompressione di un file ZIP creato da un'applicazione che ha come destinazione una versione precedente di .NET Framework nei sistemi operativi non Windows, ad esempio Macintosh, non riesce a mantenere la struttura della directory.</span><span class="sxs-lookup"><span data-stu-id="b8299-105">Decompressing a zip file created by an app that targets a previous version of the .NET Framework on non-Windows operating systems such as the Macintosh fails to preserve the directory structure.</span></span> <span data-ttu-id="b8299-106">Ad esempio, su Macintosh, crea un set di file il cui nome concatena il percorso della directory, insieme a qualsiasi barra rovesciata ("\\") e al nome del file.</span><span class="sxs-lookup"><span data-stu-id="b8299-106">For example, on the Macintosh, it creates a set of files whose filename concatenates the directory path, along with any backslash ("\\") characters, and the filename.</span></span> <span data-ttu-id="b8299-107">Di conseguenza, la struttura di directory dei file decompressi non viene mantenuta.</span><span class="sxs-lookup"><span data-stu-id="b8299-107">As a result, the directory structure of decompressed files is not preserved.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="b8299-108">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="b8299-108">Suggestion</span></span>

<span data-ttu-id="b8299-109">L'effetto di questa modifica su. I file ZIP decompressi nel sistema operativo Windows dalle API nello <xref:System.IO?displayProperty=nameWithType> spazio dei nomi .NET Framework devono essere minimi, poiché queste API possono gestire facilmente una barra ("/") o una barra rovesciata (" \\ ") come carattere separatore di percorso.</span><span class="sxs-lookup"><span data-stu-id="b8299-109">The impact of this change on .ZIP files that are decompressed on the Windows operating system by APIs in the .NET Framework <xref:System.IO?displayProperty=nameWithType> namespace should be minimal, since these APIs can seamlessly handle either a forward slash ("/") or a backslash ("\\") as the path separator character.</span></span><br /><span data-ttu-id="b8299-110">Se questa modifica è indesiderata, è possibile rifiutarla esplicitamente aggiungendo un'impostazione di configurazione alla [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) sezione del file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b8299-110">If this change is undesirable, you can opt out of it by adding a configuration setting to the [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of your application configuration file.</span></span> <span data-ttu-id="b8299-111">L'esempio seguente mostra sia la sezione `<runtime>` che l'opzione per il rifiuto esplicito `Switch.System.IO.Compression.ZipFile.UseBackslash`:</span><span class="sxs-lookup"><span data-stu-id="b8299-111">The following example shows both the `<runtime>` section and the `Switch.System.IO.Compression.ZipFile.UseBackslash` opt-out switch:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.IO.Compression.ZipFile.UseBackslash=true" />
</runtime>
```

<span data-ttu-id="b8299-112">Inoltre, le app destinate alle versioni precedenti del .NET Framework ma sono in esecuzione nel .NET Framework 4.6.1 e versioni successive possono acconsentire esplicitamente a questo comportamento aggiungendo un'impostazione di configurazione alla [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) sezione del file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b8299-112">In addition, apps that target previous versions of the .NET Framework but are running on the .NET Framework 4.6.1 and later versions can opt in to this behavior by adding a configuration setting to the [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of the application configuration file.</span></span> <span data-ttu-id="b8299-113">L'esempio seguente mostra sia la sezione `<runtime>` che l'opzione per il consenso esplicito `Switch.System.IO.Compression.ZipFile.UseBackslash`.</span><span class="sxs-lookup"><span data-stu-id="b8299-113">The following shows both the `<runtime>` section and the `Switch.System.IO.Compression.ZipFile.UseBackslash` opt-in switch.</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.IO.Compression.ZipFile.UseBackslash=false" />
</runtime>
```

| <span data-ttu-id="b8299-114">Nome</span><span class="sxs-lookup"><span data-stu-id="b8299-114">Name</span></span>    | <span data-ttu-id="b8299-115">Valore</span><span class="sxs-lookup"><span data-stu-id="b8299-115">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="b8299-116">Ambito</span><span class="sxs-lookup"><span data-stu-id="b8299-116">Scope</span></span>   | <span data-ttu-id="b8299-117">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="b8299-117">Edge</span></span>        |
| <span data-ttu-id="b8299-118">Versione</span><span class="sxs-lookup"><span data-stu-id="b8299-118">Version</span></span> | <span data-ttu-id="b8299-119">4.6.1</span><span class="sxs-lookup"><span data-stu-id="b8299-119">4.6.1</span></span>       |
| <span data-ttu-id="b8299-120">Tipo</span><span class="sxs-lookup"><span data-stu-id="b8299-120">Type</span></span>    | <span data-ttu-id="b8299-121">Ridestinazione</span><span class="sxs-lookup"><span data-stu-id="b8299-121">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="b8299-122">API interessate</span><span class="sxs-lookup"><span data-stu-id="b8299-122">Affected APIs</span></span>

- <xref:System.IO.Compression.ZipFile.CreateFromDirectory(System.String,System.String)?displayProperty=nameWithType>
- <xref:System.IO.Compression.ZipFile.CreateFromDirectory(System.String,System.String,System.IO.Compression.CompressionLevel,System.Boolean)?displayProperty=nameWithType>
- <xref:System.IO.Compression.ZipFile.CreateFromDirectory(System.String,System.String,System.IO.Compression.CompressionLevel,System.Boolean,System.Text.Encoding)?displayProperty=nameWithType>
