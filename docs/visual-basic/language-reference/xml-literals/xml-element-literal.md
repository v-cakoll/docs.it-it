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
ms.openlocfilehash: 55d5d1410a65ea8c800bbd2b310907a6d6a61c61
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33605134"
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
  
     Obbligatorio. Apre il tag iniziale dell'elemento.  
  
-   `name`  
  
     Obbligatorio. Nome dell'elemento. Il formato è uno dei valori seguenti:  
  
    -   Testo letterale per il nome dell'elemento del form `[ePrefix:]eName`, dove:  
  
        |Parte|Descrizione|  
        |---|---|  
        |`ePrefix`|Facoltativo. Prefisso dello spazio dei nomi XML per l'elemento. Deve essere uno spazio dei nomi XML globale definito con un `Imports` istruzione nel file o a livello di progetto, o uno spazio dei nomi XML locale definito in questo elemento o un elemento padre.|  
        |`eName`|Obbligatorio. Nome dell'elemento. Il formato è uno dei valori seguenti:<br /><br /> -Testo letterale. Vedere [i nomi di elementi e attributi XML dichiarati](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).<br />-Espressione incorporata del formato `<%= eNameExp %>`. Il tipo di `eNameExp` deve essere `String` o un tipo convertibile in modo implicito per <xref:System.Xml.Linq.XName>.|  
  
    -   Espressione incorporata del formato `<%= nameExp %>`. Il tipo di `nameExp` deve essere `String` o un tipo convertibile in modo implicito <xref:System.Xml.Linq.XName>. Un'espressione incorporata non è consentita in un tag di chiusura di un elemento.  
  
-   `attributeList`  
  
     Facoltativo. Elenco di attributi dichiarati nel valore letterale.  
  
     `attribute [ attribute ... ]`  
  
     Ogni `attribute` ha una delle sintassi seguenti:  
  
    -   Attributo di assegnazione, nel formato `[aPrefix:]aName=aValue`, dove:  
  
        |Parte|Descrizione|  
        |---|---|  
        |`aPrefix`|Facoltativo. Prefisso dello spazio dei nomi XML per l'attributo. Deve essere uno spazio dei nomi XML globale definito con un `Imports` istruzione o uno spazio dei nomi XML locale definito in questo elemento o un elemento padre.|  
        |`aName`|Obbligatorio. Nome dell'attributo. Il formato è uno dei valori seguenti:<br /><br /> -Testo letterale. Vedere [i nomi di elementi e attributi XML dichiarati](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).<br />-Espressione incorporata del formato `<%= aNameExp %>`. Il tipo di `aNameExp` deve essere `String` o un tipo convertibile in modo implicito per <xref:System.Xml.Linq.XName>.|  
        |`aValue`|Facoltativo. Valore dell'attributo. Il formato è uno dei valori seguenti:<br /><br /> -Testo letterale, racchiuso tra virgolette.<br />-Espressione incorporata del formato `<%= aValueExp %>`. È consentito qualsiasi tipo.|  
  
    -   Espressione incorporata del formato `<%= aExp %>`.  
  
-   `/>`  
  
     Facoltativo. Indica che l'elemento è un elemento vuoto, senza contenuto.  
  
-   `>`  
  
     Obbligatorio. Termina il tag dell'elemento iniziale o vuoto.  
  
-   `elementContents`  
  
     Facoltativo. Contenuto dell'elemento.  
  
     `content [ content ... ]`  
  
     Ogni `content` può essere uno dei seguenti:  
  
    -   Testo letterale. Tutti gli spazi vuoti in `elementContents` diventano significativi se è presente del testo letterale.  
  
    -   Espressione incorporata del formato `<%= contentExp %>`.  
  
    -   Valore letterale elemento XML.  
  
    -   Valore letterale di commento XML. Vedere [valore letterale di commento XML](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md).  
  
    -   Istruzione di elaborazione XML. Vedere [valore letterale istruzione di elaborazione XML](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md).  
  
    -   Valore letterale CDATA XML. Vedere [valore letterale CDATA XML](../../../visual-basic/language-reference/xml-literals/xml-cdata-literal.md).  
  
-   `</[name]>`  
  
     Facoltativo. Rappresenta il tag di chiusura per l'elemento. Facoltativo `name` parametro non è consentito quando è il risultato di un'espressione incorporata.  
  
## <a name="return-value"></a>Valore restituito  
 Oggetto <xref:System.Xml.Linq.XElement>.  
  
## <a name="remarks"></a>Note  
 È possibile utilizzare la sintassi del valore letterale elemento XML per creare <xref:System.Xml.Linq.XElement> oggetti nel codice.  
  
> [!NOTE]
>  Un valore letterale XML può estendersi su più righe senza utilizzare caratteri di continuazione di riga. Questa funzionalità consente di copiare il contenuto da un documento XML e incollarlo direttamente in un programma Visual Basic.  
  
 Le espressioni incorporate il formato `<%= exp %>` consentono di aggiungere informazioni dinamiche a un valore letterale elemento XML. Per ulteriori informazioni, vedere [espressioni incorporate in XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).  
  
 Il compilatore Visual Basic converte il valore letterale elemento XML in chiamate per il <xref:System.Xml.Linq.XElement.%23ctor%2A> costruttore e, se necessario, il <xref:System.Xml.Linq.XAttribute.%23ctor%2A> costruttore.  
  
## <a name="xml-namespaces"></a>Spazi dei nomi XML  
 Prefissi di spazio dei nomi XML sono utili quando è necessario creare valori letterali XML con elementi dallo spazio dei nomi stesso numero di volte nel codice. È possibile utilizzare i prefissi dello spazio dei nomi XML globali, che può essere definito utilizzando il `Imports` istruzione o prefissi locali, che può essere definito utilizzando il `xmlns:xmlPrefix="xmlNamespace"` sintassi degli attributi. Per ulteriori informazioni, vedere [istruzione Imports (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).  
  
 In base alle regole di ambito per gli spazi dei nomi XML, i prefissi locali hanno la precedenza sui prefissi globali. Tuttavia, se un valore letterale XML definisce uno spazio dei nomi XML, lo spazio dei nomi non è disponibile per le espressioni contenute in un'espressione incorporata. L'espressione incorporata può accedere solo nomi XML globale.  
  
 Il compilatore Visual Basic converte ogni spazio dei nomi XML globale viene utilizzato un valore letterale XML in una definizione locale dello spazio dei nomi nel codice generato. Spazi dei nomi XML globali non utilizzati non vengono visualizzati nel codice generato.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come creare un elemento XML semplice che dispone di due elementi vuoti nidificati.  
  
 [!code-vb[VbXMLSamples#20](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-element-literal_1.vb)]  
  
 L'esempio mostra il testo seguente. Si noti che il valore letterale mantiene la struttura degli elementi vuoti.  
  
```xml  
<outer>  
  <inner1></inner1>  
  <inner2 />  
</outer>  
```  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come utilizzare le espressioni incorporate per nome di un elemento e creare gli attributi.  
  
 [!code-vb[VbXMLSamples#21](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-element-literal_2.vb)]  
  
 Questo codice visualizza il testo seguente:  
  
```xml  
<book isbn="1234" author="My Author" year="1999" title="My Book" />  
```  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene dichiarato `ns` come un prefisso dello spazio dei nomi XML. Quindi, il prefisso dello spazio dei nomi utilizzato per creare un file XML come valore letterale e consente di visualizzare il formato dell'elemento finale.  
  
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
  
 Si noti che il compilatore converte il prefisso dello spazio dei nomi XML globali in una definizione del prefisso dello spazio dei nomi XML. Il \<ns:middle > elemento consente di ridefinire il prefisso dello spazio dei nomi XML per il \<ns:inner1 > elemento. Tuttavia, il \<ns:inner2 > elemento Usa lo spazio dei nomi definito dal `Imports` istruzione.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Xml.Linq.XElement>  
 [Nomi di elementi e attributi XML dichiarati](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)  
 [Valore letterale di commento XML](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md)  
 [Valore letterale CDATA XML](../../../visual-basic/language-reference/xml-literals/xml-cdata-literal.md)  
 [Valori letterali XML](../../../visual-basic/language-reference/xml-literals/index.md)  
 [Creazione di XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 [Espressioni incorporate in XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)  
 [Istruzione Imports (spazio dei nomi XML)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)
