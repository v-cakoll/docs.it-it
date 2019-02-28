---
title: Proprietà axis descendant XML (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlPropertyDescendantsAxis
helpviewer_keywords:
- Visual Basic code, accessing XML
- XML descendant axis property [Visual Basic]
- descendant axis property [Visual Baisc]
- XML axis [Visual Basic], descendant
- XML [Visual Basic], accessing
ms.assetid: a178f85b-5d54-438f-8479-40b62af6fe76
ms.openlocfilehash: f6d8a958b5a33c236ca5273cccda0e13693b564e
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56973535"
---
# <a name="xml-descendant-axis-property-visual-basic"></a>Proprietà axis descendant XML (Visual Basic)
Fornisce l'accesso ai discendenti di uno dei seguenti: un' <xref:System.Xml.Linq.XElement> oggetti, un' <xref:System.Xml.Linq.XDocument> oggetto, una raccolta di <xref:System.Xml.Linq.XElement> oggetti, oppure una raccolta di <xref:System.Xml.Linq.XDocument> oggetti.  
  
## <a name="syntax"></a>Sintassi  
  
```  
object...<descendant>  
```  
  
## <a name="parts"></a>Parti  
 `object`  
 Obbligatorio. Un oggetto <xref:System.Xml.Linq.XElement>, un oggetto <xref:System.Xml.Linq.XDocument>, una raccolta di oggetti <xref:System.Xml.Linq.XElement> o una raccolta di oggetti <xref:System.Xml.Linq.XDocument>.  
  
 ...<  
 Obbligatorio. Indica l'inizio di una proprietà axis discendente.  
  
 `descendant`  
 Obbligatorio. Nome dei nodi discendente per accedere, nel formato [`prefix:]name`.  
  
|Parte|Descrizione|  
|----------|-----------------|  
|`prefix`|Facoltativo. Prefisso dello spazio dei nomi XML per il nodo discendente. Deve essere uno spazio dei nomi XML globale definito usando un' `Imports` istruzione.|  
|`name`|Obbligatorio. Nome locale del nodo discendente. Visualizzare [nomi degli elementi e attributi XML dichiarati](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).|  
  
 \>  
 Obbligatorio. Indica la fine di una proprietà axis discendente.  
  
## <a name="return-value"></a>Valore restituito  
 Raccolta di oggetti <xref:System.Xml.Linq.XElement>.  
  
## <a name="remarks"></a>Note  
 È possibile usare una proprietà axis discendente XML per accedere ai nodi discendenti in base al nome da un <xref:System.Xml.Linq.XElement> oppure <xref:System.Xml.Linq.XDocument> oggetto, o da una raccolta di <xref:System.Xml.Linq.XElement> o <xref:System.Xml.Linq.XDocument> oggetti. Usare il codice XML `Value` proprietà per accedere al valore del primo nodo discendente della raccolta restituita. Per altre informazioni, vedere [proprietà Value XML](../../../visual-basic/language-reference/xml-axis/xml-value-property.md).  
  
 Il compilatore Visual Basic converte le proprietà axis discendente in chiamate al <xref:System.Xml.Linq.XContainer.Descendants%2A> (metodo).  
  
## <a name="xml-namespaces"></a>Spazi dei nomi XML  
 Il nome di una proprietà axis discendente può usare solo spazi dei nomi XML dichiarati globalmente con il `Imports` istruzione. Non può usare spazi dei nomi XML dichiarati localmente all'interno di valori letterali dell'elemento XML. Per altre informazioni, vedere [istruzione Imports (Namespace XML)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come accedere al valore del primo nodo discendente denominato `name` e i valori di tutti i nodi discendenti denominati `phone` dal `contacts` oggetto.  
  
 [!code-vb[VbXMLSamples#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples11.vb#25)]  
  
 Questo codice visualizza il testo seguente:  
  
 `Name: Patrick Hines`  
  
 `Home Phone = 206-555-0144`  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene dichiarato `ns` come un prefisso dello spazio dei nomi XML. Il prefisso dello spazio dei nomi viene quindi utilizzato per creare un file XML letterale e accedere al valore del primo nodo figlio con il nome completo `ns:name`.  
  
 [!code-vb[VbXMLSamples#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples12.vb#26)]  
  
 Questo codice visualizza il testo seguente:  
  
 `Name: Patrick Hines`  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Xml.Linq.XElement>
- [Proprietà Axis XML](../../../visual-basic/language-reference/xml-axis/index.md)
- [Valori letterali XML](../../../visual-basic/language-reference/xml-literals/index.md)
- [Creazione di XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [Nomi di elementi e attributi XML dichiarati](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
