---
title: 'Procedura: modificare valori letterali XML (Visual Basic) | Documenti di Microsoft'
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
- XML axis [Visual Basic], Value
- XML literals [Visual Basic]
- XML literals [Visual Basic], modifying
ms.assetid: 4e864522-a37a-43a2-8236-af80277c5482
caps.latest.revision: 11
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
ms.openlocfilehash: 9c21ded9fdd8f49b469b9a712be304c0d4cabb8c
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-modify-xml-literals-visual-basic"></a><span data-ttu-id="9a090-102">Procedura: modificare valori letterali XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9a090-102">How to: Modify XML Literals (Visual Basic)</span></span>
[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="9a090-103">Consente di modificare valori letterali XML agevolmente.</span><span class="sxs-lookup"><span data-stu-id="9a090-103"> provides convenient ways to modify XML literals.</span></span> <span data-ttu-id="9a090-104">È possibile aggiungere o eliminare elementi e attributi ed è inoltre possibile sostituire un elemento esistente con un nuovo elemento XML.</span><span class="sxs-lookup"><span data-stu-id="9a090-104">You can add or delete elements and attributes, and you can also replace an existing element with a new XML element.</span></span> <span data-ttu-id="9a090-105">In questo argomento fornisce alcuni esempi di come modificare un valore letterale XML esistente.</span><span class="sxs-lookup"><span data-stu-id="9a090-105">This topic provides several examples of how to modify an existing XML literal.</span></span>  
  
### <a name="to-modify-the-value-of-an-xml-literal"></a><span data-ttu-id="9a090-106">Per modificare il valore di un valore letterale XML</span><span class="sxs-lookup"><span data-stu-id="9a090-106">To modify the value of an XML literal</span></span>  
  
1.  <span data-ttu-id="9a090-107">Per modificare il valore di un valore letterale XML, ottenere un riferimento al codice XML letterale e impostare il `Value` proprietà sul valore desiderato.</span><span class="sxs-lookup"><span data-stu-id="9a090-107">To modify the value of an XML literal, obtain a reference to the XML literal and set the `Value` property to the desired value.</span></span>  
  
     <span data-ttu-id="9a090-108">Nell'esempio seguente aggiorna il valore di tutti i \<prezzo > elementi in un documento XML.</span><span class="sxs-lookup"><span data-stu-id="9a090-108">The following code example updates the value of all the \<Price> elements in an XML document.</span></span>  
  
     <span data-ttu-id="9a090-109">[!code-vb[VbXmlSamples2 n.&4;](../../../../visual-basic/programming-guide/language-features/xml/codesnippet/VisualBasic/how-to-modify-xml-literals_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="9a090-109">[!code-vb[VbXmlSamples2#4](../../../../visual-basic/programming-guide/language-features/xml/codesnippet/VisualBasic/how-to-modify-xml-literals_1.vb)]</span></span>  
  
     <span data-ttu-id="9a090-110">Di seguito viene illustrato XML di origine e quello modificato da questo esempio di codice.</span><span class="sxs-lookup"><span data-stu-id="9a090-110">The following shows sample source XML and modified XML from this code example.</span></span>  
  
    ```  
    Source XML:  
    <?xml version="1.0"?>  
    <Catalog>  
      <Book id="bk101">  
        <Author>Garghentini, Davide</Author>  
        <Title>XML Developer's Guide</Title>  
        <Price>44.95</Price>  
      </Book>  
      <Book id="bk331">  
        <Author>Spencer, Phil</Author>  
        <Title>Developing Applications with Visual Basic .NET</Title>  
        <Price>45.95</Price>  
      </Book>  
    </Catalog>  
  
    Modified XML:  
    <?xml version="1.0"?>  
    <Catalog>  
      <Book id="bk101">  
        <Author>Garghentini, Davide</Author>  
        <Title>XML Developer's Guide</Title>  
        <Price>47.20</Price>  
      </Book>  
      <Book id="bk331">  
        <Author>Spencer, Phil</Author>  
        <Title>Developing Applications with Visual Basic .NET</Title>  
        <Price>48.25</Price>  
      </Book>  
    </Catalog>  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="9a090-111">Il `Value` proprietà fa riferimento al primo elemento XML in una raccolta.</span><span class="sxs-lookup"><span data-stu-id="9a090-111">The `Value` property refers to the first XML element in a collection.</span></span> <span data-ttu-id="9a090-112">Se è presente più di un elemento che ha lo stesso nome in una raccolta, l'impostazione di `Value` proprietà influisce solo il primo elemento nella raccolta.</span><span class="sxs-lookup"><span data-stu-id="9a090-112">If there is more than one element that has the same name in a collection, setting the `Value` property affects only the first element in the collection.</span></span>  
  
### <a name="to-add-an-attribute-to-an-xml-literal"></a><span data-ttu-id="9a090-113">Per aggiungere un attributo a un valore letterale XML</span><span class="sxs-lookup"><span data-stu-id="9a090-113">To add an attribute to an XML literal</span></span>  
  
1.  <span data-ttu-id="9a090-114">Per aggiungere un attributo a un valore letterale XML, ottenere prima un riferimento al valore letterale XML.</span><span class="sxs-lookup"><span data-stu-id="9a090-114">To add an attribute to an XML literal, first obtain a reference to the XML literal.</span></span> <span data-ttu-id="9a090-115">È quindi possibile aggiungere un attributo mediante l'aggiunta di una nuova proprietà di asse attributo XML.</span><span class="sxs-lookup"><span data-stu-id="9a090-115">You can then add an attribute by adding a new XML attribute axis property.</span></span> <span data-ttu-id="9a090-116">È inoltre possibile aggiungere un nuovo <xref:System.Xml.Linq.XAttribute>oggetto per il valore letterale XML tramite il <xref:System.Xml.Linq.XContainer.Add%2A>(metodo).</xref:System.Xml.Linq.XContainer.Add%2A> </xref:System.Xml.Linq.XAttribute></span><span class="sxs-lookup"><span data-stu-id="9a090-116">You can also add a new <xref:System.Xml.Linq.XAttribute> object to the XML literal by using the <xref:System.Xml.Linq.XContainer.Add%2A> method.</span></span> <span data-ttu-id="9a090-117">Nell'esempio seguente viene illustrato entrambe le opzioni.</span><span class="sxs-lookup"><span data-stu-id="9a090-117">The following example shows both options.</span></span>  
  
     <span data-ttu-id="9a090-118">[!code-vb[VbXmlSamples2 n.&5;](../../../../visual-basic/programming-guide/language-features/xml/codesnippet/VisualBasic/how-to-modify-xml-literals_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="9a090-118">[!code-vb[VbXmlSamples2#5](../../../../visual-basic/programming-guide/language-features/xml/codesnippet/VisualBasic/how-to-modify-xml-literals_2.vb)]</span></span>  
  
     <span data-ttu-id="9a090-119">Di seguito viene illustrato XML di origine e quello modificato da questo esempio di codice.</span><span class="sxs-lookup"><span data-stu-id="9a090-119">The following shows sample source XML and modified XML from this code example.</span></span>  
  
    ```  
    Source XML:  
    <?xml version="1.0"?>  
    <Catalog>  
      <Book id="bk101" >  
        <Author>Garghentini, Davide</Author>  
        <Title>XML Developer's Guide</Title>  
        <Price>44.95</Price>  
      </Book>  
      <Book id="bk331">  
        <Author>Spencer, Phil</Author>  
        <Title>Developing Applications with Visual Basic .NET</Title>  
        <Price>45.95</Price>  
      </Book>  
    </Catalog>  
  
    Modified XML:  
    <?xml version="1.0"?>  
    <Catalog>  
      <Book id="bk101" genre="Computer" editorEmail="someone@example.com">  
        <Author>Garghentini, Davide</Author>  
        <Title>XML Developer's Guide</Title>  
        <Price>44.95</Price>  
      </Book>  
      <Book id="bk331" genre="Computer" editorEmail="someone@example.com">  
        <Author>Spencer, Phil</Author>  
        <Title>Developing Applications with Visual Basic .NET</Title>  
        <Price>45.95</Price>  
      </Book>  
    </Catalog>  
    ```  
  
     <span data-ttu-id="9a090-120">Per ulteriori informazioni sulle proprietà axis dell'attributo XML, vedere [proprietà axis dell'attributo XML](../../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md).</span><span class="sxs-lookup"><span data-stu-id="9a090-120">For more information about XML attribute axis properties, see [XML Attribute Axis Property](../../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md).</span></span>  
  
### <a name="to-add-an-element-to-an-xml-literal"></a><span data-ttu-id="9a090-121">Per aggiungere un elemento a un valore letterale XML</span><span class="sxs-lookup"><span data-stu-id="9a090-121">To add an element to an XML literal</span></span>  
  
1.  <span data-ttu-id="9a090-122">Per aggiungere un elemento a un valore letterale XML, ottenere prima un riferimento al valore letterale XML.</span><span class="sxs-lookup"><span data-stu-id="9a090-122">To add an element to an XML literal, first obtain a reference to the XML literal.</span></span> <span data-ttu-id="9a090-123">È quindi possibile aggiungere un nuovo <xref:System.Xml.Linq.XElement>oggetto come ultimo sottoelemento dell'elemento utilizzando il <xref:System.Xml.Linq.XContainer.Add%2A>(metodo).</xref:System.Xml.Linq.XContainer.Add%2A> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="9a090-123">You can then add a new <xref:System.Xml.Linq.XElement> object as the last sub-element of the element by using the <xref:System.Xml.Linq.XContainer.Add%2A> method.</span></span> <span data-ttu-id="9a090-124">È possibile aggiungere un nuovo <xref:System.Xml.Linq.XElement>oggetto come primo sottoelemento dell'elemento utilizzando il <xref:System.Xml.Linq.XContainer.AddFirst%2A>(metodo).</xref:System.Xml.Linq.XContainer.AddFirst%2A> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="9a090-124">You can add a new <xref:System.Xml.Linq.XElement> object as the first sub-element by using the <xref:System.Xml.Linq.XContainer.AddFirst%2A> method.</span></span>  
  
     <span data-ttu-id="9a090-125">Per aggiungere un nuovo elemento in un percorso specifico rispetto agli altri sottoelementi, ottenere prima un riferimento a un sottoelemento adiacente.</span><span class="sxs-lookup"><span data-stu-id="9a090-125">To add a new element in a specific location relative to other sub-elements, first obtain a reference to an adjacent sub-element.</span></span> <span data-ttu-id="9a090-126">È quindi possibile aggiungere il nuovo <xref:System.Xml.Linq.XElement>oggetto prima del sottoelemento adiacente utilizzando il <xref:System.Xml.Linq.XNode.AddBeforeSelf%2A>(metodo).</xref:System.Xml.Linq.XNode.AddBeforeSelf%2A> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="9a090-126">You can then add the new <xref:System.Xml.Linq.XElement> object before the adjacent sub-element by using the <xref:System.Xml.Linq.XNode.AddBeforeSelf%2A> method.</span></span> <span data-ttu-id="9a090-127">È inoltre possibile aggiungere il nuovo <xref:System.Xml.Linq.XElement>oggetto dopo il sottoelemento adiacente utilizzando il <xref:System.Xml.Linq.XNode.AddAfterSelf%2A>(metodo).</xref:System.Xml.Linq.XNode.AddAfterSelf%2A> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="9a090-127">You can also add the new <xref:System.Xml.Linq.XElement> object after the adjacent sub-element by using the <xref:System.Xml.Linq.XNode.AddAfterSelf%2A> method.</span></span>  
  
     <span data-ttu-id="9a090-128">Nell'esempio seguente vengono illustrati esempi di ognuna di queste tecniche.</span><span class="sxs-lookup"><span data-stu-id="9a090-128">The following example shows examples of each of these techniques.</span></span>  
  
     <span data-ttu-id="9a090-129">[!code-vb[6 VbXmlSamples2](../../../../visual-basic/programming-guide/language-features/xml/codesnippet/VisualBasic/how-to-modify-xml-literals_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="9a090-129">[!code-vb[VbXmlSamples2#6](../../../../visual-basic/programming-guide/language-features/xml/codesnippet/VisualBasic/how-to-modify-xml-literals_3.vb)]</span></span>  
  
     <span data-ttu-id="9a090-130">Di seguito viene illustrato XML di origine e quello modificato da questo esempio di codice.</span><span class="sxs-lookup"><span data-stu-id="9a090-130">The following shows sample source XML and modified XML from this code example.</span></span>  
  
    ```  
    Source XML:  
    <?xml version="1.0"?>  
    <Catalog>  
      <Book id="bk101" >  
        <Author>Garghentini, Davide</Author>  
        <Title>XML Developer's Guide</Title>  
        <Price>44.95</Price>  
      </Book>  
      <Book id="bk331">  
        <Author>Spencer, Phil</Author>  
        <Title>Developing Applications with Visual Basic .NET</Title>  
        <Price>45.95</Price>  
      </Book>  
    </Catalog>  
  
    Modified XML:  
    <?xml version="1.0"?>  
    <Catalog>  
      <Book id="bk101" >  
        <Author>Garghentini, Davide</Author>  
        <Title>XML Developer's Guide</Title>  
        <Price>44.95</Price>  
      </Book>  
      <Book id="bk000"></Book>  
      <Book id="bk331">  
        <Publisher>Microsoft Press</Publisher>  
        <Author>Spencer, Phil</Author>  
        <Title>Developing Applications with Visual Basic .NET</Title>  
        <Price>45.95</Price>  
        <PublishDate>2005-2-14</PublishDate>  
      </Book>  
      <Book id="bk999"></Book>  
    </Catalog>  
    ```  
  
### <a name="to-remove-an-element-or-attribute-from-an-xml-literal"></a><span data-ttu-id="9a090-131">Per rimuovere un elemento o attributo da un valore letterale XML</span><span class="sxs-lookup"><span data-stu-id="9a090-131">To remove an element or attribute from an XML literal</span></span>  
  
1.  <span data-ttu-id="9a090-132">Per rimuovere un elemento o un attributo da un valore letterale XML, ottenere un riferimento per l'elemento o attributo e chiamare il `Remove` (metodo), come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="9a090-132">To remove an element or an attribute from an XML literal, obtain a reference to the element or attribute and call the `Remove` method, as shown in the following example.</span></span>  
  
     <span data-ttu-id="9a090-133">[!code-vb[VbXmlSamples&#2;7](../../../../visual-basic/programming-guide/language-features/xml/codesnippet/VisualBasic/how-to-modify-xml-literals_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="9a090-133">[!code-vb[VbXmlSamples2#7](../../../../visual-basic/programming-guide/language-features/xml/codesnippet/VisualBasic/how-to-modify-xml-literals_4.vb)]</span></span>  
  
     <span data-ttu-id="9a090-134">Di seguito viene illustrato XML di origine e quello modificato da questo esempio di codice.</span><span class="sxs-lookup"><span data-stu-id="9a090-134">The following shows sample source XML and modified XML from this code example.</span></span>  
  
    ```  
    Source XML:  
    <?xml version="1.0"?>  
    <Catalog>  
      <Book id="bk101" genre="Computer" editorEmail="someone@example.com">  
        <Author>Garghentini, Davide</Author>  
        <Title>XML Developer's Guide</Title>  
        <Price>44.95</Price>  
      </Book>  
      <Book id="bk000"></Book>  
      <Book id="bk331" genre="Computer" editorEmail="someone@example.com">  
        <Author>Spencer, Phil</Author>  
        <Title>Developing Applications with Visual Basic .NET</Title>  
        <Price>45.95</Price>  
      </Book>  
      <Book id="bk999"></Book>  
    </Catalog>  
  
    Modified XML:  
    <?xml version="1.0"?>  
    <Catalog>  
      <Book id="bk101" editorEmail="someone@example.com">  
        <Author>Garghentini, Davide</Author>  
        <Title>XML Developer's Guide</Title>  
        <Price>44.95</Price>  
      </Book>  
      <Book id="bk000"></Book>  
      <Book id="bk331" editorEmail="someone@example.com">  
        <Author>Spencer, Phil</Author>  
        <Title>Developing Applications with Visual Basic .NET</Title>  
        <Price>45.95</Price>  
      </Book></Catalog>  
    ```  
  
     <span data-ttu-id="9a090-135">Per rimuovere tutti gli elementi o attributi da un valore letterale XML, ottenere un riferimento al valore letterale XML e chiamare il <xref:System.Xml.Linq.XElement.RemoveAll%2A>(metodo).</xref:System.Xml.Linq.XElement.RemoveAll%2A></span><span class="sxs-lookup"><span data-stu-id="9a090-135">To remove all elements or attributes from an XML literal, obtain a reference to the XML literal and call the <xref:System.Xml.Linq.XElement.RemoveAll%2A> method.</span></span>  
  
### <a name="to-modify-an-xml-literal"></a><span data-ttu-id="9a090-136">Per modificare un valore letterale XML</span><span class="sxs-lookup"><span data-stu-id="9a090-136">To modify an XML literal</span></span>  
  
1.  <span data-ttu-id="9a090-137">Per modificare il nome di un elemento XML, ottenere prima un riferimento all'elemento.</span><span class="sxs-lookup"><span data-stu-id="9a090-137">To change the name of an XML element, first obtain a reference to the element.</span></span> <span data-ttu-id="9a090-138">È quindi possibile creare un nuovo <xref:System.Xml.Linq.XElement>oggetto con un nuovo nome e passa il nuovo <xref:System.Xml.Linq.XElement>dell'oggetto per il <xref:System.Xml.Linq.XNode.ReplaceWith%2A>metodo dell'oggetto esistente <xref:System.Xml.Linq.XElement>oggetto.</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XNode.ReplaceWith%2A> </xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="9a090-138">You can then create a new <xref:System.Xml.Linq.XElement> object that has a new name and pass the new <xref:System.Xml.Linq.XElement> object to the <xref:System.Xml.Linq.XNode.ReplaceWith%2A> method of the existing <xref:System.Xml.Linq.XElement> object.</span></span>  
  
     <span data-ttu-id="9a090-139">Se l'elemento che si sta sostituendo ha sottoelementi che devono essere mantenuti, impostare il valore del nuovo <xref:System.Xml.Linq.XElement>dell'oggetto per il <xref:System.Xml.Linq.XContainer.Nodes%2A>proprietà dell'elemento esistente.</xref:System.Xml.Linq.XContainer.Nodes%2A> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="9a090-139">If the element that you are replacing has sub-elements that must be preserved, set the value of the new <xref:System.Xml.Linq.XElement> object to the <xref:System.Xml.Linq.XContainer.Nodes%2A> property of the existing element.</span></span> <span data-ttu-id="9a090-140">Questo imposterà il valore del nuovo elemento per il codice XML interno dell'elemento esistente.</span><span class="sxs-lookup"><span data-stu-id="9a090-140">This will set the value of the new element to the inner XML of the existing element.</span></span> <span data-ttu-id="9a090-141">In caso contrario, è possibile impostare il valore del nuovo elemento per il `Value` proprietà dell'elemento esistente.</span><span class="sxs-lookup"><span data-stu-id="9a090-141">Otherwise, you can set the value of the new element to the `Value` property of the existing element.</span></span>  
  
     <span data-ttu-id="9a090-142">Esempio di codice seguente sostituisce tutto \<descrizione > gli elementi con un \<astratta > elemento.</span><span class="sxs-lookup"><span data-stu-id="9a090-142">The following code example replaces all \<Description> elements with an \<Abstract> element.</span></span> <span data-ttu-id="9a090-143">Il contenuto di \<descrizione > elemento viene mantenuto nel nuovo \<astratta > elemento utilizzando la <xref:System.Xml.Linq.XContainer.Nodes%2A>proprietà del \<descrizione > <xref:System.Xml.Linq.XElement>oggetto.</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XContainer.Nodes%2A></span><span class="sxs-lookup"><span data-stu-id="9a090-143">The content of the \<Description> element is preserved in the new \<Abstract> element by using the <xref:System.Xml.Linq.XContainer.Nodes%2A> property of the \<Description> <xref:System.Xml.Linq.XElement> object.</span></span>  
  
     <span data-ttu-id="9a090-144">[!code-vb[VbXmlSamples2 n.&8;](../../../../visual-basic/programming-guide/language-features/xml/codesnippet/VisualBasic/how-to-modify-xml-literals_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="9a090-144">[!code-vb[VbXmlSamples2#8](../../../../visual-basic/programming-guide/language-features/xml/codesnippet/VisualBasic/how-to-modify-xml-literals_5.vb)]</span></span>  
  
     <span data-ttu-id="9a090-145">Di seguito viene illustrato XML di origine e quello modificato da questo esempio di codice.</span><span class="sxs-lookup"><span data-stu-id="9a090-145">The following shows sample source XML and modified XML from this code example.</span></span>  
  
    ```  
    Source XML:  
    <?xml version="1.0"?>  
    <Catalog>  
      <Book id="bk101">  
        <Author>Garghentini, Davide</Author>  
        <Title>XML Developer's Guide</Title>  
        <Price>44.95</Price>  
        <Description>  
          An in-depth look at creating applications  
          with <technology>XML</technology>. For   
          <audience>beginners</audience> or   
          <audience>advanced</audience> developers.  
        </Description>  
      </Book>  
      <Book id="bk331">  
        <Author>Spencer, Phil</Author>  
        <Title>Developing Applications with Visual Basic .NET</Title>  
        <Price>45.95</Price>  
        <Description>  
          Get the expert insights, practical code samples, and best  
          practices you need to advance your expertise with   
          <technology>Visual Basic .NET</technology>.   
          Learn how to create faster, more reliable applications  
          based on professional, pragmatic guidance by today's top  
          <audience>developers</audience>.  
        </Description>  
      </Book>  
    </Catalog>  
  
    Modified XML:  
    <?xml version="1.0"?>  
    <Catalog>  
      <Book id="bk101">  
        <Author>Garghentini, Davide</Author>  
        <Title>XML Developer's Guide</Title>  
        <MSRP>44.95</MSRP>    <Abstract>  
          An in-depth look at creating applications  
          with <technology>XML</technology>. For   
          <audience>beginners</audience> or   
          <audience>advanced</audience> developers.  
        </Abstract>  
      </Book>  
      <Book id="bk331">  
        <Author>Spencer, Phil</Author>  
        <Title>Developing Applications with Visual Basic .NET</Title>  
        <MSRP>45.95</MSRP>    <Abstract>  
          Get the expert insights, practical code samples, and best  
          practices you need to advance your expertise with   
          <technology>Visual Basic .NET</technology>.   
          Learn how to create faster, more reliable applications  
          based on professional, pragmatic guidance by today's top  
          <audience>developers</audience>.  
        </Abstract>  
      </Book>  
    </Catalog>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="9a090-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9a090-146">See Also</span></span>  
 <span data-ttu-id="9a090-147">[Modifica di XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md) </span><span class="sxs-lookup"><span data-stu-id="9a090-147">[Manipulating XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md) </span></span>  
<span data-ttu-id="9a090-148"> [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md) </span><span class="sxs-lookup"><span data-stu-id="9a090-148"> [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md) </span></span>  
<span data-ttu-id="9a090-149"> [Procedura: caricare XML da un File, stringa o flusso](../../../../visual-basic/programming-guide/language-features/xml/how-to-load-xml-from-a-file-string-or-stream.md) </span><span class="sxs-lookup"><span data-stu-id="9a090-149"> [How to: Load XML from a File, String, or Stream](../../../../visual-basic/programming-guide/language-features/xml/how-to-load-xml-from-a-file-string-or-stream.md) </span></span>  
<span data-ttu-id="9a090-150"> [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md) </span><span class="sxs-lookup"><span data-stu-id="9a090-150"> [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md) </span></span>  
<span data-ttu-id="9a090-151"> [Introduzione a LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)</span><span class="sxs-lookup"><span data-stu-id="9a090-151"> [Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)</span></span>
