---
ms.openlocfilehash: 26a001ec2009a1a66dd9038b9bd3a42d7bcefb73
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620254"
---
### <a name="missing-target-framework-moniker-results-in-40-behavior"></a><span data-ttu-id="8cfb1-101">Comportamento 4.0 a causa della mancanza del moniker del framework di destinazione</span><span class="sxs-lookup"><span data-stu-id="8cfb1-101">Missing Target Framework Moniker results in 4.0 behavior</span></span>

#### <a name="details"></a><span data-ttu-id="8cfb1-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="8cfb1-102">Details</span></span>

<span data-ttu-id="8cfb1-103">Le applicazioni senza un <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=fullName> applicato a livello di assembly verranno eseguite automaticamente con la semantica (non standard) di .NET Framework 4.0.</span><span class="sxs-lookup"><span data-stu-id="8cfb1-103">Applications without a <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=fullName> applied at the assembly level will automatically run using the semantics (quirks) of the .NET Framework 4.0.</span></span> <span data-ttu-id="8cfb1-104">Per garantire un livello di qualità elevato, è consigliabile applicare a tutti i file binari in modo esplicito un attributo <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=fullName> che indica la versione di .NET Framework con cui sono stati compilati.</span><span class="sxs-lookup"><span data-stu-id="8cfb1-104">To ensure high quality, it is recommended that all binaries be explicitly attributed with a <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=fullName> indicating the version of the .NET Framework they were built with.</span></span> <span data-ttu-id="8cfb1-105">Si noti che l'uso di un moniker del framework di destinazione in un file di progetto causerà l'applicazione automatica di un <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=fullName> da MSBuild.</span><span class="sxs-lookup"><span data-stu-id="8cfb1-105">Note that using a target framework moniker in a project file will cause MSBuild to automatically apply a <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=fullName>.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="8cfb1-106">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="8cfb1-106">Suggestion</span></span>

<span data-ttu-id="8cfb1-107">È consigliabile specificare un <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=fullName> aggiungendo direttamente l'attributo all'assembly oppure specificando un framework di destinazione nel [file di progetto o tramite l'interfaccia utente grafica delle proprietà del progetto di Visual Studio](https://devblogs.microsoft.com/visualstudio/visual-studio-managed-multi-targeting-part-1-concepts-target-framework-moniker-target-framework/).</span><span class="sxs-lookup"><span data-stu-id="8cfb1-107">A <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=fullName> should be supplied, either through adding the attribute directly to the assembly or by specifying a target framework in the [project file or through Visual Studio's project properties GUI](https://devblogs.microsoft.com/visualstudio/visual-studio-managed-multi-targeting-part-1-concepts-target-framework-moniker-target-framework/).</span></span>

| <span data-ttu-id="8cfb1-108">Nome</span><span class="sxs-lookup"><span data-stu-id="8cfb1-108">Name</span></span>    | <span data-ttu-id="8cfb1-109">Valore</span><span class="sxs-lookup"><span data-stu-id="8cfb1-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="8cfb1-110">Scope</span><span class="sxs-lookup"><span data-stu-id="8cfb1-110">Scope</span></span>   |<span data-ttu-id="8cfb1-111">Principale</span><span class="sxs-lookup"><span data-stu-id="8cfb1-111">Major</span></span>|
|<span data-ttu-id="8cfb1-112">Version</span><span class="sxs-lookup"><span data-stu-id="8cfb1-112">Version</span></span>|<span data-ttu-id="8cfb1-113">4.5</span><span class="sxs-lookup"><span data-stu-id="8cfb1-113">4.5</span></span>|
|<span data-ttu-id="8cfb1-114">Type</span><span class="sxs-lookup"><span data-stu-id="8cfb1-114">Type</span></span>|<span data-ttu-id="8cfb1-115">Runtime</span><span class="sxs-lookup"><span data-stu-id="8cfb1-115">Runtime</span></span>|
