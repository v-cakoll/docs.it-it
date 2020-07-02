---
ms.openlocfilehash: f78d15338aa49de5b729aca12964924a0df00ec6
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614831"
---
### <a name="improved-accessibility-for-some-net-sdk-tools"></a><span data-ttu-id="4172a-101">Accessibilità migliorata per alcuni strumenti di .NET SDK</span><span class="sxs-lookup"><span data-stu-id="4172a-101">Improved accessibility for some .NET SDK tools</span></span>

#### <a name="details"></a><span data-ttu-id="4172a-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="4172a-102">Details</span></span>

<span data-ttu-id="4172a-103">In .NET Framework SDK 4.7.1 gli strumenti SvcConfigEditor.exe e SvcTraceViewer.exe sono stati migliorati risolvendo vari problemi relativi all'accessibilità.</span><span class="sxs-lookup"><span data-stu-id="4172a-103">In the .NET Framework SDK 4.7.1, the SvcConfigEditor.exe and SvcTraceViewer.exe tools have been improved by fixing varied accessibility issues.</span></span> <span data-ttu-id="4172a-104">Molti erano problemi di lieve entità, come ad esempio un nome non definito o alcuni pattern dell'automazione interfaccia utente non implementati correttamente.</span><span class="sxs-lookup"><span data-stu-id="4172a-104">Most of these were small issues like a name not being defined or certain UI automation patterns not being implemented correctly.</span></span> <span data-ttu-id="4172a-105">Sebbene molti utenti non siano a conoscenza di questi valori non corretti, i clienti che usano tecnologie per l'accesso facilitato, ad esempio gli utilità per la lettura dello schermo, troveranno questi strumenti SDK più accessibili</span><span class="sxs-lookup"><span data-stu-id="4172a-105">While many users wouldn't be aware of these incorrect values, customers who use assistive technologies like screen readers will find these SDK tools more accessible.</span></span> <span data-ttu-id="4172a-106">Queste correzioni modificano sicuramente alcuni comportamenti precedenti, ad esempio l'ordine dello stato attivo della tastiera. Per ottenere tutte le correzioni relative all'accessibilità in questi strumenti, è possibile applicare quanto segue al file app.config:</span><span class="sxs-lookup"><span data-stu-id="4172a-106">Certainly, these fixes change some previous behaviors, like keyboard focus order.In order to get all the accessibility fixes in these tools, you can the following to your app.config file:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false"/>
</runtime>
```

| <span data-ttu-id="4172a-107">Nome</span><span class="sxs-lookup"><span data-stu-id="4172a-107">Name</span></span>    | <span data-ttu-id="4172a-108">Valore</span><span class="sxs-lookup"><span data-stu-id="4172a-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="4172a-109">Scope</span><span class="sxs-lookup"><span data-stu-id="4172a-109">Scope</span></span>   | <span data-ttu-id="4172a-110">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="4172a-110">Edge</span></span>        |
| <span data-ttu-id="4172a-111">Version</span><span class="sxs-lookup"><span data-stu-id="4172a-111">Version</span></span> | <span data-ttu-id="4172a-112">4.7.1</span><span class="sxs-lookup"><span data-stu-id="4172a-112">4.7.1</span></span>       |
| <span data-ttu-id="4172a-113">Type</span><span class="sxs-lookup"><span data-stu-id="4172a-113">Type</span></span>    | <span data-ttu-id="4172a-114">Ridestinazione</span><span class="sxs-lookup"><span data-stu-id="4172a-114">Retargeting</span></span> |
