---
title: Nomi di elementi e attributi XML dichiarati (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- declarations [XML in Visual Basic]
- element names [XML in Visual Basic]
- names in XML literals [Visual Basic]
- attribute names [XML in Visual Basic]
- XML literals [Visual Basic], element names
ms.assetid: cc110118-b6cf-4ff9-a4e4-6233c90c9fbf
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 846a028e076873d1978f751fdb70e93c7c6a81af
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="names-of-declared-xml-elements-and-attributes-visual-basic"></a><span data-ttu-id="f0e67-102">Nomi di elementi e attributi XML dichiarati (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f0e67-102">Names of Declared XML Elements and Attributes (Visual Basic)</span></span>
<span data-ttu-id="f0e67-103">Questo argomento vengono fornite [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] linee guida per denominare gli elementi XML e attributi nei valori letterali XML.</span><span class="sxs-lookup"><span data-stu-id="f0e67-103">This topic provides [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] guidelines for naming XML elements and attributes in XML literals.</span></span>  <span data-ttu-id="f0e67-104">In un valore letterale XML, è possibile specificare un nome locale o un nome completo.</span><span class="sxs-lookup"><span data-stu-id="f0e67-104">In an XML literal, you can specify a local name or a qualified name.</span></span> <span data-ttu-id="f0e67-105">Un nome completo è costituito da un prefisso dello spazio dei nomi XML, i due punti e un nome locale.</span><span class="sxs-lookup"><span data-stu-id="f0e67-105">A qualified name consists of an XML namespace prefix, a colon, and a local name.</span></span> <span data-ttu-id="f0e67-106">Per ulteriori informazioni sui prefissi dello spazio dei nomi XML, vedere [XML elemento Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</span><span class="sxs-lookup"><span data-stu-id="f0e67-106">For more information about XML namespace prefixes, see [XML Element Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="f0e67-107">Regole</span><span class="sxs-lookup"><span data-stu-id="f0e67-107">Rules</span></span>  
 <span data-ttu-id="f0e67-108">Un nome locale di un elemento o attributo in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] devono essere conformi alle regole seguenti.</span><span class="sxs-lookup"><span data-stu-id="f0e67-108">A local name of an element or attribute in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] must adhere to the following rules.</span></span>  
  
-   <span data-ttu-id="f0e67-109">Può iniziare con uno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="f0e67-109">It can begin with a namespace.</span></span> <span data-ttu-id="f0e67-110">Deve iniziare con un carattere alfabetico o un carattere di sottolineatura (`_`).</span><span class="sxs-lookup"><span data-stu-id="f0e67-110">It must begin with an alphabetical character or an underscore (`_`).</span></span>  
  
-   <span data-ttu-id="f0e67-111">Deve contenere solo caratteri alfabetici, cifre decimali, caratteri di sottolineatura, punti (.) e trattini (-).</span><span class="sxs-lookup"><span data-stu-id="f0e67-111">It must contain only alphabetical characters, decimal digits, underscores, periods (.), and hyphens (-).</span></span>  
  
-   <span data-ttu-id="f0e67-112">Non deve essere più di 1.024 caratteri.</span><span class="sxs-lookup"><span data-stu-id="f0e67-112">It must not be more than 1,024 characters long.</span></span>  
  
-   <span data-ttu-id="f0e67-113">I due punti nei nomi visualizzati indicano delimitazione dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="f0e67-113">Colons that appear in names indicate namespace demarcation.</span></span> <span data-ttu-id="f0e67-114">Pertanto, è possibile utilizzare i due punti solo per specificare uno spazio dei nomi XML per un determinato nome.</span><span class="sxs-lookup"><span data-stu-id="f0e67-114">Therefore, you can use colons only to specify an XML namespace for a particular name.</span></span>  
  
 <span data-ttu-id="f0e67-115">Inoltre, è necessario rispettare le linee guida seguente.</span><span class="sxs-lookup"><span data-stu-id="f0e67-115">In addition, you should adhere to the following guideline.</span></span>  
  
-   <span data-ttu-id="f0e67-116">La specifica XML 1.0 si riserva tutti i nomi che iniziano con la stringa "xml", di qualsiasi variazione di maiuscole/minuscole.</span><span class="sxs-lookup"><span data-stu-id="f0e67-116">The XML 1.0 specification reserves all names starting with the string "xml", of any capitalization variation.</span></span> <span data-ttu-id="f0e67-117">Pertanto, non utilizzare tali nomi per l'elemento e i nomi di attributo.</span><span class="sxs-lookup"><span data-stu-id="f0e67-117">Therefore, do not use those names for your element and attribute names.</span></span>  
  
### <a name="name-length-guidelines"></a><span data-ttu-id="f0e67-118">Linee guida di lunghezza nome</span><span class="sxs-lookup"><span data-stu-id="f0e67-118">Name Length Guidelines</span></span>  
 <span data-ttu-id="f0e67-119">In pratica, un nome deve essere il più breve possibile identificando chiaramente la natura dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="f0e67-119">As a practical matter, a name should be as short as possible while still clearly identifying the nature of the element.</span></span> <span data-ttu-id="f0e67-120">Questo migliora la leggibilità del codice e ridurre la dimensione del file di origine e di lunghezza riga.</span><span class="sxs-lookup"><span data-stu-id="f0e67-120">This improves the readability of your code and reduces line length and source-file size.</span></span>  
  
 <span data-ttu-id="f0e67-121">Tuttavia, il nome non deve essere breve in modo che non adeguatamente descrive l'elemento o come utilizzato dal codice.</span><span class="sxs-lookup"><span data-stu-id="f0e67-121">However, your name should not be so short that it does not adequately describe the element or how your code uses it.</span></span> <span data-ttu-id="f0e67-122">Questo è importante per la leggibilità del codice.</span><span class="sxs-lookup"><span data-stu-id="f0e67-122">This is important for the readability of your code.</span></span> <span data-ttu-id="f0e67-123">Se un altro utente sta tentando di capire, o se manualmente cercata è molto tempo dopo che è stata scritta, i nomi di elemento appropriato possono risparmiare tempo.</span><span class="sxs-lookup"><span data-stu-id="f0e67-123">If somebody else is trying to understand it, or if you yourself are looking at it a long time after you wrote it, appropriate element names can save time.</span></span>  
  
## <a name="case-sensitivity-in-names"></a><span data-ttu-id="f0e67-124">Distinzione maiuscole/minuscole nei nomi</span><span class="sxs-lookup"><span data-stu-id="f0e67-124">Case Sensitivity in Names</span></span>  
 <span data-ttu-id="f0e67-125">I nomi degli elementi XML vengono tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="f0e67-125">XML element names are case sensitive.</span></span> <span data-ttu-id="f0e67-126">Ciò significa che quando il [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compilatore confronta due nomi che differiscono solo i case in ordine alfabetico, li interpreta come diversi nomi.</span><span class="sxs-lookup"><span data-stu-id="f0e67-126">This means that when the [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compiler compares two names that differ in alphabetical case only, it interprets them as different names.</span></span> <span data-ttu-id="f0e67-127">Ad esempio, vengono interpretati `ABC` e `abc` come riferiti a elementi distinti.</span><span class="sxs-lookup"><span data-stu-id="f0e67-127">For example, it interprets `ABC` and `abc` as referring to separate elements.</span></span>  
  
## <a name="xml-namespaces"></a><span data-ttu-id="f0e67-128">Spazi dei nomi XML</span><span class="sxs-lookup"><span data-stu-id="f0e67-128">XML Namespaces</span></span>  
 <span data-ttu-id="f0e67-129">Quando si crea il valore letterale elemento XML, è possibile specificare il prefisso dello spazio dei nomi XML per il nome dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="f0e67-129">When creating an XML element literal, you can specify the XML namespace prefix for the element name.</span></span> <span data-ttu-id="f0e67-130">Per ulteriori informazioni, vedere [XML elemento Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</span><span class="sxs-lookup"><span data-stu-id="f0e67-130">For more information, see [XML Element Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0e67-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f0e67-131">See Also</span></span>  
 [<span data-ttu-id="f0e67-132">Creazione di XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f0e67-132">Creating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 [<span data-ttu-id="f0e67-133">Valore letterale elemento XML</span><span class="sxs-lookup"><span data-stu-id="f0e67-133">XML Element Literal</span></span>](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
