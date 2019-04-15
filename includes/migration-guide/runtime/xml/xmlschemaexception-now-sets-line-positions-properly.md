---
ms.openlocfilehash: a5b3e325c13d2f56532ebc6ebb5c259d565a4952
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235724"
---
### <a name="xmlschemaexception-now-sets-line-positions-properly"></a><span data-ttu-id="beb25-101">XmlSchemaException ora imposta correttamente le posizioni delle righe</span><span class="sxs-lookup"><span data-stu-id="beb25-101">XmlSchemaException now sets line positions properly</span></span>

|   |   |
|---|---|
|<span data-ttu-id="beb25-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="beb25-102">Details</span></span>|<span data-ttu-id="beb25-103">Se il valore <xref:System.Xml.Linq.LoadOptions.SetLineInfo> viene passato al metodo Load e si verifica un errore di convalida, le proprietà <xref:System.Xml.Schema.XmlSchemaException.LineNumber> e <xref:System.Xml.Schema.XmlSchemaException.LinePosition> contengono ora informazioni sulla riga.</span><span class="sxs-lookup"><span data-stu-id="beb25-103">If the <xref:System.Xml.Linq.LoadOptions.SetLineInfo> value is passed to the Load method and a validation error occurs, the <xref:System.Xml.Schema.XmlSchemaException.LineNumber> and <xref:System.Xml.Schema.XmlSchemaException.LinePosition> properties now contain line information.</span></span>|
|<span data-ttu-id="beb25-104">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="beb25-104">Suggestion</span></span>|<span data-ttu-id="beb25-105">È necessario aggiornare il codice di gestione delle eccezioni che presuppone che le proprietà <xref:System.Xml.Schema.XmlSchemaException.LineNumber> e <xref:System.Xml.Schema.XmlSchemaException.LinePosition> non vengano impostate, perché queste proprietà vengono ora impostate correttamente quando il metodo SetLineInfo viene usato durante il caricamento di XML.</span><span class="sxs-lookup"><span data-stu-id="beb25-105">Exception-handling code that assumes <xref:System.Xml.Schema.XmlSchemaException.LineNumber> and <xref:System.Xml.Schema.XmlSchemaException.LinePosition> will not be set should be updated since these properties will now be set properly when SetLineInfo is used while loading XML.</span></span>|
|<span data-ttu-id="beb25-106">Ambito</span><span class="sxs-lookup"><span data-stu-id="beb25-106">Scope</span></span>|<span data-ttu-id="beb25-107">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="beb25-107">Edge</span></span>|
|<span data-ttu-id="beb25-108">Versione</span><span class="sxs-lookup"><span data-stu-id="beb25-108">Version</span></span>|<span data-ttu-id="beb25-109">4.5</span><span class="sxs-lookup"><span data-stu-id="beb25-109">4.5</span></span>|
|<span data-ttu-id="beb25-110">Tipo</span><span class="sxs-lookup"><span data-stu-id="beb25-110">Type</span></span>|<span data-ttu-id="beb25-111">Runtime</span><span class="sxs-lookup"><span data-stu-id="beb25-111">Runtime</span></span>|
|<span data-ttu-id="beb25-112">API interessate</span><span class="sxs-lookup"><span data-stu-id="beb25-112">Affected APIs</span></span>|<ul><li><xref:System.Xml.Linq.LoadOptions.SetLineInfo?displayProperty=nameWithType></li></ul>|
