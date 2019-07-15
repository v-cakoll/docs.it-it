---
ms.openlocfilehash: 9bf6972812bdf4a385b99fe34d2cd3cd8a91c8cf
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/11/2019
ms.locfileid: "67804547"
---
### <a name="clickonce-supports-sha-256-on-40-targeted-apps"></a><span data-ttu-id="184cc-101">ClickOnce supporta SHA-256 per le app destinate alla versione 4.0</span><span class="sxs-lookup"><span data-stu-id="184cc-101">ClickOnce supports SHA-256 on 4.0-targeted apps</span></span>

|   |   |
|---|---|
|<span data-ttu-id="184cc-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="184cc-102">Details</span></span>|<span data-ttu-id="184cc-103">In precedenza, un'app ClickOnce con certificato firmato con SHA-256 avrebbe richiesto la presenza di .NET Framework 4.5 o versioni successive, anche se l'app era destinata alla versione 4.0.</span><span class="sxs-lookup"><span data-stu-id="184cc-103">Previously, a ClickOnce app with a certificate signed with SHA-256 would require .NET Framework 4.5 or later to be present, even if the app targeted 4.0.</span></span> <span data-ttu-id="184cc-104">È ora possibile eseguire le app ClickOnce destinate a .NET Framework 4.0 in .NET Framework 4.0, anche se firmate con SHA-256.</span><span class="sxs-lookup"><span data-stu-id="184cc-104">Now, .NET Framework 4.0-targeted ClickOnce apps can run on .NET Framework 4.0, even if signed with SHA-256.</span></span>|
|<span data-ttu-id="184cc-105">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="184cc-105">Suggestion</span></span>|<span data-ttu-id="184cc-106">Questa modifica rimuove tale dipendenza e consente di usare i certificati SHA-256 per firmare le app ClickOnce destinate a .NET Framework 4 e versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="184cc-106">This change removes that dependency and allows SHA-256 certificates to be used to sign ClickOnce apps that target .NET Framework 4 and earlier versions.</span></span>|
|<span data-ttu-id="184cc-107">Ambito</span><span class="sxs-lookup"><span data-stu-id="184cc-107">Scope</span></span>|<span data-ttu-id="184cc-108">Secondario</span><span class="sxs-lookup"><span data-stu-id="184cc-108">Minor</span></span>|
|<span data-ttu-id="184cc-109">Versione</span><span class="sxs-lookup"><span data-stu-id="184cc-109">Version</span></span>|<span data-ttu-id="184cc-110">4.6</span><span class="sxs-lookup"><span data-stu-id="184cc-110">4.6</span></span>|
|<span data-ttu-id="184cc-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="184cc-111">Type</span></span>|<span data-ttu-id="184cc-112">Ridestinazione</span><span class="sxs-lookup"><span data-stu-id="184cc-112">Retargeting</span></span>|

