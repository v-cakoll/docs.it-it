---
ms.openlocfilehash: c7500550cd9714a9788a7dea68af04823f000f7f
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614798"
---
### <a name="stack-traces-obtained-when-using-portable-pdbs-now-include-source-file-and-line-information-if-requested"></a><span data-ttu-id="8643f-101">Le analisi dello stack ottenute quando si usano file PDB portatili ora includono informazioni su file di origine e righe, se richieste</span><span class="sxs-lookup"><span data-stu-id="8643f-101">Stack traces obtained when using portable PDBs now include source file and line information if requested</span></span>

#### <a name="details"></a><span data-ttu-id="8643f-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="8643f-102">Details</span></span>

<span data-ttu-id="8643f-103">A partire da .NET Framework 4.7.2, le analisi dello stack ottenute quando si usano file PDB portatili includono informazioni su file di origine e righe, se richieste.</span><span class="sxs-lookup"><span data-stu-id="8643f-103">Starting with .NET Framework 4.7.2, stack traces obtained when using portable PDBs include source file and line information when requested.</span></span> <span data-ttu-id="8643f-104">Nelle versioni precedenti a .NET Framework 4.7.2 le informazioni su file di origine e righe non sono disponibili quando si usano file PDB portatili, anche se richieste in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="8643f-104">In versions prior to .NET Framework 4.7.2, source file and line information would be unavailable when using portable PDBs even if explicitly requested.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="8643f-105">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="8643f-105">Suggestion</span></span>

<span data-ttu-id="8643f-106">Per le applicazioni destinate a .NET Framework 4.7.2 è possibile rifiutare esplicitamente le informazioni su file di origine e righe quando si usano file PDB portatili, nel caso non siano opportune, aggiungendo il codice seguente alla sezione `<runtime>` del file `app.config`:</span><span class="sxs-lookup"><span data-stu-id="8643f-106">For applications that target the .NET Framework 4.7.2, you can opt out of the source file and line information when using portable PDBs if it is not desirable by adding the following to the `<runtime>` section of your `app.config` file:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.Diagnostics.IgnorePortablePDBsInStackTraces=true" />
</runtime>
```

<span data-ttu-id="8643f-107">Per le applicazioni destinate alle versioni precedenti di .NET Framework, ma eseguite in .NET Framework 4.7.2 o versioni successive, è possibile acconsentire esplicitamente alle informazioni su file di origine e righe quando si usano file PDB portatili aggiungendo il codice seguente alla sezione `<runtime>` del file `app.config`:</span><span class="sxs-lookup"><span data-stu-id="8643f-107">For applications that target earlier versions of the .NET Framework but run on the .NET Framework 4.7.2 or later, you can opt in to the source file and line information when using portable PDBs by adding the following to the `<runtime>` section of your `app.config` file:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.Diagnostics.IgnorePortablePDBsInStackTraces=false" />
</runtime>
```

| <span data-ttu-id="8643f-108">Nome</span><span class="sxs-lookup"><span data-stu-id="8643f-108">Name</span></span>    | <span data-ttu-id="8643f-109">Valore</span><span class="sxs-lookup"><span data-stu-id="8643f-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="8643f-110">Scope</span><span class="sxs-lookup"><span data-stu-id="8643f-110">Scope</span></span>   | <span data-ttu-id="8643f-111">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="8643f-111">Edge</span></span>        |
| <span data-ttu-id="8643f-112">Version</span><span class="sxs-lookup"><span data-stu-id="8643f-112">Version</span></span> | <span data-ttu-id="8643f-113">4.7.2</span><span class="sxs-lookup"><span data-stu-id="8643f-113">4.7.2</span></span>       |
| <span data-ttu-id="8643f-114">Type</span><span class="sxs-lookup"><span data-stu-id="8643f-114">Type</span></span>    | <span data-ttu-id="8643f-115">Ridestinazione</span><span class="sxs-lookup"><span data-stu-id="8643f-115">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="8643f-116">API interessate</span><span class="sxs-lookup"><span data-stu-id="8643f-116">Affected APIs</span></span>

- <xref:System.Diagnostics.StackTrace.%23ctor(System.Boolean)>
- <xref:System.Diagnostics.StackTrace.%23ctor(System.Exception,System.Boolean)>
- <xref:System.Diagnostics.StackTrace.%23ctor(System.Exception,System.Int32,System.Boolean)>
