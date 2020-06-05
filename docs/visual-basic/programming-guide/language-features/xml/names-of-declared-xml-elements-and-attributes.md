---
title: Nomi di elementi e attributi XML dichiarati
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [XML in Visual Basic]
- element names [XML in Visual Basic]
- names in XML literals [Visual Basic]
- attribute names [XML in Visual Basic]
- XML literals [Visual Basic], element names
ms.assetid: cc110118-b6cf-4ff9-a4e4-6233c90c9fbf
ms.openlocfilehash: 043243eeee7c24d8c63105047fa3e7e0ed58c7b0
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84374668"
---
# <a name="names-of-declared-xml-elements-and-attributes-visual-basic"></a><span data-ttu-id="12f0c-102">Nomi di elementi e attributi XML dichiarati (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="12f0c-102">Names of Declared XML Elements and Attributes (Visual Basic)</span></span>
<span data-ttu-id="12f0c-103">In questo argomento vengono fornite Visual Basic linee guida per la denominazione di elementi e attributi XML nei valori letterali XML.</span><span class="sxs-lookup"><span data-stu-id="12f0c-103">This topic provides Visual Basic guidelines for naming XML elements and attributes in XML literals.</span></span>  <span data-ttu-id="12f0c-104">In un valore letterale XML è possibile specificare un nome locale o un nome completo.</span><span class="sxs-lookup"><span data-stu-id="12f0c-104">In an XML literal, you can specify a local name or a qualified name.</span></span> <span data-ttu-id="12f0c-105">Un nome completo è costituito da un prefisso dello spazio dei nomi XML, da due punti e da un nome locale.</span><span class="sxs-lookup"><span data-stu-id="12f0c-105">A qualified name consists of an XML namespace prefix, a colon, and a local name.</span></span> <span data-ttu-id="12f0c-106">Per ulteriori informazioni sui prefissi degli spazi dei nomi XML, vedere [valore letterale elemento XML](../../../language-reference/xml-literals/xml-element-literal.md).</span><span class="sxs-lookup"><span data-stu-id="12f0c-106">For more information about XML namespace prefixes, see [XML Element Literal](../../../language-reference/xml-literals/xml-element-literal.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="12f0c-107">Regole</span><span class="sxs-lookup"><span data-stu-id="12f0c-107">Rules</span></span>  
 <span data-ttu-id="12f0c-108">Il nome locale di un elemento o di un attributo in Visual Basic deve rispettare le regole seguenti.</span><span class="sxs-lookup"><span data-stu-id="12f0c-108">A local name of an element or attribute in Visual Basic must adhere to the following rules.</span></span>  
  
- <span data-ttu-id="12f0c-109">Può iniziare con uno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="12f0c-109">It can begin with a namespace.</span></span> <span data-ttu-id="12f0c-110">Deve iniziare con un carattere alfabetico o un carattere di sottolineatura ( `_` ).</span><span class="sxs-lookup"><span data-stu-id="12f0c-110">It must begin with an alphabetical character or an underscore (`_`).</span></span>  
  
- <span data-ttu-id="12f0c-111">Deve contenere solo caratteri alfabetici, cifre decimali, caratteri di sottolineatura, punti (.) e trattini (-).</span><span class="sxs-lookup"><span data-stu-id="12f0c-111">It must contain only alphabetical characters, decimal digits, underscores, periods (.), and hyphens (-).</span></span>  
  
- <span data-ttu-id="12f0c-112">La lunghezza non deve superare i 1.024 caratteri.</span><span class="sxs-lookup"><span data-stu-id="12f0c-112">It must not be more than 1,024 characters long.</span></span>  
  
- <span data-ttu-id="12f0c-113">I due punti visualizzati nei nomi indicano la delimitazione dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="12f0c-113">Colons that appear in names indicate namespace demarcation.</span></span> <span data-ttu-id="12f0c-114">Pertanto, è possibile utilizzare i due punti solo per specificare uno spazio dei nomi XML per un determinato nome.</span><span class="sxs-lookup"><span data-stu-id="12f0c-114">Therefore, you can use colons only to specify an XML namespace for a particular name.</span></span>  
  
 <span data-ttu-id="12f0c-115">Inoltre, è necessario rispettare le linee guida seguenti.</span><span class="sxs-lookup"><span data-stu-id="12f0c-115">In addition, you should adhere to the following guideline.</span></span>  
  
- <span data-ttu-id="12f0c-116">La specifica XML 1,0 riserva tutti i nomi che iniziano con la stringa "XML", di qualsiasi variazione di maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="12f0c-116">The XML 1.0 specification reserves all names starting with the string "xml", of any capitalization variation.</span></span> <span data-ttu-id="12f0c-117">Pertanto, non utilizzare tali nomi per i nomi di elemento e di attributo.</span><span class="sxs-lookup"><span data-stu-id="12f0c-117">Therefore, do not use those names for your element and attribute names.</span></span>  
  
### <a name="name-length-guidelines"></a><span data-ttu-id="12f0c-118">Linee guida per la lunghezza del nome</span><span class="sxs-lookup"><span data-stu-id="12f0c-118">Name Length Guidelines</span></span>  
 <span data-ttu-id="12f0c-119">In pratica, un nome deve essere il più breve possibile, pur identificando chiaramente la natura dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="12f0c-119">As a practical matter, a name should be as short as possible while still clearly identifying the nature of the element.</span></span> <span data-ttu-id="12f0c-120">In questo modo è possibile migliorare la leggibilità del codice e ridurre la lunghezza delle righe e le dimensioni del file di origine.</span><span class="sxs-lookup"><span data-stu-id="12f0c-120">This improves the readability of your code and reduces line length and source-file size.</span></span>  
  
 <span data-ttu-id="12f0c-121">Il nome, tuttavia, non deve essere così breve da descrivere in modo adeguato l'elemento o il modo in cui il codice lo usa.</span><span class="sxs-lookup"><span data-stu-id="12f0c-121">However, your name should not be so short that it does not adequately describe the element or how your code uses it.</span></span> <span data-ttu-id="12f0c-122">Questo è importante per la leggibilità del codice.</span><span class="sxs-lookup"><span data-stu-id="12f0c-122">This is important for the readability of your code.</span></span> <span data-ttu-id="12f0c-123">Se un altro utente sta provando a comprenderlo o se si sta esaminando molto tempo dopo averlo scritto, i nomi di elemento appropriati possono risparmiare tempo.</span><span class="sxs-lookup"><span data-stu-id="12f0c-123">If somebody else is trying to understand it, or if you yourself are looking at it a long time after you wrote it, appropriate element names can save time.</span></span>  
  
## <a name="case-sensitivity-in-names"></a><span data-ttu-id="12f0c-124">Distinzione maiuscole/minuscole nei nomi</span><span class="sxs-lookup"><span data-stu-id="12f0c-124">Case Sensitivity in Names</span></span>  
 <span data-ttu-id="12f0c-125">Con distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="12f0c-125">XML element names are case sensitive.</span></span> <span data-ttu-id="12f0c-126">Ciò significa che quando il compilatore di Visual Basic confronta due nomi che differiscono solo per i casi alfabetici, li interpreta come nomi diversi.</span><span class="sxs-lookup"><span data-stu-id="12f0c-126">This means that when the Visual Basic compiler compares two names that differ in alphabetical case only, it interprets them as different names.</span></span> <span data-ttu-id="12f0c-127">Ad esempio, interpreta `ABC` e `abc` come riferimento a elementi distinti.</span><span class="sxs-lookup"><span data-stu-id="12f0c-127">For example, it interprets `ABC` and `abc` as referring to separate elements.</span></span>  
  
## <a name="xml-namespaces"></a><span data-ttu-id="12f0c-128">Spazi dei nomi XML</span><span class="sxs-lookup"><span data-stu-id="12f0c-128">XML Namespaces</span></span>  
 <span data-ttu-id="12f0c-129">Quando si crea un valore letterale elemento XML, è possibile specificare il prefisso dello spazio dei nomi XML per il nome dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="12f0c-129">When creating an XML element literal, you can specify the XML namespace prefix for the element name.</span></span> <span data-ttu-id="12f0c-130">Per altre informazioni, vedere [valore letterale elemento XML](../../../language-reference/xml-literals/xml-element-literal.md).</span><span class="sxs-lookup"><span data-stu-id="12f0c-130">For more information, see [XML Element Literal](../../../language-reference/xml-literals/xml-element-literal.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12f0c-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="12f0c-131">See also</span></span>

- [<span data-ttu-id="12f0c-132">Creazione di XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="12f0c-132">Creating XML in Visual Basic</span></span>](creating-xml.md)
- [<span data-ttu-id="12f0c-133">Valore letterale di elemento XML</span><span class="sxs-lookup"><span data-stu-id="12f0c-133">XML Element Literal</span></span>](../../../language-reference/xml-literals/xml-element-literal.md)
