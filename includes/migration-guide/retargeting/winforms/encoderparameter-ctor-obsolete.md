---
ms.openlocfilehash: b4e062fe3a00b76da144e706841f87b2a95888e5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59234711"
---
### <a name="encoderparameter-ctor-is-obsolete"></a><span data-ttu-id="d3e0d-101">Il costruttore EncoderParameter è obsoleto</span><span class="sxs-lookup"><span data-stu-id="d3e0d-101">EncoderParameter ctor is obsolete</span></span>

|   |   |
|---|---|
|<span data-ttu-id="d3e0d-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="d3e0d-102">Details</span></span>|<span data-ttu-id="d3e0d-103">Il costruttore <xref:System.Drawing.Imaging.EncoderParameter.%23ctor(System.Drawing.Imaging.Encoder,System.Int32,System.Int32,System.Int32,System.Int32)> è ora obsoleto e l'eventuale uso causerà avvisi di compilazione.</span><span class="sxs-lookup"><span data-stu-id="d3e0d-103">The <xref:System.Drawing.Imaging.EncoderParameter.%23ctor(System.Drawing.Imaging.Encoder,System.Int32,System.Int32,System.Int32,System.Int32)> constructor is obsolete now and will introduce build warnings if used.</span></span>|
|<span data-ttu-id="d3e0d-104">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="d3e0d-104">Suggestion</span></span>|<span data-ttu-id="d3e0d-105">Anche se il costruttore <xref:System.Drawing.Imaging.EncoderParameter.%23ctor(System.Drawing.Imaging.Encoder,System.Int32,System.Int32,System.Int32,System.Int32)> continuerà a funzionare, è necessario usare il costruttore seguente per evitare l'avviso di compilazione obsoleto durante la ricompilazione del codice con gli strumenti di .NET Framework 4.5: <xref:System.Drawing.Imaging.EncoderParameter.%23ctor(System.Drawing.Imaging.Encoder,System.Int32,System.Drawing.Imaging.EncoderParameterValueType,System.IntPtr)>.</span><span class="sxs-lookup"><span data-stu-id="d3e0d-105">Although the <xref:System.Drawing.Imaging.EncoderParameter.%23ctor(System.Drawing.Imaging.Encoder,System.Int32,System.Int32,System.Int32,System.Int32)>constructor will continue to work, the following constructor should be used instead to avoid the obsolete build warning when re-compiling code with .NET Framework  4.5 tools: <xref:System.Drawing.Imaging.EncoderParameter.%23ctor(System.Drawing.Imaging.Encoder,System.Int32,System.Drawing.Imaging.EncoderParameterValueType,System.IntPtr)>.</span></span>|
|<span data-ttu-id="d3e0d-106">Ambito</span><span class="sxs-lookup"><span data-stu-id="d3e0d-106">Scope</span></span>|<span data-ttu-id="d3e0d-107">Secondario</span><span class="sxs-lookup"><span data-stu-id="d3e0d-107">Minor</span></span>|
|<span data-ttu-id="d3e0d-108">Versione</span><span class="sxs-lookup"><span data-stu-id="d3e0d-108">Version</span></span>|<span data-ttu-id="d3e0d-109">4.5</span><span class="sxs-lookup"><span data-stu-id="d3e0d-109">4.5</span></span>|
|<span data-ttu-id="d3e0d-110">Tipo</span><span class="sxs-lookup"><span data-stu-id="d3e0d-110">Type</span></span>|<span data-ttu-id="d3e0d-111">Ridestinazione</span><span class="sxs-lookup"><span data-stu-id="d3e0d-111">Retargeting</span></span>|
|<span data-ttu-id="d3e0d-112">API interessate</span><span class="sxs-lookup"><span data-stu-id="d3e0d-112">Affected APIs</span></span>|<ul><li><xref:System.Drawing.Imaging.EncoderParameter.%23ctor(System.Drawing.Imaging.Encoder,System.Int32,System.Int32,System.Int32,System.Int32)?displayProperty=nameWithType></li></ul>|
