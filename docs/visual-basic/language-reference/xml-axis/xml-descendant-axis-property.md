---
title: XML Descendant Axis Property
ms.date: 07/20/2015
f1_keywords:
- vb.XmlPropertyDescendantsAxis
helpviewer_keywords:
- Visual Basic code, accessing XML
- XML descendant axis property [Visual Basic]
- descendant axis property [Visual Basic]
- XML axis [Visual Basic], descendant
- XML [Visual Basic], accessing
ms.assetid: a178f85b-5d54-438f-8479-40b62af6fe76
ms.openlocfilehash: 52544619171dbc7034baeb5feb61395d81096387
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400253"
---
# <a name="xml-descendant-axis-property-visual-basic"></a>Proprietà axis descendant XML (Visual Basic)

Fornisce l'accesso ai discendenti dei seguenti elementi: un <xref:System.Xml.Linq.XElement> oggetto, un <xref:System.Xml.Linq.XDocument> oggetto, una raccolta di <xref:System.Xml.Linq.XElement> oggetti o una raccolta di <xref:System.Xml.Linq.XDocument> oggetti.

## <a name="syntax"></a>Sintassi

```vb
object...<descendant>
```

## <a name="parts"></a>Parti

`object` Obbligatorio. Un oggetto <xref:System.Xml.Linq.XElement>, un oggetto <xref:System.Xml.Linq.XDocument>, una raccolta di oggetti <xref:System.Xml.Linq.XElement> o una raccolta di oggetti <xref:System.Xml.Linq.XDocument>.

`...<` Obbligatorio. Indica l'inizio di una proprietà asse discendente.

`descendant` Obbligatorio. Nome dei nodi discendenti a cui accedere, nel formato [ `prefix:]name` .

|Parte|Descrizione|
|----------|-----------------|
|`prefix`|Facoltativa. Prefisso dello spazio dei nomi XML per il nodo discendente. Deve essere uno spazio dei nomi XML globale definito usando un' `Imports` istruzione.|
|`name`|Obbligatorio. Nome locale del nodo discendente. Vedere [nomi di elementi e attributi XML dichiarati](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).|

`>` Obbligatorio. Indica la fine di una proprietà asse discendente.

## <a name="return-value"></a>Valore restituito

Una raccolta di oggetti <xref:System.Xml.Linq.XElement>.

## <a name="remarks"></a>Commenti

È possibile utilizzare una proprietà axis discendente XML per accedere ai nodi discendenti in base al nome di un <xref:System.Xml.Linq.XElement> oggetto o oppure <xref:System.Xml.Linq.XDocument> da una raccolta di <xref:System.Xml.Linq.XElement> <xref:System.Xml.Linq.XDocument> oggetti o. Utilizzare la `Value` proprietà XML per accedere al valore del primo nodo discendente nella raccolta restituita. Per ulteriori informazioni, vedere [proprietà del valore XML](xml-value-property.md).

Il compilatore Visual Basic converte le proprietà dell'asse discendente in chiamate al <xref:System.Xml.Linq.XContainer.Descendants%2A> metodo.

## <a name="xml-namespaces"></a>Spazi dei nomi XML

Il nome in una proprietà asse discendente può utilizzare solo spazi dei nomi XML dichiarati globalmente con l' `Imports` istruzione. Non può utilizzare spazi dei nomi XML dichiarati localmente nei valori letterali degli elementi XML. Per altre informazioni, vedere [istruzione Imports (spazio dei nomi XML)](../statements/imports-statement-xml-namespace.md).

## <a name="example"></a>Esempio

Nell'esempio seguente viene illustrato come accedere al valore del primo nodo discendente denominato `name` e ai valori di tutti i nodi discendenti denominati `phone` dall' `contacts` oggetto.

[!code-vb[VbXMLSamples#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples11.vb#25)]

Questo codice visualizza il testo seguente:

`Name: Patrick Hines`

`Home Phone = 206-555-0144`

## <a name="example"></a>Esempio

Nell'esempio seguente viene dichiarato `ns` come un prefisso dello spazio dei nomi XML. USA quindi il prefisso dello spazio dei nomi per creare un valore letterale XML e accedere al valore del primo nodo figlio con il nome completo `ns:name` .

[!code-vb[VbXMLSamples#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples12.vb#26)]

Questo codice visualizza il testo seguente:

`Name: Patrick Hines`

## <a name="see-also"></a>Vedere anche

- <xref:System.Xml.Linq.XElement>
- [Proprietà Axis XML](index.md)
- [Valori letterali XML](../xml-literals/index.md)
- [Creazione di XML in Visual Basic](../../programming-guide/language-features/xml/creating-xml.md)
- [Nomi di elementi e attributi XML dichiarati](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
