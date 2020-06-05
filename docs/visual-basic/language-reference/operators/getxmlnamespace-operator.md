---
title: Operatore GetXmlNamespace
ms.date: 07/20/2015
f1_keywords:
- vb.GetXmlNamespace
- GetXmlNamespace
helpviewer_keywords:
- GetXmlNamespace operator [Visual Basic]
- GetXmlNamespace keyword [Visual Basic]
ms.assetid: d0d28cfd-0755-4896-ae0b-4981aa35517c
ms.openlocfilehash: 85422fb9e11d78e228577adc25cba746149c645a
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84371116"
---
# <a name="getxmlnamespace-operator-visual-basic"></a><span data-ttu-id="2a9a7-102">Operatore GetXmlNamespace (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2a9a7-102">GetXmlNamespace Operator (Visual Basic)</span></span>
<span data-ttu-id="2a9a7-103">Ottiene l' <xref:System.Xml.Linq.XNamespace> oggetto che corrisponde al prefisso dello spazio dei nomi XML specificato.</span><span class="sxs-lookup"><span data-stu-id="2a9a7-103">Gets the <xref:System.Xml.Linq.XNamespace> object that corresponds to the specified XML namespace prefix.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a9a7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2a9a7-104">Syntax</span></span>  
  
```vb  
GetXmlNamespace(xmlNamespacePrefix)  
```  
  
## <a name="parts"></a><span data-ttu-id="2a9a7-105">Parti</span><span class="sxs-lookup"><span data-stu-id="2a9a7-105">Parts</span></span>  
 `xmlNamespacePrefix`  
 <span data-ttu-id="2a9a7-106">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="2a9a7-106">Optional.</span></span> <span data-ttu-id="2a9a7-107">Stringa che identifica il prefisso dello spazio dei nomi XML.</span><span class="sxs-lookup"><span data-stu-id="2a9a7-107">The string that identifies the XML namespace prefix.</span></span> <span data-ttu-id="2a9a7-108">Se specificato, la stringa deve essere un identificatore XML valido.</span><span class="sxs-lookup"><span data-stu-id="2a9a7-108">If supplied, this string must be a valid XML identifier.</span></span> <span data-ttu-id="2a9a7-109">Per ulteriori informazioni, vedere [nomi di elementi e attributi XML dichiarati](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="2a9a7-109">For more information, see [Names of Declared XML Elements and Attributes](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span> <span data-ttu-id="2a9a7-110">Se non viene specificato alcun prefisso, viene restituito lo spazio dei nomi predefinito.</span><span class="sxs-lookup"><span data-stu-id="2a9a7-110">If no prefix is specified, the default namespace is returned.</span></span> <span data-ttu-id="2a9a7-111">Se non viene specificato alcuno spazio dei nomi predefinito, viene restituito lo spazio dei nomi vuoto.</span><span class="sxs-lookup"><span data-stu-id="2a9a7-111">If no default namespace is specified, the empty namespace is returned.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2a9a7-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="2a9a7-112">Return Value</span></span>  
 <span data-ttu-id="2a9a7-113"><xref:System.Xml.Linq.XNamespace>Oggetto che corrisponde al prefisso dello spazio dei nomi XML.</span><span class="sxs-lookup"><span data-stu-id="2a9a7-113">The <xref:System.Xml.Linq.XNamespace> object that corresponds to the XML namespace prefix.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2a9a7-114">Commenti</span><span class="sxs-lookup"><span data-stu-id="2a9a7-114">Remarks</span></span>  
 <span data-ttu-id="2a9a7-115">L' `GetXmlNamespace` operatore ottiene l' <xref:System.Xml.Linq.XNamespace> oggetto che corrisponde al prefisso dello spazio dei nomi XML `xmlNamespacePrefix` .</span><span class="sxs-lookup"><span data-stu-id="2a9a7-115">The `GetXmlNamespace` operator gets the <xref:System.Xml.Linq.XNamespace> object that corresponds to the XML namespace prefix `xmlNamespacePrefix`.</span></span>  
  
 <span data-ttu-id="2a9a7-116">È possibile utilizzare i prefissi degli spazi dei nomi XML direttamente nei valori letterali XML e nelle proprietà Axis XML.</span><span class="sxs-lookup"><span data-stu-id="2a9a7-116">You can use XML namespace prefixes directly in XML literals and XML axis properties.</span></span> <span data-ttu-id="2a9a7-117">Tuttavia, è necessario usare l' `GetXmlNamespace` operatore per convertire un prefisso dello spazio dei nomi in un <xref:System.Xml.Linq.XNamespace> oggetto prima di poterlo usare nel codice.</span><span class="sxs-lookup"><span data-stu-id="2a9a7-117">However, you must use the `GetXmlNamespace` operator to convert a namespace prefix to an <xref:System.Xml.Linq.XNamespace> object before you can use it in your code.</span></span> <span data-ttu-id="2a9a7-118">È possibile aggiungere un nome di elemento non qualificato a un <xref:System.Xml.Linq.XNamespace> oggetto per ottenere un <xref:System.Xml.Linq.XName> oggetto completo, che richiede molti [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] metodi.</span><span class="sxs-lookup"><span data-stu-id="2a9a7-118">You can append an unqualified element name to an <xref:System.Xml.Linq.XNamespace> object to get a fully qualified <xref:System.Xml.Linq.XName> object, which many [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] methods require.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2a9a7-119">Esempio</span><span class="sxs-lookup"><span data-stu-id="2a9a7-119">Example</span></span>  
 <span data-ttu-id="2a9a7-120">Nell'esempio seguente viene importato `ns` come prefisso dello spazio dei nomi XML.</span><span class="sxs-lookup"><span data-stu-id="2a9a7-120">The following example imports `ns` as an XML namespace prefix.</span></span> <span data-ttu-id="2a9a7-121">USA quindi il prefisso dello spazio dei nomi per creare un valore letterale XML e accedere al primo nodo figlio con il nome completo `ns:phone` .</span><span class="sxs-lookup"><span data-stu-id="2a9a7-121">It then uses the prefix of the namespace to create an XML literal and access the first child node that has the qualified name `ns:phone`.</span></span> <span data-ttu-id="2a9a7-122">Passa quindi quel nodo figlio alla `ShowName` subroutine, che costruisce un nome completo usando l' `GetXmlNamespace` operatore.</span><span class="sxs-lookup"><span data-stu-id="2a9a7-122">It then passes that child node to the `ShowName` subroutine, which constructs a qualified name by using the `GetXmlNamespace` operator.</span></span> <span data-ttu-id="2a9a7-123">La `ShowName` subroutine passa quindi il nome completo al <xref:System.Xml.Linq.XNode.Ancestors%2A> metodo per ottenere il `ns:contact` nodo padre.</span><span class="sxs-lookup"><span data-stu-id="2a9a7-123">The `ShowName` subroutine then passes the qualified name to the <xref:System.Xml.Linq.XNode.Ancestors%2A> method to get the parent `ns:contact` node.</span></span>  
  
 [!code-vb[VbXMLSamples#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/GetXmlNamespace.vb#38)]  
  
 <span data-ttu-id="2a9a7-124">Quando si chiama `TestGetXmlNamespace.RunSample()` , viene visualizzata una finestra di messaggio contenente il testo seguente:</span><span class="sxs-lookup"><span data-stu-id="2a9a7-124">When you call `TestGetXmlNamespace.RunSample()`, it displays a message box that contains the following text:</span></span>  
  
 `Name: Patrick Hines`  
  
## <a name="see-also"></a><span data-ttu-id="2a9a7-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2a9a7-125">See also</span></span>

- [<span data-ttu-id="2a9a7-126">Istruzione Imports (spazio dei nomi XML)</span><span class="sxs-lookup"><span data-stu-id="2a9a7-126">Imports Statement (XML Namespace)</span></span>](../statements/imports-statement-xml-namespace.md)
- [<span data-ttu-id="2a9a7-127">Accesso a XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2a9a7-127">Accessing XML in Visual Basic</span></span>](../../programming-guide/language-features/xml/accessing-xml.md)
