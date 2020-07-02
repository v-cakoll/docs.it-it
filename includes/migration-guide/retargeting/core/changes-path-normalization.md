---
ms.openlocfilehash: 04c4fb4c8e9da8c58a5e26f78a7b13aa6a0df4a0
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614464"
---
### <a name="changes-in-path-normalization"></a><span data-ttu-id="dd9b6-101">Modifica nella normalizzazione del percorso</span><span class="sxs-lookup"><span data-stu-id="dd9b6-101">Changes in path normalization</span></span>

#### <a name="details"></a><span data-ttu-id="dd9b6-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="dd9b6-102">Details</span></span>

<span data-ttu-id="dd9b6-103">A partire dalle app destinate a .NET Framework 4.6.2, il modo in cui il runtime normalizza i percorsi è cambiato. La normalizzazione di un percorso implica la modifica della stringa che identifica un percorso o un file in modo che sia conforme a un percorso valido nel sistema operativo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="dd9b6-103">Starting with apps that target the .NET Framework 4.6.2, the way in which the runtime normalizes paths has changed.Normalizing a path involves modifying the string that identifies a path or file so that it conforms to a valid path on the target operating system.</span></span> <span data-ttu-id="dd9b6-104">In genere, la normalizzazione implica:</span><span class="sxs-lookup"><span data-stu-id="dd9b6-104">Normalization typically involves:</span></span>

- <span data-ttu-id="dd9b6-105">La conversione in forma canonica dei separatori di directory e dei componenti.</span><span class="sxs-lookup"><span data-stu-id="dd9b6-105">Canonicalizing component and directory separators.</span></span>
- <span data-ttu-id="dd9b6-106">L'applicazione della directory corrente in un percorso relativo.</span><span class="sxs-lookup"><span data-stu-id="dd9b6-106">Applying the current directory to a relative path.</span></span>
- <span data-ttu-id="dd9b6-107">La valutazione della directory relativa (.) o della directory padre (..) in un percorso.</span><span class="sxs-lookup"><span data-stu-id="dd9b6-107">Evaluating the relative directory (.) or the parent directory (..) in a path.</span></span>
- <span data-ttu-id="dd9b6-108">La rimozione di caratteri specificati.</span><span class="sxs-lookup"><span data-stu-id="dd9b6-108">Trimming specified characters.</span></span>
<span data-ttu-id="dd9b6-109">Le modifiche seguenti per la normalizzazione del percorso sono abilitate per impostazione predefinita a partire dalle app destinate a .NET Framework 4.6.2:</span><span class="sxs-lookup"><span data-stu-id="dd9b6-109">Starting with apps that target the .NET Framework 4.6.2, the following changes in path normalization are enabled by default:</span></span>
  - <span data-ttu-id="dd9b6-110">Il runtime viene rinviato alla funzione [GetFullPathName](https://docs.microsoft.com/windows/desktop/api/fileapi/nf-fileapi-getfullpathnamew) del sistema operativo per normalizzare i percorsi.</span><span class="sxs-lookup"><span data-stu-id="dd9b6-110">The runtime defers to the operating system's [GetFullPathName](https://docs.microsoft.com/windows/desktop/api/fileapi/nf-fileapi-getfullpathnamew) function to normalize paths.</span></span>
- <span data-ttu-id="dd9b6-111">La normalizzazione non consiste più nel rimuovere la fine dei segmenti di directory (ad esempio uno spazio alla fine di un nome di directory).</span><span class="sxs-lookup"><span data-stu-id="dd9b6-111">Normalization no longer involves trimming the end of directory segments (such as a space at the end of a directory name).</span></span>
- <span data-ttu-id="dd9b6-112">Supporto per la sintassi del percorso dispositivo in attendibilità totale, tra cui `\\.\` e, per le API del file I/O in mscorlib.dll, `\\?\`.</span><span class="sxs-lookup"><span data-stu-id="dd9b6-112">Support for device path syntax in full trust, including `\\.\` and, for file I/O APIs in mscorlib.dll, `\\?\`.</span></span>
- <span data-ttu-id="dd9b6-113">Il runtime non convalida i percorsi di sintassi del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="dd9b6-113">The runtime does not validate device syntax paths.</span></span>
- <span data-ttu-id="dd9b6-114">È supportato l'uso della sintassi del dispositivo per accedere ai flussi di dati alternativi.</span><span class="sxs-lookup"><span data-stu-id="dd9b6-114">The use of device syntax to access alternate data streams is supported.</span></span>
<span data-ttu-id="dd9b6-115">Queste modifiche migliorano le prestazioni, consentendo al contempo ai metodi di accedere a percorsi in precedenza inaccessibili.</span><span class="sxs-lookup"><span data-stu-id="dd9b6-115">These changes improve performance while allowing methods to access previously inaccessible paths.</span></span> <span data-ttu-id="dd9b6-116">Le applicazioni destinate a .NET Framework 4.6.1 e versioni precedenti ma in esecuzione in .NET Framework 4.6.2 o versioni successive non sono interessate da questa modifica.</span><span class="sxs-lookup"><span data-stu-id="dd9b6-116">Apps that target the .NET Framework 4.6.1 and earlier versions but are running under the .NET Framework 4.6.2 or later are unaffected by this change.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="dd9b6-117">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="dd9b6-117">Suggestion</span></span>

<span data-ttu-id="dd9b6-118">Le app destinate a .NET Framework 4.6.2 o versioni successive possono rifiutare esplicitamente questa modifica e usare la normalizzazione legacy aggiungendo il codice seguente alla sezione `<runtime>` del file di configurazione dell'applicazione:</span><span class="sxs-lookup"><span data-stu-id="dd9b6-118">Apps that target the .NET Framework 4.6.2 or later can opt out of this change and use legacy normalization by adding the following to the `<runtime>` section of the application configuration file:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.IO.UseLegacyPathHandling=true" />
</runtime>
```

<span data-ttu-id="dd9b6-119">Le app destinate a .NET Framework 4.6.1 o versioni precedenti ma in esecuzione su .NET Framework 4.6.2 o versioni successive possono abilitare le modifiche alla normalizzazione del percorso aggiungendo la riga seguente alla sezione `<runtime>` del file di configurazione dell'applicazione:</span><span class="sxs-lookup"><span data-stu-id="dd9b6-119">Apps that target the .NET Framework 4.6.1 or earlier but are running on the .NET Framework 4.6.2 or later can enable the changes to path normalization by adding the following line to the `<runtime>` section of the application .configuration file:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.IO.UseLegacyPathHandling=false" />
</runtime>
```

| <span data-ttu-id="dd9b6-120">Nome</span><span class="sxs-lookup"><span data-stu-id="dd9b6-120">Name</span></span>    | <span data-ttu-id="dd9b6-121">Valore</span><span class="sxs-lookup"><span data-stu-id="dd9b6-121">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="dd9b6-122">Scope</span><span class="sxs-lookup"><span data-stu-id="dd9b6-122">Scope</span></span>   | <span data-ttu-id="dd9b6-123">Minorenne</span><span class="sxs-lookup"><span data-stu-id="dd9b6-123">Minor</span></span>       |
| <span data-ttu-id="dd9b6-124">Version</span><span class="sxs-lookup"><span data-stu-id="dd9b6-124">Version</span></span> | <span data-ttu-id="dd9b6-125">4.6.2</span><span class="sxs-lookup"><span data-stu-id="dd9b6-125">4.6.2</span></span>       |
| <span data-ttu-id="dd9b6-126">Type</span><span class="sxs-lookup"><span data-stu-id="dd9b6-126">Type</span></span>    | <span data-ttu-id="dd9b6-127">Ridestinazione</span><span class="sxs-lookup"><span data-stu-id="dd9b6-127">Retargeting</span></span> |
