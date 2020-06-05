---
title: Valore letterale di elemento XML
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralElement
helpviewer_keywords:
- XML element literal [Visual Basic]
- element literal [Visual Basic]
- XML literals [Visual Basic], element
ms.assetid: 95039642-7893-48b7-b23f-45a6c55d8f67
ms.openlocfilehash: d6a91de4e279816bafd29f46bb4f5422cbd934ff
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400189"
---
# <a name="xml-element-literal-visual-basic"></a>Valore letterale elemento XML (Visual Basic)

Valore letterale che rappresenta un <xref:System.Xml.Linq.XElement> oggetto.

## <a name="syntax"></a>Sintassi

```xml
<name [ attributeList ] />
-or-
<name [ attributeList ] > [ elementContents ] </[ name ]>
```

## <a name="parts"></a>Parti

- `<`

  Obbligatorio. Apre il tag dell'elemento iniziale.

- `name`

  Obbligatorio. Nome dell'elemento. Il formato è uno dei seguenti:

  - Testo letterale per il nome dell'elemento, nel formato `[ePrefix:]eName` , dove:

    |Parte|Descrizione|
    |---|---|
    |`ePrefix`|Facoltativa. Prefisso dello spazio dei nomi XML per l'elemento. Deve essere uno spazio dei nomi XML globale definito con un' `Imports` istruzione nel file o a livello di progetto o uno spazio dei nomi XML locale definito in questo elemento o in un elemento padre.|
    |`eName`|Obbligatorio. Nome dell'elemento. Il formato è uno dei seguenti:<br /><br /> -Testo letterale. Vedere [nomi di elementi e attributi XML dichiarati](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).<br />-Espressione incorporata del form `<%= eNameExp %>` . Il tipo di `eNameExp` deve essere `String` o un tipo convertibile in modo implicito in <xref:System.Xml.Linq.XName> .|

  - Espressione incorporata del form `<%= nameExp %>` . Il tipo di `nameExp` deve essere `String` o un tipo convertibile in modo implicito in <xref:System.Xml.Linq.XName> . Espressione incorporata non consentita in un tag di chiusura di un elemento.

- `attributeList`

  Facoltativa. Elenco di attributi dichiarati nel valore letterale.

  `attribute [ attribute ... ]`

  Ogni `attribute` ha una delle seguenti sintassi:

  - Assegnazione di attributi, nel formato `[aPrefix:]aName=aValue` , dove:

    |Parte|Descrizione|
    |---|---|
    |`aPrefix`|Facoltativa. Prefisso dello spazio dei nomi XML per l'attributo. Deve essere uno spazio dei nomi XML globale definito con un' `Imports` istruzione o uno spazio dei nomi XML locale definito in questo elemento o in un elemento padre.|
    |`aName`|Obbligatorio. Nome dell'attributo. Il formato è uno dei seguenti:<br /><br /> -Testo letterale. Vedere [nomi di elementi e attributi XML dichiarati](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).<br />-Espressione incorporata del form `<%= aNameExp %>` . Il tipo di `aNameExp` deve essere `String` o un tipo convertibile in modo implicito in <xref:System.Xml.Linq.XName> .|
    |`aValue`|Facoltativa. Valore dell'attributo. Il formato è uno dei seguenti:<br /><br /> -Testo letterale, racchiuso tra virgolette.<br />-Espressione incorporata del form `<%= aValueExp %>` . Qualsiasi tipo è consentito.|

  - Espressione incorporata del form `<%= aExp %>` .

- `/>`

  Facoltativa. Indica che l'elemento è un elemento vuoto, senza contenuto.

- `>`

  Obbligatorio. Termina il tag dell'elemento iniziale o vuoto.

- `elementContents`

  Facoltativa. Contenuto dell'elemento.

  `content [ content ... ]`

  Ognuno `content` può essere uno dei seguenti:

  - Testo letterale. Tutti gli spazi vuoti in `elementContents` diventano significativi se è presente un testo letterale.

  - Espressione incorporata del form `<%= contentExp %>` .

  - Valore letterale elemento XML.

  - Valore letterale del commento XML. Vedere [valore letterale del commento XML](xml-comment-literal.md).

  - Valore letterale istruzione di elaborazione XML. Vedere [valore letterale istruzione di elaborazione XML](xml-processing-instruction-literal.md).

  - Valore letterale CDATA XML. Vedere [valore letterale CDATA XML](xml-cdata-literal.md).

- `</[name]>`

  Facoltativa. Rappresenta il tag di chiusura per l'elemento. Il `name` parametro facoltativo non è consentito quando è il risultato di un'espressione incorporata.

## <a name="return-value"></a>Valore restituito

Oggetto <xref:System.Xml.Linq.XElement>.

## <a name="remarks"></a>Commenti

È possibile utilizzare la sintassi dei valori letterali dell'elemento XML per creare <xref:System.Xml.Linq.XElement> oggetti nel codice.

> [!NOTE]
> Un valore letterale XML può estendersi su più righe senza usare caratteri di continuazione di riga. Questa funzionalità consente di copiare il contenuto da un documento XML e incollarlo direttamente in un programma Visual Basic.

Le espressioni incorporate del form `<%= exp %>` consentono di aggiungere informazioni dinamiche a un valore letterale elemento XML. Per ulteriori informazioni, vedere [espressioni incorporate in XML](../../programming-guide/language-features/xml/embedded-expressions-in-xml.md).

Il compilatore Visual Basic converte il valore letterale dell'elemento XML in chiamate al <xref:System.Xml.Linq.XElement.%23ctor%2A> costruttore e, se necessario, il <xref:System.Xml.Linq.XAttribute.%23ctor%2A> costruttore.

## <a name="xml-namespaces"></a>Spazi dei nomi XML

I prefissi degli spazi dei nomi XML sono utili quando è necessario creare valori letterali XML con gli elementi dello stesso spazio dei nomi più volte nel codice. È possibile utilizzare i prefissi degli spazi dei nomi XML globali, definiti utilizzando l' `Imports` istruzione o prefissi locali, definiti utilizzando la `xmlns:xmlPrefix="xmlNamespace"` sintassi dell'attributo. Per altre informazioni, vedere [istruzione Imports (spazio dei nomi XML)](../statements/imports-statement-xml-namespace.md).

In conformità alle regole di ambito per gli spazi dei nomi XML, i prefissi locali hanno la precedenza sui prefissi globali. Tuttavia, se un valore letterale XML definisce uno spazio dei nomi XML, tale spazio dei nomi non è disponibile per le espressioni visualizzate in un'espressione incorporata. L'espressione incorporata può accedere solo allo spazio dei nomi XML globale.

Il compilatore Visual Basic converte tutti gli spazi dei nomi XML globali utilizzati da un valore letterale XML in una definizione di uno spazio dei nomi locale nel codice generato. Gli spazi dei nomi XML globali non utilizzati non vengono visualizzati nel codice generato.

## <a name="example"></a>Esempio

Nell'esempio seguente viene illustrato come creare un elemento XML semplice con due elementi vuoti annidati.

[!code-vb[VbXMLSamples#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples9.vb#20)]

Nell'esempio viene visualizzato il testo seguente. Si noti che il valore letterale conserva la struttura degli elementi vuoti.

```xml
<outer>
  <inner1></inner1>
  <inner2 />
</outer>
```

## <a name="example"></a>Esempio

Nell'esempio seguente viene illustrato come utilizzare le espressioni incorporate per assegnare un nome a un elemento e creare attributi.

[!code-vb[VbXMLSamples#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples9.vb#21)]

Questo codice visualizza il testo seguente:

```xml
<book isbn="1234" author="My Author" year="1999" title="My Book" />
```

## <a name="example"></a>Esempio

Nell'esempio seguente viene dichiarato `ns` come un prefisso dello spazio dei nomi XML. USA quindi il prefisso dello spazio dei nomi per creare un valore letterale XML e visualizza il formato finale dell'elemento.

[!code-vb[VbXMLSamples#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples10.vb#22)]

Questo codice visualizza il testo seguente:

```xml
<ns:outer xmlns:ns="http://SomeNamespace">
  <ns:middle xmlns:ns="http://NewNamespace">
    <ns:inner1 />
    <inner2 xmlns="http://SomeNamespace" />
  </ns:middle>
</ns:outer>
```

Si noti che il compilatore ha convertito il prefisso dello spazio dei nomi XML globale in una definizione di prefisso per lo spazio dei nomi XML. L' \<ns:middle> elemento ridefinisce il prefisso dello spazio dei nomi XML per l' \<ns:inner1> elemento. Tuttavia, l' \<ns:inner2> elemento utilizza lo spazio dei nomi definito dall' `Imports` istruzione.

## <a name="see-also"></a>Vedere anche

- <xref:System.Xml.Linq.XElement>
- [Nomi di elementi e attributi XML dichiarati](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
- [Valore letterale di commento XML](xml-comment-literal.md)
- [Valore letterale CDATA XML](xml-cdata-literal.md)
- [Valori letterali XML](index.md)
- [Creazione di XML in Visual Basic](../../programming-guide/language-features/xml/creating-xml.md)
- [Espressioni incorporate in XML](../../programming-guide/language-features/xml/embedded-expressions-in-xml.md)
- [Istruzione Imports (spazio dei nomi XML)](../statements/imports-statement-xml-namespace.md)
