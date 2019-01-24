---
title: Valore letterale elemento XML (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralElement
helpviewer_keywords:
- XML element literal [Visual Basic]
- element literal [Visual Basic]
- XML literals [Visual Basic], element
ms.assetid: 95039642-7893-48b7-b23f-45a6c55d8f67
ms.openlocfilehash: 54ad162a1a720a1645a3b413e6518d2ccfd37bbe
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54595916"
---
# <a name="xml-element-literal-visual-basic"></a>Valore letterale elemento XML (Visual Basic)

Un valore letterale che rappresenta un <xref:System.Xml.Linq.XElement> oggetto.  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<name [ attributeList ] />  
-or-  
<name [ attributeList ] > [ elementContents ] </[ name ]>  
```  
  
## <a name="parts"></a>Parti  
  
-   `<`  
  
     Obbligatorio. Apre il tag dell'elemento iniziale.  
  
-   `name`  
  
     Obbligatorio. Nome dell'elemento. Il formato è uno dei seguenti:  
  
    -   Testo letterale per il nome dell'elemento, nel formato `[ePrefix:]eName`, dove:  
  
        |Parte|Descrizione|  
        |---|---|  
        |`ePrefix`|Facoltativo. Prefisso dello spazio dei nomi XML per l'elemento. Deve essere uno spazio dei nomi XML globale definito con un `Imports` istruzione nel file o a livello di progetto, o uno spazio dei nomi XML locale definito in questo elemento o un elemento padre.|  
        |`eName`|Obbligatorio. Nome dell'elemento. Il formato è uno dei seguenti:<br /><br /> -Testo letterale. Visualizzare [nomi degli elementi e attributi XML dichiarati](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).<br />-Espressione incorporata del form `<%= eNameExp %>`. Il tipo della `eNameExp` deve essere `String` o un tipo che è implicitamente convertibile in <xref:System.Xml.Linq.XName>.|  
  
    -   Espressione del form incorporata `<%= nameExp %>`. Il tipo della `nameExp` deve essere `String` o un tipo implicitamente convertibile in <xref:System.Xml.Linq.XName>. Un'espressione incorporata non è consentita in un tag di chiusura di un elemento.  
  
-   `attributeList`  
  
     Facoltativo. Elenco degli attributi dichiarate nel valore letterale.  
  
     `attribute [ attribute ... ]`  
  
     Ogni `attribute` dispone di una delle sintassi seguenti:  
  
    -   Assegnazione, nel formato attributo `[aPrefix:]aName=aValue`, dove:  
  
        |Parte|Descrizione|  
        |---|---|  
        |`aPrefix`|Facoltativo. Prefisso dello spazio dei nomi XML per l'attributo. Deve essere uno spazio dei nomi XML globale definito con un `Imports` istruzione o uno spazio dei nomi XML locale definito in questo elemento o un elemento padre.|  
        |`aName`|Obbligatorio. Nome dell'attributo. Il formato è uno dei seguenti:<br /><br /> -Testo letterale. Visualizzare [nomi degli elementi e attributi XML dichiarati](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).<br />-Espressione incorporata del form `<%= aNameExp %>`. Il tipo della `aNameExp` deve essere `String` o un tipo che è implicitamente convertibile in <xref:System.Xml.Linq.XName>.|  
        |`aValue`|Facoltativo. Valore dell'attributo. Il formato è uno dei seguenti:<br /><br /> -Testo letterale, racchiuso tra virgolette.<br />-Espressione incorporata del form `<%= aValueExp %>`. È consentito qualsiasi tipo.|  
  
    -   Espressione del form incorporata `<%= aExp %>`.  
  
-   `/>`  
  
     Facoltativo. Indica che l'elemento è un elemento vuoto, senza contenuto.  
  
-   `>`  
  
     Obbligatorio. Termina il tag dell'elemento iniziale o vuoto.  
  
-   `elementContents`  
  
     Facoltativo. Contenuto dell'elemento.  
  
     `content [ content ... ]`  
  
     Ogni `content` può essere uno dei seguenti:  
  
    -   Testo letterale. Tutti gli spazi vuoti in `elementContents` diventa significativo se è presente del testo letterale.  
  
    -   Espressione del form incorporata `<%= contentExp %>`.  
  
    -   Valore letterale elemento XML.  
  
    -   Valore letterale di commento XML. Visualizzare [valore letterale commento XML](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md).  
  
    -   Istruzione di elaborazione XML. Visualizzare [valore letterale istruzione di elaborazione XML](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md).  
  
    -   Valore letterale CDATA XML. Visualizzare [valore letterale CDATA XML](../../../visual-basic/language-reference/xml-literals/xml-cdata-literal.md).  
  
-   `</[name]>`  
  
     Facoltativo. Rappresenta il tag di chiusura per l'elemento. L'opzione facoltativa `name` parametro non è consentito quando è il risultato di un'espressione incorporata.  
  
## <a name="return-value"></a>Valore restituito  
 Oggetto <xref:System.Xml.Linq.XElement>.  
  
## <a name="remarks"></a>Note  
 È possibile usare la sintassi del valore letterale elemento XML per creare <xref:System.Xml.Linq.XElement> gli oggetti nel codice.  
  
> [!NOTE]
>  Un valore letterale XML può estendersi su più righe senza utilizzare caratteri di continuazione di riga. Questa funzionalità consente di copiare il contenuto da un documento XML e incollare il codice direttamente in un programma Visual Basic.  
  
 Espressioni nel formato incorporate `<%= exp %>` consentono di aggiungere informazioni dinamiche a un valore letterale elemento XML. Per altre informazioni, vedere [espressioni incorporate in XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).  
  
 Il compilatore Visual Basic converte il valore letterale elemento XML in chiamate per il <xref:System.Xml.Linq.XElement.%23ctor%2A> costruttore e, se necessario, il <xref:System.Xml.Linq.XAttribute.%23ctor%2A> costruttore.  
  
## <a name="xml-namespaces"></a>Spazi dei nomi XML  
 I prefissi dello spazio dei nomi XML sono utili quando è necessario creare valori letterali XML con gli elementi dallo spazio dei nomi stesso numero di volte nel codice. È possibile usare i prefissi dello spazio dei nomi XML globali, che può essere definito usando la `Imports` istruzione o i prefissi locali, che può essere definito usando la `xmlns:xmlPrefix="xmlNamespace"` sintassi degli attributi. Per altre informazioni, vedere [istruzione Imports (Namespace XML)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).  
  
 In conformità con le regole di ambito per gli spazi dei nomi XML, i prefissi locali hanno la precedenza sui prefissi globali. Tuttavia, se un valore letterale XML definisce uno spazio dei nomi XML, tale spazio dei nomi non è disponibile per le espressioni contenute in un'espressione incorporata. L'espressione incorporata può accedere solo i nomi XML globale.  
  
 Il compilatore Visual Basic consente di convertire ogni spazio dei nomi XML globale che viene usato da un valore letterale XML in una definizione dello spazio dei nomi locali nel codice generato. Spazi dei nomi XML globali non utilizzati non vengono visualizzati nel codice generato.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come creare un elemento XML semplice che dispone di due elementi vuoti annidati.  
  
 [!code-vb[VbXMLSamples#20](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-element-literal_1.vb)]  
  
 L'esempio visualizza il testo seguente. Si noti che il valore letterale mantiene la struttura di elementi vuoti.  
  
```xml  
<outer>  
  <inner1></inner1>  
  <inner2 />  
</outer>  
```  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come usare espressioni incorporate per nome di un elemento e creare gli attributi.  
  
 [!code-vb[VbXMLSamples#21](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-element-literal_2.vb)]  
  
 Questo codice visualizza il testo seguente:  
  
```xml  
<book isbn="1234" author="My Author" year="1999" title="My Book" />  
```  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene dichiarato `ns` come un prefisso dello spazio dei nomi XML. Quindi Usa il prefisso dello spazio dei nomi per creare un file XML letterale e visualizza il formato dell'elemento finale.  
  
 [!code-vb[VbXMLSamples#22](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-element-literal_3.vb)]  
  
 Questo codice visualizza il testo seguente:  
  
```xml  
<ns:outer xmlns:ns="http://SomeNamespace">  
  <ns:middle xmlns:ns="http://NewNamespace">  
    <ns:inner1 />  
    <inner2 xmlns="http://SomeNamespace" />  
  </ns:middle>  
</ns:outer>  
```  
  
 Si noti che il compilatore converte il prefisso dello spazio dei nomi XML globali in una definizione del prefisso dello spazio dei nomi XML. Il \<ns:middle > elemento consente di ridefinire il prefisso dello spazio dei nomi XML per il \<ns:inner1 > elemento. Tuttavia, il \<ns:inner2 > elemento utilizza lo spazio dei nomi definito dal `Imports` istruzione.  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Xml.Linq.XElement>
- [Nomi di elementi e attributi XML dichiarati](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
- [Valore letterale di commento XML](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md)
- [Valore letterale CDATA XML](../../../visual-basic/language-reference/xml-literals/xml-cdata-literal.md)
- [Valori letterali XML](../../../visual-basic/language-reference/xml-literals/index.md)
- [Creazione di XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [Espressioni incorporate in XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)
- [Istruzione Imports (spazio dei nomi XML)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)
