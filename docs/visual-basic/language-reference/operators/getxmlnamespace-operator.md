---
title: Operatore GetXmlNamespace (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.GetXmlNamespace
- GetXmlNamespace
helpviewer_keywords:
- GetXmlNamespace operator [Visual Basic]
- GetXmlNamespace keyword [Visual Basic]
ms.assetid: d0d28cfd-0755-4896-ae0b-4981aa35517c
ms.openlocfilehash: bfccdcd9b5d35418b206dfa9fefffb5ddab69c66
ms.sourcegitcommit: 35da8fb45b4cca4e59cc99a5c56262c356977159
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/28/2019
ms.locfileid: "71592160"
---
# <a name="getxmlnamespace-operator-visual-basic"></a><span data-ttu-id="7738b-102">Operatore GetXmlNamespace (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7738b-102">GetXmlNamespace Operator (Visual Basic)</span></span>
<span data-ttu-id="7738b-103">Ottiene l'oggetto <xref:System.Xml.Linq.XNamespace> che corrisponde al prefisso dello spazio dei nomi XML specificato.</span><span class="sxs-lookup"><span data-stu-id="7738b-103">Gets the <xref:System.Xml.Linq.XNamespace> object that corresponds to the specified XML namespace prefix.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7738b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7738b-104">Syntax</span></span>  
  
```vb  
GetXmlNamespace(xmlNamespacePrefix)  
```  
  
## <a name="parts"></a><span data-ttu-id="7738b-105">Parti</span><span class="sxs-lookup"><span data-stu-id="7738b-105">Parts</span></span>  
 `xmlNamespacePrefix`  
 <span data-ttu-id="7738b-106">facoltativo.</span><span class="sxs-lookup"><span data-stu-id="7738b-106">Optional.</span></span> <span data-ttu-id="7738b-107">Stringa che identifica il prefisso dello spazio dei nomi XML.</span><span class="sxs-lookup"><span data-stu-id="7738b-107">The string that identifies the XML namespace prefix.</span></span> <span data-ttu-id="7738b-108">Se specificato, la stringa deve essere un identificatore XML valido.</span><span class="sxs-lookup"><span data-stu-id="7738b-108">If supplied, this string must be a valid XML identifier.</span></span> <span data-ttu-id="7738b-109">Per ulteriori informazioni, vedere [nomi di elementi e attributi XML dichiarati](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="7738b-109">For more information, see [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span> <span data-ttu-id="7738b-110">Se non viene specificato alcun prefisso, viene restituito lo spazio dei nomi predefinito.</span><span class="sxs-lookup"><span data-stu-id="7738b-110">If no prefix is specified, the default namespace is returned.</span></span> <span data-ttu-id="7738b-111">Se non viene specificato alcuno spazio dei nomi predefinito, viene restituito lo spazio dei nomi vuoto.</span><span class="sxs-lookup"><span data-stu-id="7738b-111">If no default namespace is specified, the empty namespace is returned.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7738b-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="7738b-112">Return Value</span></span>  
 <span data-ttu-id="7738b-113">Oggetto <xref:System.Xml.Linq.XNamespace> che corrisponde al prefisso dello spazio dei nomi XML.</span><span class="sxs-lookup"><span data-stu-id="7738b-113">The <xref:System.Xml.Linq.XNamespace> object that corresponds to the XML namespace prefix.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7738b-114">Note</span><span class="sxs-lookup"><span data-stu-id="7738b-114">Remarks</span></span>  
 <span data-ttu-id="7738b-115">L'operatore `GetXmlNamespace` Ottiene l'oggetto <xref:System.Xml.Linq.XNamespace> che corrisponde al prefisso dello spazio dei nomi XML `xmlNamespacePrefix`.</span><span class="sxs-lookup"><span data-stu-id="7738b-115">The `GetXmlNamespace` operator gets the <xref:System.Xml.Linq.XNamespace> object that corresponds to the XML namespace prefix `xmlNamespacePrefix`.</span></span>  
  
 <span data-ttu-id="7738b-116">È possibile utilizzare i prefissi degli spazi dei nomi XML direttamente nei valori letterali XML e nelle proprietà Axis XML.</span><span class="sxs-lookup"><span data-stu-id="7738b-116">You can use XML namespace prefixes directly in XML literals and XML axis properties.</span></span> <span data-ttu-id="7738b-117">Tuttavia, è necessario usare l'operatore `GetXmlNamespace` per convertire un prefisso dello spazio dei nomi in un oggetto <xref:System.Xml.Linq.XNamespace> prima di poterlo usare nel codice.</span><span class="sxs-lookup"><span data-stu-id="7738b-117">However, you must use the `GetXmlNamespace` operator to convert a namespace prefix to an <xref:System.Xml.Linq.XNamespace> object before you can use it in your code.</span></span> <span data-ttu-id="7738b-118">È possibile aggiungere un nome di elemento non qualificato a un oggetto <xref:System.Xml.Linq.XNamespace> per ottenere un oggetto <xref:System.Xml.Linq.XName> completo, che richiede molti metodi [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7738b-118">You can append an unqualified element name to an <xref:System.Xml.Linq.XNamespace> object to get a fully qualified <xref:System.Xml.Linq.XName> object, which many [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] methods require.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7738b-119">Esempio</span><span class="sxs-lookup"><span data-stu-id="7738b-119">Example</span></span>  
 <span data-ttu-id="7738b-120">Nell'esempio seguente viene importato `ns` come prefisso dello spazio dei nomi XML.</span><span class="sxs-lookup"><span data-stu-id="7738b-120">The following example imports `ns` as an XML namespace prefix.</span></span> <span data-ttu-id="7738b-121">USA quindi il prefisso dello spazio dei nomi per creare un valore letterale XML e accedere al primo nodo figlio con il nome completo `ns:phone`.</span><span class="sxs-lookup"><span data-stu-id="7738b-121">It then uses the prefix of the namespace to create an XML literal and access the first child node that has the qualified name `ns:phone`.</span></span> <span data-ttu-id="7738b-122">Passa quindi quel nodo figlio alla subroutine `ShowName`, che costruisce un nome completo usando l'operatore `GetXmlNamespace`.</span><span class="sxs-lookup"><span data-stu-id="7738b-122">It then passes that child node to the `ShowName` subroutine, which constructs a qualified name by using the `GetXmlNamespace` operator.</span></span> <span data-ttu-id="7738b-123">La subroutine `ShowName` passa quindi il nome completo al metodo <xref:System.Xml.Linq.XNode.Ancestors%2A> per ottenere il nodo padre `ns:contact`.</span><span class="sxs-lookup"><span data-stu-id="7738b-123">The `ShowName` subroutine then passes the qualified name to the <xref:System.Xml.Linq.XNode.Ancestors%2A> method to get the parent `ns:contact` node.</span></span>  
  
 [!code-vb[VbXMLSamples#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/GetXmlNamespace.vb#38)]  
  
 <span data-ttu-id="7738b-124">Quando si chiama `TestGetXmlNamespace.RunSample()`, viene visualizzata una finestra di messaggio contenente il testo seguente:</span><span class="sxs-lookup"><span data-stu-id="7738b-124">When you call `TestGetXmlNamespace.RunSample()`, it displays a message box that contains the following text:</span></span>  
  
 `Name: Patrick Hines`  
  
## <a name="see-also"></a><span data-ttu-id="7738b-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7738b-125">See also</span></span>

- [<span data-ttu-id="7738b-126">Istruzione Imports (spazio dei nomi XML)</span><span class="sxs-lookup"><span data-stu-id="7738b-126">Imports Statement (XML Namespace)</span></span>](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)
- [<span data-ttu-id="7738b-127">Accesso a XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7738b-127">Accessing XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)
