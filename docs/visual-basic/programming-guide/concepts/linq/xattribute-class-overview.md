---
title: Panoramica della classe XAttribute
ms.date: 07/20/2015
ms.assetid: 7781580a-9583-4a1b-ae1e-91c5936eb0b1
ms.openlocfilehash: ceafe5478e41fb4c2038fd9300ef7b1ee6cb8411
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/03/2020
ms.locfileid: "75636653"
---
# <a name="xattribute-class-overview-visual-basic"></a>Panoramica della classe XAttribute (Visual Basic)
Gli attributi sono coppie nome/valore associate a un elemento. La classe <xref:System.Xml.Linq.XAttribute> rappresenta gli attributi XML.  
  
## <a name="overview"></a>Panoramica di  
 Le modalità di utilizzo degli attributi in [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] sono simili a quelle degli elementi. I relativi costruttori sono simili. I metodi usati per recuperare le relative raccolte sono simili. Un'espressione di query LINQ per una raccolta di attributi ha un aspetto molto simile a un'espressione di query LINQ per una raccolta di elementi.  
  
 L'ordine con cui gli attributi vengono aggiunti a un elemento viene mantenuto. Quando si scorrono gli attributi, questi vengono visualizzati nell'ordine in cui sono stati aggiunti.  
  
## <a name="the-xattribute-constructor"></a>Costruttore XAttribute  
 Il seguente costruttore della classe <xref:System.Xml.Linq.XAttribute> è quello usato più comunemente:  
  
|Costruttore|Descrizione|  
|-----------------|-----------------|  
|`XAttribute(XName name, object content)`|Crea un oggetto <xref:System.Xml.Linq.XAttribute>. L'argomento `name` specifica il nome dell'attributo, mentre `content` ne specifica il contenuto.|  
  
### <a name="creating-an-element-with-an-attribute"></a>Creazione di un elemento con un attributo  
 Il codice seguente illustra un elemento che contiene un attributo che usa valori letterali XML in Visual Basic:  
  
```vb  
Dim phone As XElement = <Phone Type="Home">555-555-5555</Phone>  
Console.WriteLine(phone)  
```  
  
 Questo esempio produce il seguente output:  
  
```xml  
<Phone Type="Home">555-555-5555</Phone>  
```  
  
### <a name="functional-construction-of-attributes"></a>Costruzione funzionale di attributi  
 È possibile costruire oggetti <xref:System.Xml.Linq.XAttribute> in linea con la costruzione di oggetti <xref:System.Xml.Linq.XElement>, come descritto di seguito:  
  
```vb  
Dim c As XElement = _  
    <Customers>  
        <Customer>  
            <Name>John Doe</Name>  
            <PhoneNumbers>  
                <Phone type="home">555-555-5555</Phone>  
                <Phone type="work">666-666-6666</Phone>  
            </PhoneNumbers>  
        </Customer>  
    </Customers>  
Console.WriteLine(c)  
```  
  
 Questo esempio produce il seguente output:  
  
```xml  
<Customers>  
  <Customer>  
    <Name>John Doe</Name>  
    <PhoneNumbers>  
      <Phone type="home">555-555-5555</Phone>  
      <Phone type="work">666-666-6666</Phone>  
    </PhoneNumbers>  
  </Customer>  
</Customers>  
```  
  
### <a name="attributes-are-not-nodes"></a>Attributi non nodi  
 Esistono alcune differenze tra attributi ed elementi. Gli oggetti <xref:System.Xml.Linq.XAttribute> non rappresentano nodi nell'albero XML, ma sono coppie nome/valore associate a un elemento XML. A differenza del modello DOM (Document Object Model), questa definizione rispecchia maggiormente la struttura del codice XML. Sebbene gli oggetti <xref:System.Xml.Linq.XAttribute> non siano effettivamente nodi dell'albero XML, le modalità di utilizzo degli oggetti <xref:System.Xml.Linq.XAttribute> sono molto simili a quelle degli oggetti <xref:System.Xml.Linq.XElement>.  
  
 Questa distinzione è di fondamentale importanza solo per gli sviluppatori che scrivono codice che riguarda gli alberi XML a livello di nodo. Non interessa quindi la maggior parte degli sviluppatori.  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica della programmazione LINQ to XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-programming-overview.md)
