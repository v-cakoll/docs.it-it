---
ms.openlocfilehash: 83d3f24680531d1e447f047151a28c98ce0da04b
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620401"
---
### <a name="managed-browser-hosting-controls-from-the-net-framework-11-and-20-are-blocked"></a><span data-ttu-id="4308e-101">I controlli di hosting di browser gestiti da .NET Framework 1.1 e 2.0 sono bloccati</span><span class="sxs-lookup"><span data-stu-id="4308e-101">Managed browser hosting controls from the .NET Framework 1.1 and 2.0 are blocked</span></span>

#### <a name="details"></a><span data-ttu-id="4308e-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="4308e-102">Details</span></span>

<span data-ttu-id="4308e-103">L'hosting di questi controlli è bloccato in Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="4308e-103">Hosting these controls is blocked in Internet Explorer.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="4308e-104">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="4308e-104">Suggestion</span></span>

<span data-ttu-id="4308e-105">Internet Explorer non riuscirà ad avviare un'applicazione che usa controlli di hosting di browser gestiti.</span><span class="sxs-lookup"><span data-stu-id="4308e-105">Internet Explorer will fail to launch an application that uses managed browser hosting controls.</span></span> <span data-ttu-id="4308e-106">È possibile ripristinare il comportamento precedente impostando il valore EnableIEHosting della sottochiave del Registro di sistema <code>HKLM/SOFTWARE/MICROSOFT/.NETFramework</code> su <code>1</code> per i sistemi x86 e i processi a 32 bit nei sistemi x64 e impostando il valore <code>EnableIEHosting</code> della sottochiave del Registro di sistema <code>HKLM/SOFTWARE/Wow6432Node/Microsoft/.NETFramework</code> su <code>1</code> per i processi a 64 bit nei sistemi x64.</span><span class="sxs-lookup"><span data-stu-id="4308e-106">The previous behavior can be restored by setting the EnableIEHosting value of the registry subkey <code>HKLM/SOFTWARE/MICROSOFT/.NETFramework</code> to <code>1</code> for x86 systems and for 32-bit processes on x64 systems, and by setting the <code>EnableIEHosting</code> value of the registry subkey <code>HKLM/SOFTWARE/Wow6432Node/Microsoft/.NETFramework</code> to <code>1</code> for 64-bit processes on x64 systems.</span></span>

| <span data-ttu-id="4308e-107">Nome</span><span class="sxs-lookup"><span data-stu-id="4308e-107">Name</span></span>    | <span data-ttu-id="4308e-108">Valore</span><span class="sxs-lookup"><span data-stu-id="4308e-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="4308e-109">Scope</span><span class="sxs-lookup"><span data-stu-id="4308e-109">Scope</span></span>   |<span data-ttu-id="4308e-110">Minorenne</span><span class="sxs-lookup"><span data-stu-id="4308e-110">Minor</span></span>|
|<span data-ttu-id="4308e-111">Version</span><span class="sxs-lookup"><span data-stu-id="4308e-111">Version</span></span>|<span data-ttu-id="4308e-112">4.5</span><span class="sxs-lookup"><span data-stu-id="4308e-112">4.5</span></span>|
|<span data-ttu-id="4308e-113">Type</span><span class="sxs-lookup"><span data-stu-id="4308e-113">Type</span></span>|<span data-ttu-id="4308e-114">Runtime</span><span class="sxs-lookup"><span data-stu-id="4308e-114">Runtime</span></span>|
