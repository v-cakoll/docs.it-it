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
# <a name="how-to-modify-xml-literals-visual-basic"></a>Procedura: modificare valori letterali XML (Visual Basic)

Visual Basic offre modi pratici per modificare i valori letterali XML. È possibile aggiungere o eliminare elementi e attributi ed è inoltre possibile sostituire un elemento esistente con un nuovo elemento XML. In questo argomento vengono forniti alcuni esempi di come modificare un valore letterale XML esistente.

### <a name="to-modify-the-value-of-an-xml-literal"></a>Per modificare il valore di un valore letterale XML

1. Per modificare il valore di un valore letterale XML, ottenere un riferimento al valore letterale XML e impostare la `Value` proprietà sul valore desiderato.

    Nell'esempio di codice seguente viene aggiornato il valore di tutti gli \<Price> elementi di un documento XML.

    [!code-vb[VbXmlSamples2#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXmlSamples2/VB/Module2.vb#4)]

    Di seguito vengono illustrati XML di origine di esempio e XML modificato da questo esempio di codice.

    XML di origine:

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

    XML modificato:

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
    > La `Value` proprietà si riferisce al primo elemento XML in una raccolta. Se è presente più di un elemento con lo stesso nome in una raccolta, l'impostazione della `Value` proprietà ha effetto solo sul primo elemento della raccolta.

### <a name="to-add-an-attribute-to-an-xml-literal"></a>Per aggiungere un attributo a un valore letterale XML

1. Per aggiungere un attributo a un valore letterale XML, ottenere prima un riferimento al valore letterale XML. È quindi possibile aggiungere un attributo aggiungendo una nuova proprietà axis dell'attributo XML. È anche possibile aggiungere un nuovo <xref:System.Xml.Linq.XAttribute> oggetto al valore letterale XML usando il <xref:System.Xml.Linq.XContainer.Add%2A> metodo. Nell'esempio seguente vengono illustrate entrambe le opzioni.

    [!code-vb[VbXmlSamples2#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXmlSamples2/VB/Module2.vb#5)]

    Di seguito vengono illustrati XML di origine di esempio e XML modificato da questo esempio di codice.

    XML di origine:

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

    XML modificato:

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

    Per ulteriori informazioni sulle proprietà axis dell'attributo XML, vedere [Proprietà Axis dell'attributo XML](../../../language-reference/xml-axis/xml-attribute-axis-property.md).

### <a name="to-add-an-element-to-an-xml-literal"></a>Per aggiungere un elemento a un valore letterale XML

1. Per aggiungere un elemento a un valore letterale XML, ottenere prima un riferimento al valore letterale XML. È quindi possibile aggiungere un nuovo <xref:System.Xml.Linq.XElement> oggetto come ultimo sottoelemento dell'elemento utilizzando il <xref:System.Xml.Linq.XContainer.Add%2A> metodo. È possibile aggiungere un nuovo <xref:System.Xml.Linq.XElement> oggetto come primo sottoelemento usando il <xref:System.Xml.Linq.XContainer.AddFirst%2A> metodo.

    Per aggiungere un nuovo elemento in una posizione specifica rispetto ad altri elementi secondari, ottenere prima un riferimento a un sottoelemento adiacente. È quindi possibile aggiungere il nuovo <xref:System.Xml.Linq.XElement> oggetto prima del sottoelemento adiacente usando il <xref:System.Xml.Linq.XNode.AddBeforeSelf%2A> metodo. È anche possibile aggiungere il nuovo <xref:System.Xml.Linq.XElement> oggetto dopo il sottoelemento adiacente usando il <xref:System.Xml.Linq.XNode.AddAfterSelf%2A> metodo.

    Nell'esempio seguente vengono illustrati alcuni esempi di queste tecniche.

    [!code-vb[VbXmlSamples2#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXmlSamples2/VB/Module2.vb#6)]

    Di seguito vengono illustrati XML di origine di esempio e XML modificato da questo esempio di codice.

    XML di origine:

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

    XML modificato:

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

### <a name="to-remove-an-element-or-attribute-from-an-xml-literal"></a>Per rimuovere un elemento o un attributo da un valore letterale XML

1. Per rimuovere un elemento o un attributo da un valore letterale XML, ottenere un riferimento all'elemento o all'attributo e chiamare il `Remove` metodo, come illustrato nell'esempio seguente.

    [!code-vb[VbXmlSamples2#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXmlSamples2/VB/Module2.vb#7)]

    Di seguito vengono illustrati XML di origine di esempio e XML modificato da questo esempio di codice.

    XML di origine:

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

    XML modificato:

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

    Per rimuovere tutti gli elementi o gli attributi da un valore letterale XML, ottenere un riferimento al valore letterale XML e chiamare il <xref:System.Xml.Linq.XElement.RemoveAll%2A> metodo.

### <a name="to-modify-an-xml-literal"></a>Per modificare un valore letterale XML

1. Per modificare il nome di un elemento XML, ottenere prima un riferimento all'elemento. È quindi possibile creare un nuovo <xref:System.Xml.Linq.XElement> oggetto con un nuovo nome e passare il nuovo <xref:System.Xml.Linq.XElement> oggetto al <xref:System.Xml.Linq.XNode.ReplaceWith%2A> metodo dell' <xref:System.Xml.Linq.XElement> oggetto esistente.

    Se l'elemento che si sta sostituendo contiene sottoelementi che devono essere conservati, impostare il valore del nuovo <xref:System.Xml.Linq.XElement> oggetto sulla <xref:System.Xml.Linq.XContainer.Nodes%2A> proprietà dell'elemento esistente. Il valore del nuovo elemento verrà impostato sul codice XML interno dell'elemento esistente. In caso contrario, è possibile impostare il valore del nuovo elemento sulla `Value` proprietà dell'elemento esistente.

    L'esempio di codice seguente sostituisce tutti \<Description> gli elementi con un \<Abstract> elemento. Il contenuto dell' \<Description> elemento viene mantenuto nel nuovo \<Abstract> elemento utilizzando la <xref:System.Xml.Linq.XContainer.Nodes%2A> proprietà dell' \<Description> <xref:System.Xml.Linq.XElement> oggetto.

    [!code-vb[VbXmlSamples2#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXmlSamples2/VB/Module2.vb#8)]

    Di seguito vengono illustrati XML di origine di esempio e XML modificato da questo esempio di codice.

    XML di origine:

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

    XML modificato:

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

## <a name="see-also"></a>Vedere anche

- [Modifica di XML in Visual Basic](manipulating-xml.md)
- [XML](index.md)
- [Procedura: caricare XML da un file, da una stringa o da un flusso](how-to-load-xml-from-a-file-string-or-stream.md)
- [LINQ](../linq/index.md)
- [Introduzione a LINQ in Visual Basic](../linq/introduction-to-linq.md)
