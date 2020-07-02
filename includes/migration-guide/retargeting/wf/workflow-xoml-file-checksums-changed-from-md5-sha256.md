---
ms.openlocfilehash: 2aa424ff5e3308b730c22cb865993d4100f193cc
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616264"
---
### <a name="workflow-xoml-file-checksums-changed-from-md5-to-sha256"></a><span data-ttu-id="0d0b4-101">Checksum del file XOML del flusso di lavoro modificati da MD5 a SHA256</span><span class="sxs-lookup"><span data-stu-id="0d0b4-101">Workflow XOML file checksums changed from MD5 to SHA256</span></span>

#### <a name="details"></a><span data-ttu-id="0d0b4-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="0d0b4-102">Details</span></span>

<span data-ttu-id="0d0b4-103">Per supportare il debug dei flussi di lavoro basati su XOML con Visual Studio, quando vengono compilati progetti di flusso di lavoro contenenti file XOML, viene inserito nel codice generato un checksum del contenuto del file XOML come valore <xref:System.Workflow.ComponentModel.Compiler.WorkflowMarkupSourceAttribute.MD5Digest?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="0d0b4-103">To support debugging XOML-based workflows with Visual Studio, when workflow projects containing XOML files build, a checksum of the contents of the XOML file is included in the code generated as a <xref:System.Workflow.ComponentModel.Compiler.WorkflowMarkupSourceAttribute.MD5Digest?displayProperty=nameWithType> value.</span></span> <span data-ttu-id="0d0b4-104">In .NET Framework 4.7.2 e versioni precedenti l'hash del checksum usava l'algoritmo MD5 che causava problemi nei sistemi abilitati per FIPS.</span><span class="sxs-lookup"><span data-stu-id="0d0b4-104">In the .NET Framework 4.7.2 and earlier versions, this checksum hashing used the MD5 algorithm, which caused issues on FIPS-enabled systems.</span></span> <span data-ttu-id="0d0b4-105">A partire da .NET Framework 4.8, viene usato l'algoritmo SHA256.</span><span class="sxs-lookup"><span data-stu-id="0d0b4-105">Starting with the .NET Framework 4.8, the algorithm used is SHA256.</span></span> <span data-ttu-id="0d0b4-106">Per ragioni di compatibilità con WorkflowMarkupSourceAttribute.MD5Digest, vengono usati solo i primi 16 byte del checksum generato. Ciò potrebbe causare problemi durante il debug.</span><span class="sxs-lookup"><span data-stu-id="0d0b4-106">To be compatibile with the WorkflowMarkupSourceAttribute.MD5Digest, only the first 16 bytes of the generated checksum are used.This may cause problems during debugging.</span></span> <span data-ttu-id="0d0b4-107">Potrebbe essere necessario ricompilare il progetto.</span><span class="sxs-lookup"><span data-stu-id="0d0b4-107">You may need to re-build your project.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="0d0b4-108">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="0d0b4-108">Suggestion</span></span>

<span data-ttu-id="0d0b4-109">Se la ricompilazione del progetto non risolve il problema, provare a impostare l'opzione `AppContext`&quot;Switch.System.Workflow.ComponentModel.UseLegacyHashForXomlFileChecksum&quot; su true. Nel codice:</span><span class="sxs-lookup"><span data-stu-id="0d0b4-109">If re-building your project does not solve the problem, try setting the `AppContext` switch &quot;Switch.System.Workflow.ComponentModel.UseLegacyHashForXomlFileChecksum&quot; to true.In code:</span></span>

<pre><code class="lang-csharp">System.AppContext.SetSwitch(&quot;Switch.System.Workflow.ComponentModel.UseLegacyHashForXomlFileChecksum&quot;, true);&#13;&#10;</code></pre>

<span data-ttu-id="0d0b4-110">Oppure in un file di configurazione (che deve trovarsi in MSBuild.exe.config per il file MSBuild.exe in uso):</span><span class="sxs-lookup"><span data-stu-id="0d0b4-110">Or in a configuration file (this needs to be in MSBuild.exe.config for the MSBuild.exe that you are using):</span></span>

<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Workflow.ComponentModel.UseLegacyHashForXomlFileChecksum=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="0d0b4-111">Nome</span><span class="sxs-lookup"><span data-stu-id="0d0b4-111">Name</span></span>    | <span data-ttu-id="0d0b4-112">Valore</span><span class="sxs-lookup"><span data-stu-id="0d0b4-112">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="0d0b4-113">Scope</span><span class="sxs-lookup"><span data-stu-id="0d0b4-113">Scope</span></span>   | <span data-ttu-id="0d0b4-114">Minorenne</span><span class="sxs-lookup"><span data-stu-id="0d0b4-114">Minor</span></span>       |
| <span data-ttu-id="0d0b4-115">Version</span><span class="sxs-lookup"><span data-stu-id="0d0b4-115">Version</span></span> | <span data-ttu-id="0d0b4-116">4.8</span><span class="sxs-lookup"><span data-stu-id="0d0b4-116">4.8</span></span>         |
| <span data-ttu-id="0d0b4-117">Type</span><span class="sxs-lookup"><span data-stu-id="0d0b4-117">Type</span></span>    | <span data-ttu-id="0d0b4-118">Ridestinazione</span><span class="sxs-lookup"><span data-stu-id="0d0b4-118">Retargeting</span></span> |
