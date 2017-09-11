---
title: I nomi di elementi XML dichiarati e attributi (Visual Basic) | Documenti di Microsoft
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- declarations [XML in Visual Basic]
- element names [XML in Visual Basic]
- names in XML literals
- attribute names [XML in Visual Basic]
- XML literals [Visual Basic], element names
ms.assetid: cc110118-b6cf-4ff9-a4e4-6233c90c9fbf
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 2c0bb2350f50138d00e202e2e887a2202d21942f
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="names-of-declared-xml-elements-and-attributes-visual-basic"></a><span data-ttu-id="3cc63-102">Nomi di elementi e attributi XML dichiarati (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3cc63-102">Names of Declared XML Elements and Attributes (Visual Basic)</span></span>
<span data-ttu-id="3cc63-103">In questo argomento vengono [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] linee guida per la denominazione di elementi XML e attributi nei valori letterali XML.</span><span class="sxs-lookup"><span data-stu-id="3cc63-103">This topic provides [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] guidelines for naming XML elements and attributes in XML literals.</span></span>  <span data-ttu-id="3cc63-104">In un valore letterale XML, è possibile specificare un nome locale o un nome completo.</span><span class="sxs-lookup"><span data-stu-id="3cc63-104">In an XML literal, you can specify a local name or a qualified name.</span></span> <span data-ttu-id="3cc63-105">Un nome completo è costituito da un prefisso dello spazio dei nomi XML, i due punti e un nome locale.</span><span class="sxs-lookup"><span data-stu-id="3cc63-105">A qualified name consists of an XML namespace prefix, a colon, and a local name.</span></span> <span data-ttu-id="3cc63-106">Per ulteriori informazioni sui prefissi dello spazio dei nomi XML, vedere [letterale elemento XML](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</span><span class="sxs-lookup"><span data-stu-id="3cc63-106">For more information about XML namespace prefixes, see [XML Element Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="3cc63-107">Regole</span><span class="sxs-lookup"><span data-stu-id="3cc63-107">Rules</span></span>  
 <span data-ttu-id="3cc63-108">Un nome locale di un elemento o attributo in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] devono essere conformi alle regole seguenti.</span><span class="sxs-lookup"><span data-stu-id="3cc63-108">A local name of an element or attribute in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] must adhere to the following rules.</span></span>  
  
-   <span data-ttu-id="3cc63-109">È possibile iniziare con uno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="3cc63-109">It can begin with a namespace.</span></span> <span data-ttu-id="3cc63-110">Deve iniziare con un carattere alfabetico o un carattere di sottolineatura (`_`).</span><span class="sxs-lookup"><span data-stu-id="3cc63-110">It must begin with an alphabetical character or an underscore (`_`).</span></span>  
  
-   <span data-ttu-id="3cc63-111">Deve contenere solo caratteri alfabetici, cifre decimali, caratteri di sottolineatura, punti (.) e trattini (-).</span><span class="sxs-lookup"><span data-stu-id="3cc63-111">It must contain only alphabetical characters, decimal digits, underscores, periods (.), and hyphens (-).</span></span>  
  
-   <span data-ttu-id="3cc63-112">Non è necessario più di 1.024 caratteri.</span><span class="sxs-lookup"><span data-stu-id="3cc63-112">It must not be more than 1,024 characters long.</span></span>  
  
-   <span data-ttu-id="3cc63-113">I due punti presenti nei nomi indicano demarcazione dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="3cc63-113">Colons that appear in names indicate namespace demarcation.</span></span> <span data-ttu-id="3cc63-114">Pertanto, è possibile utilizzare i due punti solo per specificare uno spazio dei nomi XML per un determinato nome.</span><span class="sxs-lookup"><span data-stu-id="3cc63-114">Therefore, you can use colons only to specify an XML namespace for a particular name.</span></span>  
  
 <span data-ttu-id="3cc63-115">Inoltre, è necessario rispettare le seguenti indicazioni.</span><span class="sxs-lookup"><span data-stu-id="3cc63-115">In addition, you should adhere to the following guideline.</span></span>  
  
-   <span data-ttu-id="3cc63-116">La specifica XML 1.0 si riserva tutti i nomi che iniziano con la stringa "xml", di qualsiasi variazione di maiuscole.</span><span class="sxs-lookup"><span data-stu-id="3cc63-116">The XML 1.0 specification reserves all names starting with the string "xml", of any capitalization variation.</span></span> <span data-ttu-id="3cc63-117">Pertanto, non utilizzare tali nomi per l'elemento e i nomi degli attributi.</span><span class="sxs-lookup"><span data-stu-id="3cc63-117">Therefore, do not use those names for your element and attribute names.</span></span>  
  
### <a name="name-length-guidelines"></a><span data-ttu-id="3cc63-118">Linee guida per la lunghezza nome</span><span class="sxs-lookup"><span data-stu-id="3cc63-118">Name Length Guidelines</span></span>  
 <span data-ttu-id="3cc63-119">Ai fini pratici, un nome deve essere il più breve possibile durante identificare chiaramente la natura dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="3cc63-119">As a practical matter, a name should be as short as possible while still clearly identifying the nature of the element.</span></span> <span data-ttu-id="3cc63-120">Ciò migliora la leggibilità del codice e si riduce la dimensione della linea di lunghezza e file di origine.</span><span class="sxs-lookup"><span data-stu-id="3cc63-120">This improves the readability of your code and reduces line length and source-file size.</span></span>  
  
 <span data-ttu-id="3cc63-121">Tuttavia, il nome non deve essere troppo breve che non adeguatamente descrive l'elemento o come utilizzato dal codice.</span><span class="sxs-lookup"><span data-stu-id="3cc63-121">However, your name should not be so short that it does not adequately describe the element or how your code uses it.</span></span> <span data-ttu-id="3cc63-122">Ciò è importante per la leggibilità del codice.</span><span class="sxs-lookup"><span data-stu-id="3cc63-122">This is important for the readability of your code.</span></span> <span data-ttu-id="3cc63-123">Se qualcun altro sta tentando di capire o dall'utente sono guardando molto tempo dopo che è stato scritto, i nomi di elemento appropriato possono risparmiare tempo.</span><span class="sxs-lookup"><span data-stu-id="3cc63-123">If somebody else is trying to understand it, or if you yourself are looking at it a long time after you wrote it, appropriate element names can save time.</span></span>  
  
## <a name="case-sensitivity-in-names"></a><span data-ttu-id="3cc63-124">Distinzione maiuscole/minuscole nei nomi</span><span class="sxs-lookup"><span data-stu-id="3cc63-124">Case Sensitivity in Names</span></span>  
 <span data-ttu-id="3cc63-125">I nomi degli elementi XML sono sensibili alle maiuscole.</span><span class="sxs-lookup"><span data-stu-id="3cc63-125">XML element names are case sensitive.</span></span> <span data-ttu-id="3cc63-126">Ciò significa che quando il [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compilatore confronta due nomi che differiscono solo case in ordine alfabetico, li interpreta come diversi nomi.</span><span class="sxs-lookup"><span data-stu-id="3cc63-126">This means that when the [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler compares two names that differ in alphabetical case only, it interprets them as different names.</span></span> <span data-ttu-id="3cc63-127">Ad esempio, interpreta `ABC` e `abc` come riferiti a elementi distinti.</span><span class="sxs-lookup"><span data-stu-id="3cc63-127">For example, it interprets `ABC` and `abc` as referring to separate elements.</span></span>  
  
## <a name="xml-namespaces"></a><span data-ttu-id="3cc63-128">Spazi dei nomi XML</span><span class="sxs-lookup"><span data-stu-id="3cc63-128">XML Namespaces</span></span>  
 <span data-ttu-id="3cc63-129">Quando si crea un elemento XML letterale, è possibile specificare il prefisso dello spazio dei nomi XML per il nome dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="3cc63-129">When creating an XML element literal, you can specify the XML namespace prefix for the element name.</span></span> <span data-ttu-id="3cc63-130">Per ulteriori informazioni, vedere [letterale elemento XML](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</span><span class="sxs-lookup"><span data-stu-id="3cc63-130">For more information, see [XML Element Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3cc63-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3cc63-131">See Also</span></span>  
 <span data-ttu-id="3cc63-132">[Creazione di XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md) </span><span class="sxs-lookup"><span data-stu-id="3cc63-132">[Creating XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md) </span></span>  
<span data-ttu-id="3cc63-133"> [Valore letterale elemento XML](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)</span><span class="sxs-lookup"><span data-stu-id="3cc63-133"> [XML Element Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)</span></span>
