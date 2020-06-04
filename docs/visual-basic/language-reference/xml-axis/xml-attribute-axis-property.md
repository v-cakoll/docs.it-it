---
title: XML Attribute Axis Property
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
ms.openlocfilehash: 3f60190a949856cb2bbc2eba09d097c09089bea7
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84408432"
---
# <a name="xml-attribute-axis-property-visual-basic"></a><span data-ttu-id="87dc8-102">Proprietà axis dell'attributo XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="87dc8-102">XML Attribute Axis Property (Visual Basic)</span></span>
<span data-ttu-id="87dc8-103">Fornisce l'accesso al valore di un attributo per un <xref:System.Xml.Linq.XElement> oggetto o al primo elemento in una raccolta di <xref:System.Xml.Linq.XElement> oggetti.</span><span class="sxs-lookup"><span data-stu-id="87dc8-103">Provides access to the value of an attribute for an <xref:System.Xml.Linq.XElement> object or to the first element in a collection of <xref:System.Xml.Linq.XElement> objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87dc8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="87dc8-104">Syntax</span></span>  
  
```vb  
object.@attribute  
' -or-  
object.@<attribute>  
```  
  
## <a name="parts"></a><span data-ttu-id="87dc8-105">Parti</span><span class="sxs-lookup"><span data-stu-id="87dc8-105">Parts</span></span>  
 `object`  
 <span data-ttu-id="87dc8-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="87dc8-106">Required.</span></span> <span data-ttu-id="87dc8-107">Un <xref:System.Xml.Linq.XElement> oggetto o una raccolta di <xref:System.Xml.Linq.XElement> oggetti.</span><span class="sxs-lookup"><span data-stu-id="87dc8-107">An <xref:System.Xml.Linq.XElement> object or a collection of <xref:System.Xml.Linq.XElement> objects.</span></span>  
  
 <span data-ttu-id="87dc8-108">.@</span><span class="sxs-lookup"><span data-stu-id="87dc8-108">.@</span></span>  
 <span data-ttu-id="87dc8-109">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="87dc8-109">Required.</span></span> <span data-ttu-id="87dc8-110">Indica l'inizio di una proprietà axis dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="87dc8-110">Denotes the start of an attribute axis property.</span></span>  
  
 <  
 <span data-ttu-id="87dc8-111">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="87dc8-111">Optional.</span></span> <span data-ttu-id="87dc8-112">Indica l'inizio del nome dell'attributo quando `attribute` non è un identificatore valido in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="87dc8-112">Denotes the beginning of the name of the attribute when `attribute` is not a valid identifier in Visual Basic.</span></span>  
  
 `attribute`  
 <span data-ttu-id="87dc8-113">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="87dc8-113">Required.</span></span> <span data-ttu-id="87dc8-114">Nome dell'attributo a cui accedere, nel formato [ `prefix` :] `name` .</span><span class="sxs-lookup"><span data-stu-id="87dc8-114">Name of the attribute to access, of the form [`prefix`:]`name`.</span></span>  
  
|<span data-ttu-id="87dc8-115">Parte</span><span class="sxs-lookup"><span data-stu-id="87dc8-115">Part</span></span>|<span data-ttu-id="87dc8-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="87dc8-116">Description</span></span>|  
|----------|-----------------|  
|`prefix`|<span data-ttu-id="87dc8-117">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="87dc8-117">Optional.</span></span> <span data-ttu-id="87dc8-118">Prefisso dello spazio dei nomi XML per l'attributo.</span><span class="sxs-lookup"><span data-stu-id="87dc8-118">XML namespace prefix for the attribute.</span></span> <span data-ttu-id="87dc8-119">Deve essere uno spazio dei nomi XML globale definito usando un'istruzione `Imports`.</span><span class="sxs-lookup"><span data-stu-id="87dc8-119">Must be a global XML namespace defined with an `Imports` statement.</span></span>|  
|`name`|<span data-ttu-id="87dc8-120">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="87dc8-120">Required.</span></span> <span data-ttu-id="87dc8-121">Nome dell'attributo locale.</span><span class="sxs-lookup"><span data-stu-id="87dc8-121">Local attribute name.</span></span> <span data-ttu-id="87dc8-122">Vedere [nomi di elementi e attributi XML dichiarati](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="87dc8-122">See [Names of Declared XML Elements and Attributes](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span>|  
  
 \>  
 <span data-ttu-id="87dc8-123">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="87dc8-123">Optional.</span></span> <span data-ttu-id="87dc8-124">Indica la fine del nome dell'attributo quando `attribute` non è un identificatore valido in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="87dc8-124">Denotes the end of the name of the attribute when `attribute` is not a valid identifier in Visual Basic.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="87dc8-125">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="87dc8-125">Return Value</span></span>  
 <span data-ttu-id="87dc8-126">Stringa che contiene il valore di `attribute` .</span><span class="sxs-lookup"><span data-stu-id="87dc8-126">A string that contains the value of `attribute`.</span></span> <span data-ttu-id="87dc8-127">Se il nome dell'attributo non esiste, `Nothing` viene restituito.</span><span class="sxs-lookup"><span data-stu-id="87dc8-127">If the attribute name does not exist, `Nothing` is returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="87dc8-128">Commenti</span><span class="sxs-lookup"><span data-stu-id="87dc8-128">Remarks</span></span>  
 <span data-ttu-id="87dc8-129">È possibile utilizzare una proprietà axis dell'attributo XML per accedere al valore di un attributo in base al nome da un <xref:System.Xml.Linq.XElement> oggetto o dal primo elemento di una raccolta di <xref:System.Xml.Linq.XElement> oggetti.</span><span class="sxs-lookup"><span data-stu-id="87dc8-129">You can use an XML attribute axis property to access the value of an attribute by name from an <xref:System.Xml.Linq.XElement> object or from the first element in a collection of <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="87dc8-130">È possibile recuperare un valore di attributo in base al nome o aggiungere un nuovo attributo a un elemento specificando un nuovo nome preceduto da @ Identifier.</span><span class="sxs-lookup"><span data-stu-id="87dc8-130">You can retrieve an attribute value by name, or add a new attribute to an element by specifying a new name preceded by the @ identifier.</span></span>  
  
 <span data-ttu-id="87dc8-131">Quando si fa riferimento a un attributo XML usando l'identificatore @, il valore dell'attributo viene restituito come stringa e non è necessario specificare in modo esplicito la <xref:System.Xml.Linq.XAttribute.Value%2A> Proprietà.</span><span class="sxs-lookup"><span data-stu-id="87dc8-131">When you refer to an XML attribute using the @ identifier, the attribute value is returned as a string and you do not need to explicitly specify the <xref:System.Xml.Linq.XAttribute.Value%2A> property.</span></span>  
  
 <span data-ttu-id="87dc8-132">Le regole di denominazione per gli attributi XML sono diverse dalle regole di denominazione per gli identificatori di Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="87dc8-132">The naming rules for XML attributes differ from the naming rules for Visual Basic identifiers.</span></span> <span data-ttu-id="87dc8-133">Per accedere a un attributo XML con un nome diverso da un identificatore di Visual Basic valido, racchiudere il nome tra parentesi acute ( \< and > ).</span><span class="sxs-lookup"><span data-stu-id="87dc8-133">To access an XML attribute that has a name that is not a valid Visual Basic identifier, enclose the name in angle brackets (\< and >).</span></span>  
  
## <a name="xml-namespaces"></a><span data-ttu-id="87dc8-134">Spazi dei nomi XML</span><span class="sxs-lookup"><span data-stu-id="87dc8-134">XML Namespaces</span></span>  
 <span data-ttu-id="87dc8-135">Il nome in una proprietà axis dell'attributo può utilizzare solo i prefissi degli spazi dei nomi XML dichiarati globalmente utilizzando l' `Imports` istruzione.</span><span class="sxs-lookup"><span data-stu-id="87dc8-135">The name in an attribute axis property can use only XML namespace prefixes declared globally by using the `Imports` statement.</span></span> <span data-ttu-id="87dc8-136">Non può usare prefissi degli spazi dei nomi XML dichiarati localmente all'interno di valori letterali dell'elemento XML.</span><span class="sxs-lookup"><span data-stu-id="87dc8-136">It cannot use XML namespace prefixes declared locally within XML element literals.</span></span> <span data-ttu-id="87dc8-137">Per altre informazioni, vedere [istruzione Imports (spazio dei nomi XML)](../statements/imports-statement-xml-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="87dc8-137">For more information, see [Imports Statement (XML Namespace)](../statements/imports-statement-xml-namespace.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="87dc8-138">Esempio</span><span class="sxs-lookup"><span data-stu-id="87dc8-138">Example</span></span>  
 <span data-ttu-id="87dc8-139">Nell'esempio seguente viene illustrato come ottenere i valori degli attributi XML denominati `type` da una raccolta di elementi XML denominati `phone` .</span><span class="sxs-lookup"><span data-stu-id="87dc8-139">The following example shows how to get the values of the XML attributes named `type` from a collection of XML elements that are named `phone`.</span></span>  
  
 [!code-vb[VbXMLSamples#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples5.vb#12)]  
  
 <span data-ttu-id="87dc8-140">Questo codice visualizza il testo seguente:</span><span class="sxs-lookup"><span data-stu-id="87dc8-140">This code displays the following text:</span></span>  
  
 `<phoneTypes>`  
  
 `<type>home</type>`  
  
 `<type>work</type>`  
  
 `</phoneTypes>`  
  
## <a name="example"></a><span data-ttu-id="87dc8-141">Esempio</span><span class="sxs-lookup"><span data-stu-id="87dc8-141">Example</span></span>  
 <span data-ttu-id="87dc8-142">Nell'esempio seguente viene illustrato come creare attributi per un elemento XML in modo dichiarativo, come parte del codice XML, e in modo dinamico aggiungendo un attributo a un'istanza di un <xref:System.Xml.Linq.XElement> oggetto.</span><span class="sxs-lookup"><span data-stu-id="87dc8-142">The following example shows how to create attributes for an XML element both declaratively, as part of the XML, and dynamically by adding an attribute to an instance of an <xref:System.Xml.Linq.XElement> object.</span></span> <span data-ttu-id="87dc8-143">L' `type` attributo viene creato in modo dichiarativo e l' `owner` attributo viene creato dinamicamente.</span><span class="sxs-lookup"><span data-stu-id="87dc8-143">The `type` attribute is created declaratively and the `owner` attribute is created dynamically.</span></span>  
  
 [!code-vb[VbXMLSamples#44](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples5.vb#44)]  
  
 <span data-ttu-id="87dc8-144">Questo codice visualizza il testo seguente:</span><span class="sxs-lookup"><span data-stu-id="87dc8-144">This code displays the following text:</span></span>  
  
```xml  
<phone type="home" owner="Harris, Phyllis">206-555-0144</phone>  
```  
  
## <a name="example"></a><span data-ttu-id="87dc8-145">Esempio</span><span class="sxs-lookup"><span data-stu-id="87dc8-145">Example</span></span>  
 <span data-ttu-id="87dc8-146">Nell'esempio seguente viene utilizzata la sintassi della parentesi angolare per ottenere il valore dell'attributo XML denominato `number-type` , che non è un identificatore valido in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="87dc8-146">The following example uses the angle bracket syntax to get the value of the XML attribute named `number-type`, which is not a valid identifier in Visual Basic.</span></span>  
  
 [!code-vb[VbXMLSamples#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples5.vb#13)]  
  
 <span data-ttu-id="87dc8-147">Questo codice visualizza il testo seguente:</span><span class="sxs-lookup"><span data-stu-id="87dc8-147">This code displays the following text:</span></span>  
  
 `Phone type: work`  
  
## <a name="example"></a><span data-ttu-id="87dc8-148">Esempio</span><span class="sxs-lookup"><span data-stu-id="87dc8-148">Example</span></span>  
 <span data-ttu-id="87dc8-149">Nell'esempio seguente viene dichiarato `ns` come un prefisso dello spazio dei nomi XML.</span><span class="sxs-lookup"><span data-stu-id="87dc8-149">The following example declares `ns` as an XML namespace prefix.</span></span> <span data-ttu-id="87dc8-150">USA quindi il prefisso dello spazio dei nomi per creare un valore letterale XML e accedere al primo nodo figlio con il nome completo " `ns:name` ".</span><span class="sxs-lookup"><span data-stu-id="87dc8-150">It then uses the prefix of the namespace to create an XML literal and access the first child node with the qualified name "`ns:name`".</span></span>  
  
 [!code-vb[VbXMLSamples#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples6.vb#14)]  
  
 <span data-ttu-id="87dc8-151">Questo codice visualizza il testo seguente:</span><span class="sxs-lookup"><span data-stu-id="87dc8-151">This code displays the following text:</span></span>  
  
 `Phone type: home`  
  
## <a name="see-also"></a><span data-ttu-id="87dc8-152">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="87dc8-152">See also</span></span>

- <xref:System.Xml.Linq.XElement>
- [<span data-ttu-id="87dc8-153">Proprietà Axis XML</span><span class="sxs-lookup"><span data-stu-id="87dc8-153">XML Axis Properties</span></span>](index.md)
- [<span data-ttu-id="87dc8-154">Valori letterali XML</span><span class="sxs-lookup"><span data-stu-id="87dc8-154">XML Literals</span></span>](../xml-literals/index.md)
- [<span data-ttu-id="87dc8-155">Creazione di XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="87dc8-155">Creating XML in Visual Basic</span></span>](../../programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="87dc8-156">Nomi di elementi e attributi XML dichiarati</span><span class="sxs-lookup"><span data-stu-id="87dc8-156">Names of Declared XML Elements and Attributes</span></span>](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
