---
title: IntelliSense XML in Visual Basic | Documenti di Microsoft
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
- Visual Basic code, XML
- XML IntelliSense [Visual Basic]
- XML [Visual Basic], IntelliSense
- IntelliSense [Visual Basic], XML
ms.assetid: 59506ce9-d64e-417e-90fc-e9fe19f0a8fa
caps.latest.revision: 27
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
ms.sourcegitcommit: a32f50ce8a92fa22d9627a1510a4b3ec1087364e
ms.openlocfilehash: 9a3c6f923bc9458997c388d4cf74ca113265a8cc
ms.contentlocale: it-it
ms.lasthandoff: 06/01/2017

---
# <a name="xml-intellisense-in-visual-basic"></a><span data-ttu-id="893d3-102">IntelliSense XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="893d3-102">XML IntelliSense in Visual Basic</span></span>
<span data-ttu-id="893d3-103">L'Editor di codice Visual Basic include funzionalità di IntelliSense per XML che forniscono il completamento delle parole per gli elementi definiti in uno schema XML.</span><span class="sxs-lookup"><span data-stu-id="893d3-103">The Visual Basic Code Editor includes IntelliSense features for XML that provide word completion for elements defined in an XML schema.</span></span> <span data-ttu-id="893d3-104">Se si include un file XML Schema Definition (XSD) nel progetto e importare lo spazio dei nomi di destinazione dello schema utilizzando il `Imports` istruzione, l'Editor di codice includerà elementi dallo schema XSD nell'elenco IntelliSense di variabili membro valide per <xref:System.Xml.Linq.XElement>e <xref:System.Xml.Linq.XDocument>oggetti.</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="893d3-104">If you include an XML Schema Definition (XSD) file in your project and import the target namespace of the schema by using the `Imports` statement, the Code Editor will include elements from the XSD schema in the IntelliSense list of valid member variables for <xref:System.Xml.Linq.XElement> and <xref:System.Xml.Linq.XDocument> objects.</span></span> <span data-ttu-id="893d3-105">La figura seguente mostra l'elenco dei membri di IntelliSense per un <xref:System.Xml.Linq.XElement>oggetto.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="893d3-105">The following illustration shows the IntelliSense members list for an <xref:System.Xml.Linq.XElement> object.</span></span>  
  
 <span data-ttu-id="893d3-106">![IntelliSense XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/media/xml_intellisense.png "XML_Intellisense")</span><span class="sxs-lookup"><span data-stu-id="893d3-106">![XML IntelliSense in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/media/xml_intellisense.png "XML_Intellisense")</span></span>  
<span data-ttu-id="893d3-107">IntelliSense XML</span><span class="sxs-lookup"><span data-stu-id="893d3-107">XML IntelliSense</span></span>  
  
## <a name="enabling-xml-intellisense-in-visual-basic"></a><span data-ttu-id="893d3-108">L'abilitazione di IntelliSense XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="893d3-108">Enabling XML IntelliSense in Visual Basic</span></span>  
 <span data-ttu-id="893d3-109">Per abilitare IntelliSense XML in Visual Basic, è necessario includere un file di schema XSD nel progetto di Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="893d3-109">To enable XML IntelliSense in Visual Basic, you must include an XSD schema file in your Visual Basic project.</span></span> <span data-ttu-id="893d3-110">È inoltre necessario importare lo spazio dei nomi di destinazione per lo schema XSD nel file di codice utilizzando il `Imports` istruzione.</span><span class="sxs-lookup"><span data-stu-id="893d3-110">You must also import the target namespace for the XSD schema into your code file by using the `Imports` statement.</span></span> <span data-ttu-id="893d3-111">In alternativa, è possibile aggiungere lo spazio dei nomi all'elenco di nomi a livello di progetto utilizzando il **riferimenti** pagina della finestra di progettazione di progetto Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="893d3-111">Alternatively, you can add the target namespace to the project-level namespace list by using the **References** page of the Visual Basic Project Designer.</span></span> <span data-ttu-id="893d3-112">Per esempi, vedere [procedura: abilitare IntelliSense XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/how-to-enable-xml-intellisense.md).</span><span class="sxs-lookup"><span data-stu-id="893d3-112">For examples, see [How to: Enable XML IntelliSense in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/how-to-enable-xml-intellisense.md).</span></span> <span data-ttu-id="893d3-113">Per ulteriori informazioni, vedere [istruzione Imports (XML Namespace)](../../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md) e [pagina riferimenti, Progettazione progetti (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/references-page-project-designer-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="893d3-113">For more information, see [Imports Statement (XML Namespace)](../../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md) and [References Page, Project Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/references-page-project-designer-visual-basic).</span></span>  
  
 <span data-ttu-id="893d3-114">Si noti che per impostazione predefinita è possono vedere i file di schema XSD nei progetti Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="893d3-114">Note that by default you cannot see XSD schema files in Visual Basic projects.</span></span> <span data-ttu-id="893d3-115">È necessario scegliere il **Mostra tutti i file** per selezionare un file XSD da includere nel progetto.</span><span class="sxs-lookup"><span data-stu-id="893d3-115">You may have to click the **Show All Files** button to select an XSD file to include in your project.</span></span>  
  
### <a name="generating-a-schema-file-schema-inference"></a><span data-ttu-id="893d3-116">Generazione di un File di Schema (inferenza dello Schema)</span><span class="sxs-lookup"><span data-stu-id="893d3-116">Generating a Schema File (Schema Inference)</span></span>  
 <span data-ttu-id="893d3-117">È possibile creare uno schema XSD per un file XML esistente per l'inferenza dello schema XSD utilizzando gli strumenti XML di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="893d3-117">You can create an XSD schema for an existing XML file by inferring the XSD schema by using Visual Studio XML tools.</span></span>  
  
-   <span data-ttu-id="893d3-118">A partire da SP1, è possibile utilizzare il codice XML Schema guidata per creare un set di XML Schema che viene dedotto da uno o più documenti XML e includerlo nel progetto.</span><span class="sxs-lookup"><span data-stu-id="893d3-118">Starting in SP1, you can use the XML to Schema Wizard to create an XML Schema set that is inferred from one or more XML documents and include it your project.</span></span> <span data-ttu-id="893d3-119">È possibile utilizzare qualsiasi combinazione di documenti XML sotto forma di file di testo, XML provenienti da indirizzi HTTP Internet o XML che viene digitato o incollato nel XML Schema guidata.</span><span class="sxs-lookup"><span data-stu-id="893d3-119">You can use any combination of XML documents in the form of text files, XML from HTTP Internet addresses, or XML that is typed or pasted into the XML to Schema Wizard.</span></span> <span data-ttu-id="893d3-120">Per accedere a XML Schema guidata, fare clic su **Aggiungi nuovo elemento** sul **progetto** menu e aggiungere un **XML in Schema** modello presente la **dati** o **elementi comuni** gruppo di modelli.</span><span class="sxs-lookup"><span data-stu-id="893d3-120">To access the XML to Schema Wizard, click **Add New Item** on the **Project** menu and add an **XML to Schema** template from either the **Data** or **Common Items** template group.</span></span> <span data-ttu-id="893d3-121">Dopo che sono state incluse tutte le origini di documento XML per dedurre il set di XML Schema da, fare clic su **OK** per creare lo schema inferito set.</span><span class="sxs-lookup"><span data-stu-id="893d3-121">After you have included all the XML document sources to infer the XML Schema set from, click **OK** to create the inferred schema set.</span></span> <span data-ttu-id="893d3-122">Per ulteriori informazioni, vedere [procedura guidata Schema XML in](../../../../visual-basic/programming-guide/language-features/xml/xml-to-schema-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="893d3-122">For more information, see [XML to Schema Wizard](../../../../visual-basic/programming-guide/language-features/xml/xml-to-schema-wizard.md).</span></span>  
  
-   <span data-ttu-id="893d3-123">È inoltre possibile utilizzare l'Editor XML di Visual Studio per inferire uno schema XSD impostato da un file XML.</span><span class="sxs-lookup"><span data-stu-id="893d3-123">You can also use the Visual Studio XML Editor to infer an XSD schema set from an XML file.</span></span> <span data-ttu-id="893d3-124">Per creare un insieme utilizzando l'Editor XML dello schema XML, aprire un file XML in Progettazione XML di Visual Studio e quindi fare clic su **Create Schema** sul **XML** menu.</span><span class="sxs-lookup"><span data-stu-id="893d3-124">To create an XML schema set by using the XML Editor, open an XML file in the Visual Studio XML Designer and then click **Create Schema** on the **XML** menu.</span></span> <span data-ttu-id="893d3-125">Dopo aver creato il set di schemi XSD, è possibile salvare il set di schema creato in uno o più file XSD e includerli nel progetto.</span><span class="sxs-lookup"><span data-stu-id="893d3-125">After you create the XSD schema set, you can save the created schema set to one or more XSD files and include them in your project.</span></span> <span data-ttu-id="893d3-126">Per ulteriori informazioni, vedere[procedura: abilitare IntelliSense XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/how-to-enable-xml-intellisense.md).</span><span class="sxs-lookup"><span data-stu-id="893d3-126">For more information, see[How to: Enable XML IntelliSense in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/how-to-enable-xml-intellisense.md).</span></span>  
  
 <span data-ttu-id="893d3-127">Si noti che nel set di schemi XSD diversi potrà essere dedotto da più documenti XML che devono avere lo stesso schema.</span><span class="sxs-lookup"><span data-stu-id="893d3-127">Note that different XSD schema sets might be inferred from multiple XML documents that are intended to have the same schema.</span></span> <span data-ttu-id="893d3-128">Ciò può verificarsi quando vengono trovati determinati elementi e attributi in un file XML e non in un'altra o quando sono inclusi elementi in ordine diverso, ad esempio.</span><span class="sxs-lookup"><span data-stu-id="893d3-128">This can occur when particular elements and attributes are found in one XML file and not in another, or when elements are included in different order, for example.</span></span> <span data-ttu-id="893d3-129">Quando si utilizza l'inferenza dello schema XSD, è opportuno esaminare derivato nel set di schemi XSD per completezza e accuratezza.</span><span class="sxs-lookup"><span data-stu-id="893d3-129">You should review inferred XSD schema sets for completeness and accuracy when you use XSD schema inference.</span></span>  
  
## <a name="member-list"></a><span data-ttu-id="893d3-130">Elenco dei membri</span><span class="sxs-lookup"><span data-stu-id="893d3-130">Member List</span></span>  
 <span data-ttu-id="893d3-131">Dopo aver digitato un punto (.) per delimitare un'istanza di un <xref:System.Xml.Linq.XElement>o <xref:System.Xml.Linq.XDocument>oggetto (o un'istanza di `IEnumerable(Of XElement)` o `IEnumerable(Of XDocument)`), IntelliSense di Visual Basic viene visualizzato un elenco di membri dell'oggetto possibili.</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="893d3-131">After you type a period (.) to delimit an instance of an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> object (or an instance of `IEnumerable(Of XElement)` or `IEnumerable(Of XDocument)`), Visual Basic IntelliSense displays a list of possible object members.</span></span> <span data-ttu-id="893d3-132">L'elenco iniziale include tre opzioni che rappresentano le proprietà axis XML, come descritto nell'elenco seguente.</span><span class="sxs-lookup"><span data-stu-id="893d3-132">The initial list includes three options that represent XML axis properties, as described in the following list.</span></span>  
  
|<span data-ttu-id="893d3-133">Opzione</span><span class="sxs-lookup"><span data-stu-id="893d3-133">Option</span></span>|<span data-ttu-id="893d3-134">Descrizione</span><span class="sxs-lookup"><span data-stu-id="893d3-134">Description</span></span>|  
|---|---|  
|**\< >**|<span data-ttu-id="893d3-135">Selezionare questa opzione per visualizzare un elenco di possibili figlio di elementi.</span><span class="sxs-lookup"><span data-stu-id="893d3-135">Select this option to show a list of possible child elements.</span></span> <span data-ttu-id="893d3-136">Per ulteriori informazioni, vedere [letterale elemento XML](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) e <xref:System.Xml.Linq.XContainer.Elements%2A>metodo.</xref:System.Xml.Linq.XContainer.Elements%2A></span><span class="sxs-lookup"><span data-stu-id="893d3-136">For more information, see [XML Element Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) and the <xref:System.Xml.Linq.XContainer.Elements%2A> method.</span></span>|  
|**@**|<span data-ttu-id="893d3-137">Selezionare questa opzione per visualizzare un elenco di attributi possibili.</span><span class="sxs-lookup"><span data-stu-id="893d3-137">Select this option to show a list of possible attributes.</span></span> <span data-ttu-id="893d3-138">Per ulteriori informazioni, vedere [proprietà Axis XML](../../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md). Questa opzione è disponibile solo per gli oggetti di tipo <xref:System.Xml.Linq.XElement>.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="893d3-138">For more information, see [XML Axis Properties](../../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md).This option is available only for objects of type <xref:System.Xml.Linq.XElement>.</span></span>|  
|<span data-ttu-id="893d3-139">**…\< >**</span><span class="sxs-lookup"><span data-stu-id="893d3-139">**…\< >**</span></span>|<span data-ttu-id="893d3-140">Selezionare questa opzione per visualizzare un elenco di possibili elementi discendenti.</span><span class="sxs-lookup"><span data-stu-id="893d3-140">Select this option to show a list of possible descendant elements.</span></span> <span data-ttu-id="893d3-141">Per ulteriori informazioni, vedere [procedura: accedere agli elementi discendenti XML](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-descendant-elements.md) e <xref:System.Xml.Linq.XContainer.Elements%2A>metodo.</xref:System.Xml.Linq.XContainer.Elements%2A></span><span class="sxs-lookup"><span data-stu-id="893d3-141">For more information, see [How to: Access XML Descendant Elements](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-descendant-elements.md) and the <xref:System.Xml.Linq.XContainer.Elements%2A> method.</span></span>|  
  
 <span data-ttu-id="893d3-142">Selezionare o digitare le opzioni XML dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="893d3-142">Select or begin typing any of the XML options from the list.</span></span> <span data-ttu-id="893d3-143">L'elenco dei membri visualizzerà quindi membri potenziali dallo schema XML che sono specifici dell'opzione selezionata.</span><span class="sxs-lookup"><span data-stu-id="893d3-143">The member list will then display potential members from the XML schema that are specific to the selected option.</span></span> <span data-ttu-id="893d3-144">Se si dispone di spazi dei nomi XML importato associati a uno specifico prefisso dello spazio dei nomi XML, un elenco di potenziali prefissi di spazio dei nomi XML è incluso nell'elenco dei membri.</span><span class="sxs-lookup"><span data-stu-id="893d3-144">If you have XML namespaces imported that are associated with a specific XML namespace prefix, a list of potential XML namespace prefixes is included in the member list.</span></span>  
  
 <span data-ttu-id="893d3-145">Ad esempio, si consideri il seguente schema XSD.</span><span class="sxs-lookup"><span data-stu-id="893d3-145">For example, consider the following XSD schema.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<xs:schema attributeFormDefault="unqualified"   
           elementFormDefault="qualified"   
           targetNamespace="http://SamplePurchaseOrder"   
           xmlns:xs="http://www.w3.org/2001/XMLSchema">  
  <xs:element name="PurchaseOrders">  
    <xs:complexType>  
      <xs:sequence>  
        <xs:element name="PurchaseOrder">  
          <xs:complexType>  
            <xs:sequence>  
              <xs:element name="Address" />  
              <xs:element name="Items" />  
              <xs:element name="Comment" />  
            </xs:sequence>  
            <xs:attribute name="PurchaseOrderNumber" type="xs:unsignedShort" use="required" />  
            <xs:attribute name="OrderDate" type="xs:string" use="required" />  
          </xs:complexType>  
        </xs:element>  
      </xs:sequence>  
    </xs:complexType>  
  </xs:element>  
</xs:schema>  
```  
  
 <span data-ttu-id="893d3-146">XML valido per lo schema XSD sarà simile alla seguente.</span><span class="sxs-lookup"><span data-stu-id="893d3-146">Valid XML for the XSD schema would resemble the following.</span></span>  
  
```xml  
<?xml version="1.0"?>  
<PurchaseOrders xmlns="http://SamplePurchaseOrder">  
  <PurchaseOrder PurchaseOrderNumber="12345" OrderDate="2000-1-1">  
    <Address />  
    <Items />  
    <Comment />  
  </PurchaseOrder>  
</PurchaseOrders>  
```  
  
 <span data-ttu-id="893d3-147">Se si include questo file di schema XSD in un progetto e importa lo spazio dei nomi di destinazione dallo schema XSD in un progetto o del file di codice, IntelliSense di Visual Basic Visualizza membri dallo schema durante la digitazione del codice Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="893d3-147">If you include this XSD schema file in a project and import the target namespace from the XSD schema into your code file or project, Visual Basic IntelliSense displays members from the schema as you type your Visual Basic code.</span></span> <span data-ttu-id="893d3-148">Se lo spazio dei nomi di destinazione per lo schema XSD viene importato come spazio dei nomi predefinito e si digita quanto segue, IntelliSense visualizza un elenco di possibili elementi figlio per il `PurchaseOrder` (elemento XML).</span><span class="sxs-lookup"><span data-stu-id="893d3-148">If the target namespace for the XSD schema is imported as the default namespace and you type the following, IntelliSense displays a list of possible child elements for the `PurchaseOrder` XML element.</span></span>  
  
```  
Dim po = <PurchaseOrder />  
po.<  
```  
  
 <span data-ttu-id="893d3-149">L'elenco è costituito da elementi di indirizzo, commento e gli elementi.</span><span class="sxs-lookup"><span data-stu-id="893d3-149">The list consists of the Address, Comment, and Items elements.</span></span>  
  
### <a name="certainty-levels-for-intellisense-list-items"></a><span data-ttu-id="893d3-150">Livelli di attendibilità per gli elementi dell'elenco di IntelliSense</span><span class="sxs-lookup"><span data-stu-id="893d3-150">Certainty Levels for IntelliSense List Items</span></span>  
 <span data-ttu-id="893d3-151">Determinazione del tipo XSD da utilizzare per IntelliSense non è esatta.</span><span class="sxs-lookup"><span data-stu-id="893d3-151">Determining the XSD type to use for IntelliSense is not exact.</span></span> <span data-ttu-id="893d3-152">Di conseguenza, IntelliSense XML spesso Visualizza un elenco di possibili membri espanso.</span><span class="sxs-lookup"><span data-stu-id="893d3-152">As a result, XML IntelliSense will often show an expanded list of possible members.</span></span> <span data-ttu-id="893d3-153">Per facilitare la selezione di un elemento dall'elenco dei membri IntelliSense, gli elementi vengono visualizzati con l'indicazione del livello di certezza che dispone di IntelliSense XML per un particolare membro.</span><span class="sxs-lookup"><span data-stu-id="893d3-153">To aid you in selecting an item from the IntelliSense member list, items are displayed with an indication of the level of certainty that XML IntelliSense has for a particular member.</span></span>  
  
 <span data-ttu-id="893d3-154">A volte IntelliSense XML può identificare un tipo specifico dallo schema XSD.</span><span class="sxs-lookup"><span data-stu-id="893d3-154">Sometimes XML IntelliSense can identify a specific type from the XSD schema.</span></span> <span data-ttu-id="893d3-155">In questi casi, verrà visualizzato possibili elementi figlio, attributi o gli elementi discendenti di tale tipo XSD con un elevato livello di attendibilità.</span><span class="sxs-lookup"><span data-stu-id="893d3-155">In these cases, it will display possible child elements, attributes, or descendant elements for that XSD type with a high degree of certainty.</span></span> <span data-ttu-id="893d3-156">Questi elementi vengono identificati con un segno di spunta.</span><span class="sxs-lookup"><span data-stu-id="893d3-156">These items are identified with a check mark.</span></span>  
  
 <span data-ttu-id="893d3-157">Tuttavia, a volte IntelliSense XML non è in grado di identificare un tipo specifico dallo schema XSD.</span><span class="sxs-lookup"><span data-stu-id="893d3-157">However, sometimes XML IntelliSense is not able to identify a specific type from the XSD schema.</span></span> <span data-ttu-id="893d3-158">In questi casi, visualizzerà un elenco espanso di possibili elementi figlio, attributi o elementi discendenti dallo schema XSD per il progetto con un livello di certezza basso.</span><span class="sxs-lookup"><span data-stu-id="893d3-158">In these cases, it will display an expanded list of possible child elements, attributes, or descendant elements from the XSD schema for the project with a low degree of certainty.</span></span> <span data-ttu-id="893d3-159">Questi elementi vengono identificati con un punto interrogativo.</span><span class="sxs-lookup"><span data-stu-id="893d3-159">These items are identified with a question mark.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="893d3-160">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="893d3-160">See Also</span></span>  
 <span data-ttu-id="893d3-161">[Procedura: abilitare IntelliSense XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/how-to-enable-xml-intellisense.md) </span><span class="sxs-lookup"><span data-stu-id="893d3-161">[How to: Enable XML IntelliSense in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/how-to-enable-xml-intellisense.md) </span></span>  
<span data-ttu-id="893d3-162"> [Procedura guidata Schema XML in](../../../../visual-basic/programming-guide/language-features/xml/xml-to-schema-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="893d3-162"> [XML to Schema Wizard](../../../../visual-basic/programming-guide/language-features/xml/xml-to-schema-wizard.md) </span></span>  
<span data-ttu-id="893d3-163"> [Istruzione Imports (XML Namespace)](../../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md) </span><span class="sxs-lookup"><span data-stu-id="893d3-163"> [Imports Statement (XML Namespace)](../../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md) </span></span>  
<span data-ttu-id="893d3-164"> [Valore letterale elemento XML](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) </span><span class="sxs-lookup"><span data-stu-id="893d3-164"> [XML Element Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) </span></span>  
<span data-ttu-id="893d3-165"> [Proprietà axis dell'attributo XML](../../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md) </span><span class="sxs-lookup"><span data-stu-id="893d3-165"> [XML Attribute Axis Property](../../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md) </span></span>  
<span data-ttu-id="893d3-166"> [Proprietà Axis Descendant XML](../../../../visual-basic/language-reference/xml-axis/xml-descendant-axis-property.md) </span><span class="sxs-lookup"><span data-stu-id="893d3-166"> [XML Descendant Axis Property](../../../../visual-basic/language-reference/xml-axis/xml-descendant-axis-property.md) </span></span>  
<span data-ttu-id="893d3-167"> [Pagina Riferimenti, Creazione progetti (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/references-page-project-designer-visual-basic)</span><span class="sxs-lookup"><span data-stu-id="893d3-167"> [References Page, Project Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/references-page-project-designer-visual-basic)</span></span>
