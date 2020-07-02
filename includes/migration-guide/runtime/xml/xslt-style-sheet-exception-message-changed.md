---
ms.openlocfilehash: 5c27e8acdf30533036546ba4cca9e06877bde362
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620521"
---
### <a name="xslt-style-sheet-exception-message-changed"></a><span data-ttu-id="6a33a-101">Modificato il messaggio di eccezione del foglio di stile XSLT</span><span class="sxs-lookup"><span data-stu-id="6a33a-101">XSLT style sheet exception message changed</span></span>

#### <a name="details"></a><span data-ttu-id="6a33a-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="6a33a-102">Details</span></span>

<span data-ttu-id="6a33a-103">Nel .NET Framework 4,5, il testo del messaggio di errore quando un file XSLT è troppo complesso è &quot; il foglio di stile è troppo complesso. &quot; Nelle versioni precedenti il messaggio di errore era &quot; errore di compilazione XSLT. &quot; Il codice dell'applicazione che dipende dal testo del messaggio di errore non funzionerà più.</span><span class="sxs-lookup"><span data-stu-id="6a33a-103">In the .NET Framework 4.5, the text of the error message when an XSLT file is too complex is &quot;The style sheet is too complex.&quot; In previous versions, the error message was &quot;XSLT compile error.&quot; Application code that depends on the text of the error message will no longer work.</span></span> <span data-ttu-id="6a33a-104">Tuttavia, i tipi di eccezione rimangono gli stessi e pertanto questa modifica non dovrebbe avere un impatto reale.</span><span class="sxs-lookup"><span data-stu-id="6a33a-104">However, the exception types remain the same, so this change should have no real impact.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="6a33a-105">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="6a33a-105">Suggestion</span></span>

<span data-ttu-id="6a33a-106">Aggiornare il codice dell'app che dipende dal messaggio di eccezione da questa condizione di errore in modo che preveda il nuovo messaggio oppure, ancora meglio, aggiornare il codice in modo che dipenda solo dal tipo di eccezione (<xref:System.Xml.Xsl.XsltException?displayProperty=fullName>), che non è stato modificato.</span><span class="sxs-lookup"><span data-stu-id="6a33a-106">Update any app code depending on the exception message from this error condition to expect the new message, or (even better) update the code to depend only on the exception type (<xref:System.Xml.Xsl.XsltException?displayProperty=fullName>), which has not changed.</span></span>

| <span data-ttu-id="6a33a-107">Nome</span><span class="sxs-lookup"><span data-stu-id="6a33a-107">Name</span></span>    | <span data-ttu-id="6a33a-108">Valore</span><span class="sxs-lookup"><span data-stu-id="6a33a-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="6a33a-109">Scope</span><span class="sxs-lookup"><span data-stu-id="6a33a-109">Scope</span></span>   |<span data-ttu-id="6a33a-110">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="6a33a-110">Edge</span></span>|
|<span data-ttu-id="6a33a-111">Version</span><span class="sxs-lookup"><span data-stu-id="6a33a-111">Version</span></span>|<span data-ttu-id="6a33a-112">4.5</span><span class="sxs-lookup"><span data-stu-id="6a33a-112">4.5</span></span>|
|<span data-ttu-id="6a33a-113">Type</span><span class="sxs-lookup"><span data-stu-id="6a33a-113">Type</span></span>|<span data-ttu-id="6a33a-114">Runtime</span><span class="sxs-lookup"><span data-stu-id="6a33a-114">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="6a33a-115">API interessate</span><span class="sxs-lookup"><span data-stu-id="6a33a-115">Affected APIs</span></span>

-<xref:System.Xml.Xsl.XslCompiledTransform.Load(System.String)?displayProperty=nameWithType></li><li><xref:System.Xml.Xsl.XslCompiledTransform.Load(System.Type)?displayProperty=nameWithType></li><li><xref:System.Xml.Xsl.XslCompiledTransform.Load(System.Xml.XmlReader)?displayProperty=nameWithType></li><li><xref:System.Xml.Xsl.XslCompiledTransform.Load(System.Xml.XPath.IXPathNavigable)?displayProperty=nameWithType></li><li><xref:System.Xml.Xsl.XslCompiledTransform.Load(System.Reflection.MethodInfo,System.Byte[],System.Type[])?displayProperty=nameWithType></li><li><xref:System.Xml.Xsl.XslCompiledTransform.Load(System.String,System.Xml.Xsl.XsltSettings,System.Xml.XmlResolver)?displayProperty=nameWithType></li><li><xref:System.Xml.Xsl.XslCompiledTransform.Load(System.Xml.XmlReader,System.Xml.Xsl.XsltSettings,System.Xml.XmlResolver)?displayProperty=nameWithType></li><li><xref:System.Xml.Xsl.XslCompiledTransform.Load(System.Xml.XPath.IXPathNavigable,System.Xml.Xsl.XsltSettings,System.Xml.XmlResolver)?displayProperty=nameWithType></li></ul>|
