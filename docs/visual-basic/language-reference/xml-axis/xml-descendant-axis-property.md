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
ms.openlocfilehash: b2bf524214fa8ecca215d50c198b23d127e3b400
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349441"
---
# <a name="xml-descendant-axis-property-visual-basic"></a>Proprietà axis descendant XML (Visual Basic)

Fornisce l'accesso ai discendenti dei seguenti elementi: un oggetto <xref:System.Xml.Linq.XElement>, un oggetto <xref:System.Xml.Linq.XDocument>, una raccolta di oggetti <xref:System.Xml.Linq.XElement> o una raccolta di oggetti <xref:System.Xml.Linq.XDocument>.

## <a name="syntax"></a>Sintassi

```vb
object...<descendant>
```

## <a name="parts"></a>Parti

`object` Obbligatorio. Un oggetto <xref:System.Xml.Linq.XElement>, un oggetto <xref:System.Xml.Linq.XDocument>, una raccolta di oggetti <xref:System.Xml.Linq.XElement> o una raccolta di oggetti <xref:System.Xml.Linq.XDocument>.

`...<` Obbligatorio. Indica l'inizio di una proprietà asse discendente.

`descendant` Obbligatorio. Nome dei nodi discendenti a cui accedere, nel formato [`prefix:]name`.

|Parte|Descrizione|
|----------|-----------------|
|`prefix`|Facoltativa. Prefisso dello spazio dei nomi XML per il nodo discendente. Deve essere uno spazio dei nomi XML globale definito tramite un'istruzione `Imports`.|
|`name`|Obbligatoria. Nome locale del nodo discendente. Vedere [nomi di elementi e attributi XML dichiarati](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).|

`>` Obbligatorio. Indica la fine di una proprietà asse discendente.

## <a name="return-value"></a>Valore restituito

Raccolta di oggetti <xref:System.Xml.Linq.XElement>.

## <a name="remarks"></a>Note

È possibile utilizzare una proprietà axis discendente XML per accedere ai nodi discendenti in base al nome da un oggetto <xref:System.Xml.Linq.XElement> o <xref:System.Xml.Linq.XDocument> oppure da una raccolta di oggetti <xref:System.Xml.Linq.XElement> o <xref:System.Xml.Linq.XDocument>. Utilizzare la proprietà `Value` XML per accedere al valore del primo nodo discendente nella raccolta restituita. Per ulteriori informazioni, vedere [proprietà del valore XML](../../../visual-basic/language-reference/xml-axis/xml-value-property.md).

Il compilatore Visual Basic converte le proprietà dell'asse discendente in chiamate al metodo <xref:System.Xml.Linq.XContainer.Descendants%2A>.

## <a name="xml-namespaces"></a>Spazi dei nomi XML

Il nome in una proprietà asse discendente può utilizzare solo spazi dei nomi XML dichiarati globalmente con l'istruzione `Imports`. Non può utilizzare spazi dei nomi XML dichiarati localmente nei valori letterali degli elementi XML. Per altre informazioni, vedere [istruzione Imports (spazio dei nomi XML)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).

## <a name="example"></a>Esempio

Nell'esempio seguente viene illustrato come accedere al valore del primo nodo discendente denominato `name` e i valori di tutti i nodi discendenti denominati `phone` dall'oggetto `contacts`.

[!code-vb[VbXMLSamples#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples11.vb#25)]

Questo codice visualizza il testo seguente:

`Name: Patrick Hines`

`Home Phone = 206-555-0144`

## <a name="example"></a>Esempio

Nell'esempio seguente viene dichiarato `ns` come un prefisso dello spazio dei nomi XML. USA quindi il prefisso dello spazio dei nomi per creare un valore letterale XML e accedere al valore del primo nodo figlio con il nome completo `ns:name`.

[!code-vb[VbXMLSamples#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples12.vb#26)]

Questo codice visualizza il testo seguente:

`Name: Patrick Hines`

## <a name="see-also"></a>Vedere anche

- <xref:System.Xml.Linq.XElement>
- [Proprietà Axis XML](../../../visual-basic/language-reference/xml-axis/index.md)
- [Valori letterali XML](../../../visual-basic/language-reference/xml-literals/index.md)
- [Creazione di XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [Nomi di elementi e attributi XML dichiarati](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
