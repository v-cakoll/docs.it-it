---
ms.openlocfilehash: 38c35f3f6f2262d06409690d2326d9b982e1ec86
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235774"
---
### <a name="managed-browser-hosting-controls-from-the-net-framework-11-and-20-are-blocked"></a><span data-ttu-id="e56ba-101">I controlli di hosting di browser gestiti da .NET Framework 1.1 e 2.0 sono bloccati</span><span class="sxs-lookup"><span data-stu-id="e56ba-101">Managed browser hosting controls from the .NET Framework 1.1 and 2.0 are blocked</span></span>

|   |   |
|---|---|
|<span data-ttu-id="e56ba-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="e56ba-102">Details</span></span>|<span data-ttu-id="e56ba-103">L'hosting di questi controlli è bloccato in Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="e56ba-103">Hosting these controls is blocked in Internet Explorer.</span></span>|
|<span data-ttu-id="e56ba-104">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="e56ba-104">Suggestion</span></span>|<span data-ttu-id="e56ba-105">Internet Explorer non riuscirà ad avviare un'applicazione che usa controlli di hosting di browser gestiti.</span><span class="sxs-lookup"><span data-stu-id="e56ba-105">Internet Explorer will fail to launch an application that uses managed browser hosting controls.</span></span> <span data-ttu-id="e56ba-106">È possibile ripristinare il comportamento precedente impostando il valore EnableIEHosting della sottochiave del Registro di sistema <code>HKLM/SOFTWARE/MICROSOFT/.NETFramework</code> su <code>1</code> per i sistemi x86 e i processi a 32 bit nei sistemi x64 e impostando il valore <code>EnableIEHosting</code> della sottochiave del Registro di sistema <code>HKLM/SOFTWARE/Wow6432Node/Microsoft/.NETFramework</code> su <code>1</code> per i processi a 64 bit nei sistemi x64.</span><span class="sxs-lookup"><span data-stu-id="e56ba-106">The previous behavior can be restored by setting the EnableIEHosting value of the registry subkey <code>HKLM/SOFTWARE/MICROSOFT/.NETFramework</code> to <code>1</code> for x86 systems and for 32-bit processes on x64 systems, and by setting the <code>EnableIEHosting</code> value of the registry subkey <code>HKLM/SOFTWARE/Wow6432Node/Microsoft/.NETFramework</code> to <code>1</code> for 64-bit processes on x64 systems.</span></span>|
|<span data-ttu-id="e56ba-107">Ambito</span><span class="sxs-lookup"><span data-stu-id="e56ba-107">Scope</span></span>|<span data-ttu-id="e56ba-108">Secondario</span><span class="sxs-lookup"><span data-stu-id="e56ba-108">Minor</span></span>|
|<span data-ttu-id="e56ba-109">Versione</span><span class="sxs-lookup"><span data-stu-id="e56ba-109">Version</span></span>|<span data-ttu-id="e56ba-110">4.5</span><span class="sxs-lookup"><span data-stu-id="e56ba-110">4.5</span></span>|
|<span data-ttu-id="e56ba-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="e56ba-111">Type</span></span>|<span data-ttu-id="e56ba-112">Runtime</span><span class="sxs-lookup"><span data-stu-id="e56ba-112">Runtime</span></span>|
