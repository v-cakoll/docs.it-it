---
title: Esempi di espressioni regolari
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- regular expressions [.NET Framework], examples
- regular expressions [.NET Framework]
- strings [.NET Framework], regular expressions
ms.assetid: e9fd53f2-ed56-4b09-b2ea-e9bc9d65e6d6
ms.openlocfilehash: 788fa2a6793e14189def4c30a0baf0d4a5cf6b0a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "73128086"
---
# <a name="regular-expression-examples"></a><span data-ttu-id="0494f-102">Esempi di espressioni regolari</span><span class="sxs-lookup"><span data-stu-id="0494f-102">Regular Expression Examples</span></span>
<span data-ttu-id="0494f-103">Questa sezione contiene esempi di codice che illustrano l'uso delle espressioni regolari nelle applicazioni comuni.</span><span class="sxs-lookup"><span data-stu-id="0494f-103">This section contains code examples that illustrate the use of regular expressions in common applications.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0494f-104">Lo spazio dei nomi <xref:System.Web.RegularExpressions> contiene un numero di oggetti di espressione regolare che implementano i modelli di espressione regolare predefiniti per l'analisi di stringhe da documenti HTML, XML e ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="0494f-104">The <xref:System.Web.RegularExpressions> namespace contains a number of regular expression objects that implement predefined regular expression patterns for parsing strings from HTML, XML, and ASP.NET documents.</span></span> <span data-ttu-id="0494f-105">Ad esempio, la classe <xref:System.Web.RegularExpressions.TagRegex> identifica i tag di inizio in una stringa e la classe <xref:System.Web.RegularExpressions.CommentRegex> identifica i commenti ASP.NET in una stringa.</span><span class="sxs-lookup"><span data-stu-id="0494f-105">For example, the <xref:System.Web.RegularExpressions.TagRegex> class identifies start tags in a string and the <xref:System.Web.RegularExpressions.CommentRegex> class identifies ASP.NET comments in a string.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0494f-106">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="0494f-106">In This Section</span></span>  
 [<span data-ttu-id="0494f-107">Esempio: ricerca di HREF</span><span class="sxs-lookup"><span data-stu-id="0494f-107">Example: Scanning for HREFs</span></span>](../../../docs/standard/base-types/regular-expression-example-scanning-for-hrefs.md)  
 <span data-ttu-id="0494f-108">Esempio in cui viene cercata una stringa di input e vengono stampati tutti i valori href="…" con le relative posizioni nella stringa.</span><span class="sxs-lookup"><span data-stu-id="0494f-108">Provides an example that searches an input string and prints out all the href="…" values and their locations in the string.</span></span>  
  
 [<span data-ttu-id="0494f-109">Esempio: modifica dei formati di data</span><span class="sxs-lookup"><span data-stu-id="0494f-109">Example: Changing Date Formats</span></span>](../../../docs/standard/base-types/regular-expression-example-changing-date-formats.md)  
 <span data-ttu-id="0494f-110">Esempio che sostituisce le date nel formato mm/gg/aa con date nel formato gg-mm-aa.</span><span class="sxs-lookup"><span data-stu-id="0494f-110">Provides an example that replaces dates in the form mm/dd/yy with dates in the form dd-mm-yy.</span></span>  
  
 [<span data-ttu-id="0494f-111">Procedura: Estrarre un protocollo e un numero di porta da un URL</span><span class="sxs-lookup"><span data-stu-id="0494f-111">How to: Extract a Protocol and Port Number from a URL</span></span>](../../../docs/standard/base-types/how-to-extract-a-protocol-and-port-number-from-a-url.md)  
 <span data-ttu-id="0494f-112">Esempio che consente di estrarre un protocollo e un numero di porta da una stringa contenente un URL.</span><span class="sxs-lookup"><span data-stu-id="0494f-112">Provides an example that extracts a protocol and port number from a string that contains a URL.</span></span> <span data-ttu-id="0494f-113">Ad esempio, "http://www.contoso.com:8080/letters/readme.html" restituisce "http:8080".</span><span class="sxs-lookup"><span data-stu-id="0494f-113">For example, "http://www.contoso.com:8080/letters/readme.html" returns "http:8080".</span></span>  
  
 [<span data-ttu-id="0494f-114">Procedura: rimuovere caratteri non validi da una stringaHow to: Strip Invalid Characters from a String</span><span class="sxs-lookup"><span data-stu-id="0494f-114">How to: Strip Invalid Characters from a String</span></span>](../../../docs/standard/base-types/how-to-strip-invalid-characters-from-a-string.md)  
 <span data-ttu-id="0494f-115">Esempio che consente di rimuovere i caratteri non alfanumerici non validi da una stringa.</span><span class="sxs-lookup"><span data-stu-id="0494f-115">Provides an example that strips invalid non-alphanumeric characters from a string.</span></span>  
  
 [<span data-ttu-id="0494f-116">Procedura: Verificare che le stringhe siano in formato di posta elettronica valido</span><span class="sxs-lookup"><span data-stu-id="0494f-116">How to: Verify that Strings Are in Valid Email Format</span></span>](../../../docs/standard/base-types/how-to-verify-that-strings-are-in-valid-email-format.md)  
 <span data-ttu-id="0494f-117">Esempio che consente di verificare se una stringa presenta il formato di posta elettronica valido.</span><span class="sxs-lookup"><span data-stu-id="0494f-117">Provides an example that verifies that a string is in valid email format.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="0494f-118">Informazioni di riferimento</span><span class="sxs-lookup"><span data-stu-id="0494f-118">Reference</span></span>  
 <xref:System.Text.RegularExpressions>  
 <span data-ttu-id="0494f-119">Informazioni di riferimento sulla libreria di classi per lo spazio dei nomi di .NET **System.Text.RegularExpressions**.</span><span class="sxs-lookup"><span data-stu-id="0494f-119">Provides class library reference information for the .NET **System.Text.RegularExpressions** namespace.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="0494f-120">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="0494f-120">Related Sections</span></span>  
 [<span data-ttu-id="0494f-121">Espressioni regolari .NET</span><span class="sxs-lookup"><span data-stu-id="0494f-121">.NET Regular Expressions</span></span>](../../../docs/standard/base-types/regular-expressions.md)  
 <span data-ttu-id="0494f-122">Panoramica dell'aspetto del linguaggio di programmazione delle espressioni regolari.</span><span class="sxs-lookup"><span data-stu-id="0494f-122">Provides an overview of the programming language aspect of regular expressions.</span></span>  
  
 [<span data-ttu-id="0494f-123">Modello a oggetti delle espressioni regolariThe Regular Expression Object Model</span><span class="sxs-lookup"><span data-stu-id="0494f-123">The Regular Expression Object Model</span></span>](../../../docs/standard/base-types/the-regular-expression-object-model.md)  
 <span data-ttu-id="0494f-124">Descrive le classi di espressioni regolari contenute nello spazio dei nomi `System.Text.RegularExpression` con esempi del relativo utilizzo.</span><span class="sxs-lookup"><span data-stu-id="0494f-124">Describes the regular expression classes contained in the `System.Text.RegularExpression` namespace and provides examples of their use.</span></span>  
  
 [<span data-ttu-id="0494f-125">Dettagli sul comportamento delle espressioni regolari</span><span class="sxs-lookup"><span data-stu-id="0494f-125">Details of Regular Expression Behavior</span></span>](../../../docs/standard/base-types/details-of-regular-expression-behavior.md)  
 <span data-ttu-id="0494f-126">Offre informazioni sulle funzionalità e il funzionamento delle espressioni regolari di .NET.</span><span class="sxs-lookup"><span data-stu-id="0494f-126">Provides information about the capabilities and behavior of .NET regular expressions.</span></span>  
  
 [<span data-ttu-id="0494f-127">Linguaggio delle espressioni regolari - Guida di riferimento rapidoRegular Expression Language - Quick Reference</span><span class="sxs-lookup"><span data-stu-id="0494f-127">Regular Expression Language - Quick Reference</span></span>](../../../docs/standard/base-types/regular-expression-language-quick-reference.md)  
 <span data-ttu-id="0494f-128">Fornisce informazioni sul set di caratteri, di operatori e di costrutti che è possibile usare per definire le espressioni regolari.</span><span class="sxs-lookup"><span data-stu-id="0494f-128">Provides information on the set of characters, operators, and constructs that you can use to define regular expressions.</span></span>
