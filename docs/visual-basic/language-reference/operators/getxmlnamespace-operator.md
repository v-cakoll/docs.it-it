---
title: Operatore GetXmlNamespace (Visual Basic) | Documenti di Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.GetXmlNamespace
- GetXmlNamespace
dev_langs:
- VB
helpviewer_keywords:
- GetXmlNamespace operator
- GetXmlNamespace keyword
ms.assetid: d0d28cfd-0755-4896-ae0b-4981aa35517c
caps.latest.revision: 14
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
ms.openlocfilehash: d6f977ab8c0b7dfb2dee936436ef4ec8530ba8f6
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="getxmlnamespace-operator-visual-basic"></a><span data-ttu-id="d2ab8-102">Operatore GetXmlNamespace (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d2ab8-102">GetXmlNamespace Operator (Visual Basic)</span></span>
<span data-ttu-id="d2ab8-103">Ottiene il <xref:System.Xml.Linq.XNamespace>oggetto che corrisponde al prefisso dello spazio dei nomi XML specificato.</xref:System.Xml.Linq.XNamespace></span><span class="sxs-lookup"><span data-stu-id="d2ab8-103">Gets the <xref:System.Xml.Linq.XNamespace> object that corresponds to the specified XML namespace prefix.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2ab8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d2ab8-104">Syntax</span></span>  
  
```  
GetXmlNamespace(xmlNamespacePrefix)  
```  
  
## <a name="parts"></a><span data-ttu-id="d2ab8-105">Parti</span><span class="sxs-lookup"><span data-stu-id="d2ab8-105">Parts</span></span>  
 `xmlNamespacePrefix`  
 <span data-ttu-id="d2ab8-106">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="d2ab8-106">Optional.</span></span> <span data-ttu-id="d2ab8-107">Stringa che identifica il prefisso dello spazio dei nomi XML.</span><span class="sxs-lookup"><span data-stu-id="d2ab8-107">The string that identifies the XML namespace prefix.</span></span> <span data-ttu-id="d2ab8-108">Se fornito, questa stringa deve essere un identificatore XML valido.</span><span class="sxs-lookup"><span data-stu-id="d2ab8-108">If supplied, this string must be a valid XML identifier.</span></span> <span data-ttu-id="d2ab8-109">Per ulteriori informazioni, vedere [attributi e i nomi di elementi XML dichiarato](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="d2ab8-109">For more information, see [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span> <span data-ttu-id="d2ab8-110">Se non viene specificato alcun prefisso, viene restituito lo spazio dei nomi predefinito.</span><span class="sxs-lookup"><span data-stu-id="d2ab8-110">If no prefix is specified, the default namespace is returned.</span></span> <span data-ttu-id="d2ab8-111">Se viene specificato nessuno spazio dei nomi predefinito, viene restituito lo spazio dei nomi vuoto.</span><span class="sxs-lookup"><span data-stu-id="d2ab8-111">If no default namespace is specified, the empty namespace is returned.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d2ab8-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="d2ab8-112">Return Value</span></span>  
 <span data-ttu-id="d2ab8-113">Il <xref:System.Xml.Linq.XNamespace>oggetto che corrisponde al prefisso dello spazio dei nomi XML.</xref:System.Xml.Linq.XNamespace></span><span class="sxs-lookup"><span data-stu-id="d2ab8-113">The <xref:System.Xml.Linq.XNamespace> object that corresponds to the XML namespace prefix.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d2ab8-114">Note</span><span class="sxs-lookup"><span data-stu-id="d2ab8-114">Remarks</span></span>  
 <span data-ttu-id="d2ab8-115">Il `GetXmlNamespace` operatore ottiene il <xref:System.Xml.Linq.XNamespace>oggetto che corrisponde al prefisso dello spazio dei nomi XML `xmlNamespacePrefix`.</xref:System.Xml.Linq.XNamespace></span><span class="sxs-lookup"><span data-stu-id="d2ab8-115">The `GetXmlNamespace` operator gets the <xref:System.Xml.Linq.XNamespace> object that corresponds to the XML namespace prefix `xmlNamespacePrefix`.</span></span>  
  
 <span data-ttu-id="d2ab8-116">È possibile utilizzare i prefissi dello spazio dei nomi XML direttamente in valori letterali XML e le proprietà axis XML.</span><span class="sxs-lookup"><span data-stu-id="d2ab8-116">You can use XML namespace prefixes directly in XML literals and XML axis properties.</span></span> <span data-ttu-id="d2ab8-117">Tuttavia, è necessario utilizzare il `GetXmlNamespace` per convertire un prefisso dello spazio dei nomi a un <xref:System.Xml.Linq.XNamespace>dell'oggetto prima che sia possibile utilizzarlo nel codice.</xref:System.Xml.Linq.XNamespace></span><span class="sxs-lookup"><span data-stu-id="d2ab8-117">However, you must use the `GetXmlNamespace` operator to convert a namespace prefix to an <xref:System.Xml.Linq.XNamespace> object before you can use it in your code.</span></span> <span data-ttu-id="d2ab8-118">È possibile aggiungere un nome di elemento non qualificato di un <xref:System.Xml.Linq.XNamespace>oggetto da ottenere un nome completo <xref:System.Xml.Linq.XName>dell'oggetto, quale molti [!INCLUDE[sqltecxlinq](../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] metodi richiedono.</xref:System.Xml.Linq.XName> </xref:System.Xml.Linq.XNamespace></span><span class="sxs-lookup"><span data-stu-id="d2ab8-118">You can append an unqualified element name to an <xref:System.Xml.Linq.XNamespace> object to get a fully qualified <xref:System.Xml.Linq.XName> object, which many [!INCLUDE[sqltecxlinq](../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] methods require.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d2ab8-119">Esempio</span><span class="sxs-lookup"><span data-stu-id="d2ab8-119">Example</span></span>  
 <span data-ttu-id="d2ab8-120">L'esempio seguente importa `ns` come un prefisso dello spazio dei nomi XML.</span><span class="sxs-lookup"><span data-stu-id="d2ab8-120">The following example imports `ns` as an XML namespace prefix.</span></span> <span data-ttu-id="d2ab8-121">Viene quindi utilizzato il prefisso dello spazio dei nomi per creare valori letterali XML e accedere al primo nodo figlio con il nome completo `ns:phone`.</span><span class="sxs-lookup"><span data-stu-id="d2ab8-121">It then uses the prefix of the namespace to create an XML literal and access the first child node that has the qualified name `ns:phone`.</span></span> <span data-ttu-id="d2ab8-122">Viene quindi passato come nodo figlio per il `ShowName` subroutine, che costruisce un nome completo utilizzando il `GetXmlNamespace` operatore.</span><span class="sxs-lookup"><span data-stu-id="d2ab8-122">It then passes that child node to the `ShowName` subroutine, which constructs a qualified name by using the `GetXmlNamespace` operator.</span></span> <span data-ttu-id="d2ab8-123">Il `ShowName` subroutine passa quindi il nome completo per il <xref:System.Xml.Linq.XNode.Ancestors%2A>per ottenere l'elemento padre `ns:contact` nodo.</xref:System.Xml.Linq.XNode.Ancestors%2A></span><span class="sxs-lookup"><span data-stu-id="d2ab8-123">The `ShowName` subroutine then passes the qualified name to the <xref:System.Xml.Linq.XNode.Ancestors%2A> method to get the parent `ns:contact` node.</span></span>  
  
 <span data-ttu-id="d2ab8-124">[!code-vb[VbXMLSamples&#38;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/getxmlnamespace-operator_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="d2ab8-124">[!code-vb[VbXMLSamples#38](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/getxmlnamespace-operator_1.vb)]</span></span>  
  
 <span data-ttu-id="d2ab8-125">Quando si chiama `TestGetXmlNamespace.RunSample()`, viene visualizzata una finestra di messaggio che contiene il testo seguente:</span><span class="sxs-lookup"><span data-stu-id="d2ab8-125">When you call `TestGetXmlNamespace.RunSample()`, it displays a message box that contains the following text:</span></span>  
  
 `Name: Patrick Hines`  
  
## <a name="see-also"></a><span data-ttu-id="d2ab8-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d2ab8-126">See Also</span></span>  
 <span data-ttu-id="d2ab8-127">[Istruzione Imports (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md) </span><span class="sxs-lookup"><span data-stu-id="d2ab8-127">[Imports Statement (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md) </span></span>  
<span data-ttu-id="d2ab8-128"> [Accesso a XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)</span><span class="sxs-lookup"><span data-stu-id="d2ab8-128"> [Accessing XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)</span></span>
