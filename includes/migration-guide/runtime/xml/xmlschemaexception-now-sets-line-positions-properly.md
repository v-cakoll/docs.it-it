---
ms.openlocfilehash: c3e39e49747be709977d7fba3c39b59f5575c40d
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620506"
---
### <a name="xmlschemaexception-now-sets-line-positions-properly"></a><span data-ttu-id="e3800-101">XmlSchemaException ora imposta correttamente le posizioni delle righe</span><span class="sxs-lookup"><span data-stu-id="e3800-101">XmlSchemaException now sets line positions properly</span></span>

#### <a name="details"></a><span data-ttu-id="e3800-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="e3800-102">Details</span></span>

<span data-ttu-id="e3800-103">Se il valore <xref:System.Xml.Linq.LoadOptions.SetLineInfo> viene passato al metodo Load e si verifica un errore di convalida, le proprietà <xref:System.Xml.Schema.XmlSchemaException.LineNumber> e <xref:System.Xml.Schema.XmlSchemaException.LinePosition> contengono ora informazioni sulla riga.</span><span class="sxs-lookup"><span data-stu-id="e3800-103">If the <xref:System.Xml.Linq.LoadOptions.SetLineInfo> value is passed to the Load method and a validation error occurs, the <xref:System.Xml.Schema.XmlSchemaException.LineNumber> and <xref:System.Xml.Schema.XmlSchemaException.LinePosition> properties now contain line information.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="e3800-104">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="e3800-104">Suggestion</span></span>

<span data-ttu-id="e3800-105">È necessario aggiornare il codice di gestione delle eccezioni che presuppone che le proprietà <xref:System.Xml.Schema.XmlSchemaException.LineNumber> e <xref:System.Xml.Schema.XmlSchemaException.LinePosition> non vengano impostate, perché queste proprietà vengono ora impostate correttamente quando il metodo SetLineInfo viene usato durante il caricamento di XML.</span><span class="sxs-lookup"><span data-stu-id="e3800-105">Exception-handling code that assumes <xref:System.Xml.Schema.XmlSchemaException.LineNumber> and <xref:System.Xml.Schema.XmlSchemaException.LinePosition> will not be set should be updated since these properties will now be set properly when SetLineInfo is used while loading XML.</span></span>

| <span data-ttu-id="e3800-106">Nome</span><span class="sxs-lookup"><span data-stu-id="e3800-106">Name</span></span>    | <span data-ttu-id="e3800-107">Valore</span><span class="sxs-lookup"><span data-stu-id="e3800-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="e3800-108">Scope</span><span class="sxs-lookup"><span data-stu-id="e3800-108">Scope</span></span>   |<span data-ttu-id="e3800-109">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="e3800-109">Edge</span></span>|
|<span data-ttu-id="e3800-110">Version</span><span class="sxs-lookup"><span data-stu-id="e3800-110">Version</span></span>|<span data-ttu-id="e3800-111">4.5</span><span class="sxs-lookup"><span data-stu-id="e3800-111">4.5</span></span>|
|<span data-ttu-id="e3800-112">Type</span><span class="sxs-lookup"><span data-stu-id="e3800-112">Type</span></span>|<span data-ttu-id="e3800-113">Runtime</span><span class="sxs-lookup"><span data-stu-id="e3800-113">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="e3800-114">API interessate</span><span class="sxs-lookup"><span data-stu-id="e3800-114">Affected APIs</span></span>

-<xref:System.Xml.Linq.LoadOptions.SetLineInfo?displayProperty=nameWithType></li></ul>|
