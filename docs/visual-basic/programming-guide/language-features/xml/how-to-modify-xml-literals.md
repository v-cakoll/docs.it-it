---
title: 'Procedura: modificare valori letterali XML (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XML axis [Visual Basic], Value
- XML literals [Visual Basic]
- XML literals [Visual Basic], modifying
ms.assetid: 4e864522-a37a-43a2-8236-af80277c5482
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: bdc60542477d15f4fe9dd85dae4c9a918e695740
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-modify-xml-literals-visual-basic"></a>Procedura: modificare valori letterali XML (Visual Basic)
[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]Consente di modificare i valori letterali XML agevolmente. È possibile aggiungere o eliminare elementi e attributi ed è inoltre possibile sostituire un elemento esistente con un nuovo elemento XML. In questo argomento fornisce alcuni esempi di come modificare un valore letterale XML esistente.  
  
### <a name="to-modify-the-value-of-an-xml-literal"></a>Per modificare il valore di un valore letterale XML  
  
1.  Per modificare il valore di un valore letterale XML, ottenere un riferimento al codice XML letterale e impostare il `Value` proprietà sul valore desiderato.  
  
     Nell'esempio seguente aggiorna il valore di tutti i \<prezzo > elementi in un documento XML.  
  
     [!code-vb[VbXmlSamples2#4](../../../../visual-basic/programming-guide/language-features/xml/codesnippet/VisualBasic/how-to-modify-xml-literals_1.vb)]  
  
     Di seguito viene illustrato XML di origine e quello modificato da questo esempio di codice.  
  
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
    >  Il `Value` proprietà fa riferimento al primo elemento in una raccolta di XML. Se è presente più di un elemento che ha lo stesso nome in una raccolta, l'impostazione di `Value` proprietà interessa solo il primo elemento nella raccolta.  
  
### <a name="to-add-an-attribute-to-an-xml-literal"></a>Per aggiungere un attributo a un valore letterale XML  
  
1.  Per aggiungere un attributo a un valore letterale XML, è innanzitutto ottenere un riferimento al valore letterale XML. È quindi possibile aggiungere un attributo mediante l'aggiunta di una nuova proprietà axis dell'attributo XML. È inoltre possibile aggiungere un nuovo <xref:System.Xml.Linq.XAttribute> oggetto per il valore letterale XML tramite il <xref:System.Xml.Linq.XContainer.Add%2A> metodo. Nell'esempio seguente illustra entrambe le opzioni.  
  
     [!code-vb[VbXmlSamples2#5](../../../../visual-basic/programming-guide/language-features/xml/codesnippet/VisualBasic/how-to-modify-xml-literals_2.vb)]  
  
     Di seguito viene illustrato XML di origine e quello modificato da questo esempio di codice.  
  
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
  
     Per ulteriori informazioni sulle proprietà asse attributo XML, vedere [proprietà asse attributo XML](../../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md).  
  
### <a name="to-add-an-element-to-an-xml-literal"></a>Per aggiungere un elemento a un valore letterale XML  
  
1.  Per aggiungere un elemento a un valore letterale XML, è innanzitutto ottenere un riferimento al valore letterale XML. È quindi possibile aggiungere un nuovo <xref:System.Xml.Linq.XElement> oggetto come ultimo sottoelemento dell'elemento utilizzando il <xref:System.Xml.Linq.XContainer.Add%2A> metodo. È possibile aggiungere un nuovo <xref:System.Xml.Linq.XElement> oggetto come primo sottoelemento dell'elemento utilizzando il <xref:System.Xml.Linq.XContainer.AddFirst%2A> metodo.  
  
     Per aggiungere un nuovo elemento in un percorso specifico rispetto agli altri sottoelementi, innanzitutto ottenere un riferimento a un sottoelemento adiacente. È quindi possibile aggiungere il nuovo <xref:System.Xml.Linq.XElement> oggetto prima del sottoelemento adiacente utilizzando il <xref:System.Xml.Linq.XNode.AddBeforeSelf%2A> metodo. È inoltre possibile aggiungere il nuovo <xref:System.Xml.Linq.XElement> oggetto dopo il sottoelemento adiacente utilizzando il <xref:System.Xml.Linq.XNode.AddAfterSelf%2A> metodo.  
  
     Nell'esempio seguente vengono illustrati esempi di ognuna di queste tecniche.  
  
     [!code-vb[VbXmlSamples2#6](../../../../visual-basic/programming-guide/language-features/xml/codesnippet/VisualBasic/how-to-modify-xml-literals_3.vb)]  
  
     Di seguito viene illustrato XML di origine e quello modificato da questo esempio di codice.  
  
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
  
### <a name="to-remove-an-element-or-attribute-from-an-xml-literal"></a>Per rimuovere un elemento o attributo da un valore letterale XML  
  
1.  Per rimuovere un elemento o un attributo da un valore letterale XML, ottenere un riferimento per l'elemento o attributo e chiamare il `Remove` (metodo), come illustrato nell'esempio seguente.  
  
     [!code-vb[VbXmlSamples2#7](../../../../visual-basic/programming-guide/language-features/xml/codesnippet/VisualBasic/how-to-modify-xml-literals_4.vb)]  
  
     Di seguito viene illustrato XML di origine e quello modificato da questo esempio di codice.  
  
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
  
     Per rimuovere tutti gli elementi o attributi da un valore letterale XML, ottenere un riferimento al valore letterale XML e chiamare il <xref:System.Xml.Linq.XElement.RemoveAll%2A> metodo.  
  
### <a name="to-modify-an-xml-literal"></a>Per modificare un valore letterale XML  
  
1.  Per modificare il nome di un elemento XML, è innanzitutto ottenere un riferimento all'elemento. È quindi possibile creare un nuovo <xref:System.Xml.Linq.XElement> oggetto con un nuovo nome e passa il nuovo <xref:System.Xml.Linq.XElement> dell'oggetto per il <xref:System.Xml.Linq.XNode.ReplaceWith%2A> metodo dell'oggetto esistente <xref:System.Xml.Linq.XElement> oggetto.  
  
     Se l'elemento che si sta sostituendo ha sottoelementi che devono essere mantenuti, impostare il valore del nuovo <xref:System.Xml.Linq.XElement> dell'oggetto per il <xref:System.Xml.Linq.XContainer.Nodes%2A> proprietà dell'elemento esistente. Si imposterà il valore del nuovo elemento al codice XML interno dell'elemento esistente. In caso contrario, è possibile impostare il valore del nuovo elemento per il `Value` proprietà dell'elemento esistente.  
  
     Esempio di codice seguente sostituisce tutte \<descrizione > gli elementi con un \<astratta > elemento. Il contenuto del \<descrizione > elemento viene mantenuto nel nuovo \<astratta > elemento utilizzando il <xref:System.Xml.Linq.XContainer.Nodes%2A> proprietà del \<descrizione > <xref:System.Xml.Linq.XElement> oggetto.  
  
     [!code-vb[VbXmlSamples2#8](../../../../visual-basic/programming-guide/language-features/xml/codesnippet/VisualBasic/how-to-modify-xml-literals_5.vb)]  
  
     Di seguito viene illustrato XML di origine e quello modificato da questo esempio di codice.  
  
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
  
## <a name="see-also"></a>Vedere anche  
 [Modifica di XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)  
 [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)  
 [Procedura: Caricare XML da un file, da una stringa o da un flusso](../../../../visual-basic/programming-guide/language-features/xml/how-to-load-xml-from-a-file-string-or-stream.md)  
 [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 [Introduzione a LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
