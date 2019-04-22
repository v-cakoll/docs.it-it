---
title: Proprietà axis dell'attributo XML (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlPropertyAttributeAxis
helpviewer_keywords:
- attribute axis property [Visual Basic]
- Visual Basic code, accessing XML
- XML attribute axis property [Visual Basic]
- XML axis [Visual Basic], attribute
- XML [Visual Basic], accessing
ms.assetid: 7a4777e1-0618-4de9-9510-fb9ace2bf4db
ms.openlocfilehash: a7a93608d14bcbec316228b59467b23e9247e043
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58828806"
---
# <a name="xml-attribute-axis-property-visual-basic"></a><span data-ttu-id="483c4-102">Proprietà axis dell'attributo XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="483c4-102">XML Attribute Axis Property (Visual Basic)</span></span>
<span data-ttu-id="483c4-103">Fornisce l'accesso al valore di un attributo per un <xref:System.Xml.Linq.XElement> oggetto o al primo elemento in una raccolta di <xref:System.Xml.Linq.XElement> oggetti.</span><span class="sxs-lookup"><span data-stu-id="483c4-103">Provides access to the value of an attribute for an <xref:System.Xml.Linq.XElement> object or to the first element in a collection of <xref:System.Xml.Linq.XElement> objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="483c4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="483c4-104">Syntax</span></span>  
  
```  
      object.@attribute  
-or-  
object.@<attribute>  
```  
  
## <a name="parts"></a><span data-ttu-id="483c4-105">Parti</span><span class="sxs-lookup"><span data-stu-id="483c4-105">Parts</span></span>  
 `object`  
 <span data-ttu-id="483c4-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="483c4-106">Required.</span></span> <span data-ttu-id="483c4-107">Un' <xref:System.Xml.Linq.XElement> oggetto o una raccolta di <xref:System.Xml.Linq.XElement> oggetti.</span><span class="sxs-lookup"><span data-stu-id="483c4-107">An <xref:System.Xml.Linq.XElement> object or a collection of <xref:System.Xml.Linq.XElement> objects.</span></span>  
  
 <span data-ttu-id="483c4-108">.@</span><span class="sxs-lookup"><span data-stu-id="483c4-108">.@</span></span>  
 <span data-ttu-id="483c4-109">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="483c4-109">Required.</span></span> <span data-ttu-id="483c4-110">Indica l'inizio di una proprietà axis dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="483c4-110">Denotes the start of an attribute axis property.</span></span>  
  
 <  
 <span data-ttu-id="483c4-111">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="483c4-111">Optional.</span></span> <span data-ttu-id="483c4-112">Indica l'inizio del nome dell'attributo quando `attribute` non è un identificatore valido in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="483c4-112">Denotes the beginning of the name of the attribute when `attribute` is not a valid identifier in Visual Basic.</span></span>  
  
 `attribute`  
 <span data-ttu-id="483c4-113">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="483c4-113">Required.</span></span> <span data-ttu-id="483c4-114">Nome dell'attributo a cui accedere, nel formato [`prefix`:]`name`.</span><span class="sxs-lookup"><span data-stu-id="483c4-114">Name of the attribute to access, of the form [`prefix`:]`name`.</span></span>  
  
|<span data-ttu-id="483c4-115">Parte</span><span class="sxs-lookup"><span data-stu-id="483c4-115">Part</span></span>|<span data-ttu-id="483c4-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="483c4-116">Description</span></span>|  
|----------|-----------------|  
|`prefix`|<span data-ttu-id="483c4-117">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="483c4-117">Optional.</span></span> <span data-ttu-id="483c4-118">Prefisso dello spazio dei nomi XML per l'attributo.</span><span class="sxs-lookup"><span data-stu-id="483c4-118">XML namespace prefix for the attribute.</span></span> <span data-ttu-id="483c4-119">Deve essere uno spazio dei nomi XML globale definito usando un'istruzione `Imports`.</span><span class="sxs-lookup"><span data-stu-id="483c4-119">Must be a global XML namespace defined with an `Imports` statement.</span></span>|  
|`name`|<span data-ttu-id="483c4-120">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="483c4-120">Required.</span></span> <span data-ttu-id="483c4-121">Nome locale dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="483c4-121">Local attribute name.</span></span> <span data-ttu-id="483c4-122">Visualizzare [nomi degli elementi e attributi XML dichiarati](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="483c4-122">See [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span>|  
  
 \>  
 <span data-ttu-id="483c4-123">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="483c4-123">Optional.</span></span> <span data-ttu-id="483c4-124">Indica la fine del nome dell'attributo quando `attribute` non è un identificatore valido in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="483c4-124">Denotes the end of the name of the attribute when `attribute` is not a valid identifier in Visual Basic.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="483c4-125">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="483c4-125">Return Value</span></span>  
 <span data-ttu-id="483c4-126">Stringa che contiene il valore di `attribute`.</span><span class="sxs-lookup"><span data-stu-id="483c4-126">A string that contains the value of `attribute`.</span></span> <span data-ttu-id="483c4-127">Se il nome dell'attributo non esiste, `Nothing` viene restituito.</span><span class="sxs-lookup"><span data-stu-id="483c4-127">If the attribute name does not exist, `Nothing` is returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="483c4-128">Note</span><span class="sxs-lookup"><span data-stu-id="483c4-128">Remarks</span></span>  
 <span data-ttu-id="483c4-129">È possibile usare una proprietà asse attributo XML per accedere al valore di un attributo in base al nome da un <xref:System.Xml.Linq.XElement> oggetto o tra il primo elemento in una raccolta di <xref:System.Xml.Linq.XElement> oggetti.</span><span class="sxs-lookup"><span data-stu-id="483c4-129">You can use an XML attribute axis property to access the value of an attribute by name from an <xref:System.Xml.Linq.XElement> object or from the first element in a collection of <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="483c4-130">È possibile recuperare un valore di attributo in base al nome o aggiungere un nuovo attributo a un elemento specificando un nuovo nome preceduto dal @ identificatore.</span><span class="sxs-lookup"><span data-stu-id="483c4-130">You can retrieve an attribute value by name, or add a new attribute to an element by specifying a new name preceded by the @ identifier.</span></span>  
  
 <span data-ttu-id="483c4-131">Quando fa riferimento a un attributo XML con l'identificatore @, viene restituito il valore dell'attributo sotto forma di stringa e non è necessario specificare in modo esplicito il <xref:System.Xml.Linq.XAttribute.Value%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="483c4-131">When you refer to an XML attribute using the @ identifier, the attribute value is returned as a string and you do not need to explicitly specify the <xref:System.Xml.Linq.XAttribute.Value%2A> property.</span></span>  
  
 <span data-ttu-id="483c4-132">Le regole di denominazione per gli attributi XML differiscono dalle regole di denominazione per gli identificatori di Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="483c4-132">The naming rules for XML attributes differ from the naming rules for Visual Basic identifiers.</span></span> <span data-ttu-id="483c4-133">Per accedere a un attributo XML che ha un nome che non è un valido identificatore Visual Basic, racchiuderlo tra parentesi angolari (\< e >).</span><span class="sxs-lookup"><span data-stu-id="483c4-133">To access an XML attribute that has a name that is not a valid Visual Basic identifier, enclose the name in angle brackets (\< and >).</span></span>  
  
## <a name="xml-namespaces"></a><span data-ttu-id="483c4-134">Spazi dei nomi XML</span><span class="sxs-lookup"><span data-stu-id="483c4-134">XML Namespaces</span></span>  
 <span data-ttu-id="483c4-135">Il nome di una proprietà axis dell'attributo può usare solo i prefissi dello spazio dei nomi XML dichiarati a livello globale usando il `Imports` istruzione.</span><span class="sxs-lookup"><span data-stu-id="483c4-135">The name in an attribute axis property can use only XML namespace prefixes declared globally by using the `Imports` statement.</span></span> <span data-ttu-id="483c4-136">Non può usare prefissi degli spazi dei nomi XML dichiarati localmente all'interno di valori letterali dell'elemento XML.</span><span class="sxs-lookup"><span data-stu-id="483c4-136">It cannot use XML namespace prefixes declared locally within XML element literals.</span></span> <span data-ttu-id="483c4-137">Per altre informazioni, vedere [istruzione Imports (Namespace XML)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="483c4-137">For more information, see [Imports Statement (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="483c4-138">Esempio</span><span class="sxs-lookup"><span data-stu-id="483c4-138">Example</span></span>  
 <span data-ttu-id="483c4-139">Nell'esempio seguente viene illustrato come ottenere i valori degli attributi XML denominati `type` da una raccolta di elementi XML che sono denominate `phone`.</span><span class="sxs-lookup"><span data-stu-id="483c4-139">The following example shows how to get the values of the XML attributes named `type` from a collection of XML elements that are named `phone`.</span></span>  
  
 [!code-vb[VbXMLSamples#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples5.vb#12)]  
  
 <span data-ttu-id="483c4-140">Questo codice visualizza il testo seguente:</span><span class="sxs-lookup"><span data-stu-id="483c4-140">This code displays the following text:</span></span>  
  
 `<phoneTypes>`  
  
 `<type>home</type>`  
  
 `<type>work</type>`  
  
 `</phoneTypes>`  
  
## <a name="example"></a><span data-ttu-id="483c4-141">Esempio</span><span class="sxs-lookup"><span data-stu-id="483c4-141">Example</span></span>  
 <span data-ttu-id="483c4-142">Nell'esempio seguente viene illustrato come creare in modo dichiarativo, come parte del codice XML e in modo dinamico mediante l'aggiunta di un attributo a un'istanza di attributi per un elemento XML sia un <xref:System.Xml.Linq.XElement> oggetto.</span><span class="sxs-lookup"><span data-stu-id="483c4-142">The following example shows how to create attributes for an XML element both declaratively, as part of the XML, and dynamically by adding an attribute to an instance of an <xref:System.Xml.Linq.XElement> object.</span></span> <span data-ttu-id="483c4-143">Il `type` l'attributo viene creato in modo dichiarativo e `owner` attributo viene creato dinamicamente.</span><span class="sxs-lookup"><span data-stu-id="483c4-143">The `type` attribute is created declaratively and the `owner` attribute is created dynamically.</span></span>  
  
 [!code-vb[VbXMLSamples#44](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples5.vb#44)]  
  
 <span data-ttu-id="483c4-144">Questo codice visualizza il testo seguente:</span><span class="sxs-lookup"><span data-stu-id="483c4-144">This code displays the following text:</span></span>  
  
```xml  
<phone type="home" owner="Harris, Phyllis">206-555-0144</phone>  
```  
  
## <a name="example"></a><span data-ttu-id="483c4-145">Esempio</span><span class="sxs-lookup"><span data-stu-id="483c4-145">Example</span></span>  
 <span data-ttu-id="483c4-146">L'esempio seguente usa la sintassi di parentesi uncinate per ottenere il valore dell'attributo XML denominato `number-type`, che non è un identificatore valido in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="483c4-146">The following example uses the angle bracket syntax to get the value of the XML attribute named `number-type`, which is not a valid identifier in Visual Basic.</span></span>  
  
 [!code-vb[VbXMLSamples#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples5.vb#13)]  
  
 <span data-ttu-id="483c4-147">Questo codice visualizza il testo seguente:</span><span class="sxs-lookup"><span data-stu-id="483c4-147">This code displays the following text:</span></span>  
  
 `Phone type: work`  
  
## <a name="example"></a><span data-ttu-id="483c4-148">Esempio</span><span class="sxs-lookup"><span data-stu-id="483c4-148">Example</span></span>  
 <span data-ttu-id="483c4-149">Nell'esempio seguente viene dichiarato `ns` come un prefisso dello spazio dei nomi XML.</span><span class="sxs-lookup"><span data-stu-id="483c4-149">The following example declares `ns` as an XML namespace prefix.</span></span> <span data-ttu-id="483c4-150">Il prefisso dello spazio dei nomi viene quindi utilizzato per creare un file XML letterale e accedere al primo nodo figlio con il nome completo "`ns:name`".</span><span class="sxs-lookup"><span data-stu-id="483c4-150">It then uses the prefix of the namespace to create an XML literal and access the first child node with the qualified name "`ns:name`".</span></span>  
  
 [!code-vb[VbXMLSamples#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples6.vb#14)]  
  
 <span data-ttu-id="483c4-151">Questo codice visualizza il testo seguente:</span><span class="sxs-lookup"><span data-stu-id="483c4-151">This code displays the following text:</span></span>  
  
 `Phone type: home`  
  
## <a name="see-also"></a><span data-ttu-id="483c4-152">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="483c4-152">See also</span></span>

- <xref:System.Xml.Linq.XElement>
- [<span data-ttu-id="483c4-153">Proprietà Axis XML</span><span class="sxs-lookup"><span data-stu-id="483c4-153">XML Axis Properties</span></span>](../../../visual-basic/language-reference/xml-axis/index.md)
- [<span data-ttu-id="483c4-154">Valori letterali XML</span><span class="sxs-lookup"><span data-stu-id="483c4-154">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="483c4-155">Creazione di XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="483c4-155">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="483c4-156">Nomi di elementi e attributi XML dichiarati</span><span class="sxs-lookup"><span data-stu-id="483c4-156">Names of Declared XML Elements and Attributes</span></span>](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
