---
title: XML Child Axis Property
ms.date: 07/20/2015
f1_keywords:
- vb.XmlPropertyChildAxis
helpviewer_keywords:
- Visual Basic code, accessing XML
- XML axis [Visual Basic], child
- child axis property [Visual Basic]
- XML child axis property [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: 89a59d00-985e-4f5c-b59f-29b47bad11cb
ms.openlocfilehash: 90dc22d12be5566fa1ee40f6b0e48eff8088e67b
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400266"
---
# <a name="xml-child-axis-property-visual-basic"></a><span data-ttu-id="6970b-102">Proprietà Child Axis XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6970b-102">XML Child Axis Property (Visual Basic)</span></span>
<span data-ttu-id="6970b-103">Fornisce l'accesso agli elementi figlio di uno dei seguenti oggetti: <xref:System.Xml.Linq.XElement>, <xref:System.Xml.Linq.XDocument>, raccolta di <xref:System.Xml.Linq.XElement> o raccolta di <xref:System.Xml.Linq.XDocument>.</span><span class="sxs-lookup"><span data-stu-id="6970b-103">Provides access to the children of one of the following: an <xref:System.Xml.Linq.XElement> object, an <xref:System.Xml.Linq.XDocument> object, a collection of <xref:System.Xml.Linq.XElement> objects, or a collection of <xref:System.Xml.Linq.XDocument> objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6970b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6970b-104">Syntax</span></span>  
  
```vb  
object.<child>  
```  
  
## <a name="parts"></a><span data-ttu-id="6970b-105">Parti</span><span class="sxs-lookup"><span data-stu-id="6970b-105">Parts</span></span>  
  
|<span data-ttu-id="6970b-106">Termine</span><span class="sxs-lookup"><span data-stu-id="6970b-106">Term</span></span>|<span data-ttu-id="6970b-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="6970b-107">Definition</span></span>|  
|---|---|  
|`object`|<span data-ttu-id="6970b-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="6970b-108">Required.</span></span> <span data-ttu-id="6970b-109">Un oggetto <xref:System.Xml.Linq.XElement>, un oggetto <xref:System.Xml.Linq.XDocument>, una raccolta di oggetti <xref:System.Xml.Linq.XElement> o una raccolta di oggetti <xref:System.Xml.Linq.XDocument>.</span><span class="sxs-lookup"><span data-stu-id="6970b-109">An <xref:System.Xml.Linq.XElement> object, an <xref:System.Xml.Linq.XDocument> object, a collection of <xref:System.Xml.Linq.XElement> objects, or a collection of <xref:System.Xml.Linq.XDocument> objects.</span></span>|  
|<span data-ttu-id="6970b-110">. <</span><span class="sxs-lookup"><span data-stu-id="6970b-110">.<</span></span>|<span data-ttu-id="6970b-111">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="6970b-111">Required.</span></span> <span data-ttu-id="6970b-112">Indica l'inizio di una proprietà axis dell'elemento figlio.</span><span class="sxs-lookup"><span data-stu-id="6970b-112">Denotes the start of a child axis property.</span></span>|  
|`child`|<span data-ttu-id="6970b-113">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="6970b-113">Required.</span></span> <span data-ttu-id="6970b-114">Nome dei nodi figlio a cui accedere, nel formato `[prefix:]name` .</span><span class="sxs-lookup"><span data-stu-id="6970b-114">Name of the child nodes to access, of the form `[prefix:]name`.</span></span><br /><br /> <span data-ttu-id="6970b-115">-   `Prefix`Opzionale.</span><span class="sxs-lookup"><span data-stu-id="6970b-115">-   `Prefix` - Optional.</span></span> <span data-ttu-id="6970b-116">Prefisso dello spazio dei nomi XML per il nodo figlio.</span><span class="sxs-lookup"><span data-stu-id="6970b-116">XML namespace prefix for the child node.</span></span> <span data-ttu-id="6970b-117">Deve essere uno spazio dei nomi XML globale definito usando un'istruzione `Imports`.</span><span class="sxs-lookup"><span data-stu-id="6970b-117">Must be a global XML namespace defined with an `Imports` statement.</span></span><br /><span data-ttu-id="6970b-118">-   `Name`Necessaria.</span><span class="sxs-lookup"><span data-stu-id="6970b-118">-   `Name` - Required.</span></span> <span data-ttu-id="6970b-119">Nome del nodo figlio locale.</span><span class="sxs-lookup"><span data-stu-id="6970b-119">Local child node name.</span></span> <span data-ttu-id="6970b-120">Vedere [nomi di elementi e attributi XML dichiarati](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="6970b-120">See [Names of Declared XML Elements and Attributes](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span>|  
|>|<span data-ttu-id="6970b-121">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="6970b-121">Required.</span></span> <span data-ttu-id="6970b-122">Indica la fine di una proprietà axis dell'elemento figlio.</span><span class="sxs-lookup"><span data-stu-id="6970b-122">Denotes the end of a child axis property.</span></span>|  
  
## <a name="return-value"></a><span data-ttu-id="6970b-123">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="6970b-123">Return Value</span></span>  
 <span data-ttu-id="6970b-124">Una raccolta di oggetti <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="6970b-124">A collection of <xref:System.Xml.Linq.XElement> objects.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6970b-125">Commenti</span><span class="sxs-lookup"><span data-stu-id="6970b-125">Remarks</span></span>  
 <span data-ttu-id="6970b-126">È possibile usare una proprietà axis dell'elemento figlio XML per accedere a nodi figlio in base al nome, da un oggetto <xref:System.Xml.Linq.XElement> o <xref:System.Xml.Linq.XDocument> o da raccolte di oggetti <xref:System.Xml.Linq.XElement> o <xref:System.Xml.Linq.XDocument>.</span><span class="sxs-lookup"><span data-stu-id="6970b-126">You can use an XML child axis property to access child nodes by name from an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> object, or from a collection of <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> objects.</span></span> <span data-ttu-id="6970b-127">Usare la proprietà `Value` XML per accedere al valore del primo nodo figlio nella raccolta restituita.</span><span class="sxs-lookup"><span data-stu-id="6970b-127">Use the XML `Value` property to access the value of the first child node in the returned collection.</span></span> <span data-ttu-id="6970b-128">Per ulteriori informazioni, vedere [proprietà del valore XML](xml-value-property.md).</span><span class="sxs-lookup"><span data-stu-id="6970b-128">For more information, see [XML Value Property](xml-value-property.md).</span></span>  
  
 <span data-ttu-id="6970b-129">Il compilatore Visual Basic converte le proprietà dell'asse figlio in chiamate al <xref:System.Xml.Linq.XContainer.Elements%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="6970b-129">The Visual Basic compiler converts child axis properties to calls to the <xref:System.Xml.Linq.XContainer.Elements%2A> method.</span></span>  
  
## <a name="xml-namespaces"></a><span data-ttu-id="6970b-130">Spazi dei nomi XML</span><span class="sxs-lookup"><span data-stu-id="6970b-130">XML Namespaces</span></span>  
 <span data-ttu-id="6970b-131">Il nome in una proprietà axis dell'elemento figlio può usare solo prefissi degli spazi dei nomi XML dichiarati globalmente con l'istruzione `Imports`.</span><span class="sxs-lookup"><span data-stu-id="6970b-131">The name in a child axis property can use only XML namespace prefixes declared globally with the `Imports` statement.</span></span> <span data-ttu-id="6970b-132">Non può usare prefissi degli spazi dei nomi XML dichiarati localmente all'interno di valori letterali dell'elemento XML.</span><span class="sxs-lookup"><span data-stu-id="6970b-132">It cannot use XML namespace prefixes declared locally within XML element literals.</span></span> <span data-ttu-id="6970b-133">Per altre informazioni, vedere [istruzione Imports (spazio dei nomi XML)](../statements/imports-statement-xml-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="6970b-133">For more information, see [Imports Statement (XML Namespace)](../statements/imports-statement-xml-namespace.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6970b-134">Esempio</span><span class="sxs-lookup"><span data-stu-id="6970b-134">Example</span></span>  
 <span data-ttu-id="6970b-135">L'esempio seguente illustra come accedere ai nodi figlio denominati `phone` dall'oggetto `contact`.</span><span class="sxs-lookup"><span data-stu-id="6970b-135">The following example shows how to access the child nodes named `phone` from the `contact` object.</span></span>  
  
 [!code-vb[VbXMLSamples#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples7.vb#17)]  
  
 <span data-ttu-id="6970b-136">Questo codice visualizza il testo seguente:</span><span class="sxs-lookup"><span data-stu-id="6970b-136">This code displays the following text:</span></span>  
  
 `Home Phone = 206-555-0144`  
  
## <a name="example"></a><span data-ttu-id="6970b-137">Esempio</span><span class="sxs-lookup"><span data-stu-id="6970b-137">Example</span></span>  
 <span data-ttu-id="6970b-138">L'esempio seguente illustra come accedere ai nodi figlio denominati `phone` dalla raccolta restituita dalla proprietà axis dell'elemento figlio `contact` dell'oggetto `contacts`.</span><span class="sxs-lookup"><span data-stu-id="6970b-138">The following example shows how to access the child nodes named `phone` from the collection returned by the `contact` child axis property of the `contacts` object.</span></span>  
  
 [!code-vb[VbXMLSamples#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples7.vb#18)]  
  
 <span data-ttu-id="6970b-139">Questo codice visualizza il testo seguente:</span><span class="sxs-lookup"><span data-stu-id="6970b-139">This code displays the following text:</span></span>  
  
 `Home Phone = 206-555-0144`  
  
## <a name="example"></a><span data-ttu-id="6970b-140">Esempio</span><span class="sxs-lookup"><span data-stu-id="6970b-140">Example</span></span>  
 <span data-ttu-id="6970b-141">Nell'esempio seguente viene dichiarato `ns` come un prefisso dello spazio dei nomi XML.</span><span class="sxs-lookup"><span data-stu-id="6970b-141">The following example declares `ns` as an XML namespace prefix.</span></span> <span data-ttu-id="6970b-142">Il prefisso dello spazio dei nomi viene quindi usato per creare un valore letterale XML e accedere al primo nodo figlio con il nome completo `ns:name`.</span><span class="sxs-lookup"><span data-stu-id="6970b-142">It then uses the prefix of the namespace to create an XML literal and access the first child node with the qualified name `ns:name`.</span></span>  
  
 [!code-vb[VbXMLSamples#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples8.vb#19)]  
  
 <span data-ttu-id="6970b-143">Questo codice visualizza il testo seguente:</span><span class="sxs-lookup"><span data-stu-id="6970b-143">This code displays the following text:</span></span>  
  
 `Patrick Hines`  
  
## <a name="see-also"></a><span data-ttu-id="6970b-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6970b-144">See also</span></span>

- <xref:System.Xml.Linq.XElement>
- [<span data-ttu-id="6970b-145">Proprietà Axis XML</span><span class="sxs-lookup"><span data-stu-id="6970b-145">XML Axis Properties</span></span>](index.md)
- [<span data-ttu-id="6970b-146">Valori letterali XML</span><span class="sxs-lookup"><span data-stu-id="6970b-146">XML Literals</span></span>](../xml-literals/index.md)
- [<span data-ttu-id="6970b-147">Creazione di XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6970b-147">Creating XML in Visual Basic</span></span>](../../programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="6970b-148">Nomi di elementi e attributi XML dichiarati</span><span class="sxs-lookup"><span data-stu-id="6970b-148">Names of Declared XML Elements and Attributes</span></span>](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
