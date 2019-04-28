---
title: Nomi di elementi e attributi XML dichiarati (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [XML in Visual Basic]
- element names [XML in Visual Basic]
- names in XML literals [Visual Basic]
- attribute names [XML in Visual Basic]
- XML literals [Visual Basic], element names
ms.assetid: cc110118-b6cf-4ff9-a4e4-6233c90c9fbf
ms.openlocfilehash: 2221f2677183cf360fa82a4d73a679a8b68927d1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61761702"
---
# <a name="names-of-declared-xml-elements-and-attributes-visual-basic"></a><span data-ttu-id="338cb-102">Nomi di elementi e attributi XML dichiarati (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="338cb-102">Names of Declared XML Elements and Attributes (Visual Basic)</span></span>
<span data-ttu-id="338cb-103">In questo argomento vengono fornite linee guida di Visual Basic per denominare gli elementi XML e attributi nei valori letterali XML.</span><span class="sxs-lookup"><span data-stu-id="338cb-103">This topic provides Visual Basic guidelines for naming XML elements and attributes in XML literals.</span></span>  <span data-ttu-id="338cb-104">In un valore letterale XML, è possibile specificare un nome locale o un nome completo.</span><span class="sxs-lookup"><span data-stu-id="338cb-104">In an XML literal, you can specify a local name or a qualified name.</span></span> <span data-ttu-id="338cb-105">Un nome completo è costituito da un prefisso dello spazio dei nomi XML, i due punti e un nome locale.</span><span class="sxs-lookup"><span data-stu-id="338cb-105">A qualified name consists of an XML namespace prefix, a colon, and a local name.</span></span> <span data-ttu-id="338cb-106">Per altre informazioni sui prefissi dello spazio dei nomi XML, vedere [letterale elemento XML](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</span><span class="sxs-lookup"><span data-stu-id="338cb-106">For more information about XML namespace prefixes, see [XML Element Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="338cb-107">Regole</span><span class="sxs-lookup"><span data-stu-id="338cb-107">Rules</span></span>  
 <span data-ttu-id="338cb-108">Un nome locale di un elemento o attributo in Visual Basic deve essere conformi alle regole seguenti.</span><span class="sxs-lookup"><span data-stu-id="338cb-108">A local name of an element or attribute in Visual Basic must adhere to the following rules.</span></span>  
  
- <span data-ttu-id="338cb-109">È possibile iniziare con uno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="338cb-109">It can begin with a namespace.</span></span> <span data-ttu-id="338cb-110">Deve iniziare con un carattere alfabetico o un carattere di sottolineatura (`_`).</span><span class="sxs-lookup"><span data-stu-id="338cb-110">It must begin with an alphabetical character or an underscore (`_`).</span></span>  
  
- <span data-ttu-id="338cb-111">Deve contenere solo caratteri alfabetici, cifre decimali, caratteri di sottolineatura, punti (.) e trattini (-).</span><span class="sxs-lookup"><span data-stu-id="338cb-111">It must contain only alphabetical characters, decimal digits, underscores, periods (.), and hyphens (-).</span></span>  
  
- <span data-ttu-id="338cb-112">Non deve essere lungo più di 1.024 caratteri.</span><span class="sxs-lookup"><span data-stu-id="338cb-112">It must not be more than 1,024 characters long.</span></span>  
  
- <span data-ttu-id="338cb-113">I due punti che vengono visualizzati nei nomi indicano demarcazione dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="338cb-113">Colons that appear in names indicate namespace demarcation.</span></span> <span data-ttu-id="338cb-114">Pertanto, è possibile usare i due punti solo per specificare uno spazio dei nomi XML per un determinato nome.</span><span class="sxs-lookup"><span data-stu-id="338cb-114">Therefore, you can use colons only to specify an XML namespace for a particular name.</span></span>  
  
 <span data-ttu-id="338cb-115">Inoltre, è necessario rispettare le linee guida seguenti.</span><span class="sxs-lookup"><span data-stu-id="338cb-115">In addition, you should adhere to the following guideline.</span></span>  
  
- <span data-ttu-id="338cb-116">La specifica XML 1.0 si riserva tutti i nomi che iniziano con la stringa "xml", di qualsiasi variazione di maiuscole/minuscole.</span><span class="sxs-lookup"><span data-stu-id="338cb-116">The XML 1.0 specification reserves all names starting with the string "xml", of any capitalization variation.</span></span> <span data-ttu-id="338cb-117">Pertanto, non utilizzare tali nomi per l'elemento e i nomi degli attributi.</span><span class="sxs-lookup"><span data-stu-id="338cb-117">Therefore, do not use those names for your element and attribute names.</span></span>  
  
### <a name="name-length-guidelines"></a><span data-ttu-id="338cb-118">Nome lunghezza orientamenti</span><span class="sxs-lookup"><span data-stu-id="338cb-118">Name Length Guidelines</span></span>  
 <span data-ttu-id="338cb-119">Ai fini pratici, un nome deve essere più corte possibili durante identificare chiaramente la natura dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="338cb-119">As a practical matter, a name should be as short as possible while still clearly identifying the nature of the element.</span></span> <span data-ttu-id="338cb-120">Ciò migliora la leggibilità del codice e riduce le dimensioni di file di origine e lunghezza riga.</span><span class="sxs-lookup"><span data-stu-id="338cb-120">This improves the readability of your code and reduces line length and source-file size.</span></span>  
  
 <span data-ttu-id="338cb-121">Tuttavia, il nome non deve essere così breve che non in modo adeguato descrive l'elemento o come utilizzato dal codice.</span><span class="sxs-lookup"><span data-stu-id="338cb-121">However, your name should not be so short that it does not adequately describe the element or how your code uses it.</span></span> <span data-ttu-id="338cb-122">Questo è importante per la leggibilità del codice.</span><span class="sxs-lookup"><span data-stu-id="338cb-122">This is important for the readability of your code.</span></span> <span data-ttu-id="338cb-123">Se qualcun altro tenta di comprenderne il concetto, o se ne sta analizzando, molto tempo dopo che è stato scritto, i nomi degli elementi appropriati può risparmiare tempo.</span><span class="sxs-lookup"><span data-stu-id="338cb-123">If somebody else is trying to understand it, or if you yourself are looking at it a long time after you wrote it, appropriate element names can save time.</span></span>  
  
## <a name="case-sensitivity-in-names"></a><span data-ttu-id="338cb-124">Distinzione maiuscole/minuscole nei nomi</span><span class="sxs-lookup"><span data-stu-id="338cb-124">Case Sensitivity in Names</span></span>  
 <span data-ttu-id="338cb-125">Nomi degli elementi XML sono tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="338cb-125">XML element names are case sensitive.</span></span> <span data-ttu-id="338cb-126">Ciò significa che quando il compilatore Visual Basic consente di confrontare due nomi che differiscono solo i case in ordine alfabetico, li interpreta come nomi diversi.</span><span class="sxs-lookup"><span data-stu-id="338cb-126">This means that when the Visual Basic compiler compares two names that differ in alphabetical case only, it interprets them as different names.</span></span> <span data-ttu-id="338cb-127">Ad esempio, interpreta `ABC` e `abc` come se facessero riferimento a elementi distinti.</span><span class="sxs-lookup"><span data-stu-id="338cb-127">For example, it interprets `ABC` and `abc` as referring to separate elements.</span></span>  
  
## <a name="xml-namespaces"></a><span data-ttu-id="338cb-128">Spazi dei nomi XML</span><span class="sxs-lookup"><span data-stu-id="338cb-128">XML Namespaces</span></span>  
 <span data-ttu-id="338cb-129">Quando si crea un elemento XML letterale, è possibile specificare il prefisso dello spazio dei nomi XML per il nome dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="338cb-129">When creating an XML element literal, you can specify the XML namespace prefix for the element name.</span></span> <span data-ttu-id="338cb-130">Per altre informazioni, vedere [letterale elemento XML](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</span><span class="sxs-lookup"><span data-stu-id="338cb-130">For more information, see [XML Element Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="338cb-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="338cb-131">See also</span></span>

- [<span data-ttu-id="338cb-132">Creazione di XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="338cb-132">Creating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="338cb-133">Valore letterale elemento XML</span><span class="sxs-lookup"><span data-stu-id="338cb-133">XML Element Literal</span></span>](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
