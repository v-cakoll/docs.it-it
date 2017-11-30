---
title: Operatore GetXmlNamespace (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.GetXmlNamespace
- GetXmlNamespace
helpviewer_keywords:
- GetXmlNamespace operator [Visual Basic]
- GetXmlNamespace keyword [Visual Basic]
ms.assetid: d0d28cfd-0755-4896-ae0b-4981aa35517c
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 47ba67bc58debf8f144f6468bf510932414c0698
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="getxmlnamespace-operator-visual-basic"></a><span data-ttu-id="56bdd-102">Operatore GetXmlNamespace (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="56bdd-102">GetXmlNamespace Operator (Visual Basic)</span></span>
<span data-ttu-id="56bdd-103">Ottiene il <xref:System.Xml.Linq.XNamespace> oggetto che corrisponde al prefisso dello spazio dei nomi XML specificato.</span><span class="sxs-lookup"><span data-stu-id="56bdd-103">Gets the <xref:System.Xml.Linq.XNamespace> object that corresponds to the specified XML namespace prefix.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="56bdd-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="56bdd-104">Syntax</span></span>  
  
```  
GetXmlNamespace(xmlNamespacePrefix)  
```  
  
## <a name="parts"></a><span data-ttu-id="56bdd-105">Parti</span><span class="sxs-lookup"><span data-stu-id="56bdd-105">Parts</span></span>  
 `xmlNamespacePrefix`  
 <span data-ttu-id="56bdd-106">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="56bdd-106">Optional.</span></span> <span data-ttu-id="56bdd-107">Stringa che identifica il prefisso dello spazio dei nomi XML.</span><span class="sxs-lookup"><span data-stu-id="56bdd-107">The string that identifies the XML namespace prefix.</span></span> <span data-ttu-id="56bdd-108">Se fornito, questa stringa deve essere un identificatore XML valido.</span><span class="sxs-lookup"><span data-stu-id="56bdd-108">If supplied, this string must be a valid XML identifier.</span></span> <span data-ttu-id="56bdd-109">Per ulteriori informazioni, vedere [attributi e i nomi di elementi XML dichiarati](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="56bdd-109">For more information, see [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span> <span data-ttu-id="56bdd-110">Se non viene specificato alcun prefisso, viene restituito lo spazio dei nomi predefinito.</span><span class="sxs-lookup"><span data-stu-id="56bdd-110">If no prefix is specified, the default namespace is returned.</span></span> <span data-ttu-id="56bdd-111">Se non viene specificato alcun spazio dei nomi predefinito, viene restituito lo spazio dei nomi vuoto.</span><span class="sxs-lookup"><span data-stu-id="56bdd-111">If no default namespace is specified, the empty namespace is returned.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="56bdd-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="56bdd-112">Return Value</span></span>  
 <span data-ttu-id="56bdd-113">Il <xref:System.Xml.Linq.XNamespace> oggetto che corrisponde al prefisso dello spazio dei nomi XML.</span><span class="sxs-lookup"><span data-stu-id="56bdd-113">The <xref:System.Xml.Linq.XNamespace> object that corresponds to the XML namespace prefix.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="56bdd-114">Note</span><span class="sxs-lookup"><span data-stu-id="56bdd-114">Remarks</span></span>  
 <span data-ttu-id="56bdd-115">Il `GetXmlNamespace` operatore ottiene il <xref:System.Xml.Linq.XNamespace> oggetto che corrisponde al prefisso dello spazio dei nomi XML `xmlNamespacePrefix`.</span><span class="sxs-lookup"><span data-stu-id="56bdd-115">The `GetXmlNamespace` operator gets the <xref:System.Xml.Linq.XNamespace> object that corresponds to the XML namespace prefix `xmlNamespacePrefix`.</span></span>  
  
 <span data-ttu-id="56bdd-116">È possibile utilizzare i prefissi di spazio dei nomi XML direttamente in valori letterali XML e proprietà axis XML.</span><span class="sxs-lookup"><span data-stu-id="56bdd-116">You can use XML namespace prefixes directly in XML literals and XML axis properties.</span></span> <span data-ttu-id="56bdd-117">Tuttavia, è necessario utilizzare il `GetXmlNamespace` per convertire un prefisso dello spazio dei nomi per un <xref:System.Xml.Linq.XNamespace> dell'oggetto prima che sia possibile utilizzarlo nel codice.</span><span class="sxs-lookup"><span data-stu-id="56bdd-117">However, you must use the `GetXmlNamespace` operator to convert a namespace prefix to an <xref:System.Xml.Linq.XNamespace> object before you can use it in your code.</span></span> <span data-ttu-id="56bdd-118">È possibile aggiungere un nome dell'elemento non qualificati da un <xref:System.Xml.Linq.XNamespace> oggetto da ottenere un nome completo <xref:System.Xml.Linq.XName> dell'oggetto, quale molti [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] metodi richiedono.</span><span class="sxs-lookup"><span data-stu-id="56bdd-118">You can append an unqualified element name to an <xref:System.Xml.Linq.XNamespace> object to get a fully qualified <xref:System.Xml.Linq.XName> object, which many [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] methods require.</span></span>  
  
## <a name="example"></a><span data-ttu-id="56bdd-119">Esempio</span><span class="sxs-lookup"><span data-stu-id="56bdd-119">Example</span></span>  
 <span data-ttu-id="56bdd-120">L'esempio seguente importa `ns` come un prefisso dello spazio dei nomi XML.</span><span class="sxs-lookup"><span data-stu-id="56bdd-120">The following example imports `ns` as an XML namespace prefix.</span></span> <span data-ttu-id="56bdd-121">Viene quindi utilizzato il prefisso dello spazio dei nomi per creare valori letterali XML e accedere al primo nodo figlio con il nome completo `ns:phone`.</span><span class="sxs-lookup"><span data-stu-id="56bdd-121">It then uses the prefix of the namespace to create an XML literal and access the first child node that has the qualified name `ns:phone`.</span></span> <span data-ttu-id="56bdd-122">Passa quindi tale nodo figlio per il `ShowName` subroutine, che costruisce un nome completo utilizzando il `GetXmlNamespace` operatore.</span><span class="sxs-lookup"><span data-stu-id="56bdd-122">It then passes that child node to the `ShowName` subroutine, which constructs a qualified name by using the `GetXmlNamespace` operator.</span></span> <span data-ttu-id="56bdd-123">Il `ShowName` subroutine passa quindi il nome completo per il <xref:System.Xml.Linq.XNode.Ancestors%2A> metodo per ottenere l'elemento padre `ns:contact` nodo.</span><span class="sxs-lookup"><span data-stu-id="56bdd-123">The `ShowName` subroutine then passes the qualified name to the <xref:System.Xml.Linq.XNode.Ancestors%2A> method to get the parent `ns:contact` node.</span></span>  
  
 [!code-vb[VbXMLSamples#38](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/getxmlnamespace-operator_1.vb)]  
  
 <span data-ttu-id="56bdd-124">Quando si chiama `TestGetXmlNamespace.RunSample()`, viene visualizzata una finestra di messaggio che contiene il testo seguente:</span><span class="sxs-lookup"><span data-stu-id="56bdd-124">When you call `TestGetXmlNamespace.RunSample()`, it displays a message box that contains the following text:</span></span>  
  
 `Name: Patrick Hines`  
  
## <a name="see-also"></a><span data-ttu-id="56bdd-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="56bdd-125">See Also</span></span>  
 [<span data-ttu-id="56bdd-126">Istruzione Imports (spazio dei nomi XML)</span><span class="sxs-lookup"><span data-stu-id="56bdd-126">Imports Statement (XML Namespace)</span></span>](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)  
 [<span data-ttu-id="56bdd-127">Accesso a XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="56bdd-127">Accessing XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)
