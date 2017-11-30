---
title: 'Esempio di espressione regolare: ricerca di HREF'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- searching with regular expressions, examples
- parsing text with regular expressions, examples
- regular expressions, examples
- .NET Framework regular expressions, examples
- regular expressions [.NET Framework], examples
- pattern-matching with regular expressions, examples
ms.assetid: fae2c15b-7adf-4b15-b118-58eb3906994f
caps.latest.revision: "24"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2bc9db7317c7a73f70a2cb83322b8b3a4c3771b9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="regular-expression-example-scanning-for-hrefs"></a><span data-ttu-id="9b451-102">Esempio di espressione regolare: ricerca di HREF</span><span class="sxs-lookup"><span data-stu-id="9b451-102">Regular Expression Example: Scanning for HREFs</span></span>
<span data-ttu-id="9b451-103">Nell'esempio riportato di seguito viene cercata una stringa di input e vengono visualizzati tutti i valori href="…" e le relative posizioni nella stringa.</span><span class="sxs-lookup"><span data-stu-id="9b451-103">The following example searches an input string and displays all the href="…" values and their locations in the string.</span></span>  
  
## <a name="the-regex-object"></a><span data-ttu-id="9b451-104">L'oggetto Regex</span><span class="sxs-lookup"><span data-stu-id="9b451-104">The Regex Object</span></span>  
 <span data-ttu-id="9b451-105">Poiché il `DumpHRefs` metodo può essere chiamato più volte dal codice utente, viene utilizzato il `static` (`Shared` in Visual Basic) <xref:System.Text.RegularExpressions.Regex.Match%28System.String%2CSystem.String%2CSystem.Text.RegularExpressions.RegexOptions%29?displayProperty=nameWithType> metodo.</span><span class="sxs-lookup"><span data-stu-id="9b451-105">Because the `DumpHRefs` method can be called multiple times from user code, it uses the `static` (`Shared` in Visual Basic) <xref:System.Text.RegularExpressions.Regex.Match%28System.String%2CSystem.String%2CSystem.Text.RegularExpressions.RegexOptions%29?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="9b451-106">In questo modo il motore delle espressioni regolari memorizzare nella cache l'espressione regolare ed evita l'overhead di un'istanza di un nuovo <xref:System.Text.RegularExpressions.Regex> ogni volta che viene chiamato il metodo di oggetto.</span><span class="sxs-lookup"><span data-stu-id="9b451-106">This enables the regular expression engine to cache the regular expression and avoids the overhead of instantiating a new <xref:System.Text.RegularExpressions.Regex> object each time the method is called.</span></span> <span data-ttu-id="9b451-107">Oggetto <xref:System.Text.RegularExpressions.Match> oggetto viene quindi utilizzato per scorrere tutte le corrispondenze nella stringa.</span><span class="sxs-lookup"><span data-stu-id="9b451-107">A <xref:System.Text.RegularExpressions.Match> object is then used to iterate through all matches in the string.</span></span>  
  
 [!code-csharp[RegularExpressions.Examples.HREF#1](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.HREF/cs/example.cs#1)]
 [!code-vb[RegularExpressions.Examples.HREF#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.HREF/vb/example.vb#1)]  
  
 <span data-ttu-id="9b451-108">Nell'esempio seguente viene illustrata una chiamata al metodo `DumpHRefs`.</span><span class="sxs-lookup"><span data-stu-id="9b451-108">The following example then illustrates a call to the `DumpHRefs` method.</span></span>  
  
 [!code-csharp[RegularExpressions.Examples.HREF#2](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.HREF/cs/example.cs#2)]
 [!code-vb[RegularExpressions.Examples.HREF#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.HREF/vb/example.vb#2)]  
  
 <span data-ttu-id="9b451-109">Il criterio di ricerca di espressioni regolari `href\s*=\s*(?:["'](?<1>[^"']*)["']|(?<1>\S+))` è interpretato nel modo illustrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="9b451-109">The regular expression pattern `href\s*=\s*(?:["'](?<1>[^"']*)["']|(?<1>\S+))` is interpreted as shown in the following table.</span></span>  
  
|<span data-ttu-id="9b451-110">Criterio</span><span class="sxs-lookup"><span data-stu-id="9b451-110">Pattern</span></span>|<span data-ttu-id="9b451-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9b451-111">Description</span></span>|  
|-------------|-----------------|  
|`href`|<span data-ttu-id="9b451-112">Corrisponde alla stringa letterale "href".</span><span class="sxs-lookup"><span data-stu-id="9b451-112">Match the literal string "href".</span></span> <span data-ttu-id="9b451-113">La corrispondenza non fa distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="9b451-113">The match is case-insensitive.</span></span>|  
|`\s*`|<span data-ttu-id="9b451-114">Trovare la corrispondenza di zero o più spazi vuoti.</span><span class="sxs-lookup"><span data-stu-id="9b451-114">Match zero or more white-space characters.</span></span>|  
|`=`|<span data-ttu-id="9b451-115">Trova la corrispondenza di segno di uguale.</span><span class="sxs-lookup"><span data-stu-id="9b451-115">Match the equals sign.</span></span>|  
|`\s*`|<span data-ttu-id="9b451-116">Trovare la corrispondenza di zero o più spazi vuoti.</span><span class="sxs-lookup"><span data-stu-id="9b451-116">Match zero or more white-space characters.</span></span>|  
|`(?:["'](?<1>[^"']*)"&#124;(?<1>\S+))`|<span data-ttu-id="9b451-117">Senza l'assegnazione del risultato a un gruppo acquisito, corrisponde a uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="9b451-117">Match one of the following without assigning the result to a captured group:</span></span><br /><br /> <span data-ttu-id="9b451-118">-Una virgoletta o un apostrofo, seguito da zero o più occorrenze di qualsiasi carattere diverso da una virgoletta o un apostrofo, seguito da una virgoletta o un apostrofo.</span><span class="sxs-lookup"><span data-stu-id="9b451-118">-   A quotation mark or apostrophe, followed by zero or more occurrences of any character other than a quotation mark or apostrophe, followed by a quotation mark or apostrophe.</span></span> <span data-ttu-id="9b451-119">Il gruppo denominato `1` è incluso in questo modello.</span><span class="sxs-lookup"><span data-stu-id="9b451-119">The group named `1` is included in this pattern.</span></span><br /><span data-ttu-id="9b451-120">-Uno o più caratteri di spazio non vuoto.</span><span class="sxs-lookup"><span data-stu-id="9b451-120">-   One or more non-white-space characters.</span></span> <span data-ttu-id="9b451-121">Il gruppo denominato `1` è incluso in questo modello.</span><span class="sxs-lookup"><span data-stu-id="9b451-121">The group named `1` is included in this pattern.</span></span>|  
|`(?<1>[^"']*)`|<span data-ttu-id="9b451-122">Assegnare zero o più occorrenze di qualsiasi carattere diverso da una virgoletta o un apostrofo al gruppo di acquisizione denominato `1`.</span><span class="sxs-lookup"><span data-stu-id="9b451-122">Assign zero or more occurrences of any character other than a quotation mark or apostrophe to the capturing group named `1`.</span></span>|  
|`"(?<1>\S+)`|<span data-ttu-id="9b451-123">Assegnare uno o più caratteri diversi da spazi vuoti al gruppo di acquisizione denominato `1`.</span><span class="sxs-lookup"><span data-stu-id="9b451-123">Assign one or more non-white-space characters to the capturing group named `1`.</span></span>|  
  
## <a name="match-result-class"></a><span data-ttu-id="9b451-124">Classe di risultati di corrispondenza</span><span class="sxs-lookup"><span data-stu-id="9b451-124">Match Result Class</span></span>  
 <span data-ttu-id="9b451-125">I risultati della ricerca vengono archiviati nel <xref:System.Text.RegularExpressions.Match> (classe), che fornisce l'accesso a tutte le sottostringhe estratte dalla ricerca.</span><span class="sxs-lookup"><span data-stu-id="9b451-125">The results of a search are stored in the <xref:System.Text.RegularExpressions.Match> class, which provides access to all the substrings extracted by the search.</span></span> <span data-ttu-id="9b451-126">Tale classe memorizza inoltre la stringa di cui eseguire la ricerca e l'espressione regolare utilizzata, pertanto è possibile chiamare il <xref:System.Text.RegularExpressions.Match.NextMatch%2A?displayProperty=nameWithType> metodo per eseguire un'altra ricerca a partire dal punto in cui il penultimo termina.</span><span class="sxs-lookup"><span data-stu-id="9b451-126">It also remembers the string being searched and the regular expression being used, so it can call the <xref:System.Text.RegularExpressions.Match.NextMatch%2A?displayProperty=nameWithType> method to perform another search starting where the last one ended.</span></span>  
  
## <a name="explicitly-named-captures"></a><span data-ttu-id="9b451-127">Acquisizioni denominate in modo esplicito</span><span class="sxs-lookup"><span data-stu-id="9b451-127">Explicitly Named Captures</span></span>  
 <span data-ttu-id="9b451-128">Nelle espressioni regolari tradizionali, le parentesi di cattura vengono automaticamente numerate in sequenza.</span><span class="sxs-lookup"><span data-stu-id="9b451-128">In traditional regular expressions, capturing parentheses are automatically numbered sequentially.</span></span> <span data-ttu-id="9b451-129">Ciò comporta due problemi.</span><span class="sxs-lookup"><span data-stu-id="9b451-129">This leads to two problems.</span></span> <span data-ttu-id="9b451-130">In primo luogo, se un'espressione regolare viene modificata dall'inserimento o rimozione di un set di parentesi, tutto il codice che fa riferimento alle catture numerate deve essere riscritto per riflettere la nuova numerazione.</span><span class="sxs-lookup"><span data-stu-id="9b451-130">First, if a regular expression is modified by inserting or removing a set of parentheses, all code that refers to the numbered captures must be rewritten to reflect the new numbering.</span></span> <span data-ttu-id="9b451-131">In secondo luogo, poiché diversi set di parentesi spesso vengono usati per specificare due espressioni alternative per una corrispondenza accettabile, potrebbe essere difficile determinare quale delle due espressioni ha effettivamente restituito un risultato.</span><span class="sxs-lookup"><span data-stu-id="9b451-131">Second, because different sets of parentheses often are used to provide two alternative expressions for an acceptable match, it might be difficult to determine which of the two expressions actually returned a result.</span></span>  
  
 <span data-ttu-id="9b451-132">Per risolvere questi problemi, il <xref:System.Text.RegularExpressions.Regex> classe supporta la sintassi `(?<name>…)` per l'acquisizione di una corrispondenza in uno slot specificato (slot può essere denominato tramite una stringa o un numero intero, che può essere richiamato più rapidamente).</span><span class="sxs-lookup"><span data-stu-id="9b451-132">To address these problems, the <xref:System.Text.RegularExpressions.Regex> class supports the syntax `(?<name>…)` for capturing a match into a specified slot (the slot can be named using a string or an integer; integers can be recalled more quickly).</span></span> <span data-ttu-id="9b451-133">Le corrispondenze alternative per la stessa stringa possono perciò essere tutte indirizzate verso la stessa posizione.</span><span class="sxs-lookup"><span data-stu-id="9b451-133">Thus, alternative matches for the same string all can be directed to the same place.</span></span> <span data-ttu-id="9b451-134">In caso di conflitto, l'ultima corrispondenza rilasciata in uno slot è quella corretta.</span><span class="sxs-lookup"><span data-stu-id="9b451-134">In case of a conflict, the last match dropped into a slot is the successful match.</span></span> <span data-ttu-id="9b451-135">(È tuttavia disponibile un elenco completo di più corrispondenze per un unico slot.</span><span class="sxs-lookup"><span data-stu-id="9b451-135">(However, a complete list of multiple matches for a single slot is available.</span></span> <span data-ttu-id="9b451-136">Vedere il <xref:System.Text.RegularExpressions.Group.Captures%2A?displayProperty=nameWithType> raccolta per i dettagli.)</span><span class="sxs-lookup"><span data-stu-id="9b451-136">See the <xref:System.Text.RegularExpressions.Group.Captures%2A?displayProperty=nameWithType> collection for details.)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b451-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9b451-137">See Also</span></span>  
 [<span data-ttu-id="9b451-138">Espressioni regolari di .NET</span><span class="sxs-lookup"><span data-stu-id="9b451-138">.NET Regular Expressions</span></span>](../../../docs/standard/base-types/regular-expressions.md)
