---
title: 'Procedura: modificare valori letterali XML'
ms.date: 07/20/2015
helpviewer_keywords:
- XML axis [Visual Basic], Value
- XML literals [Visual Basic]
- XML literals [Visual Basic], modifying
ms.assetid: 4e864522-a37a-43a2-8236-af80277c5482
ms.openlocfilehash: a2ac2e9802d4c8ab522bb430d15cce5616430437
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84374879"
---
# <a name="how-to-modify-xml-literals-visual-basic"></a><span data-ttu-id="b226e-102">Procedura: modificare valori letterali XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b226e-102">How to: Modify XML Literals (Visual Basic)</span></span>

<span data-ttu-id="b226e-103">Visual Basic offre modi pratici per modificare i valori letterali XML.</span><span class="sxs-lookup"><span data-stu-id="b226e-103">Visual Basic provides convenient ways to modify XML literals.</span></span> <span data-ttu-id="b226e-104">È possibile aggiungere o eliminare elementi e attributi ed è inoltre possibile sostituire un elemento esistente con un nuovo elemento XML.</span><span class="sxs-lookup"><span data-stu-id="b226e-104">You can add or delete elements and attributes, and you can also replace an existing element with a new XML element.</span></span> <span data-ttu-id="b226e-105">In questo argomento vengono forniti alcuni esempi di come modificare un valore letterale XML esistente.</span><span class="sxs-lookup"><span data-stu-id="b226e-105">This topic provides several examples of how to modify an existing XML literal.</span></span>

### <a name="to-modify-the-value-of-an-xml-literal"></a><span data-ttu-id="b226e-106">Per modificare il valore di un valore letterale XML</span><span class="sxs-lookup"><span data-stu-id="b226e-106">To modify the value of an XML literal</span></span>

1. <span data-ttu-id="b226e-107">Per modificare il valore di un valore letterale XML, ottenere un riferimento al valore letterale XML e impostare la `Value` proprietà sul valore desiderato.</span><span class="sxs-lookup"><span data-stu-id="b226e-107">To modify the value of an XML literal, obtain a reference to the XML literal and set the `Value` property to the desired value.</span></span>

    <span data-ttu-id="b226e-108">Nell'esempio di codice seguente viene aggiornato il valore di tutti gli \<Price> elementi di un documento XML.</span><span class="sxs-lookup"><span data-stu-id="b226e-108">The following code example updates the value of all the \<Price> elements in an XML document.</span></span>

    [!code-vb[VbXmlSamples2#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXmlSamples2/VB/Module2.vb#4)]

    <span data-ttu-id="b226e-109">Di seguito vengono illustrati XML di origine di esempio e XML modificato da questo esempio di codice.</span><span class="sxs-lookup"><span data-stu-id="b226e-109">The following shows sample source XML and modified XML from this code example.</span></span>

    <span data-ttu-id="b226e-110">XML di origine:</span><span class="sxs-lookup"><span data-stu-id="b226e-110">Source XML:</span></span>

    ```xml
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
    ```

    <span data-ttu-id="b226e-111">XML modificato:</span><span class="sxs-lookup"><span data-stu-id="b226e-111">Modified XML:</span></span>

    ```xml
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
    > <span data-ttu-id="b226e-112">La `Value` proprietà si riferisce al primo elemento XML in una raccolta.</span><span class="sxs-lookup"><span data-stu-id="b226e-112">The `Value` property refers to the first XML element in a collection.</span></span> <span data-ttu-id="b226e-113">Se è presente più di un elemento con lo stesso nome in una raccolta, l'impostazione della `Value` proprietà ha effetto solo sul primo elemento della raccolta.</span><span class="sxs-lookup"><span data-stu-id="b226e-113">If there is more than one element that has the same name in a collection, setting the `Value` property affects only the first element in the collection.</span></span>

### <a name="to-add-an-attribute-to-an-xml-literal"></a><span data-ttu-id="b226e-114">Per aggiungere un attributo a un valore letterale XML</span><span class="sxs-lookup"><span data-stu-id="b226e-114">To add an attribute to an XML literal</span></span>

1. <span data-ttu-id="b226e-115">Per aggiungere un attributo a un valore letterale XML, ottenere prima un riferimento al valore letterale XML.</span><span class="sxs-lookup"><span data-stu-id="b226e-115">To add an attribute to an XML literal, first obtain a reference to the XML literal.</span></span> <span data-ttu-id="b226e-116">È quindi possibile aggiungere un attributo aggiungendo una nuova proprietà axis dell'attributo XML.</span><span class="sxs-lookup"><span data-stu-id="b226e-116">You can then add an attribute by adding a new XML attribute axis property.</span></span> <span data-ttu-id="b226e-117">È anche possibile aggiungere un nuovo <xref:System.Xml.Linq.XAttribute> oggetto al valore letterale XML usando il <xref:System.Xml.Linq.XContainer.Add%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="b226e-117">You can also add a new <xref:System.Xml.Linq.XAttribute> object to the XML literal by using the <xref:System.Xml.Linq.XContainer.Add%2A> method.</span></span> <span data-ttu-id="b226e-118">Nell'esempio seguente vengono illustrate entrambe le opzioni.</span><span class="sxs-lookup"><span data-stu-id="b226e-118">The following example shows both options.</span></span>

    [!code-vb[VbXmlSamples2#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXmlSamples2/VB/Module2.vb#5)]

    <span data-ttu-id="b226e-119">Di seguito vengono illustrati XML di origine di esempio e XML modificato da questo esempio di codice.</span><span class="sxs-lookup"><span data-stu-id="b226e-119">The following shows sample source XML and modified XML from this code example.</span></span>

    <span data-ttu-id="b226e-120">XML di origine:</span><span class="sxs-lookup"><span data-stu-id="b226e-120">Source XML:</span></span>

    ```xml
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
    ```

    <span data-ttu-id="b226e-121">XML modificato:</span><span class="sxs-lookup"><span data-stu-id="b226e-121">Modified XML:</span></span>

    ```xml
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

    <span data-ttu-id="b226e-122">Per ulteriori informazioni sulle proprietà axis dell'attributo XML, vedere [Proprietà Axis dell'attributo XML](../../../language-reference/xml-axis/xml-attribute-axis-property.md).</span><span class="sxs-lookup"><span data-stu-id="b226e-122">For more information about XML attribute axis properties, see [XML Attribute Axis Property](../../../language-reference/xml-axis/xml-attribute-axis-property.md).</span></span>

### <a name="to-add-an-element-to-an-xml-literal"></a><span data-ttu-id="b226e-123">Per aggiungere un elemento a un valore letterale XML</span><span class="sxs-lookup"><span data-stu-id="b226e-123">To add an element to an XML literal</span></span>

1. <span data-ttu-id="b226e-124">Per aggiungere un elemento a un valore letterale XML, ottenere prima un riferimento al valore letterale XML.</span><span class="sxs-lookup"><span data-stu-id="b226e-124">To add an element to an XML literal, first obtain a reference to the XML literal.</span></span> <span data-ttu-id="b226e-125">È quindi possibile aggiungere un nuovo <xref:System.Xml.Linq.XElement> oggetto come ultimo sottoelemento dell'elemento utilizzando il <xref:System.Xml.Linq.XContainer.Add%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="b226e-125">You can then add a new <xref:System.Xml.Linq.XElement> object as the last sub-element of the element by using the <xref:System.Xml.Linq.XContainer.Add%2A> method.</span></span> <span data-ttu-id="b226e-126">È possibile aggiungere un nuovo <xref:System.Xml.Linq.XElement> oggetto come primo sottoelemento usando il <xref:System.Xml.Linq.XContainer.AddFirst%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="b226e-126">You can add a new <xref:System.Xml.Linq.XElement> object as the first sub-element by using the <xref:System.Xml.Linq.XContainer.AddFirst%2A> method.</span></span>

    <span data-ttu-id="b226e-127">Per aggiungere un nuovo elemento in una posizione specifica rispetto ad altri elementi secondari, ottenere prima un riferimento a un sottoelemento adiacente.</span><span class="sxs-lookup"><span data-stu-id="b226e-127">To add a new element in a specific location relative to other sub-elements, first obtain a reference to an adjacent sub-element.</span></span> <span data-ttu-id="b226e-128">È quindi possibile aggiungere il nuovo <xref:System.Xml.Linq.XElement> oggetto prima del sottoelemento adiacente usando il <xref:System.Xml.Linq.XNode.AddBeforeSelf%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="b226e-128">You can then add the new <xref:System.Xml.Linq.XElement> object before the adjacent sub-element by using the <xref:System.Xml.Linq.XNode.AddBeforeSelf%2A> method.</span></span> <span data-ttu-id="b226e-129">È anche possibile aggiungere il nuovo <xref:System.Xml.Linq.XElement> oggetto dopo il sottoelemento adiacente usando il <xref:System.Xml.Linq.XNode.AddAfterSelf%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="b226e-129">You can also add the new <xref:System.Xml.Linq.XElement> object after the adjacent sub-element by using the <xref:System.Xml.Linq.XNode.AddAfterSelf%2A> method.</span></span>

    <span data-ttu-id="b226e-130">Nell'esempio seguente vengono illustrati alcuni esempi di queste tecniche.</span><span class="sxs-lookup"><span data-stu-id="b226e-130">The following example shows examples of each of these techniques.</span></span>

    [!code-vb[VbXmlSamples2#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXmlSamples2/VB/Module2.vb#6)]

    <span data-ttu-id="b226e-131">Di seguito vengono illustrati XML di origine di esempio e XML modificato da questo esempio di codice.</span><span class="sxs-lookup"><span data-stu-id="b226e-131">The following shows sample source XML and modified XML from this code example.</span></span>

    <span data-ttu-id="b226e-132">XML di origine:</span><span class="sxs-lookup"><span data-stu-id="b226e-132">Source XML:</span></span>

    ```xml
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
    ```

    <span data-ttu-id="b226e-133">XML modificato:</span><span class="sxs-lookup"><span data-stu-id="b226e-133">Modified XML:</span></span>

    ```xml
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

### <a name="to-remove-an-element-or-attribute-from-an-xml-literal"></a><span data-ttu-id="b226e-134">Per rimuovere un elemento o un attributo da un valore letterale XML</span><span class="sxs-lookup"><span data-stu-id="b226e-134">To remove an element or attribute from an XML literal</span></span>

1. <span data-ttu-id="b226e-135">Per rimuovere un elemento o un attributo da un valore letterale XML, ottenere un riferimento all'elemento o all'attributo e chiamare il `Remove` metodo, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="b226e-135">To remove an element or an attribute from an XML literal, obtain a reference to the element or attribute and call the `Remove` method, as shown in the following example.</span></span>

    [!code-vb[VbXmlSamples2#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXmlSamples2/VB/Module2.vb#7)]

    <span data-ttu-id="b226e-136">Di seguito vengono illustrati XML di origine di esempio e XML modificato da questo esempio di codice.</span><span class="sxs-lookup"><span data-stu-id="b226e-136">The following shows sample source XML and modified XML from this code example.</span></span>

    <span data-ttu-id="b226e-137">XML di origine:</span><span class="sxs-lookup"><span data-stu-id="b226e-137">Source XML:</span></span>

    ```xml
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
    ```

    <span data-ttu-id="b226e-138">XML modificato:</span><span class="sxs-lookup"><span data-stu-id="b226e-138">Modified XML:</span></span>

    ```xml
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

    <span data-ttu-id="b226e-139">Per rimuovere tutti gli elementi o gli attributi da un valore letterale XML, ottenere un riferimento al valore letterale XML e chiamare il <xref:System.Xml.Linq.XElement.RemoveAll%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="b226e-139">To remove all elements or attributes from an XML literal, obtain a reference to the XML literal and call the <xref:System.Xml.Linq.XElement.RemoveAll%2A> method.</span></span>

### <a name="to-modify-an-xml-literal"></a><span data-ttu-id="b226e-140">Per modificare un valore letterale XML</span><span class="sxs-lookup"><span data-stu-id="b226e-140">To modify an XML literal</span></span>

1. <span data-ttu-id="b226e-141">Per modificare il nome di un elemento XML, ottenere prima un riferimento all'elemento.</span><span class="sxs-lookup"><span data-stu-id="b226e-141">To change the name of an XML element, first obtain a reference to the element.</span></span> <span data-ttu-id="b226e-142">È quindi possibile creare un nuovo <xref:System.Xml.Linq.XElement> oggetto con un nuovo nome e passare il nuovo <xref:System.Xml.Linq.XElement> oggetto al <xref:System.Xml.Linq.XNode.ReplaceWith%2A> metodo dell' <xref:System.Xml.Linq.XElement> oggetto esistente.</span><span class="sxs-lookup"><span data-stu-id="b226e-142">You can then create a new <xref:System.Xml.Linq.XElement> object that has a new name and pass the new <xref:System.Xml.Linq.XElement> object to the <xref:System.Xml.Linq.XNode.ReplaceWith%2A> method of the existing <xref:System.Xml.Linq.XElement> object.</span></span>

    <span data-ttu-id="b226e-143">Se l'elemento che si sta sostituendo contiene sottoelementi che devono essere conservati, impostare il valore del nuovo <xref:System.Xml.Linq.XElement> oggetto sulla <xref:System.Xml.Linq.XContainer.Nodes%2A> proprietà dell'elemento esistente.</span><span class="sxs-lookup"><span data-stu-id="b226e-143">If the element that you are replacing has sub-elements that must be preserved, set the value of the new <xref:System.Xml.Linq.XElement> object to the <xref:System.Xml.Linq.XContainer.Nodes%2A> property of the existing element.</span></span> <span data-ttu-id="b226e-144">Il valore del nuovo elemento verrà impostato sul codice XML interno dell'elemento esistente.</span><span class="sxs-lookup"><span data-stu-id="b226e-144">This will set the value of the new element to the inner XML of the existing element.</span></span> <span data-ttu-id="b226e-145">In caso contrario, è possibile impostare il valore del nuovo elemento sulla `Value` proprietà dell'elemento esistente.</span><span class="sxs-lookup"><span data-stu-id="b226e-145">Otherwise, you can set the value of the new element to the `Value` property of the existing element.</span></span>

    <span data-ttu-id="b226e-146">L'esempio di codice seguente sostituisce tutti \<Description> gli elementi con un \<Abstract> elemento.</span><span class="sxs-lookup"><span data-stu-id="b226e-146">The following code example replaces all \<Description> elements with an \<Abstract> element.</span></span> <span data-ttu-id="b226e-147">Il contenuto dell' \<Description> elemento viene mantenuto nel nuovo \<Abstract> elemento utilizzando la <xref:System.Xml.Linq.XContainer.Nodes%2A> proprietà dell' \<Description> <xref:System.Xml.Linq.XElement> oggetto.</span><span class="sxs-lookup"><span data-stu-id="b226e-147">The content of the \<Description> element is preserved in the new \<Abstract> element by using the <xref:System.Xml.Linq.XContainer.Nodes%2A> property of the \<Description> <xref:System.Xml.Linq.XElement> object.</span></span>

    [!code-vb[VbXmlSamples2#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXmlSamples2/VB/Module2.vb#8)]

    <span data-ttu-id="b226e-148">Di seguito vengono illustrati XML di origine di esempio e XML modificato da questo esempio di codice.</span><span class="sxs-lookup"><span data-stu-id="b226e-148">The following shows sample source XML and modified XML from this code example.</span></span>

    <span data-ttu-id="b226e-149">XML di origine:</span><span class="sxs-lookup"><span data-stu-id="b226e-149">Source XML:</span></span>

    ```xml
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
    ```

    <span data-ttu-id="b226e-150">XML modificato:</span><span class="sxs-lookup"><span data-stu-id="b226e-150">Modified XML:</span></span>

    ```xml
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

## <a name="see-also"></a><span data-ttu-id="b226e-151">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b226e-151">See also</span></span>

- [<span data-ttu-id="b226e-152">Modifica di XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b226e-152">Manipulating XML in Visual Basic</span></span>](manipulating-xml.md)
- [<span data-ttu-id="b226e-153">XML</span><span class="sxs-lookup"><span data-stu-id="b226e-153">XML</span></span>](index.md)
- [<span data-ttu-id="b226e-154">Procedura: caricare XML da un file, da una stringa o da un flusso</span><span class="sxs-lookup"><span data-stu-id="b226e-154">How to: Load XML from a File, String, or Stream</span></span>](how-to-load-xml-from-a-file-string-or-stream.md)
- [<span data-ttu-id="b226e-155">LINQ</span><span class="sxs-lookup"><span data-stu-id="b226e-155">LINQ</span></span>](../linq/index.md)
- [<span data-ttu-id="b226e-156">Introduzione a LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b226e-156">Introduction to LINQ in Visual Basic</span></span>](../linq/introduction-to-linq.md)
