---
title: Controllo della serializzazione XML mediante attributi
description: Gli attributi possono essere utilizzati per controllare la serializzazione XML di un oggetto o per creare un flusso XML alternativo dallo stesso set di classi.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- classes, serializing
- XML serialization, examples
- derived classes, serializing
- arrays, serializing
- XML serialization, attributes
- preventing serialization
- attributes [.NET Framework], XML serialization
- serialization, examples
- serialization, attributes
ms.assetid: 47d4c39d-30e1-4c7b-8a2e-301325390647
ms.openlocfilehash: 79c5541b4c384e91fbec8c8f1b2130887e79a252
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "84289681"
---
# <a name="controlling-xml-serialization-using-attributes"></a>Controllo della serializzazione XML mediante attributi

Gli attributi possono essere utilizzati per controllare la serializzazione XML di un oggetto o per creare un flusso XML alternativo dallo stesso set di classi. Per altri dettagli sulla creazione di un flusso XML alternativo, vedere [Procedura: Specificare un nome di elemento alternativo per un flusso XML](how-to-specify-an-alternate-element-name-for-an-xml-stream.md).

> [!NOTE]
> Se il codice XML generato deve essere conforme alla sezione 5 del documento World Wide Web Consortium (W3C) denominato [Simple Object Access Protocol (SOAP) 1,1](https://www.w3.org/TR/2000/NOTE-SOAP-20000508/), utilizzare gli attributi elencati negli [attributi che controllano la serializzazione SOAP codificata](attributes-that-control-encoded-soap-serialization.md).

Per impostazione predefinita, un nome di elemento XML è determinato dal nome della classe o del membro. In una classe semplice denominata `Book` , un campo denominato `ISBN` produrrà un tag di elemento XML \<ISBN> , come illustrato nell'esempio seguente.

```vb
Public Class Book
    Public ISBN As String
End Class
' When an instance of the Book class is serialized, it might
' produce this XML:
' <ISBN>1234567890</ISBN>.
```

```csharp
public class Book
{
    public string ISBN;
}
// When an instance of the Book class is serialized, it might
// produce this XML:
// <ISBN>1234567890</ISBN>.
```

Questo comportamento predefinito può essere modificato se si vuole assegnare un nuovo nome all'elemento. Il codice riportato di seguito mostra il modo in cui un attributo svolge tale funzione impostando la proprietà <xref:System.Xml.Serialization.XmlElementAttribute.ElementName%2A> di una classe <xref:System.Xml.Serialization.XmlElementAttribute>.

```vb
Public Class TaxRates
   < XmlElement(ElementName = "TaxRate")> _
    Public ReturnTaxRate As Decimal
End Class
```

```csharp
public class TaxRates {
    [XmlElement(ElementName = "TaxRate")]
    public decimal ReturnTaxRate;
}
```

Per altre informazioni sugli attributi, vedere [Attributi](../attributes/index.md). Per l'elenco degli attributi che controllano la serializzazione XML, vedere [Attributi per il controllo della serializzazione XML](attributes-that-control-xml-serialization.md).

## <a name="controlling-array-serialization"></a>Controllo della serializzazione di matrice

Gli attributi <xref:System.Xml.Serialization.XmlArrayAttribute> e <xref:System.Xml.Serialization.XmlArrayItemAttribute> sono progettati per controllare la serializzazione delle matrici. Tramite l'utilizzo di questi attributi, è possibile controllare il nome dell'elemento, lo spazio dei nomi e tipo di dati XML Schema (XSD) (come definito nel documento intitolato "XML Schema Part 2: Datatypes" del World Wide Web Consortium [www.w3.org]). È inoltre possibile specificare i tipi che possono essere inclusi in una matrice.

<xref:System.Xml.Serialization.XmlArrayAttribute> determinerà le proprietà dell'elemento XML di inclusione risultante dalla serializzazione di una matrice. Ad esempio, la serializzazione della matrice riportata di seguito, per impostazione predefinita comporterà la creazione di un elemento XML denominato `Employees`. L'elemento `Employees` conterrà una serie di elementi denominati dopo il tipo di matrice `Employee`.

```vb
Public Class Group
    Public Employees() As Employee
End Class
Public Class Employee
    Public Name As String
End Class
```

```csharp
public class Group {
    public Employee[] Employees;
}
public class Employee {
    public string Name;
}
```

Un'istanza serializzata potrebbe assomigliare agli elementi seguenti.

```xml
<Group>
<Employees>
    <Employee>
        <Name>Haley</Name>
    </Employee>
</Employees>
</Group>
```

Tramite l'applicazione di un attributo <xref:System.Xml.Serialization.XmlArrayAttribute>, è possibile modificare il nome dell'elemento XML, come segue.

```vb
Public Class Group
    <XmlArray("TeamMembers")> _
    Public Employees() As Employee
End Class
```

```csharp
public class Group {
    [XmlArray("TeamMembers")]
    public Employee[] Employees;
}
```

L'XML risultante potrebbe assomigliare agli elementi seguenti.

```xml
<Group>
<TeamMembers>
    <Employee>
        <Name>Haley</Name>
    </Employee>
</TeamMembers>
</Group>
```

<xref:System.Xml.Serialization.XmlArrayItemAttribute>, d'altra parte, controlla il modo in cui vengono serializzati gli elementi contenuti nella matrice. Notare che l'attributo viene applicato al campo che restituisce la matrice.

```vb
Public Class Group
    <XmlArrayItem("MemberName")> _
    Public Employee() As Employees
End Class
```

```csharp
public class Group {
    [XmlArrayItem("MemberName")]
    public Employee[] Employees;
}
```

L'XML risultante potrebbe assomigliare agli elementi seguenti.

```xml
<Group>
<Employees>
    <MemberName>Haley</MemberName>
</Employees>
</Group>
```

## <a name="serializing-derived-classes"></a>Serializzazione delle classi derivate

Un altro utilizzo di <xref:System.Xml.Serialization.XmlArrayItemAttribute> è quello di consentire la serializzazione di classi derivate. Ad esempio, al precedente esempio è possibile aggiungere un'altra classe denominata `Manager` che deriva da `Employee`. Se non si applica <xref:System.Xml.Serialization.XmlArrayItemAttribute>, il codice provocherà un errore in fase di esecuzione perché il tipo di classe derivata non verrà riconosciuto. Per risolvere questo problema, applicare due volte l'attributo, impostando ogni volta la proprietà <xref:System.Xml.Serialization.XmlArrayItemAttribute.Type%2A> per ogni tipo accettabile (base e derivato).

```vb
Public Class Group
    <XmlArrayItem(Type:=GetType(Employee)), _
    XmlArrayItem(Type:=GetType(Manager))> _
    Public Employees() As Employee
End Class
Public Class Employee
    Public Name As String
End Class
Public Class Manager
Inherits Employee
    Public Level As Integer
End Class
```

```csharp
public class Group {
    [XmlArrayItem(Type = typeof(Employee)),
    XmlArrayItem(Type = typeof(Manager))]
    public Employee[] Employees;
}
public class Employee {
    public string Name;
}
public class Manager:Employee {
    public int Level;
}
```

Un'istanza serializzata potrebbe assomigliare agli elementi seguenti.

```xml
<Group>
<Employees>
    <Employee>
        <Name>Haley</Name>
    </Employee>
    <Employee xsi:type = "Manager">
        <Name>Ann</Name>
        <Level>3</Level>
    </Employee>
</Employees>
</Group>
```

## <a name="serializing-an-array-as-a-sequence-of-elements"></a>Serializzazione di una matrice come sequenza di elementi

È possibile anche serializzare una matrice come un'unica sequenza di elementi XML applicando un attributo <xref:System.Xml.Serialization.XmlElementAttribute> al campo che restituisce la matrice nel modo riportato di seguito.

```vb
Public Class Group
    <XmlElement> _
    Public Employees() As Employee
End Class
```

```csharp
public class Group {
    [XmlElement]
    public Employee[] Employees;
}
```

Un'istanza serializzata potrebbe assomigliare agli elementi seguenti.

```xml
<Group>
<Employees>
    <Name>Haley</Name>
</Employees>
<Employees>
    <Name>Noriko</Name>
</Employees>
<Employees>
    <Name>Marco</Name>
</Employees>
</Group>
```

Un altro modo per differenziare i due flussi XML è quello di utilizzare lo strumento XML Schema Definition per generare i file del documento XML Schema (XSD) dal codice compilato. Per ulteriori informazioni sull'utilizzo dello strumento, vedere [lo strumento XML Schema Definition e la serializzazione XML](the-xml-schema-definition-tool-and-xml-serialization.md). Quando al campo non viene applicato alcun attributo, lo schema descrive l'elemento nel modo seguente.

```xml
<xs:element minOccurs="0" maxOccurs ="1" name="Employees" type="ArrayOfEmployee" />
```

Se al campo è applicato l'attributo <xref:System.Xml.Serialization.XmlElementAttribute>, lo schema risultante descrive l'elemento nel modo riportato di seguito.

```xml
<xs:element minOccurs="0" maxOccurs="unbounded" name="Employees" type="Employee" />
```

## <a name="serializing-an-arraylist"></a>Serializzazione di un ArrayList

La classe <xref:System.Collections.ArrayList> contiene una raccolta di oggetti diversi. È quindi possibile utilizzare una classe <xref:System.Collections.ArrayList> allo stesso modo con cui si utilizza una matrice. Anziché creare un campo che restituisca una matrice di oggetti tipizzati, è tuttavia possibile creare un campo che restituisca un solo <xref:System.Collections.ArrayList>. Tuttavia, così come avviene con le matrici, è necessario informare <xref:System.Xml.Serialization.XmlSerializer> dei tipi di oggetti contenuti in <xref:System.Collections.ArrayList>. A tale scopo, assegnare più istanze di <xref:System.Xml.Serialization.XmlElementAttribute> al campo, come illustrato nell'esempio riportato di seguito.

```vb
Public Class Group
    <XmlElement(Type:=GetType(Employee)), _
    XmlElement(Type:=GetType(Manager))> _
    Public Info As ArrayList
End Class
```

```csharp
public class Group {
    [XmlElement(Type = typeof(Employee)),
    XmlElement(Type = typeof(Manager))]
    public ArrayList Info;
}
```

## <a name="controlling-serialization-of-classes-using-xmlrootattribute-and-xmltypeattribute"></a>Controllo della serializzazione di classi tramite XmlRootAttribute e XmlTypeAttribute

Esistono due attributi applicabili a una classe (e solo a una classe): <xref:System.Xml.Serialization.XmlRootAttribute> e <xref:System.Xml.Serialization.XmlTypeAttribute>. Questi attributi sono molto simili. <xref:System.Xml.Serialization.XmlRootAttribute> può essere applicato a una sola classe, ovvero alla classe che, se serializzata, rappresenta l'elemento di apertura e chiusura del documento XML, in altre parole, l'elemento principale. <xref:System.Xml.Serialization.XmlTypeAttribute>, invece, può essere applicato a qualsiasi classe, inclusa la classe radice.

Ad esempio, negli esempi precedenti, la classe `Group` è la classe radice e tutte le sue proprietà e i campi pubblici diventano gli elementi XML trovati nel documento XML. Pertanto, può essere presente un solo nodo radice. Tramite l'applicazione di <xref:System.Xml.Serialization.XmlRootAttribute>, è possibile controllare il flusso XML generato da <xref:System.Xml.Serialization.XmlSerializer>. Ad esempio, è possibile modificare il nome dell'elemento e lo spazio dei nomi.

<xref:System.Xml.Serialization.XmlTypeAttribute> consente di controllare lo schema dell'XML generato. Questa funzionalità risulta utile quando è necessario pubblicare lo schema tramite un servizio Web XML. Nell'esempio riportato di seguito, viene applicato sia <xref:System.Xml.Serialization.XmlTypeAttribute> che <xref:System.Xml.Serialization.XmlRootAttribute> alla stessa classe.

```vb
<XmlRoot("NewGroupName"), _
XmlType("NewTypeName")> _
Public Class Group
    Public Employees() As Employee
End Class
```

```csharp
[XmlRoot("NewGroupName")]
[XmlType("NewTypeName")]
public class Group {
    public Employee[] Employees;
}
```

Se questa classe è compilata e viene utilizzato lo strumento XML Schema Definition per generare lo schema, viene creato il seguente XML che descrive `Group`.

```xml
<xs:element name="NewGroupName" type="NewTypeName" />
```

Al contrario, se si fosse dovuta serializzare un'istanza della classe, nel documento XML si sarebbe trovato solo `NewGroupName`.

```xml
<NewGroupName>
    . . .
</NewGroupName>
```

## <a name="preventing-serialization-with-the-xmlignoreattribute"></a>Come impedire la serializzazione con XmlIgnoreAttribute

Potrebbero presentarsi delle situazioni in cui un campo o una proprietà pubblica non necessitano della serializzazione. Ad esempio, un campo o una proprietà possono essere utilizzati per contenere metadati. In tali casi, applicare <xref:System.Xml.Serialization.XmlIgnoreAttribute> al campo o alla proprietà e <xref:System.Xml.Serialization.XmlSerializer> permetterà di ignorarli.

## <a name="see-also"></a>Vedi anche

- [Attributi che controllano la serializzazione XML](attributes-that-control-xml-serialization.md)
- [Attributi che controllano la serializzazione SOAP codificata](attributes-that-control-encoded-soap-serialization.md)
- [Introduzione alla serializzazione XML](introducing-xml-serialization.md)
- [Esempi di serializzazione XML](examples-of-xml-serialization.md)
- [Procedura: specificare un nome di elemento alternativo per un flusso XML](how-to-specify-an-alternate-element-name-for-an-xml-stream.md)
- [Procedura: serializzare un oggetto](how-to-serialize-an-object.md)
- [Procedura: Deserializzare un oggetto](how-to-deserialize-an-object.md)
