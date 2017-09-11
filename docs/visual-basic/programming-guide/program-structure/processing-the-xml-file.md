---
title: Elaborazione del File XML (Visual Basic) | Documenti di Microsoft
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- XML comments, parsing [Visual Basic]
ms.assetid: 78a15cd0-7708-4e79-85d1-c154b7a14a8c
caps.latest.revision: 16
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
ms.openlocfilehash: cf15cf59413e0e019086dd1a79951ccb212f037b
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="processing-the-xml-file-visual-basic"></a><span data-ttu-id="ca9b1-102">Elaborazione del file XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ca9b1-102">Processing the XML File (Visual Basic)</span></span>
<span data-ttu-id="ca9b1-103">Il compilatore genera una stringa ID per ogni costrutto nel codice che contiene tag per generare la documentazione.</span><span class="sxs-lookup"><span data-stu-id="ca9b1-103">The compiler generates an ID string for each construct in your code that is tagged to generate documentation.</span></span> <span data-ttu-id="ca9b1-104">(Per informazioni su come contrassegnare il codice, vedere [tag di commento XML](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md).) Stringa ID identifica in modo univoco il costrutto.</span><span class="sxs-lookup"><span data-stu-id="ca9b1-104">(For information on how to tag your code, see [XML Comment Tags](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md).) The ID string uniquely identifies the construct.</span></span> <span data-ttu-id="ca9b1-105">I programmi che elaborano il file XML è possono utilizzare la stringa di ID per identificare il corrispondente [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] elemento metadati/reflection.</span><span class="sxs-lookup"><span data-stu-id="ca9b1-105">Programs that process the XML file can use the ID string to identify the corresponding [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] metadata/reflection item.</span></span>  
  
 <span data-ttu-id="ca9b1-106">Il file XML non è una rappresentazione gerarchica del codice. è un elenco semplice con un ID generato per ogni elemento.</span><span class="sxs-lookup"><span data-stu-id="ca9b1-106">The XML file is not a hierarchical representation of your code; it is a flat list with a generated ID for each element.</span></span>  
  
 <span data-ttu-id="ca9b1-107">Quando genera le stringhe di ID, il compilatore applica le regole seguenti:</span><span class="sxs-lookup"><span data-stu-id="ca9b1-107">The compiler observes the following rules when it generates the ID strings:</span></span>  
  
-   <span data-ttu-id="ca9b1-108">Gli spazi vuoti non viene inserito nella stringa.</span><span class="sxs-lookup"><span data-stu-id="ca9b1-108">No white space is placed in the string.</span></span>  
  
-   <span data-ttu-id="ca9b1-109">La prima parte della stringa di ID identifica il tipo di membro identificato, con un singolo carattere seguito da due punti.</span><span class="sxs-lookup"><span data-stu-id="ca9b1-109">The first part of the ID string identifies the kind of member being identified, with a single character followed by a colon.</span></span> <span data-ttu-id="ca9b1-110">Vengono utilizzati i seguenti tipi di membro.</span><span class="sxs-lookup"><span data-stu-id="ca9b1-110">The following member types are used.</span></span>  
  
|<span data-ttu-id="ca9b1-111">Carattere</span><span class="sxs-lookup"><span data-stu-id="ca9b1-111">Character</span></span>|<span data-ttu-id="ca9b1-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ca9b1-112">Description</span></span>|  
|---|---|  
|<span data-ttu-id="ca9b1-113">N</span><span class="sxs-lookup"><span data-stu-id="ca9b1-113">N</span></span>|<span data-ttu-id="ca9b1-114">namespace</span><span class="sxs-lookup"><span data-stu-id="ca9b1-114">namespace</span></span><br /><br /> <span data-ttu-id="ca9b1-115">È possibile aggiungere commenti sulla documentazione a uno spazio dei nomi, ma è possibile creare riferimenti CREF ad essi, in cui è supportata.</span><span class="sxs-lookup"><span data-stu-id="ca9b1-115">You cannot add documentation comments to a namespace, but you can make CREF references to them, where supported.</span></span>|  
|<span data-ttu-id="ca9b1-116">T</span><span class="sxs-lookup"><span data-stu-id="ca9b1-116">T</span></span>|<span data-ttu-id="ca9b1-117">type: `Class`, `Module`, `Interface`, `Structure`, `Enum`,`Delegate`</span><span class="sxs-lookup"><span data-stu-id="ca9b1-117">type: `Class`, `Module`, `Interface`, `Structure`, `Enum`, `Delegate`</span></span>|  
|<span data-ttu-id="ca9b1-118">F</span><span class="sxs-lookup"><span data-stu-id="ca9b1-118">F</span></span>|<span data-ttu-id="ca9b1-119">campo:`Dim`</span><span class="sxs-lookup"><span data-stu-id="ca9b1-119">field: `Dim`</span></span>|  
|<span data-ttu-id="ca9b1-120">P</span><span class="sxs-lookup"><span data-stu-id="ca9b1-120">P</span></span>|<span data-ttu-id="ca9b1-121">proprietà: `Property` (incluse le proprietà predefinite)</span><span class="sxs-lookup"><span data-stu-id="ca9b1-121">property: `Property` (including default properties)</span></span>|  
|<span data-ttu-id="ca9b1-122">M</span><span class="sxs-lookup"><span data-stu-id="ca9b1-122">M</span></span>|<span data-ttu-id="ca9b1-123">method: `Sub`, `Function`, `Declare`,`Operator`</span><span class="sxs-lookup"><span data-stu-id="ca9b1-123">method: `Sub`, `Function`, `Declare`, `Operator`</span></span>|  
|<span data-ttu-id="ca9b1-124">E</span><span class="sxs-lookup"><span data-stu-id="ca9b1-124">E</span></span>|<span data-ttu-id="ca9b1-125">evento:`Event`</span><span class="sxs-lookup"><span data-stu-id="ca9b1-125">event: `Event`</span></span>|  
|<span data-ttu-id="ca9b1-126">!</span><span class="sxs-lookup"><span data-stu-id="ca9b1-126">!</span></span>|<span data-ttu-id="ca9b1-127">stringa di errore</span><span class="sxs-lookup"><span data-stu-id="ca9b1-127">error string</span></span><br /><br /> <span data-ttu-id="ca9b1-128">Il resto della stringa vengono fornite informazioni sull'errore.</span><span class="sxs-lookup"><span data-stu-id="ca9b1-128">The rest of the string provides information about the error.</span></span> <span data-ttu-id="ca9b1-129">Il [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] il compilatore genera informazioni di errore per i collegamenti che non possono essere risolti.</span><span class="sxs-lookup"><span data-stu-id="ca9b1-129">The [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler generates error information for links that cannot be resolved.</span></span>|  
  
-   <span data-ttu-id="ca9b1-130">La seconda parte di `String` è il nome completo dell'elemento, iniziando dalla radice dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="ca9b1-130">The second part of the `String` is the fully qualified name of the item, starting at the root of the namespace.</span></span> <span data-ttu-id="ca9b1-131">Il nome dell'elemento, il relativo tipo contenitore e lo spazio dei nomi sono separati da punti.</span><span class="sxs-lookup"><span data-stu-id="ca9b1-131">The name of the item, its enclosing type(s), and the namespace are separated by periods.</span></span> <span data-ttu-id="ca9b1-132">Se il nome dell'elemento stesso contiene punti, vengono sostituiti con il simbolo di cancelletto (#).</span><span class="sxs-lookup"><span data-stu-id="ca9b1-132">If the name of the item itself contains periods, they are replaced by the number sign (#).</span></span> <span data-ttu-id="ca9b1-133">Si presuppone che nessun elemento è un simbolo di cancelletto direttamente nel relativo nome.</span><span class="sxs-lookup"><span data-stu-id="ca9b1-133">It is assumed that no item has a number sign directly in its name.</span></span> <span data-ttu-id="ca9b1-134">Ad esempio, il nome completo di `String` costruttore sarebbe `System.String.#ctor`.</span><span class="sxs-lookup"><span data-stu-id="ca9b1-134">For example, the fully qualified name of the `String` constructor would be `System.String.#ctor`.</span></span>  
  
-   <span data-ttu-id="ca9b1-135">Per le proprietà e metodi, se sono presenti argomenti del metodo, l'elenco di argomenti racchiuso tra parentesi.</span><span class="sxs-lookup"><span data-stu-id="ca9b1-135">For properties and methods, if there are arguments to the method, the argument list enclosed in parentheses follows.</span></span> <span data-ttu-id="ca9b1-136">Se non sono presenti argomenti, le parentesi non sono presenti.</span><span class="sxs-lookup"><span data-stu-id="ca9b1-136">If there are no arguments, no parentheses are present.</span></span> <span data-ttu-id="ca9b1-137">Gli argomenti sono separati da virgole.</span><span class="sxs-lookup"><span data-stu-id="ca9b1-137">The arguments are separated by commas.</span></span> <span data-ttu-id="ca9b1-138">La codifica di ciascun argomento simile alla modalità di codifica un [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] firma.</span><span class="sxs-lookup"><span data-stu-id="ca9b1-138">The encoding of each argument follows directly how it is encoded in a [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] signature.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ca9b1-139">Esempio</span><span class="sxs-lookup"><span data-stu-id="ca9b1-139">Example</span></span>  
 <span data-ttu-id="ca9b1-140">Nel codice seguente viene illustrato come le stringhe di ID per una classe e i relativi membri vengono generati.</span><span class="sxs-lookup"><span data-stu-id="ca9b1-140">The following code shows how the ID strings for a class and its members are generated.</span></span>  
  
 <span data-ttu-id="ca9b1-141">[!code-vb[VbVbcnXmlDocComments&#10;](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/processing-the-xml-file_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="ca9b1-141">[!code-vb[VbVbcnXmlDocComments#10](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/processing-the-xml-file_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca9b1-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ca9b1-142">See Also</span></span>  
 <span data-ttu-id="ca9b1-143">[/doc](../../../visual-basic/reference/command-line-compiler/doc.md) </span><span class="sxs-lookup"><span data-stu-id="ca9b1-143">[/doc](../../../visual-basic/reference/command-line-compiler/doc.md) </span></span>  
<span data-ttu-id="ca9b1-144"> [Procedura: Creare documentazione XML](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)</span><span class="sxs-lookup"><span data-stu-id="ca9b1-144"> [How to: Create XML Documentation](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)</span></span>
